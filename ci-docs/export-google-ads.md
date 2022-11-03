---
title: Segmentide eksportimine Google Adsi (eelvaade)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Google Adsi.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725073"
---
# <a name="export-segments-to-google-ads-preview"></a>Segmentide eksportimine Google Adsi (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid Google Ads vaatajaskonna loendisse ja kasutage neid Google'i otsingus, Gmailis, YouTube ja Google Display Network'is reklaamimiseks.

## <a name="prerequisites"></a>eeltingimused

- [Google Adsi konto](https://ads.google.com/) ja vastavad administraatori mandaadid.
- Google [Adsi kliendi ID](https://support.google.com/google-ads/answer/1704344).
- Kliendi vaste poliitika [nõuded](https://support.google.com/adspolicy/answer/6299717) on täidetud.
- Uuesti turundamise loendi suuruste [nõuded](https://support.google.com/google-ads/answer/7558048) on täidetud.
- [Konfigureeritud segmendid](segments.md).
- Eksporditud segmentide ühtsed kliendiprofiilid sisaldavad välju, mis tähistavad meiliaadressi, telefoni, mobiilireklaamija ID-d, kolmanda osapoole kasutaja ID-d või aadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Privaatset linki koos teenusega Bring your own storage (BYOS) ei toetata.
- Eksportige Google Adsi kuni 1 miljon kliendiprofiili ekspordi kohta, mille täitmine võib teenusepakkujapoolsete piirangute tõttu võtta kuni 30 minutit.
- Ainult segmendid.
- Google Adsis vastendamine võib võtta kuni 48 tundi.

## <a name="set-up-connection-to-google-ads"></a>Ühenduse Google Ads loomine

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Tehke valik **Lisa ühendus** ja valige **Google Ads**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma Google Adsi kliendi ID.

1. [Vaadake üle andmete privaatsus ja nõuetele vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Valige **Autentimine Google Adsiga** ja sisestage oma Google Adsi identimisteave.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport.**

1. Valige **Ekspordiühendus** väljal ühendus Google Ads jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige, kas kasutada olemasolevat vaatajaskonda või luua uus.
   - Google Adsi olemasoleva vaatajaskonna värskendamiseks sisestage oma [Google Adsi vaatajaskonna ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Uue vaatajaskonna loomiseks jätke väli Google’i vaatajaskonna ID tühjaks. Customer Insights loob teie Google Adsi kontol automaatselt uue vaatajaskonna ja kasutab eksporditud segmendi nime.

1. **Valige jaotises Andmete vastendamine** üks või mitu eksporditavat andmevälja ja valige väli, mis esindab Customer Insightsi vastavaid andmevälju.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
