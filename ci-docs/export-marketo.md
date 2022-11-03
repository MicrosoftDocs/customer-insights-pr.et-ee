---
title: Segmentide eksportimine platvormile Marketo (eelversioon)
description: Lugege, kuidas konfigureerida ühendust ja eksportida platvormile Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724935"
---
# <a name="export-segments-to-marketo-preview"></a>Segmentide eksportimine platvormile Marketo (eelversioon)

Eksportige Marketo abil koondatud kliendiprofiilide segmente kampaaniate loomiseks, meiliturunduse pakkumiseks ja konkreetsete kliendirühmade kasutamiseks.

## <a name="prerequisites"></a>eeltingimused

- Marketo [konto](https://login.marketo.com/) ja vastavad administraatori mandaadid.
- Marketo [kliendi ID, kliendi saladus ja REST lõpp-punkti hostinimi](https://developers.marketo.com/rest-api/authentication/).
- [Marketos](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) olemasolevad nimekirjad ja vastavad ID-d.
- [Konfigureeritud segmendid](segments.md).
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Privaatset linki koos teenusega Bring your own storage (BYOS) ei toetata.
- Kuni 1 miljon kliendiprofiili Marketosse eksportimise kohta, mis võib võtta kuni 3 tundi. Kliendiprofiilide arv, mida saate Marketosse eksportida, sõltub teie lepingust Marketoga.
- Ainult segmendid.

## <a name="set-up-connection-to-marketo"></a>Ühenduse loomine platvormiga Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Marketo**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma **Marketo kliendi ID, kliendi saladus ja REST Endpoint hostinimi**. REST lõpp-punkti hostinimi on ainult hostinimi ilma https://. Näide: xyz-abc-123.mktorest.com.

1. [Vaadake üle andmete privaatsus ja nõuetele vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport.**

1. Valige **Ekspordiühendus** väljal ühendus Marketo jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Sisestage oma **Marketo loendi ID.** Loendi ID on lihtsalt arvväärtus. Näiteks kui teie Marketo loendi ID on ST12345A7, eemaldage märk enne ja pärast numbreid ning sisestage *12345*.

1. **Valige jaotises Andmete vastendamine** vähemalt üks väli, mis tähistab kliendi meiliaadressi või kliendi Marketo ID-d.

1. Soovi korral eksportige **eesnimi**, perekonnanimi **, linn**, **osariik** ja **riik/regioon**, **et** luua isikupärasemaid meilisõnumeid. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Marketos leidke oma segmendid Marketo loendite [alt](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
