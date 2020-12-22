---
title: Customer Insightsi andmete eksportimine Marketosse
description: Vaadake, kuidas konfigureerida ühendust Marketoga.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570398"
---
# <a name="connector-for-marketo-preview"></a>Marketo konnektor (eelversioon)

Eksportige Marketo abil koondatud kliendiprofiilide segmente kampaaniate loomiseks, meiliturunduse pakkumiseks ja konkreetsete kliendirühmade kasutamiseks.

## <a name="prerequisites"></a>Eeltingimused

-   Teil on [Marketo konto](https://login.marketo.com/) ja asjakohane administraatori identimisteave.
-   Marketos on olemas loendid ja asjakohased ID-d. Lisateavet leiate artiklist [Marketo loendid](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Te olete [konfigureerinud segmendid](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="connect-to-marketo"></a>Marketoga ühendumine

1. Avage **Haldus** > **Ekspordi sihtkohad**.

1. Tehke jaotises **Marketo** valik **Seadista**.

1. Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.

1. Sisestage oma **[Marketo kliendi-ID, klientrakenduse salatus ja REST-i lõpp-punkti hostinimi](https://developers.marketo.com/rest-api/authentication/)**.

1. Sisestage oma **[Marketo loendi ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Valige **Nõustun**, et nõustuda jaotise **Andmete privaatsus ja nõuetele vastavus** tingimustega ja valige **Ühenda**, et Marketoga ühenduda.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Marketo ühenduse ekspordi kuvatõmmis":::

1. Ekspordi konfigureerimiseks valige **Edasi**.

## <a name="configure-the-connector"></a>Konnektori konfigureerimine

1. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. 

1. Soovi korral saate isikupärastatud meilide loomiseks täiendavalt eksportida väljad **Eesnimi**, **Perekonnanimi**, **Linn**, **Maakond** ja **Riik/regioon**. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida. Marketosse saate eksportida kuni miljon kliendiprofiili.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Väljade ja segmentide valimine Marketosse eksportimiseks":::

1. Valige **Salvesta**.

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab). Marketos leiate nüüd oma segmendid jaotisest [Marketo loendid](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Teadaolevad piirangud

- Marketosse saab eksportida korraga kuni miljon profiili.
- Marketosse saab eksportida ainult segmente.
- Miljoni profiiliga segmentide eksportimine võib kesta kuni kolm tundi. 
- Marketosse eksporditavate profiilide arv sõltub Marketoga sõlmitud lepingust.

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Marketosse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Marketo täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
