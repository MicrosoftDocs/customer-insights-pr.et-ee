---
title: Segmentide eksportimine Sendinblue (eelversioon)
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724889"
---
# <a name="export-segments-to-sendinblue-preview"></a>Segmentide eksportimine Sendinblue (eelversioon)

Kampaaniate loomiseks, e-posti teel turundamiseks ja konkreetsete klientide rühmade kasutamiseks saate eksportida ühtsete kliendiprofiilide segmente Sendinblue.

## <a name="prerequisites"></a>eeltingimused

- Sendinblue [konto](https://www.sendinblue.com/) ja vastavad administraatori mandaadid.
- SendinBlue [API võti](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Sendinblue olemasolevad loendid ja vastavad ID-d.
- [Konfigureeritud segmendid](segments.md).
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Privaatset linki koos teenusega Bring your own storage (BYOS) ei toetata.
- Kuni 1 miljon kliendiprofiili ekspordi kohta Sendinblue’sse, mille täitmine võib võtta kuni 90 minutit. Sendinblue’sse eksporditavate kliendiprofiilide arv sõltub teie lepingust Sendinblue’ga.
- Ainult segmendid.

## <a name="set-up-connection-to-sendinblue"></a>Sendinblue ühenduse häälestamine

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige Lisa **ühendus ja valige** Sendinblue **·**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma **SendinBlue API võti**.

1. [Vaadake üle andmete privaatsus ja nõuetele vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport.**

1. Valige **Ühendus ekspordiks** väljal soovitud ühendus Sendinblue jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Sisestage oma **Sendinblue loendi ID**.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi.

1. Soovi korral eksportige **eesnimi**, **perekonnanimi** ja **telefon**, et luua isikupärasemaid meilisõnumeid. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
