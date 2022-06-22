---
title: Ettevõtte andmete täiustamine
description: Rikastage ja normaliseerige ettevõtte andmeid Microsofti mudelitega.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4247d59806468907d93fc7848231ec5a2985580e
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953944"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Ettevõtte profiilide rikastamine ettevõtte täiustatud andmetega

Ettevõtte profiilide parandamiseks, täiendamiseks ja standardimiseks kasutage Microsofti mudeleid ja kogutud ettevõtte andmeid. Parema täpsuse ja ülevaate saamiseks kasutame [common data model'i vormingut](/common-data-model/schema/core/applicationcommon/account).

Samuti [saate täiustada ettevõtte andmeid andmeallikate](data-sources-enrichment.md) kohta, et parandada andmete ühendamise protsessi vaste täpsust.

Ameerika Ühendriikide avalik-õiguslike ettevõtete jaoks on saadaval teave, nagu tulud, varude märgistaja, tööstus ja palju muud.  

## <a name="how-we-enhance-company-data"></a>Kuidas me ettevõtte andmeid täiustame?

Meie mudel läbib kaheastmelise protsessi ettevõtte profiili parandamiseks. Esiteks normaliseerib see ettevõtte nime. Näiteks *Microsoft Corp* parandatakse ja standardiseeritakse Microsoft *Corporationile*. See püüab leida vastet Microsofti koostatud ettevõtte andmetest. Kui leitakse vaste, rikastame ettevõtte profiili teabega, mis on saadud meie ettevõtte kogutud andmetest, sealhulgas ettevõtte nimest.

### <a name="example"></a>Näide

Teie ettevõtte teave ei pruugi järgida standardiseeritud vormingut ja sisaldada õigekirjavigu. Mudel püüab neid probleeme lahendada ja luua järjepidevat teavet.

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

Mudel ei ole:

- Kinnitage ettevõtte isik. Me ei kontrolli, kas sisend on olemasolev organisatsioon või et ettevõte kasutab väljundit oma standardnimena.
- Hõlmab põhjalikult ettevõtteid kogu maailmas. Microsofti kogutud ettevõtte andmed on ülemaailmse katvusega, kuid pakuvad kõige rohkem katvust Austraalias, Kanadas, Ühendkuningriigis ja Ameerika Ühendriikides.
- Standardige ettevõtte aadressid kogu maailmas. Praegu toetame aadresside standardimist nendes riikides või piirkondades: Austraalias, Kanadas, Prantsusmaal, Saksamaal, Itaalias, Jaapanis, Ühendkuningriigis ja Ameerika Ühendriikides.
- Tagada andmete täpsus või värskus. Kuna äriteave muutub sageli, ei saa me tagada, et esitatud täiustatud ettevõtte andmed on alati täpsed või ajakohased.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **Täiustatud ettevõtte andmepaanil** Täiustatud ettevõtte andmete **suvand Rikasta minu andmeid**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Rikastamisplaat ettevõtte andmete rikastamiskeskuses.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. **Valige kliendi andmestik** ja valige profiil või segment, mida soovite rikastada. Olem *Klient* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

1. Valige, millist tüüpi välju teie ettevõtte profiilidest kasutada Microsofti koostatud ettevõtte andmetega sobitamiseks. See valik mõjutab kaardistamisvälju, millele teil on järgmises etapis juurdepääs.

1. Tehke valik **Edasi**.

1. Vastendage oma ettevõtte väljad Microsofti ettevõtte andmetega. Suurema vaste täpsuse tagamiseks lisage rohkem välju.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Andmete vastendamise etapp ettevõtte rikastamise konfigureerimisel.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. **Sisestage rikastamise ja** olemi **Väljund nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Rikastamisprotsessi alustamiseks või lehele Rikastamine naasmise **lähedal** valige **Käivita**.

## <a name="enrichment-results"></a>Rikastamise tulemused

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

### <a name="overview-card"></a>Ülevaatekaart

Kliendimuudatuste **ülevaatepaanil** kuvatakse üksikasjad rikastamise katvuse kohta

- **Ettevõtted, mida töödeldi ja muudeti**: edukalt rikastatud kliendiettevõtte profiilide arv.
- **Töödeldud ja muutmata** ettevõtted: kliendiettevõtte profiilide arv, mida on tuvastatud, kuid mida ei muudetud. See juhtub tavaliselt siis, kui sisendandmed on kehtivad ja rikastamine ei saa neid parandada.
- **Ettevõtted, mida pole töödeldud ja mida pole muudetud**: kliendiettevõtte profiilide arv, mida ei tuvastatud. See juhtub tavaliselt sisendandmete puhul, mis on kehtetud või rikastamine seda ei toeta.

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
