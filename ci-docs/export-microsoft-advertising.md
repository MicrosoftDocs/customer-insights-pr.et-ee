---
title: Segmentide eksportimine Microsoft Advertisingusse (eelvaade)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Microsoft Advertisingusse.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196527"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Segmentide eksportimine Microsoft Advertisingusse (eelvaade)

Customer Insights segmentide eksportimine Microsoft Advertisingusse, et luua kliendisobivuse sihtrühmad. Kasutage neid vaatajaskondi oma reklaamikampaaniate jaoks.

## <a name="prerequisites"></a>eeltingimused

- [Microsofti reklaamikonto](https://ads.microsoft.com/) ja vastav administraatori identimisteave.
- Microsofti reklaamikliendi ID ja konto ID. Leidke kliendi ID (`cid`) ja konto ID (`aid`) URL-i parameetritest, kui olete teenusesse Microsoft Advertising sisse logitud.
- Kliendivaste kasutustingimused on aktsepteeritud.
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 500 000 kliendiprofiili ekspordi kohta Microsoft Advertisingisse, mis võib võtta kuni 10 minutit.
- Ainult segmendid.

## <a name="set-up-connection-to-microsoft-advertising"></a>Teenusega Microsoft Advertising ühenduse loomine

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Microsoft Advertising**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage **Microsofti reklaamikliendi ID**.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Autentimine Microsoft Advertisinguga** ja sisestage oma administraatori mandaadid Microsoft Advertisingu jaoks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus Microsoft Advertisingu jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige eksportimiseks segmendid. Microsoft Advertisingi kliendisobituse sihtrühmad luuakse automaatselt ekspordiks valitud segmentide nimega. Iga segmendi tulemuseks on eraldi kliendisobitatud sihtrühm.

1. Sisestage oma **Microsofti Advertising Customer ID ja Account ID**.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, kliendi meiliaadressiga väli.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
