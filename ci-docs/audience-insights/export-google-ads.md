---
title: Customer Insightsi andmete eksportimine Google Adsi
description: Vaadake, kuidas konfigureerida ühendust Google Adsiga.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268957"
---
# <a name="connector-for-google-ads-preview"></a>Google Adsi konnektor (eelversioon)

Eksportige koondatud kliendiprofiilide segmendid Google Adsi vaatajaskonna loendisse ning kasutage neid, et näidata reklaame Google'i otsingus, Gmailis, YouTube'is ja Google'i Display-võrgustikus. 

## <a name="prerequisites"></a>Eeltingimused

-   Teil on [Google Adsi konto](https://ads.google.com/) ja asjakohane administraatori identimisteave.
-   Google Adsis on olemas vaatajaskonnad ja asjakohased ID-d. Lisateavet leiate teemast [Google Adsi vaatajaskonnad](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Te olete [konfigureerinud segmendid](segments.md)
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välju, mis tähistavad meiliaadressi, eesnime ja perekonnanime

## <a name="connect-to-google-ads"></a>Google Adsiga ühenduse loomine

1. Avage **Haldus** > **Ekspordi sihtkohad**.

1. Valige jaotises **Google Ads** suvand **Seadista**.

1. Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.

1. Sisestage oma **[Google Adsi kliendi-ID](https://support.google.com/google-ads/answer/1704344)**.

1. Sisestage oma **[Google Adsi kinnitatud arendajatunnus](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Sisestage oma **[Google Adsi vaatajaskonna ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ja valige **Ühenda**, et käivitada ühendus Google Adsiga.

1. Valige **Autentimine Google Adsiga** ja sisestage oma Google Adsi identimisteave.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Google Adsi ühenduse ekspordi kuvatõmmis":::

1. Ekspordi konfigureerimiseks valige **Edasi**.

## <a name="configure-the-connector"></a>Konnektori konfigureerimine

1. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. Korrake samu samme väljade **Eesnimi** ja **Perekonnanimi** korral.

1. Valige segmendid, mille soovite eksportida. Google Adsi saate eksportida kuni miljon kliendiprofiili.

1. Valige **Salvesta**.

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab). Google Adsis leiate nüüd oma segmendid jaotisest [Google Adsi vaatajaskonnad](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Teadaolevad piirangud

- Google Adsi saab eksportida korraga kuni miljon profiili.
- Google Adsi saab eksportida ainult segmente.
- Miljoni profiiliga segmentide eksportimiseks võib teenusepakkuja tõttu kuluda kuni viis minutit. 
- Google Adsis võib vastavusseviimine võtta kuni 48 tundi.

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Google Adsi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Google Ads täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]