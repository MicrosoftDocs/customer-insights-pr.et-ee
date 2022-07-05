---
title: Common Data Modeli kausta ühendamine Azure Data Lake’i kontot kasutades
description: Töötage Common Data Modeli andmete kallal Azure Data Lake Storage'i abil.
ms.date: 05/30/2022
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
ms.openlocfilehash: b1cdcb46df17d722ad49d361ae4c7ab34c83eeb1
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082257"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Andmetega ühenduse loomine Azure Data Lake Storageis

Andmete sisestamine Gen2 konto kasutamisse Dynamics 365 Customer Insights Azure Data Lake Storage. Andmete allaneelamine võib olla täielik või järkjärguline.

## <a name="prerequisites"></a>eeltingimused

- Andmete allaneelamine toetab Azure Data Lake Storage *ainult Gen2* kontosid. Data Lake Storage Gen1 kontosid ei saa andmete allaneelamiseks kasutada.

- Kontol Azure Data Lake Storage peab [olema lubatud hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace). Andmed tuleb talletada hierarhilises kaustavormingus, mis määratleb juurkausta ja millel on iga olemi jaoks alamkaustad. Alamkaustadel võivad olla täielikud andmed või täiendavad andmekaustad.

- Azure'i teenusesubjektiga autentimiseks veenduge, et see oleks teie rentnikus konfigureeritud. Lisateavet vt teemast [Connect to a Azure Data Lake Storage Gen2 kontoga Azure'i teenuse käsundiandja](connect-service-principal.md) abil.

- Andmed Azure Data Lake Storage, millest soovite andmeid ühendada ja alla neelata, peavad olema keskkonnaga samas Azure'i Dynamics 365 Customer Insights piirkonnas. Ühendused Common Data Modeli kausta ja muus Azure'i regioonis oleva andmejärve vahel pole toetatud. Keskkonna Azure'i piirkonna tundmaõppimiseks avage **customer insights'is administraatorisüsteemi** > **·** > **teave**.

