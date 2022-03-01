---
title: Customer Insightsi andmete eksportimine AdRolli
description: Vaadake, kuidas konfigureerida ühendust AdRolliga.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697069"
---
# <a name="connector-for-adroll-preview"></a>AdRolli konnektor (eelversioon)

Eksportige kliendi koondprofiili segmendid AdRolli ja kasutage neid reklaamimiseks. 

## <a name="prerequisites"></a>Eeltingimused

-   Teil on [AdRolli konto](https://www.adroll.com/) ja asjakohane administraatori identimisteave.
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="connect-to-adroll"></a>Ühenda AdRolliga

1. Avage **Haldus** > **Ekspordi sihtkohad**.

1. Tehke jaotises **AdRoll** valik **Seadista**.

1. Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRolli ühenduse konfiguratsioonipaan.":::

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda**, et käivitada ühendus AdRolliga.

1. Valige **Autentimine AdRolliga** ja sisestage oma AdRolli administraatori identimisteave. 

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Sisestage **AdRolli reklaamija ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Ekspordi konfigureerimiseks valige **Edasi**.

## <a name="configure-the-connector"></a>Konnektori konfigureerimine

1. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. See on vajalik segmentide eksportimiseks AdRolli.

1. Valige segmendid, mille soovite eksportida. Valige vähemalt 100 liikmega segment. Väiksemaid segmente ei saa eksportida. Lisaks on eksporditava segmendi maksimummaht 250 000 liiget ekspordi kohta. 

1. Valige **Salvesta**.

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).

## <a name="known-limitations"></a>Teadaolevad piirangud

- AdRolli saate ühe ekspordi kohta eksportida kuni 250 000 profiili.
- Vähem kui 100 profiiliga segmente ei saa AdRolli eksportida. 
- AdRolli saab eksportida ainult segmente.
- Kuni 250 000 profiili eksportimiseks AdRolli võib kuluda kuni 10 minutit. 
- AdRolli eksporditavate profiilide arv sõltub AdRollga sõlmitud lepingust ja on sellega piiratud.

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil AdRolli andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et AdRoll täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
