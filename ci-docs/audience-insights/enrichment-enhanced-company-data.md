---
title: Ettevõtte andmete täiustamine
description: Rikastage ja normaliseerige ettevõtte andmeid Microsofti mudelitega.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e9cf93f28ba6918c72039670e42d26c8aaa7f922
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376317"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Ettevõtte profiilide rikastamine ettevõtte täiustatud andmetega

Ettevõtte profiilide parandamiseks, täiendamiseks ja standardimiseks kasutage Microsofti mudeleid ja kogutud ettevõtte andmeid. Parema täpsuse ja ülevaate saamiseks kasutame [common data model'i vormingut](/common-data-model/schema/core/applicationcommon/account).

Samuti [saate täiustada ettevõtte andmeid andmeallikate](data-sources-enrichment.md) kohta, et parandada andmete ühendamise protsessi vaste täpsust. 

## <a name="how-we-enhance-company-data"></a>Kuidas me ettevõtte andmeid täiustame?

Meie mudel läbib kaheastmelise protsessi ettevõtte profiili parandamiseks. Esiteks normaliseerib see ettevõtte nime. Näiteks *Microsoft Corp* parandatakse ja standardiseeritakse Microsoft *Corporationile*. See püüab leida vastet Microsofti koostatud ettevõtte andmetest. Kui leitakse vaste, rikastame ettevõtte profiili teabega, mis on saadud meie ettevõtte kogutud andmetest, sealhulgas ettevõtte nimest.


### <a name="example"></a>Näide

Teie ettevõtte teave ei pruugi järgida standardiseeritud vormingut ja sisaldada õigekirjavigu. Mudel proovib neid probleeme lahendada ja luua järjepidevat teavet.

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

Täiustatud andmetel on mõned piirangud. Allolevas loendis olevaid üksusi mudel ei toeta.

1.  Kinnitage ettevõtte isik. Me ei kontrolli, kas sisend on olemasolev organisatsioon või et ettevõte kasutab väljundit oma standardnimena.
2.  Hõlmab põhjalikult ettevõtteid kogu maailmas. Microsofti kogutud ettevõtte andmed on ülemaailmse katvusega, kuid pakuvad kõige rohkem katvust Austraalias, Kanadas, Ühendkuningriigis ja Ameerika Ühendriikides.
3.  Standardige ettevõtte aadressid kogu maailmas. Praegu toetame aadresside standardimist nendes riikides või piirkondades: Austraalias, Kanadas, Prantsusmaal, Saksamaal, Itaalias, Jaapanis, Ühendkuningriigis ja Ameerika Ühendriikides.
4.  Tagada andmete täpsus või värskus. Kuna äriteave muutub sageli, ei saa me tagada, et esitatud täiustatud ettevõtte andmed on alati täpsed või ajakohased.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage **Andmed** > **Rikastamine**.

1. Valige **Täiustatud ettevõtte andmepaanil** Täiustatud ettevõtte andmete **suvand Rikasta minu andmeid**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Rikastamisplaat ettevõtte andmete rikastamiskeskuses.":::

1. Valige **Kliendi andmekogum** ja klõpsake olemit, mis sisaldab aadresse, mida soovite rikastada. Saate valida olemi *Klient*, et rikastada aadresse kõigis oma kliendiprofiilides, või valida segmendi olemi aadresside rikastamiseks ainult selles segmendis sisalduvates kliendiprofiilides.

1. Valige, millist tüüpi välju tuleks ettevõtte profiilidest kasutada Microsofti koostatud ettevõtte andmetega vastavusse viimiseks. See valik mõjutab kaardistamisvälju, millele teil on järgmises etapis juurdepääs.

1.  Vastendage ettevõtte väljad oma ühtse kliendiolemi kaudu. Mida rohkem võtmeidentifikaatoreid ja välju vastendate, seda suurem on tõenäosus, et mängumäär on suurem.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Andmete vastendamise etapp ettevõtte rikastamise konfigureerimisel.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Sisestage rikastamise nimi ja väljundolemi nimi.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

## <a name="enrichment-results"></a>Rikastamise tulemused

Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**. Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab). Töötlemisaeg sõltub teie kliendiandmete mahust.

Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt. Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.

Rikastatud andmete näidist näete paanil **Rikastatud kliendid** eelvaatepaanil. Valige **Kuva rohkem** ja valige **vahekaart Andmed**, et pääseda juurde iga rikastatud profiili üksikasjalikule vaatele.

### <a name="overview-card"></a>Ülevaatekaart

Ülevaatekaardil kuvatakse andmed rikastamise katvuse kohta. 

* **Ettevõtted, mida töödeldi ja muudeti**: edukalt rikastatud kliendiettevõtte profiilide arv.

* **Töödeldud ja muutmata** ettevõtted: kliendiettevõtte profiilide arv, mida on tuvastatud, kuid mida ei muudetud. See juhtub tavaliselt siis, kui sisendandmed on kehtivad ja rikastamine ei saa neid parandada.

* **Ettevõtted, mida pole töödeldud ja mida pole muudetud**: kliendiettevõtte profiilide arv, mida ei tuvastatud. See juhtub tavaliselt sisendandmete puhul, mis on kehtetud või rikastamine seda ei toeta.

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
