---
title: Segmentide eksportimine Mailchimpi (eelversioon)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Mailchimpi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 54aec10e24b6356e2e4317cf33e740a1a086a2dd
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196849"
---
# <a name="export-segments-to-mailchimp-preview"></a>Segmentide eksportimine Mailchimpi (eelversioon)

Eksportige koondatud kliendiprofiilide segmendid MailChimpi, et luua teabelehti ja meilikampaaniad.

## <a name="prerequisites"></a>eeltingimused

- [Mailchimpi konto](https://mailchimp.com/) ja vastavad administraatori mandaadid.
- [Olemasolevad vaatajaskonnad Mailchimpis](https://mailchimp.com/help/create-audience/) ja vastavad [vaatajaskonna ID-d](https://mailchimp.com/help/find-audience-id/).
- [Konfigureeritud segmendid](segments.md).
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 1 miljon kliendiprofiili ekspordi kohta Mailchimpi, mis võib võtta kuni kolm tundi. Kliendiprofiilide arv, mida saate Mailchimpi eksportida, sõltub teie lepingust Mailchimpiga.
- Ainult segmendid.

## <a name="set-up-connection-to-mailchimp"></a>Ühenduse loomine Mailchimpiga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Mailchimp**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Autentimine Mailchimpiga** ja sisestage oma Mailchimpi identimisteave.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus Mailchimp jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Sisestage oma **Mailchimpi vaatajaskonna ID**.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi.

1. Soovi korral eksportige **eesnimi** ja **perekonnanimi**, et luua isikupärasemaid e-kirju. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
