---
title: Common Data Modeli andmete ühendamine Azure Data Lake'i kontoga
description: Töötage Common Data Modeli andmete kallal Azure Data Lake Storage'i abil.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 49bab0605197912cd4b81ff193b914599a092792
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554889"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Common Data Modeli kausta ühendamine Azure Data Lake’i kontot kasutades

See artikkel annab teavet selle kohta, kuidas valmendada andmeid Common Data Modeli kaustast, kasutades Azure Data Lake Storage Gen2 kontot.

## <a name="important-considerations"></a>Olulised kaalutlused

- Andmed Azure Data Lake'is peavad vastama Common Data Modeli standardile. Hetkel muid vorminguid ei toetata.

- Andmete valmendamise korral toetatakse ainult Azure Data Lake *Gen2* salvestuskontosid. Andmete valmendamiseks ei saa kasutada Azure Data Lake Gen1 salvestuskontosid.

- Azure'i teenusesubjektiga autentimiseks veenduge, et see oleks teie rentnikus konfigureeritud. Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md).

- Azure Data Lake, millega soovite ühenduda ja millest andmeid valmendada, peab olema samas Azure'i regioonis nagu Dynamics 365 Customer Insightsi keskkond. Ühendused Common Data Modeli kausta ja muus Azure'i regioonis oleva andmejärve vahel pole toetatud. Selleks et uurida välja keskkonna Azure'i regioon, minge sihtrühmaülevaadetes jaotisse **Haldus** > **Süsteem** > **Teave**.

- Võrguteenustes talletatud andmed võivad olla talletatud mõnes muus kohas, mis erineb kohast, kus Dynamics 365 Customer Insightsis andmeid töödeldakse või talletatakse. Kui impordite võrguteenustes talletatavaid andmeid või ühendate konto teenusega, siis nõustute, et andmeid võidakse transportida ja salvestada rakenduses Dynamics 365 Customer Insights. [Lisateavet leiate Microsofti usalduskeskusest.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Loo ühendus Common Data Modeli kaustaga

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige **Loo ühendus Common Data Modeli kaustaga**, sisestage andmeallikale **Nimi** ja valige **Edasi**. Nime juhised: 
   - peab algama tähega;
   - kasutage ainult tähti ja numbreid; erimärkide ja tühikute sisestamine pole lubatud;
   - kasutage 3–64 tähemärki.

1. Saate autentimiseks valida ressursipõhise ja tellimusepõhise valiku vahel. Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md). Sisestage **konteineri** teave ja valige **Edasi**.
   > [!div class="mx-imgBorder"]
   > ![Azure Data Lake'i uute ühenduse üksikasjade sisestamise dialoogiboks.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Ühenduse ja andmeallika loomiseks on vaja ühte järgmistest ülalviidatud konteineri või salvestusruumi konto rollidest.
   >  - Salvestusruumi bloobiandmete luger
   >  - Salvestusruumi bloobiandmete omanik
   >  - Salvestusruumi bloobiandmete kaasautor

1. Valige dialoogis **Common Data Modeli kausta valimine** fail model.json või manifest.json, kuhu andmeid importida, ja valige **Edasi**.
   > [!NOTE]
   > Keskkonnas muu andmeallikaga seotud faile model.json või manifest.json ei kuvata loendis.

1. Saadaolevate olemite loendi leiate valitud failist model.json või manifest.json. Saate vaadata üle ja valida saadaolevate olemite loendist ning valida suvandi **Salvesta**. Kõik valitud olemid valmendatakse uuest andmeallikast.
   > [!div class="mx-imgBorder"]
   > ![Dialoogiboks, kus on esitatud model.json failist saadud olemite loetelu.](media/review-entities.png)

8. Andmete profiilimise lubamiseks valige soovitud andmeüksused ja valige **Salvesta**. Andmete profiilimine teeb võimalikuks analüüsi ja palju muud. Saate valida kogu olemi, mis valib olemi kõik atribuudid, või valida oma soovi järgi kindlad atribuudid. Vaikimisi pole olemeid andmete profiilimiseks lubatud.
   > [!div class="mx-imgBorder"]
   > ![Andmete profiilimist kuvav dialoogiboks.](media/dataprofiling-entities.png)

9. Pärast valikute salvestamist avaneb leht **Andmeallikad**. Nüüd peaksite nägema Common Data Modeli kausta ühendust andmeallikana.

> [!NOTE]
> Faili model.json või manifest.json saab seostada samas keskkonnas ühe andmeallikaga. Kuid sama faili model.json või manifest.json saab kasutada mitmes keskkonnas andmeallikate jaoks.

## <a name="edit-a-common-data-model-folder-data-source"></a>Common Data Modeli kausta andmeallika redigeerimine

Saate värskendada pääsuvõtit, mis kuulub salvestuskontole, mis sisaldab Common Data Modeli kausta. Võite ka faili model.json või manifest.json muuta. Kui soovite luua ühenduse muu konteineriga teie salvestuskontol või muuta konto nime, siis peate looma [uue andmeallika ühenduse](#connect-to-a-common-data-model-folder).

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2. Valige uuendatava andmeallika kõrval suvand kolm punkti.

3. Valige loetelust valik **Redigeeri**.

4. Soovi korral saate uuendada **Pääsuvõtit** ja valida seejärel **Järgmine**.

   ![Olemasoleva andmeallika pääsuvõtme redigeerimise ja uuendamise dialoog.](media/edit-access-key.png)

5. Soovi korral saate kasutada kontovõtmepõhise ühenduse asemel ressursi- või tellimusepõhist ühendust. Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md). Ühenduse värskendamisel ei saa te muuta **konteineri** teavet.
   > [!div class="mx-imgBorder"]

   > ![Ühenduse andmete sisestamise dialoogiboks Azure Data Lake'i ühendamiseks olemasoleva salvestusruumi kontoga.](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Ühenduse ja andmeallika loomiseks on vaja ühte järgmistest ülalviidatud konteineri või salvestusruumi konto rollidest.
   >  - Salvestusruumi bloobiandmete luger
   >  - Salvestusruumi bloobiandmete omanik
   >  - Salvestusruumi bloobiandmete kaasautor


6. Soovi korral saate valida konteinerist erineva olemikomplektiga faili model.json või manifest.json.

7. Soovi korral saate valmendamiseks valida täiendavaid olemeid. Samuti saate sõltuvuste puudumise korral eemaldada kõiki juba valitud olemeid.

   > [!IMPORTANT]
   > Kui olemasoleval failil model.json või manifest.json ja olemikomplektil on sõltuvusi, kuvatakse tõrketeade ja te ei saa valida muud faili model.json või manifest.json. Eemaldage need sõltuvused enne faili model.json või manifest.json muutmist või looge uus andmeallikas failiga model.json või manifest.json, mida soovite kasutada, et vältida sõltuvuste eemaldamist.

8. Soovi korral saate valida täiendavaid atribuute või olemeid, mille korral lubada andmete profiilimine, või keelata juba valitud üksused.   


[!INCLUDE[footer-include](../includes/footer-banner.md)]