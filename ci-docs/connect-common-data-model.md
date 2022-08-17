---
title: Common Data Modeli kausta ühendamine Azure Data Lake’i kontot kasutades
description: Töötage Common Data Modeli andmete kallal Azure Data Lake Storage'i abil.
ms.date: 07/27/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: b237c291bb4dd22ca22ab2cdd8b6293490aa83e1
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245782"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Andmetega ühenduse loomine Azure Data Lake Storageis

Kasutage andmeid Dynamics 365 Customer Insights oma Azure Data Lake Storage Gen2 konto kasutamiseks. Andmete allaneelamine võib olla täielik või järkjärguline.

## <a name="prerequisites"></a>eeltingimused

- Andmete allaneelamine toetab Azure Data Lake Storage *ainult Gen2* kontosid. Andmete allaneelamiseks ei saa kasutada Data Lake Storage Gen1 kontosid.

- Kontol Azure Data Lake Storage peab olema [lubatud hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace). Andmed tuleb salvestada hierarhilises kaustavormingus, mis määratleb juurkausta ja millel on iga olemi jaoks alamkaustad. Alamkaustadel võivad olla täisandmed või astmelised andmekaustad.

- Azure'i teenusesubjektiga autentimiseks veenduge, et see oleks teie rentnikus konfigureeritud. Lisateavet vaadake jaotisest [Azure Data Lake Storage Gen2 kontoga ühenduse loomine Azure’i teenuse printsipaaliga](connect-service-principal.md).

- Andmed Azure Data Lake Storage, mida soovite ühendada ja kust andmeid alla neelata, peavad asuma keskkonnaga samas Azure’i Dynamics 365 Customer Insights piirkonnas. Ühendused Common Data Modeli kausta ja muus Azure'i regioonis oleva andmejärve vahel pole toetatud. Keskkonna Azure’i piirkonna tundmaõppimiseks **avage Customer Insightsis jaotis Haldussüsteemi** > **·** > **teave**.

