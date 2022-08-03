---
title: Segmentide eksportimine Autopilot'isse (eelversioon)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Autopilot'isse.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 449d2c5e32697e4a5d2c9dff4a5a1cbdb26aeb4d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195055"
---
# <a name="export-segments-to-autopilot-preview"></a>Segmentide eksportimine Autopilot'isse (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente Autopiloti kontaktiloenditesse ja kasutada neid Autopilotis kampaaniate ja meiliturunduste jaoks.

## <a name="prerequisites-for-a-connection"></a>Ühenduse eeltingimus

- Autopiloodi [konto](https://www.autopilothq.com/) ja vastavad administraatori mandaadid.
- Autopiloodi [API võti](https://autopilot.docs.apiary.io/#)
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 100 000 kliendiprofiili ühe ekspordi kohta Autopiloodile, mille täitmine võib võtta kuni paar tundi. Kliendiprofiilide arv, mida saate Autopiloodile eksportida, sõltub teie lepingust Autopilotiga.
- Ainult segmendid.

## <a name="set-up-connection-to-autopilot"></a>Ühenduse loomine Autopilot'iga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Autopilot**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma Autopiloti API võti.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus Autopilot jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi.

1. Soovi korral eksportige muid välju, näiteks **eesnimi** ja **perekonnanimi**.

1. Valige segmendid, mida soovite eksportida, järgides teadaolevaid piiranguid.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
