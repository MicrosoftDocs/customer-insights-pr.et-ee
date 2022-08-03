---
title: Segmentide eksportimine iterable'i (eelvaade)
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Iterable'i.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ccf10b6e3a28a75f9d1bd3d8da3bf870ebc2b1b2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195424"
---
# <a name="export-segments-to-iterable-preview"></a>Segmentide eksportimine iterable'i (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid Iterable'i ja kasutage neid turundustegevustes.

## <a name="prerequisites"></a>eeltingimused

- Iterable [konto](https://iterable.com/) ja vastavad administraatori mandaadid.
- Iterable [API võti](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Iterable'ile kuni 1 miljon kliendiprofiili, mille täitmine võib võtta kuni 30 minutit. Kliendiprofiilide arv, mida saate Iterable'i eksportida, sõltub teie lepingust Iterable'iga.
- Ainult segmendid.

## <a name="set-up-connection-to-iterable"></a>Ühenduse seadistamine iterable'iga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Add connection (Lisa ühendus)** ja valige **Iterable (Iterable)**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisselogimise jätkamiseks esitage oma Iterable API võti.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige väljal **Ühendus ekspordiks** jaotisest Iterable ühendus. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Iterable'is loodud loend saab täpselt sama nime, mis teie segmendi nimi Dynamics 365 Customer Insights rakenduses.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
