---
title: Customer Insightsi andmete eksportimine DotDigitali
description: Vaadake, kuidas konfigureerida ühendust DotDigitaliga.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644443"
---
# <a name="connector-for-dotdigital-preview"></a>DotDigitali konnektor (eelversioon)

Eksportige koondatud kliendiprofiilid DotDigitali aadressiraamatutesse ning kasutage neid kampaaniate ja e-turunduse jaoks ning DotDigitali abil kliendisegmentide loomiseks. 

## <a name="prerequisites"></a>Eeltingimused

-   Teil on [DotDigitali konto](https://dotdigital.com/) ja asjakohane administraatori identimisteave.
-   DotDigitalis on olemas aadressiraamatud ja asjakohased ID-d. ID leiate URL-ist, kui valite ja avate aadressiraamatu. Lisateavet leiate teemast [DotDigitali aadressiraamatud](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="connect-to-dotdigital"></a>DotDigitaliga ühenduse loomine

1. Avage **Haldus** > **Ekspordi sihtkohad**.

1. Tehke jaotises **DotDigital** valik **Seadista**.

1. Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigitali konfigureerimise paan.":::

1. Sisestage oma **DotDigitali kasutajanimi ja parool**.

1. Sisestage oma **[DotDigitali aadressiraamatu ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda**, et käivitada ühendus DotDigitaliga.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ekspordi konfigureerimiseks valige **Edasi**.

## <a name="configure-the-connector"></a>Konnektori konfigureerimine

1. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. Korrake samu juhiseid muude valikuliste väljade puhul, nagu **Eesnimi**, **Perekonnanimi**, **Täisnimi**, **Sugu** ja **Sihtnumber**.

1. Valige segmendid, mille soovite eksportida. DotDigitali saate eksportida kuni miljon kliendiprofiili.

1. Valige **Salvesta**.

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab). DotDigitalis leiate nüüd oma segmendid [DotDigitali aadressiraamatutest](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Teadaolevad piirangud

- DotDigitali saab eksportida korraga kuni miljon profiili.
- DotDigitali saab eksportida ainult segmente.
- Miljoni profiiliga segmentide eksportimiseks võib teenusepakkuja tõttu kuluda kuni kolm tundi. 
- DotDigitali eksporditavate profiilide arv sõltub DotDigitaliga sõlmitud lepingust.

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil DotDigitali andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et DotDigital täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
