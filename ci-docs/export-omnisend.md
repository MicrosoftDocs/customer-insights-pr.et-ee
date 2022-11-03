---
title: Segmentide eksportimine Omnisendi (eelversioon)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Omnisendi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fb57e2bd70592f4ce4e1a13e21901dc69734f6bf
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725165"
---
# <a name="export-segments-to-omnisend-preview"></a>Segmentide eksportimine Omnisendi (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente Omnisendi ja kasutada neid turundustegevuste jaoks.

## <a name="prerequisites"></a>eeltingimused

- Omnisendi [konto](https://www.omnisend.com/) ja vastavad administraatori mandaadid.
- Omnisend [API võti](https://support.omnisend.com/en/articles/1061890-generating-api-key).
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Privaatset linki koos teenusega Bring your own storage (BYOS) ei toetata.
- Kuni 1 miljon kliendiprofiili ekspordi kohta Omnisendisse, mille täitmine võib võtta kuni neli tundi. Kliendiprofiilide arv, mida saate Omnisend'i eksportida, sõltub teie Omnisend lepingust.
- Ainult segmendid.

## <a name="set-up-connection-to-omnisend"></a>Ühenduse loomine Omnisendiga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Omnisend**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma Omnisend API võti.

1. [Vaadake üle andmete privaatsus ja nõuetele vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport.**

1. Valige **Ekspordiühendus** väljal ühendus Omnisend jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi.

1. Soovi korral eksportige **eesnimi**, perekonnanimi **, aadress**, riik/regioon **, osariik**, linn **ja** sihtnumber **,** **·** **et** luua isikupärasemaid meilisõnumeid. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
