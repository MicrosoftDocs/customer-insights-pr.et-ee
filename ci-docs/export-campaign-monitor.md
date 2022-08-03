---
title: Segmentide eksportimine Campaign Monitori (eelversioon)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Campaign Monitori.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196297"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Segmentide eksportimine Campaign Monitori (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente Campaign Monitori ja kasutada neid turundustegevuste jaoks.

## <a name="prerequisites"></a>eeltingimused

- Kampaaniamonitori [konto](https://www.campaignmonitor.com/) ja vastav administraatori identimisteave.
- [Kampaaniamonitori loendi ID](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Kampaaniamonitori [konto seadetest](https://www.campaignmonitor.com/api/getting-started/)**loodud API-võti** API loendi ID hankimiseks.
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 1 miljon kliendiprofiili ühe ekspordi kohta kampaaniamonitori, mille täitmine võib võtta kuni 20 minutit. Kliendiprofiilide arv, mida saate kampaaniamonitorisse eksportida, sõltub teie lepingust kampaaniamonitoriga.
- Ainult segmendid.

## <a name="set-up-connection-to-campaign-monitor"></a>Campaign Monitoriga ühenduse loomine

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Kampaaniamonitor**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Valige **Ühenda** Campaign Monitoriga ühenduse lähtestamiseks.

1. Valige **Autentimine Campaign Monitoriga** ja sisestage oma administraatori mandaadid Campaign Monitori jaoks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus Campaign Monitori jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Sisestage oma **kampaaniamonitoride loendi ID**.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Segmentide eksportimine Campaign Monitori on vajalik.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