- Võrgupõhistes teenustes salvestatud andmeid võidakse säilitada muus kohas kui see, kus andmeid töödeldakse või säilitatakse Dynamics 365 Customer Insights.Võrguteenustes salvestatud andmete importimisel või nendega ühenduse loomisel nõustute, et andmeid saab edastada ja salvestada.Dynamics 365 Customer Insights  [Lisateavet leiate Microsofti usalduskeskusest](https://www.microsoft.com/trust-center).

- Customer Insightsi teeninduse printsipaal peab salvestusruumikontole juurdepääsemiseks olema ühes järgmistest rollidest. Lisateavet leiate teemast [Teenuse printsipaalile salvestusruumikontole juurdepääsu õiguste andmine](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Salvestusruumi bloobiandmete luger
  - Salvestusruumi bloobiandmete omanik
  - Salvestusruumi bloobiandmete kaasautor

- Andmesalvestusruumis olevad andmed peaksid järgima teie andmete salvestamiseks standardit Common Data Model ja neil peaks olema ühine andmemudeli manifest, mis esindab andmefailide skeemi (*.csv või *.parquet). Manifest peab sisaldama olemite üksikasju, nagu olemiveerud ja andmetüübid ning andmefaili asukoht ja failitüüp. Lisateavet leiate teemast [Manifest Common Data Model](/common-data-model/sdk/manifest). Kui manifesti pole, saavad salvestusruumi bloobi andmete omaniku või salvestusruumi bloobi andmete esitaja juurdepääsuga administraatorikasutajad andmete allaneelamisel skeemi määratleda.

## <a name="connect-to-azure-data-lake-storage"></a>Azure Data Lake Storageiga ühenduse loomine

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige **Azure data lake storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dialoogiboks Azure Data Lake’i ühenduse üksikasjade sisestamiseks." lightbox="media/data_sources_ADLS.png":::

1. **Sisestage andmeallikas nimi** ja valikuline **kirjeldus**. Nimi identifitseerib kordumatult andmeallikas ja sellele viidatakse järgnevates protsessides ning seda ei saa muuta.

1. Valige üks järgmistest suvanditest jaotises **Ühenda salvestusruum, kasutades**. Lisateavet vaadake jaotisest [Customer Insightsi Azure Data Lake Storage ühendamine Gen2 kontoga Azure’i teeninduse printsipaal](connect-service-principal.md).

   - **Azure’i ressurss**: sisestage **ressursi ID**. Soovi korral, kui soovite talletamiskontolt andmeid alla neelata Azure Private Linki kaudu, valige **Luba privaatne link**. Lisateavet vaadake jaotisest [Privaatsed lingid](security-overview.md#set-up-an-azure-private-link).
   - **Azure’i tellimus**: valige **tellimus** ning seejärel **ressursirühm** ja **salvestusruumikonto**. Soovi korral, kui soovite talletamiskontolt andmeid alla neelata Azure Private Linki kaudu, valige **Luba privaatne link**. Lisateavet vaadake jaotisest [Privaatsed lingid](security-overview.md#set-up-an-azure-private-link).
  
   > [!NOTE]
   > Andmeallikas loomiseks vajate konteinerile või salvestusruumikontole ühte järgmistest rollidest.
   >
   >  - Salvestusruumi bloobi andmelugeja on piisav, et lugeda salvestusruumikontolt ja neelata andmed Customer Insightsi. 
   >  - Salvestusruumi bloobiandmete kaasautor või omanik on nõutav, kui soovite manifestifaile redigeerida otse Customer Insightsis.  
  
1. Valige selle konteineri **nimi**, mis sisaldab andmeid ja skeemi (fail model.json või manifest.json), millest andmeid importida, ja valige **Edasi**.
   > [!NOTE]
   > Keskkonnas muu andmeallikaga seotud faile model.json või manifest.json ei kuvata loendis. Kuid sama faili model.json või manifest.json saab kasutada mitmes keskkonnas andmeallikate jaoks.

1. Uue skeemi loomiseks lugege teemat [Uue skeemifaili](#create-a-new-schema-file) loomine.

1. Olemasoleva skeemi kasutamiseks liikuge kausta, mis sisaldab faili model.json või manifest.cdm.json. Faili leidmiseks saate otsida kataloogist.

1. Valige json-fail ja valige **Edasi**. Kuvatakse saadaolevate olemite loend.

   :::image type="content" source="media/review-entities.png" alt-text="Valitavate olemite loendi dialoogiboks":::

1. Valige olemid, mida soovite kaasata.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialoogiboks, kus on kuvatud primaarvõtme jaoks nõutav":::

   > [!TIP]
   > Olemi redigeerimiseks JSON-i redigeerimisliideses valige olem ja seejärel **Redigeeri skeemifaili**. Tehke muudatusi ja valige **Salvesta**.

1. Valitud olemite puhul, mis vajavad astmelist allaneelamist, **kuvatakse jaotises** Astmeline värskendamine **suvand Nõutav**. Kõigi nende olemite kohta leiate teavet teemast [Azure Data Lake’i andmeallikate](incremental-refresh-data-sources.md) astmelise värskendamise konfigureerimine.

1. Valitud olemite puhul, kus primaarvõtit pole määratletud, **kuvatakse jaotises** Primaarvõti **jaotises Nõutav**. Kõigi nende olemite puhul:
   1. Valige **Nõutav**. Kuvatakse **paan Redigeeri olemit**.
   1. Valige **primaarvõti**. Primaarvõti on olemile ainuomane atribuut. Et atribuut saaks olla sobiv primaarvõti, ei tohi see sisaldada topeltväärtusi, puuduvaid väärtusi ega null-väärtusi. Stringi, täisarvu ja GUID andmetüübi atribuute toetatakse primaarvõtmetena.
   1. Soovi korral muutke partitsioonimustrit.
   1. Paani salvestamiseks ja sulgemiseks valige **Sule**.

1. Valige iga kaasatud olemi atribuutide **arv**. Kuvatakse **leht Atribuutide** haldamine.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialoogiboks andmete profileerimise valimiseks.":::

   1. Looge uusi atribuute, redigeerige või kustutage olemasolevaid atribuute. Saate muuta nime, andmevormingut või lisada semantilise tüübi.
   1. Analüüsi- ja muude võimaluste lubamiseks valige **Andmete profileerimine** kogu olemi või konkreetsete atribuutide jaoks. Vaikimisi pole olemeid andmete profiilimiseks lubatud.
   1. Valige nupp **Valmis**.

1. Valige **Salvesta**. Avaneb **leht Andmeallikad**, kus kuvatakse uus andmeallikas olekus **Värskendamine**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Andmete laadimine võib võtta aega. Pärast edukat värskendamist saab allaneelatud andmeid vaadata lehelt [**Olemid**](entities.md).

### <a name="create-a-new-schema-file"></a>Uue skeemifaili loomine

1. Valige **Uus skeemifail**.

1. Sisestage faili nimi ja valige **Salvesta**.

1. Valige **Uus olem**. Kuvatakse **paan Uus olem**.

1. Sisestage olemi nimi ja valige **andmefailide asukoht**.
   - **Mitu .csv- või .parketifaili**: sirvige juurkaustani, valige mustri tüüp ja sisestage avaldis.
   - **Ühe .csv- või .parketifailid**: sirvige .csv- või .parketifailini ja valige see.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dialoogiboks uue olemi loomiseks, kus on esile tõstetud andmefailide asukoht.":::

1. Valige **Salvesta**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dialoogiboks atribuutide määratlemiseks või automaatseks loomiseks.":::

1. Valige **atribuutide** käsitsi lisamiseks määratlege atribuudid või valige **automaatne genereerimine**. Atribuutide määratlemiseks sisestage nimi, valige andmevorming ja valikuline semantiline tüüp. Automaatselt loodud atribuutide puhul tehke järgmist.

   1. Kui atribuudid on automaatselt loodud, valige **Vaata atribuudid** üle. Kuvatakse **leht Atribuutide** haldamine.

   1. Veenduge, et andmevorming oleks iga atribuudi puhul õige.

   1. Analüüsi- ja muude võimaluste lubamiseks valige **Andmete profileerimine** kogu olemi või konkreetsete atribuutide jaoks. Vaikimisi pole olemeid andmete profiilimiseks lubatud.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialoogiboks andmete profileerimise valimiseks.":::

   1. Valige nupp **Valmis**. Kuvatakse **leht Olemite** valimine.

1. Jätkake olemite ja atribuutide lisamist, kui see on kohaldatav.

1. Kui kõik olemid on lisatud, valige **Kaasa**, et kaasata olemid andmeallikas allaneelamist.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialoogiboks, kus on kuvatud primaarvõtme jaoks nõutav":::

1. Valitud olemite puhul, mis vajavad astmelist allaneelamist, **kuvatakse jaotises** Astmeline värskendamine **suvand Nõutav**. Kõigi nende olemite kohta leiate teavet teemast [Azure Data Lake’i andmeallikate](incremental-refresh-data-sources.md) astmelise värskendamise konfigureerimine.

1. Valitud olemite puhul, kus primaarvõtit pole määratletud, **kuvatakse jaotises** Primaarvõti **jaotises Nõutav**. Kõigi nende olemite puhul:
   1. Valige **Nõutav**. Kuvatakse **paan Redigeeri olemit**.
   1. Valige **primaarvõti**. Primaarvõti on olemile ainuomane atribuut. Et atribuut saaks olla sobiv primaarvõti, ei tohi see sisaldada topeltväärtusi, puuduvaid väärtusi ega null-väärtusi. Stringi, täisarvu ja GUID andmetüübi atribuute toetatakse primaarvõtmetena.
   1. Soovi korral muutke partitsioonimustrit.
   1. Paani salvestamiseks ja sulgemiseks valige **Sule**.

1. Valige **Salvesta**. Avaneb **leht Andmeallikad**, kus kuvatakse uus andmeallikas olekus **Värskendamine**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Andmete laadimine võib võtta aega. Pärast edukat värskendamist saab allaneelatud andmeid vaadata lehelt [**Olemid**](entities.md).

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Azure Data Lake Storage andmeallikas redigeerimine

Saate värskendada suvandit *Ühenda salvestusruumikontoga, kasutades* suvandit. Lisateavet vaadake jaotisest [Customer Insightsi Azure Data Lake Storage ühendamine Gen2 kontoga Azure’i teeninduse printsipaal](connect-service-principal.md). Kui soovite luua ühenduse muu konteineriga teie salvestuskontol või muuta konto nime, siis peate looma [uue andmeallika ühenduse](#connect-to-azure-data-lake-storage).

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige värskendatava andmeallikas kõrval käsk **Redigeeri**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dialoogiboks Azure Data Lake andmeallikas redigeerimiseks.":::

1. Muutke mõnda järgmistest andmetest.

   - **Kirjeldus**
   - **Ühendage oma salvestusruum, kasutades** ja ühendusteavet. Ühenduse värskendamisel ei saa te muuta **konteineri** teavet.
      > [!NOTE]
      > Salvestusruumikontole või -konteinerile tuleb määrata üks järgmistest rollidest.
        > - Salvestusruumi bloobiandmete luger
        > - Salvestusruumi bloobiandmete omanik
        > - Salvestusruumi bloobiandmete kaasautor

   - **Luba privaatne link**, kui soovite andmeid talletamiskontolt Azure Private Linki kaudu alla neelata. Lisateavet vaadake jaotisest [Privaatsed lingid](security-overview.md#set-up-an-azure-private-link).

1. Tehke valik **Edasi**.
1. Muutke ühte järgmistest.
   - Liikuge failile model.json või manifest.json, millel on konteinerist erinev olemite komplekt.
   - Allaneelamiseks täiendavate olemite lisamiseks valige **Uus olem**.
   - Juba valitud olemite eemaldamiseks, kui sõltuvusi pole, valige olem ja **Kustuta**.
      > [!IMPORTANT]
      > Kui olemasoleval failil model.json või manifest.json ja olemikomplektil on sõltuvusi, kuvatakse tõrketeade ja te ei saa valida muud faili model.json või manifest.json. Eemaldage need sõltuvused enne faili model.json või manifest.json muutmist või looge uus andmeallikas failiga model.json või manifest.json, mida soovite kasutada, et vältida sõltuvuste eemaldamist.
   - Andmefaili asukoha või primaarvõtme muutmiseks valige **Redigeeri**.
   - Inkrementaalse allaneelamise andmete muutmise kohta leiate teavet teemast [Azure Data Lake’i andmeallikate astmelise värskendamise konfigureerimine](incremental-refresh-data-sources.md).
   - Muutke olemi nime ainult nii, et see vastaks .json-failis olevale olemi nimele.

     > [!NOTE]
     > Hoidke olemi nimi Customer Insightsis alati sama, mis olemi nimi failis model.json või manifest.json pärast allaneelamist. Customer Insights valideerib iga süsteemi värskendamise ajal kõik olemite nimed mudeliga model.json või manifest.json. Kui olemi nime muudetakse kas Customer Insightsis või väljaspool seda, ilmneb tõrge, kuna Customer Insights ei leia JSON-failist uut olemi nime. Kui allaneelatud olemi nime muudeti kogemata, redigeerige olemi nime Customer Insightsis nii, et see vastaks JSON-failis olevale nimele.

1. Valige **Atribuudid atribuutide** lisamiseks või muutmiseks või andmete profileerimise lubamiseks. Seejärel valige **Valmis**.

1. Muudatuste rakendamiseks ja lehele Andmeallikad **naasmiseks** klõpsake nuppu **Salvesta**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
