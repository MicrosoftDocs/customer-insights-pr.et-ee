---
title: Klienditegevused
description: Määratlege klienditegevusi ja vaadake neid kliendi ajaskaalal.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596724"
---
# <a name="customer-activities"></a>Klienditegevused

Kombineerige [mitmesugustest andmeallikatest](data-sources.md) pärit klienditegevused Dynamics 365 Customer Insightsis, et luua kliendi ajaskaala, mis loetleb tegevused kronoloogilises järjestuses. Saate kaasata ajaskaala Customer Engagementi rakendustesse Dynamics 365-s [kliendikaardi lisandmooduli](customer-card-add-in.md) või Power BI armatuurlaua kaudu.

## <a name="define-an-activity"></a>Määratle tegevus

Teie andmeallikad hõlmavad mitmesugustest andmeallikatest pärinevaid tehingute ja tegevustega seotud andmeid sisaldavaid olemeid. Tuvastage need olemid ja valige tegevused, mida soovite kliendi ajajoonel kuvada. Valige olem, mis hõlmab teie sihttegevust või -tegevusi.

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Tegevused**.

1. Valige **Lisa tegevus**.

   > [!NOTE]
   > Olemil peab olema vähemalt üks **Kuupäeva** tüüpi atribuut, mis lisatakse kliendi ajajoonele ning ilma **Kuupäeva** väljata olemeid ei saa lisada. Kui sellist olemit ei leita, siis **Lisa tegevus** funktsioon keelatakse.

1. Määrake paanil **Lisa tegevus** järgmiste väljade väärtused.

   - **Olem**: valige olem, mis sisaldab tehingu või tegevuse andmeid.
   - **Primaarvõti**: valige väli, milles tuvastatakse kirje kordumatult. See ei tohiks sisaldada korduvväärtusi, tühjasid väärtusi ega puuduvaid väärtusi.
   - **Ajatempel**: valige väli, mis tähistab teie tegevuse algusaega.
   - **Sündmus**: valige väli, mis on tegevuse sündmus.
   - **Veebiaadress**: valige väli, mis tähistab URL-i, mis annab selle tegevuse kohta täiendavat teavet. Näiteks tehingute süsteem, mis on selle tegevuse allikaks. See URL võib olla andmeallika mis tahes väli või seda saab luua uue väljana Power Query teisenduse abil. Need URL-i andmed salvestatakse Unified Activity olemisse, mida saab kasutada allavoolu API-de abil.
   - **Üksikasjad**: soovi korral valige väli, mis on lisatud täiendava teabena.
   - **Ikoon**: soovi korral valige tegevust tähistav ikoon.
   - **Tegevuse tüüp**: määratlege Common Data Modeli tegevuse tüübi viide, mis kirjeldab kõige paremini tegevuse semantilist määratlust.

1. Konfigureerige jaotises **Seose seadistamine** üksikasjad oma tegevuse andmete ühendamiseks vastava kliendiga.

    - **Tegevuse olemi väli**: valige oma tegevuse olemis väli, mida kasutatakse teise olemiga seose loomiseks.
    - **Kliendi olem**: valige vastav lähtekliendi olem, millega teie tegevuse olem siduda. Saate seostada ainult neid lähtekliendi olemeid, mida kasutatakse andmete ühendamise protsessis.
    - **Kliendi olemi väli**: sellel väljal kuvatakse vastendamisel valitud lähtekliendi olemi primaarvõti. Seda lähtekliendi olemi primaarvõtme välja kasutatakse tegevuse olemiga seose loomiseks.
    - **Nimi**: kui selle tegevuse olemi ja valitud lähtekliendi olemi vaheline seos on juba olemas, on seose nimi kirjutuskaitstud režiimis. Kui sellist seost pole olemas, luuakse uus seos siin esitatud nimega.
   
   > [!div class="mx-imgBorder"]
   > ![Olemi seose määratlemine](media/activities-entities-define.png "Olemi seose määratlemine")

1. Vajutage nuppu **Salvesta**, et muudatused rakendada.

1. Valige lehel **Tegevused** käsk **Käita**.

> [!TIP]
> Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types). Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies). Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku. Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.

## <a name="edit-an-activity"></a>Tegevuse redigeerimine

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Tegevused**.

2. Valige tegevuse olem, mida soovite redigeerida, ja valige **Redigeeri**. Võite ka liikuda üle olemi rea ja valida ikooni **Redigeeri**.

3. Klõpsake ikoonil **Redigeeri**.

4. Värskendage paanis **Redigeeri tegevust** sisalduvad väärtused ja valige **Salvesta**.

5. Valige lehel **Tegevused** käsk **Käita**.

## <a name="delete-an-activity"></a>Tegevuse kustutamine

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Tegevused**.

2. Valige tegevuse olem, mida soovite eemaldada, ja valige **Kustuta**. Võite ka liikuda üle olemi rea ja valida ikooni **Kustuta**. Lisaks võite valida mitu tegevuse olemit korraga kustutamiseks.
   > [!div class="mx-imgBorder"]
   > ![Olemi seose redigeerimine või kustutamine](media/activities-entities-edit-delete.png "Olemi seose redigeerimine või kustutamine")

3. Valige ikoon **Kustuta**.

4. Kinnitage, et soovite kustutada.


[!INCLUDE[footer-include](../includes/footer-banner.md)]