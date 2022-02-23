---
title: Keskkondade loomine ja haldamine
description: Siit leiate teavet selle kohta, kuidas teenuse kasutamiseks registreeruda ja kuidas keskkondasid hallata.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8251cac9f95455b61eb0300b6c72cd4ab2969591
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046328"
---
# <a name="manage-environments"></a>Keskkondade haldamine



## <a name="switch-environments"></a>Vaheta keskkondasid

Keskkondade vahetamiseks valige juhtelement **Keskkond** lehe paremas ülanurgas.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Juhtelemendi kuvatõmmis keskkondade vahetamiseks.":::

Halduskeskused saavad keskkondi [luua](create-environment.md) ja hallata.

## <a name="edit-an-existing-environment"></a>Olemasoleva keskkonna redigeerimine

Saate muuta olemasolevate keskkondade teatud üksikasju.

1.  Valige rakenduse päises valija **Environment** (Keskkond).

2.  Valige ikoon **Edit** (Redigeeri).

3. Väljal **Redigeeri keskkonda** saate keskkonnasätteid värskendada.

Keskkonna sätete kohta leiate lisateavet teemast [Uue keskkonna loomine](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Microsoft Dataverse’iga ühenduse loomine
   
**Microsoft Dataverse** etapp lubab teil Customer Insights'i oma Dataverse keskkonnaga ühendada.

Kui soovite kasutada [karbist välja ennustamise mudeleid](predictions-overview.md#out-of-box-models), siis konfigureerige andmete ühiskasutus rakendusega Dataverse. Võite ka lubada asutusesisestest allikatest pärinevad andmed, pakkudes teie Microsoft Dataverse organisatsiooni hallatava keskkonna URL-i. Valige suvand **Luba andmete ühiskasutus**, et jagada Customer Insights väljundandmeid Dataverse hallatava Data Lake'iga.

> [!IMPORTANT]
> Customer Insights ja Dataverse peab andmete jagamise lubamiseks olema samas piirkonnas.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Konfigureerimissuvandid andmete jagamise lubamiseks Microsoft Dataverse abil.":::

> [!NOTE]
> Customer Insights ei toeta järgmisi andmete jagamise stsenaariume:
> - Kui salvestate kõik andmed enda Azure Data Lake Storage abil, siis ei saa te lubada andmete jagamist Dataverse hallatava Data Lake-iga.
> - Kui lubate andmete ühiskasutuse Dataverse-ga, ei saa te [olemis luua ennustatud ega puuduvad väärtused](predictions.md).

## <a name="copy-the-environment-configuration"></a>Kopeerige keskkonna konfiguratsioon

Uue keskkonna loomisel saate konfiguratsiooni kopeerida olemasolevast keskkonnast. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Kuvatõmmis suvandisätetest keskkonnasätetes.":::

Näete teie ettevõtte kõigi saadaolevate keskkondade loendit, kust saate andmeid kopeerida.

Kopeeritakse järgmised konfiguratsioonisätted.

- Valmendatud/imporditud andmeallikad
- Andmete ühtlustamiskonfiguratsioon (kaardistamine, vastendamine, ühendamine)
- Segmendid
- Meetmed
- Seosed
- Tegevused 
- Otsingu ja filtri register
- Ekspordisihtkohad
- Ajastatud värskendamine
- Rikastamised
- Mudeli haldus
- Rolli määramised

Järgnevaid andmeid *ei* kopeerita:

- Kliendiprofiilid.
- Andmeallika identimisteave. Peate sisestama identimisteabe iga andmeallika jaoks ja värskendama andmeallikaid käsitsi.

- Andmeallikad ühisandmemudeli kaustast ja Dataverse hallatavatest Data Lake-st. Peate need andmeallikad looma käsitsi sama nimega kui lähtekeskkond.

Keskkonna kopeerimisel näete kinnitusteadet, et loodi uus keskkond. Andmeallikate loendi nägemiseks valige suvand **Ava andmeallikad**.

Kõik andmeallikad kuvavad olekut **Mandaat nõutav**. Redigeerige andmeallikaid ja sisestage nende värskendamiseks identimisteave.

:::image type="content" source="media/data-sources-copied.png" alt-text="Kopeeritud ja autentimist vajav andmeallikate loend.":::

Pärast andmeallikate värskendamist avage jaotis **Andme** > **Ühendamine**. Siit leiate lähtekeskkonna sätted. Redigeerige neid vastavalt vajadusele või valige **Käivita**, et käivitada andmete ühendamise protsess ja luua ühtne kliendi olem.

Kui andmete ühendamine on lõpetatud, avage **Meetmed** ja **Segmendid**, et neid samuti värskendada.

## <a name="reset-an-existing-environment"></a>Olemasoleva keskkonna lähtestamine

Kui soovite kustutada kõik konfiguratsioonid ja eemaldada valmendatud andmed, saate keskkonna lähtestada nii, et see oleks täiesti tühi.

1.  Valige rakenduse päises valija **Environment** (Keskkond). 

2.  Valige keskkond, mille soovite lähtestada, ja valige ellips (**...**). 

3. Valige suvand **Reset** (Lähtesta). 

4.  Kustutamise kinnitamiseks sisestage keskkonna nimi ja valige **Lähtesta**.

## <a name="delete-an-existing-environment"></a>Olemasoleva keskkonna kustutamine

Administraatorina saate kustutada halduskeskkonna.

1.  Valige rakenduse päises valija **Environment** (Keskkond).

2.  Valige keskkond, mille soovite lähtestada, ja valige ellips (**...**). 

3. Valige suvand **Delete** (Kustuta). 

4.  Kustutamise kinnitamiseks sisestage soovitud keskkonna nimi ja valige **Kustuta**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
