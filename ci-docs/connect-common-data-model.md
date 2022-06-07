---
title: Common Data Modeli andmete ühendamine Azure Data Lake'i kontoga
description: Töötage Common Data Modeli andmete kallal Azure Data Lake Storage'i abil.
ms.date: 05/24/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 2e8564950a3269180a85f80fb736d2dcbd1b03b6
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833351"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Common Data Modeli kausta ühendamine Azure Data Lake’i kontot kasutades

Selles artiklis antakse teavet selle kohta, kuidas oma Gen2 konto abil Dynamics 365 Customer Insights ühisandmete mudeli kaustast andmeid Azure Data Lake Storage alla neelata.

## <a name="important-considerations"></a>Olulised kaalutlused

- Andmed Azure Data Lake'is peavad vastama Common Data Modeli standardile. Hetkel muid vorminguid ei toetata.

- Andmete valmendamise korral toetatakse ainult Azure Data Lake *Gen2* salvestuskontosid. Andmete valmendamiseks ei saa kasutada Azure Data Lake Gen1 salvestuskontosid.

- Azure Data Lake'i salvestuskontol [peab olema lubatud hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace).

- Azure'i teenusesubjektiga autentimiseks veenduge, et see oleks teie rentnikus konfigureeritud. Lisateavet vt teemast [Connect to a Azure Data Lake Storage Gen2 kontoga Azure'i teenuse käsundiandja abil](connect-service-principal.md).

- Azure Data Lake, millega soovite ühenduda ja millest andmeid valmendada, peab olema samas Azure'i regioonis nagu Dynamics 365 Customer Insightsi keskkond. Ühendused Common Data Modeli kausta ja muus Azure'i regioonis oleva andmejärve vahel pole toetatud. Keskkonna Azure'i piirkonna tundmaõppimiseks avage **customer insights'is administraatorisüsteemi** > **·** > **teave**.

- Võrguteenustes talletatavaid andmeid võidakse talletada mõnes muus asukohas Dynamics 365 Customer Insights kui siis, kui andmeid töödeldakse või talletatakse.Veebiteenustes talletatavate andmete importimisel või nendega ühenduse loomisel nõustute, et andmeid saab edastada ja salvestada rakendusega Dynamics 365 Customer Insights. [Lisateavet leiate Microsofti usalduskeskusest](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Loo ühendus Common Data Modeli kaustaga

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige **Azure'i andmejärve salvestusruum**, sisestage **andmeallikas nimi** ja seejärel valige **Edasi**.

   - Kui küsitakse, valige üks näidisandmehulkadest, mis on seotud teie valdkonnaga, ja seejärel valige **Edasi**.

1. Saate autentimiseks valida ressursipõhise ja tellimusepõhise valiku vahel. Lisateavet vt teemast [Connect to a Azure Data Lake Storage Gen2 kontoga Azure'i teenuse käsundiandja abil](connect-service-principal.md). Sisestage **serveri aadress**, valige **logi sisse** ja seejärel valige **Edasi**.
   > [!div class="mx-imgBorder"]
   > ![Azure Data Lake'i uute ühenduse üksikasjade sisestamise dialoogiboks.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Salvestusruumikontol olevale konteinerile on vaja ühte järgmistest rollidest, et luua andmeallikas.
   >
   >  - Storage Blob Data Reader on piisav, et lugeda salvestuskontolt ja neelata andmed Customer Insightsi. 
   >  - Kui soovite manifestifaile redigeerida otse Customer Insightsis, on vaja salvestusruumi bloobi andmete kaasautorit või omanikku.

1. Valige dialoogis **Common Data Modeli kausta valimine** fail model.json või manifest.json, kuhu andmeid importida, ja valige **Edasi**.
   > [!NOTE]
   > Keskkonnas muu andmeallikaga seotud faile model.json või manifest.json ei kuvata loendis.

1. Valitud failis model.json või manifest.json kuvatakse saadaolevate olemite loend. Vaadake üle ja valige saadaolevate olemite loendist, seejärel valige **Salvesta**. Kõik valitud olemid valmendatakse uuest andmeallikast.
   > [!div class="mx-imgBorder"]
   > ![Dialoogiboks, kus on esitatud model.json failist saadud olemite loetelu.](media/review-entities.png)

1. Saate märkida, milliseid andmeolemeid soovite andmete profileerimist lubada, seejärel valige **Salvesta**. Andmete profiilimine teeb võimalikuks analüüsi ja palju muud. Saate valida kogu olemi, mis valib olemi kõik atribuudid, või valida oma soovi järgi kindlad atribuudid. Vaikimisi pole olemeid andmete profiilimiseks lubatud.
   > [!div class="mx-imgBorder"]
   > ![Andmete profiilimist kuvav dialoogiboks.](media/dataprofiling-entities.png)

1. Pärast valikute salvestamist avaneb leht **Andmeallikad**. Nüüd peaksite nägema Common Data Modeli kausta ühendust andmeallikana.

> [!NOTE]
> Faili model.json või manifest.json saab seostada samas keskkonnas ühe andmeallikaga. Kuid sama faili model.json või manifest.json saab kasutada mitmes keskkonnas andmeallikate jaoks.

## <a name="edit-a-common-data-model-folder-data-source"></a>Common Data Modeli kausta andmeallika redigeerimine

Saate värskendada pääsuvõtit, mis kuulub salvestuskontole, mis sisaldab Common Data Modeli kausta. Võite ka faili model.json või manifest.json muuta. Kui soovite luua ühenduse muu konteineriga teie salvestuskontol või muuta konto nime, siis peate looma [uue andmeallika ühenduse](#connect-to-a-common-data-model-folder).

1. Avage suvandid **Andmed** > **Andmeallikad**.

2. Valige värskendatava andmeallikas kõrval vertikaalne kolmikpunkt (&vellip;).

3. Valige loetelust valik **Redigeeri**.

4. Soovi korral saate uuendada **Pääsuvõtit** ja valida seejärel **Järgmine**.

   ![Olemasoleva andmeallika pääsuvõtme redigeerimise ja uuendamise dialoog.](media/edit-access-key.png)

5. Soovi korral saate kasutada kontovõtmepõhise ühenduse asemel ressursi- või tellimusepõhist ühendust. Lisateavet vt teemast [Connect to a Azure Data Lake Storage Gen2 kontoga Azure'i teenuse käsundiandja abil](connect-service-principal.md). Ühenduse värskendamisel ei saa te muuta **konteineri** teavet.
   > [!div class="mx-imgBorder"]

   > ![Ühenduse andmete sisestamise dialoogiboks Azure Data Lake'i ühendamiseks olemasoleva salvestusruumi kontoga.](media/enter-existing-storage-details.png)

6. Soovi korral saate valida konteinerist erineva olemikomplektiga faili model.json või manifest.json.

7. Soovi korral saate valmendamiseks valida täiendavaid olemeid. Samuti saate sõltuvuste puudumise korral eemaldada kõiki juba valitud olemeid.

   > [!IMPORTANT]
   > Kui olemasoleval failil model.json või manifest.json ja olemikomplektil on sõltuvusi, kuvatakse tõrketeade ja te ei saa valida muud faili model.json või manifest.json. Eemaldage need sõltuvused enne faili model.json või manifest.json muutmist või looge uus andmeallikas failiga model.json või manifest.json, mida soovite kasutada, et vältida sõltuvuste eemaldamist.

8. Soovi korral saate valida täiendavaid atribuute või olemeid, mille korral lubada andmete profiilimine, või keelata juba valitud üksused.

[!INCLUDE [footer-include](includes/footer-banner.md)]
