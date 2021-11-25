---
title: Ettevõtte andmete täiustamine
description: Rikastage ja normaliseerige ettevõtte andmeid Microsofti mudelitega.
ms.date: 11/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9bfb96d47de4ec98325e644c60752fc7cab2706c
ms.sourcegitcommit: 6efcba688d1db1a5d6343c229f292a26c48fc007
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/05/2021
ms.locfileid: "7770165"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Ettevõtte profiilide rikastamine täiustatud ettevõtte andmetega

Microsofti mudelite ja kompileeritud ettevõtteandmete abil saate oma ettevõtte profiile parandada, täiendada ja standardiseerida. Parema täpsuse ja ülevaate saamiseks kasutame [vormingut Common Data](/common-data-model/schema/core/applicationcommon/account) Model.

## <a name="how-we-enhance-company-data"></a>Kuidas me ettevõtte andmeid täiustame

Meie mudel läbib kaheastmelise protsessi ettevõtte profiili täiustamiseks. Esiteks normaliseerib see ettevõtte nime. Näiteks *Microsoft Corp* parandatakse ja standarditakse *Microsoft Corporationiks*. See proovib leida vastet Microsofti kompileeritud ettevõtte andmetes. Kui leitakse vaste, rikastame ettevõtte profiili meie koostatud ettevõtte andmetest saadud teabega, sealhulgas ettevõtte nimega.


### <a name="example"></a>Näide

Teie ettevõtte teave ei pruugi järgida standardvormingut ja sisaldada õigekirjavigu. Mudel proovib neid probleeme lahendada ja luua järjepidevat teavet.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Piirangud

Täiustatud andmetega on mõned piirangud. Mudel ei toeta alloleva loendi üksusi.

1.  Kinnitage ettevõtte identiteet. Me ei kontrolli, kas sisend on olemasolev organisatsioon või et ettevõte kasutab väljundit standardnimena.
2.  Hõlmab igakülgselt ettevõtteid kogu maailmas. Microsofti koostatud ettevõtte andmetel on globaalne katvus, kuid see pakub enamikku leviala austraalias, Kanadas, Ühendkuningriigis ja Ameerika Ühendriikides.
3.  Tagada andmete täpsus või värskus. Kuna äriteave muutub sageli, ei saa me garanteerida, et esitatud täiustatud ettevõtte andmed on alati täpsed või ajakohased.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage **Andmed** > **Rikastamine**.

1. Valige **·** Paanil Täiustatud ettevõtte andmed käsk Rikasta minu **·** andmeid.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Rikastamisplaat rikastamiskeskuses ettevõtte andmete jaoks.":::

1. Valige **Kliendi andmekogum** ja klõpsake olemit, mis sisaldab aadresse, mida soovite rikastada. Saate valida olemi *Klient*, et rikastada aadresse kõigis oma kliendiprofiilides, või valida segmendi olemi aadresside rikastamiseks ainult selles segmendis sisalduvates kliendiprofiilides.

1. Valige, millist tüüpi välju tuleks teie ettevõtteprofiilidest kasutada Microsofti kompileeritud ettevõtteandmetega võrdlemiseks. See valik mõjutab kaardistamisvälju, millele teil on järgmises etapis juurdepääs.

1.  Vastendage ettevõtte väljad ühendatud kliendiolemist. Mida rohkem võtmeidentifikaatoreid ja välju kaardistate, seda tõenäolisem on suurem vastendamise määr.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Andmete vastendamise etapp ettevõtte rikastamise konfigureerimisel.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Sisestage rikastamise nimi ja väljundolemi nimi.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

## <a name="enrichment-results"></a>Rikastamise tulemused

Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**. Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab). Töötlemisaeg sõltub teie kliendiandmete mahust.

Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt. Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.

Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.

## <a name="next-steps"></a>Järgmised etapid

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
