---
title: Segmentide eksportimine SendGrid (eelversioon)
description: Lugege, kuidas konfigureerida ühendust ja eksportida SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 855e77055eeb24a2c6cff0d45cd23edf93cc0581
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724843"
---
# <a name="export-segments-to-sendgrid-preview"></a>Segmentide eksportimine SendGrid (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente SendGridi kontaktiloenditesse ja kasutada neid SendGridis kampaaniate ja meiliturunduste jaoks.

## <a name="prerequisites"></a>eeltingimused

- SendGridi [konto](https://sendgrid.com/) ja vastavad administraatori identimisteabed.
- [Olemasolevad kontaktiloendid SendGridis](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) ja vastavad ID-d.
- [SendGrid API võti](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Privaatset linki koos teenusega Bring your own storage (BYOS) ei toetata.
- Kokku kuni 100 000 kliendiprofiili SendGridile, mille täitmine võib võtta kuni paar tundi. Kliendiprofiilide arv, mida saate SendGridi eksportida, sõltub teie lepingust SendGridiga.
- Ainult segmendid.

## <a name="set-up-connection-to-sendgrid"></a>Ühenduse loomine SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **SendGrid**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma **SendGrid API võti**.

1. [Vaadake üle andmete privaatsus ja nõuetele vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport.**

1. Valige **Ekspordiühendus** väljal ühendus SendGrid jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Sisestage oma **SendGridi loendi ID.**

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi.

1. Soovi korral valige väljad nagu **eesnimi, perekonnanimi**, Riik/regioon **, Osariik**, **·** **Linn** **ja** Sihtnumber.**·**

1. Valige segmendid, mida soovite teadaolevate piirangute järgi eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
