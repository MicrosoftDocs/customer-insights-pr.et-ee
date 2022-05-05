---
title: Customer Insightsi andmete eksportimine Google Adsi
description: Lugege, kuidas konfigureerida ühendust ja eksportida Google Adsi.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3e0eb91be97d69a999e90708d29c572f0055527e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642684"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmentide eksportimine Google Adsi (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid Google Ads vaatajaskonna loendisse ja kasutage neid Google'i otsingus, Gmailis, YouTube ja Google Display Network'is reklaamimiseks. 


## <a name="prerequisites-for-connection"></a>Ühenduse eeltingimus

-   Teil on [Google Adsi konto](https://ads.google.com/) ja asjakohane administraatori identimisteave.
-   Te täidate [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717) nõuded.
-   Te täidate [uuesti turundamise loendi suurused](https://support.google.com/google-ads/answer/7558048) nõudeid.
-   Te olete [konfigureerinud segmendid](segments.md).
-   Eksporditud segmentide ühtsed kliendiprofiilid sisaldavad välju, mis tähistavad meiliaadressi, telefoni, mobiilireklaami ID-d, kolmanda osapoole kasutaja ID-d või aadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Google Adsi saab eksportida ainult segmente.
- Segmentide eksportimine kokku 1 miljoni kliendiprofiiliga võib teenusepakkujapoolsete piirangute tõttu võtta kuni 30 minutit. 
- Google Adsis võib vastavusseviimine võtta kuni 48 tundi.

## <a name="set-up-connection-to-google-ads"></a>Ühenduse Google Ads loomine

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Google Ads** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma **[Google Adsi kliendi-ID](https://support.google.com/google-ads/answer/1704344)**.

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Autentimine Google Adsiga** ja sisestage oma Google Adsi identimisteave.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**. 

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus Google Ads jaotisest. Kui te seda jaotise nime ei näe, pole seda tüüpi ühendused teile saadaval.

1. Kui soovite luua uue vaatajaskonna, jätke Google'i vaatajaskonna ID tühjaks. Loome teie Google Adsi kontol automaatselt uue vaatajaskonna ja kasutame eksporditud segmendi nime. Kui soovite värskendada olemasolevat Google Adsi vaatajaskonda, sisestage oma [Google Adsi vaatajaskonna ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. **Valige jaotises Andmete sobitamine** eksportimiseks üks või mitu andmevälja ja valige väli, mis esindab Customer Insightsi vastavaid andmevälju.

1. Valige segmendid, mille soovite eksportida. 

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). 

Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Google Adsi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Google Ads täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE [footer-include](includes/footer-banner.md)]
