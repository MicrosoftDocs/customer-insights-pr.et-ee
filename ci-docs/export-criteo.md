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
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760021"
---
# <a name="export-segments-to-criteo-preview"></a>Segmentide eksportimine Criteosse (eelvaade)

Eksportige ühtsete kliendiprofiilide segmente, et luua kampaaniaid, pakkuda e-posti turundust ja kasutada Criteo abil konkreetseid kliendirühmi.

## <a name="prerequisites"></a>eeltingimused

- Criteo [Dynamicsi uuesti sihtimise konto](https://www.criteo.com/login/) ja vastavad administraatori mandaadid.
- [Konfigureeritud segmendid](segments.md).
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 1 miljon kliendiprofiili ekspordi kohta Criteosse, mille täitmine võib võtta kuni 30 minutit. Kliendiprofiilide arv, mida saate Criteosse eksportida, sõltub teie lepingust Criteoga.
- Ainult segmendid.

## <a name="set-up-connection-to-criteo"></a>Seadistage ühendus Criteoga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Criteo**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Vaadake üle andmete privaatsus ja nõuetele vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda** .

1. Valige **Autenti Criteoga** ja sisestage oma administraatori kasutajanimi ja mandaadid Criteo jaoks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport.**

1. **Valige väljal Ekspordiühendus** ühendus jaotisest Criteo. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
