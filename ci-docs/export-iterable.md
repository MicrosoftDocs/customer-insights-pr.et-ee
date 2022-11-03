---
title: Segmentide eksportimine iterable’i (eelvaade)
description: Vaadake, kuidas konfigureerida ühendust ja eksportida rakendusse Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 69e2bd207c98fc2530620018bf95dd869d1798f6
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724477"
---
# <a name="export-segments-to-iterable-preview"></a>Segmentide eksportimine iterable’i (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid Iterable’i ja kasutage neid turundustegevusteks.

## <a name="prerequisites"></a>eeltingimused

- Iterable [konto](https://iterable.com/) ja vastavad administraatori mandaadid.
- [Korduvkasutatav API-võti](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Privaatset linki koos teenusega Bring your own storage (BYOS) ei toetata.
- Iterable’ile kuni 1 miljon kliendiprofiili, mille täitmine võib võtta kuni 30 minutit. Iterable’i eksportitavate kliendiprofiilide arv sõltub teie lepingust Iterable’iga.
- Ainult segmendid.

## <a name="set-up-connection-to-iterable"></a>Iterable’iga ühenduse loomine

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige Lisa **ühendus** ja valige **Iterable**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisselogimise jätkamiseks sisestage oma iterable API-võti.

1. [Vaadake üle andmete privaatsus ja nõuetele vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport.**

1. **Valige väljal Ekspordiühendus** ühendus jaotisest Iterable. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Iterable’is loodud loend saab täpselt sama nime, mis teie segmendi nimi .Dynamics 365 Customer Insights

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
