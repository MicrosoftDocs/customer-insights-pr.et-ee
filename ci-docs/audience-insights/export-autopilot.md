---
title: Customer Insightsi andmete eksportimine Autopilotisse
description: Vaadake, kuidas konfigureerida ühendust Autopilotiga.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269233"
---
# <a name="connector-for-autopilot-preview"></a>Autopiloti konnektor (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente Autopiloti kontaktiloenditesse ja kasutada neid Autopilotis kampaaniate ja meiliturunduste jaoks. 

## <a name="prerequisites"></a>Eeltingimused

-   Teil on [Autopiloti konto](https://www.autopilothq.com/) ja asjakohane administraatori identimisteave.
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="connect-to-autopilot"></a>Ühenda Autopilotiga

1. Avage **Haldus** > **Ekspordi sihtkohad**.

1. Tehke jaotises **Autopilot** valik **Seadista**.

1. Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopiloti ühenduse konfiguratsioonipaan.":::

1. Sisestage oma **Autopiloti API võti** [Autopiloti API võti](https://autopilot.docs.apiary.io/#).

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda**, et käivitada ühendus Autopilotiga.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ekspordi konfigureerimiseks valige **Edasi**.

## <a name="configure-the-connector"></a>Konnektori konfigureerimine

1. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. Korrake samu juhiseid muude valikuliste väljade puhul, nagu **Eesnimi** ja **Perekonnanimi**.

1. Valige segmendid, mille soovite eksportida. Soovitame **tungivalt mitte eksportida kokku üle 100 000 kliendiprofiili** Autopilotisse. 

1. Valige **Salvesta**.

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).

## <a name="known-limitations"></a>Teadaolevad piirangud

- Autopilotisse saate eksportida kuni 100 000 profiili.
- Autopilotisse saab eksportida ainult segmente.
- Kuni 100 000 profiili eksportimiseks Autopilotisse võib kuluda paar tundi. 
- Autopilotisse eksporditavate profiilide arv sõltub Autopilotiga sõlmitud lepingust.

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Autopilotisse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Autopilot täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]