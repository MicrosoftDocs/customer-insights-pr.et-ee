---
title: Segmentide eksportimine Braze'i (eelvaade)
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Braze'i.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 84dc7f13f30e0334d431fe5b5866c7f87e82ab27
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195102"
---
# <a name="export-segments-to-braze-preview"></a>Segmentide eksportimine Braze'i (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid Braze'i ja kasutage neid turundustegevusteks.

## <a name="prerequisites"></a>eeltingimused

- [Braze'i konto](https://www.braze.com/) ja vastavad administraatori mandaadid.
- [Braze API võti](https://www.braze.com/docs/api/basics/)
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide ühtsed kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi ja Braze'i kliendi ID-d.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Braze'ile kuni 1 miljon kliendiprofiili, mille täitmine võib võtta kuni 40 minutit. Kliendiprofiilide arv, mida saate Braze'i eksportida, sõltub teie lepingust Braze'iga.
- Ainult segmendid.

## <a name="set-up-connection-to-braze"></a>Braze'iga ühenduse loomine

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Braze**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisselogimise jätkamiseks esitage oma Braze API võti.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige väljal **Ekspordiühendus** jaotisest Braze ühendus. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Valige väljal **Kliendi ID** väli, mis tähistab kliendi Braze'i ID-d. Braze'i segmendid luuakse segmendi sama nimega nagu Dynamics 365 Customer Insights. Andmete vastendamiseks saate valida rohkem valikulisi välju.

1. Valige olemid või segmendid, mida soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