- Võrguteenustes talletatavaid andmeid võidakse talletada mõnes muus asukohas Dynamics 365 Customer Insights kui siis, kui andmeid töödeldakse või talletatakse.Veebiteenustes talletatavate andmete importimisel või nendega ühenduse loomisel nõustute, et andmeid saab edastada ja salvestada rakendusega Dynamics 365 Customer Insights. [Lisateavet leiate Microsofti usalduskeskusest](https://www.microsoft.com/trust-center).

- Customer Insightsi teenuse põhiosa peab salvestuskontole pääsemiseks olema ühes järgmistest rollidest. Lisateavet leiate teemast [Hooldusdirektori õiguste andmine salvestuskontole](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account) juurdepääsuks.
  - Salvestusruumi bloobiandmete luger
  - Salvestusruumi bloobiandmete omanik
  - Salvestusruumi bloobiandmete kaasautor

- Teie Data Lake Storage'is olevad andmed peaksid teie andmete salvestamiseks järgima ühist andmemudeli standardit ja neil peab olema ühine andmemudeli manifest, mis esindab andmefailide skeemi (*.csv või *.parkett). Manifest peab sisaldama olemite üksikasju ( nt olemiveerud ja andmetüübid) ning andmefaili asukohta ja failitüüpi. Lisateavet leiate teemast [Levinud andmemudeli manifest](/common-data-model/sdk/manifest). Kui manifesti pole olemas, saavad salvestusruumi bloobiandmete omaniku või salvestusruumi bloobi andmete kaasautori juurdepääsuga administraatori kasutajad andmete allaneelamisel skeemi määratleda.

## <a name="connect-to-azure-data-lake-storage"></a>Azure Data Lake Storageiga ühenduse loomine

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige **Azure data lake storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Dialoogiboks Azure Data Lake'i ühenduse üksikasjade sisestamiseks." lightbox="media/data_sources_ADLS.png":::

1. **Sisestage andmeallikas nimi** ja valikuline **kirjeldus**. Nimi tuvastab kordumatult andmeallikas ja sellele viidatakse järgmise etapi protsessides ning seda ei saa muuta.

1. Valige üks järgmistest suvanditest, et **ühendada oma salvestusruum.** Lisateavet leiate teemast [Customer Insightsi Azure Data Lake Storage ühendamine Gen2 kontoga Azure'i teenuse põhiosaga](connect-service-principal.md).

   - **Azure'i ressurss**: sisestage **resource ID**. Soovi korral, kui soovite salvestusruumikontolt andmeid Azure'i privaatlingi kaudu alla neelata, valige **Luba privaatlink**. Lisateavet vt teemast [Private Links](security-overview.md#private-links-tab).
   - **Azure'i tellimus**: valige tellimus **ja seejärel** ressursirühm **ja** salvestusruumikonto **·**. Soovi korral, kui soovite salvestusruumikontolt andmeid Azure'i privaatlingi kaudu alla neelata, valige **Luba privaatlink**. Lisateavet vt teemast [Private Links](security-overview.md#private-links-tab).
  
   > [!NOTE]
   > Andmeallikas loomiseks on vaja ühte järgmistest rollidest kas konteinerisse või salvestuskontole.
   >
   >  - Storage Blob Data Reader on piisav, et lugeda salvestuskontolt ja neelata andmed Customer Insightsi. 
   >  - Kui soovite manifestifaile redigeerida otse Customer Insightsis, on vaja salvestusruumi bloobi andmete kaasautorit või omanikku.  
  
1. Valige andmete importimiseks **andmeid ja skeemi sisaldava konteineri** (model.json või manifest.json fail) nimi ja valige **Edasi**.
   > [!NOTE]
   > Keskkonnas muu andmeallikaga seotud faile model.json või manifest.json ei kuvata loendis. Kuid sama faili model.json või manifest.json saab kasutada mitmes keskkonnas andmeallikate jaoks.

1. Uue skeemi loomiseks avage [uue skeemifaili](#create-a-new-schema-file) loomine.

1. Olemasoleva skeemi kasutamiseks liikuge kausta, mis sisaldab faili model.json või manifest.cdm.json. Faili leidmiseks saate otsida kataloogist.

1. Valige json-fail ja valige **Edasi**. Kuvatakse saadaolevate olemite loend.

   :::image type="content" source="media/review-entities.png" alt-text="Valitavate olemite loendi dialoogiboks":::

1. Valige olemid, mida soovite kaasata.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialoogiboks, kus on kuvatud Primaarvõtme jaoks nõutav":::

   > [!TIP]
   > JSON redigeerimisliidese olemite redigeerimiseks valige **Kuva veel** > **Redigeeri skeemifaili**. Tehke muudatusi ja valige **Salvesta**.

1. Valitud olemite puhul, mis vajavad järkjärgulist allaneelamist, **kuvatakse jaotises Nõutav** jaotises **Astmeline värskendamine nõutav**. Kõigi nende olemite kohta leiate teavet teemast [Azure Data Lake'i andmeallikate täiendava värskenduse konfigureerimine](incremental-refresh-data-sources.md).

1. Valitud olemite puhul, kus primaarvõtit pole määratletud, **kuvatakse jaotises** Primaarvõti **nõutav**. Kõigi nende üksuste puhul tehke järgmist.
   1. Valige **Nõutav**. Kuvatakse **paneel Redigeeri olemit**.
   1. **Valige primaarvõti**. Primaarvõti on olemile ainuomane atribuut. Et atribuut saaks olla sobiv primaarvõti, ei tohi see sisaldada topeltväärtusi, puuduvaid väärtusi ega null-väärtusi. Põhivõtmetena toetatakse stringi-, täisarvu- ja GUID-andmetüübi atribuute.
   1. Soovi korral muutke partitsioonimustrit.
   1. Paneeli salvestamiseks ja sulgemiseks valige **Sule**.

1. Valige iga kaasatud olemi jaoks atribuutide **arv**. Kuvatakse **leht Atribuutide** haldamine.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialoogiboks andmete profileerimise valimiseks.":::

   1. Looge uusi atribuute, redigeerige või kustutage olemasolevaid atribuute. Saate muuta nime, andmevormingut või lisada semantilist tüüpi.
   1. Analüüsi ja muude võimaluste lubamiseks valige **Andmete profileerimine** kogu olemi või kindlate atribuutide jaoks. Vaikimisi pole olemeid andmete profiilimiseks lubatud.
   1. Valige nupp **Valmis**.

1. Valige **Salvesta**. Avaneb **andmeallikate** leht, kus kuvatakse uus andmeallikas olekus **Värskendamine**.

### <a name="create-a-new-schema-file"></a>Uue skeemifaili loomine

1. Valige **Uus skeemifail**.

1. Sisestage faili nimi ja valige **Salvesta**.

1. Valige **Uus olem**. Kuvatakse **paneel Uus olem**.

1. Sisestage olemi nimi ja valige **andmefailide asukoht**.
   - **Mitu .csv- või .parkettfaili**: sirvige juurkausta, valige mustritüüp ja sisestage avaldis.
   - **Üksikud .csv- või .parkettfailid**: sirvige .csv- või parkettfailini ja valige see.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Dialoogiboks uue olemi loomiseks, kus on esile tõstetud andmefailide asukoht.":::

1. Valige **Salvesta**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Dialoogiboks atribuutide määratlemiseks või automaatseks loomiseks.":::

1. Valige **atribuutide** käsitsi lisamiseks atribuutide määratlemine või valige **automaatne loomine**. Atribuutide määratlemiseks sisestage nimi, valige andmevorming ja valikuline semantiline tüüp. Automaatselt genereeritud atribuutide puhul tehke järgmist.

   1. Pärast atribuutide automaatset loomist valige **Atribuutide ülevaatamine**. Kuvatakse **leht Atribuutide** haldamine.

   1. Veenduge, et andmevorming oleks iga atribuudi jaoks õige.

   1. Analüüsi ja muude võimaluste lubamiseks valige **Andmete profileerimine** kogu olemi või kindlate atribuutide jaoks. Vaikimisi pole olemeid andmete profiilimiseks lubatud.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Dialoogiboks andmete profileerimise valimiseks.":::

   1. Valige nupp **Valmis**. Kuvatakse **leht Vali olemid**.

1. Vajadusel jätkake olemite ja atribuutide lisamist.

1. Kui kõik olemid on lisatud, valige **Kaasa**, et kaasata olemid andmeallikas allaneelamisse.

   :::image type="content" source="media/ADLS_required.png" alt-text="Dialoogiboks, kus on kuvatud Primaarvõtme jaoks nõutav":::

1. Valitud olemite puhul, mis vajavad järkjärgulist allaneelamist, **kuvatakse jaotises Nõutav** jaotises **Astmeline värskendamine nõutav**. Kõigi nende olemite kohta leiate teavet teemast [Azure Data Lake'i andmeallikate täiendava värskenduse konfigureerimine](incremental-refresh-data-sources.md).

1. Valitud olemite puhul, kus primaarvõtit pole määratletud, **kuvatakse jaotises** Primaarvõti **nõutav**. Kõigi nende üksuste puhul tehke järgmist.
   1. Valige **Nõutav**. Kuvatakse **paneel Redigeeri olemit**.
   1. **Valige primaarvõti**. Primaarvõti on olemile ainuomane atribuut. Et atribuut saaks olla sobiv primaarvõti, ei tohi see sisaldada topeltväärtusi, puuduvaid väärtusi ega null-väärtusi. Põhivõtmetena toetatakse stringi-, täisarvu- ja GUID-andmetüübi atribuute.
   1. Soovi korral muutke partitsioonimustrit.
   1. Paneeli salvestamiseks ja sulgemiseks valige **Sule**.

1. Valige **Salvesta**. Avaneb **andmeallikate** leht, kus kuvatakse uus andmeallikas olekus **Värskendamine**.


## <a name="edit-an-azure-data-lake-storage-data-source"></a>Andmeallikas redigeerimine Azure Data Lake Storage

Suvandi Ühenda salvestusruumiga saate värskendada *suvandi abil*. Lisateavet leiate teemast [Customer Insightsi Azure Data Lake Storage ühendamine Gen2 kontoga Azure'i teenuse põhiosaga](connect-service-principal.md). Kui soovite luua ühenduse muu konteineriga teie salvestuskontol või muuta konto nime, siis peate looma [uue andmeallika ühenduse](#connect-to-azure-data-lake-storage).

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige värskendatava andmeallikas kõrval Käsk **Redigeeri**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Dialoogiboks Azure Data Lake andmeallikas redigeerimiseks.":::

1. Muutke mõnda järgmistest andmetest.

   - **Kirjeldus**
   - **Ühendage oma salvestusruum ühenduse teabe ja ühendusteabe abil**. Ühenduse värskendamisel ei saa te muuta **konteineri** teavet.
      > [!NOTE]
      > Salvestuskontole või konteinerile tuleb määrata üks järgmistest rollidest.
        > - Salvestusruumi bloobiandmete luger
        > - Salvestusruumi bloobiandmete omanik
        > - Salvestusruumi bloobiandmete kaasautor

   - **Lubage privaatlink,** kui soovite azure'i privaatlingi kaudu salvestusruumikontolt andmeid alla neelata. Lisateavet vt teemast [Private Links](security-overview.md#private-links-tab).

1. Tehke valik **Edasi**.
1. Muutke ühte järgmistest.
   - Navigeerige mõnele muule model.json või manifest.json failile, millel on konteinerist erinev olemite kogum.
   - Täiendavate olemite lisamiseks allaneelamisse valige **Uus olem**.
   - Juba valitud olemite eemaldamiseks, kui sõltuvusi pole, valige olem ja **Kustuta**.
      > [!IMPORTANT]
      > Kui olemasoleval failil model.json või manifest.json ja olemikomplektil on sõltuvusi, kuvatakse tõrketeade ja te ei saa valida muud faili model.json või manifest.json. Eemaldage need sõltuvused enne faili model.json või manifest.json muutmist või looge uus andmeallikas failiga model.json või manifest.json, mida soovite kasutada, et vältida sõltuvuste eemaldamist.
   - Andmefaili asukoha või primaarvõtme muutmiseks valige **Redigeeri**.
   - Täiendavate allaneelamisandmete muutmiseks lugege teemat [Azure Data Lake'i andmeallikate täiendusvärskenduse konfigureerimine](incremental-refresh-data-sources.md)

1. Atribuutide **lisamiseks või muutmiseks või andmete profileerimise lubamiseks valige** Atribuudid. Seejärel valige **Valmis**.

1. Muudatuste rakendamiseks ja andmeallikate **lehele naasmiseks** klõpsake nuppu **Salvesta**.
