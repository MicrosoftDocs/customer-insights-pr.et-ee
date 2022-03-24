---
title: Keskkondade loomine ja haldamine
description: Siit leiate teavet selle kohta, kuidas teenuse kasutamiseks registreeruda ja kuidas keskkondasid hallata.
ms.date: 02/09/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 4f4e5a8415f6c2128b0480edf67f317124eeeba9
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376871"
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

Kui soovite kasutada [karbist välja ennustamise mudeleid](predictions-overview.md#out-of-box-models), siis konfigureerige andmete ühiskasutus rakendusega Dataverse. Võite ka lubada asutusesisestest allikatest pärinevad andmed, pakkudes teie Microsoft Dataverse organisatsiooni hallatava keskkonna URL-i.

> [!IMPORTANT]
> Customer Insights ja Dataverse andmete jagamise lubamiseks peab see olema samas piirkonnas.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Konfigureerimissuvandid andmete jagamise lubamiseks Microsoft Dataverse abil.":::

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

## <a name="change-the-owner-of-an-environment"></a>Keskkonna omaniku muutmine

Kuigi customer Insightsis võivad administraatoriõigused olla mitmel kasutajal, on keskkonna omanik ainult üks kasutaja. Vaikimisi loob algselt keskkonna administraator. Keskkonna administraatorina saate määrata omandiõiguse teisele administraatoriõigustega kasutajale.

1. Valige rakenduse päises valija **Environment** (Keskkond).

1. Valige ikoon **Edit** (Redigeeri).

1. Avage väljal **Keskkonna** redigeerimine juhised **Põhiteave**.

1. Valige väljal **Keskkonna** omaniku muutmine keskkonna uus omanik.  

1. Muudatuste rakendamiseks valige **Läbivaatus ja lõpeta**, seejärel **Värskenda**. 

## <a name="claim-ownership-of-an-environment"></a>Nõuda keskkonna omandiõigust

Kui keskkonna omanik lahkub organisatsioonist või tema kasutajakonto kustutatakse, ei ole keskkonnal omanikku. Administraatoriõigustega kasutaja saab omandiõiguse endale nõuda ja saada uueks omanikuks. Nad võivad jätkata keskkonna omamist või [omaniku muutmist teisele administraatorile](#change-the-owner-of-an-environment). 

Omandiõiguse taotlemiseks valige **nupp Võta omandiõigus**, mis kuvatakse Customer Insightsi iga lehe ülaosas, kui algne omanik organisatsioonist lahkus.

## <a name="reset-an-existing-environment"></a>Olemasoleva keskkonna lähtestamine

Keskkonna omanikuna saate keskkonna lähtestada tühja olekusse, kui soovite kustutada kõik konfiguratsioonid ja eemaldada allaneelatud andmed.

1.  Valige rakenduse päises valija **Environment** (Keskkond). 

2.  Valige keskkond, mille soovite lähtestada, ja valige ellips (**...**). 

3. Valige suvand **Reset** (Lähtesta). 

4.  Kustutamise kinnitamiseks sisestage keskkonna nimi ja valige **Lähtesta**.

## <a name="delete-an-existing-environment"></a>Olemasoleva keskkonna kustutamine

Keskkonna omanikuna saate kustutada hallatava keskkonna.

1.  Valige rakenduse päises valija **Environment** (Keskkond).

2.  Valige keskkond, mille soovite lähtestada, ja valige ellips (**...**). 

3. Valige suvand **Delete** (Kustuta). 

4.  Kustutamise kinnitamiseks sisestage soovitud keskkonna nimi ja valige **Kustuta**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
