---
title: Keskkondade loomine ja haldamine
description: Siit leiate teavet selle kohta, kuidas teenuse kasutamiseks registreeruda ja kuidas keskkondasid hallata.
ms.date: 11/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 65c6a68f550c2873ec30c6ac54f1752d880ce12c
ms.sourcegitcommit: fb9f118b4e16b5aabb3e503463efca21718f5d72
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 11/12/2021
ms.locfileid: "7799631"
---
# <a name="manage-environments"></a>Keskkondade haldamine

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

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

## <a name="connect-to-microsoft-dataverse"></a>Ühenduse loomine Microsoft Dataverse
   
**Microsoft Dataverse samm võimaldab teil ühendada Customer** Insightsi oma Dataverse keskkonnaga.

[Väljaminevate prognoos mudelite kasutamiseks](predictions-overview.md#out-of-box-models) konfigureerige andmete jagamine Dataverse. Samuti saate lubada andmete allaneelamise asutusesisene andmeallikatest, pakkudes Microsoft Dataverse keskkonna URL-i, mida teie asutus haldab. Valige **Luba andmete jagamine,** et jagada Customer Insightsi väljundandmeid Dataverse'i hallatava andmejärvega.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="Konfiguratsioonisuvandid andmete jagamise lubamiseks Microsoft Dataverse.":::

> [!NOTE]
> Customer Insights ei toeta järgmisi andmete jagamise stsenaariume:
> - Kui salvestate kõik andmed oma Azure Data Lake Storage, ei saa te andmejagamist Dataverse'i hallatava andmejärvega lubada.
> - Kui lubate andmete jagamise Dataverse, ei saa te [olemis luua ennustatud või puuduvaid](predictions.md) väärtusi.

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

- Andmeallikad kaustast Common Data Model ja Dataverse'i hallatavast andmejärvest. Peate need andmeallikad looma käsitsi sama nimega kui lähtekeskkond.

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
