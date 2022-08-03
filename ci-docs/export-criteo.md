---
title: Segmentide eksportimine Criteosse (eelvaade)
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Criteosse.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d7c8d6f0121fe18a6c886ba3776109a1a592ef33
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195331"
---
# <a name="export-segments-to-criteo-preview"></a>Segmentide eksportimine Criteosse (eelvaade)

Eksportige Criteo abil ühtsete kliendiprofiilide segmente kampaaniate loomiseks, e-posti turunduse pakkumiseks ja konkreetsete kliendirühmade kasutamiseks.

## <a name="prerequisites"></a>eeltingimused

- [Criteo Dynamicsi konto](https://www.criteo.com/login/) uuesti sihtimine ja vastavad administraatori mandaadid.
- [Konfigureeritud segmendid](segments.md).
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 1 miljon kliendiprofiili ühe ekspordi kohta Criteosse, mille täitmine võib võtta kuni 30 minutit. Kliendiprofiilide arv, mida saate Criteosse eksportida, sõltub teie lepingust Criteoga.
- Ainult segmendid.

## <a name="set-up-connection-to-criteo"></a>Criteoga ühenduse loomine

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Criteo**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Autentimine Criteoga** ja sisestage oma administraatori kasutajanimi ja Criteo mandaat.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige väljal **Ekspordiühendus** jaotisest Criteo ühendus. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi.

1. Soovi korral eksportige **reklaamija ID** ja **nimi**.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
