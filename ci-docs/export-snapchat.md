---
title: Segmentide eksportimine Snapchati (eelversioon)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Snapchati.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195377"
---
# <a name="export-segments-to-snapchat-preview"></a>Segmentide eksportimine Snapchati (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente Snapchati ja kasutada neid turundustegevuste jaoks.

## <a name="prerequisites"></a>eeltingimused

- [Snapchati ettevõtte konto](https://business.snapchat.com/), [Snapchati reklaamikonto](https://ads.snapchat.com/) ja vastavad administraatori mandaadid. Peate olema vähemalt organisatsioonikonto liige ja konkreetse reklaamikonto andmehaldur.
- Vähemalt üks vaatajaskond Snapchati vaatajaskonna halduris tüüpi SAM (Snap Audience Match).
- Snapchati [segmendi / vaatajaskonna ID](https://businesshelp.snapchat.com/s/article/custom-audiences). Vaatajaskonna ID leiate URL-ist pärast vaatajaskonna valimist Snapchati vaatajaskonna halduris.
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 1 miljon kliendiprofiili, mille täitmine võib võtta kuni 15 minutit.
- Ainult segmendid.

## <a name="set-up-connection-to-snapchat"></a>Ühenduse loomine Snapchatiga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Snapchat**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Autentimine Snapchatiga** ja sisestage oma administraatori mandaadid Snapchati jaoks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus Snapchat jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Sisestage Snapchati **segmendi / vaatajaskonna ID**.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
