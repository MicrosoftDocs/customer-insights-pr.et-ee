---
title: Aadressi täiustamise rikastamine (sisaldab videot)
description: Rikastage ja normaliseerige kliendiprofiilide aadressiteavet Microsofti mudelitega.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: f6279b9bb721d99d66f73e8dc839a92f1ad90140
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953806"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Kliendiprofiilide rikastamine täiustatud aadressidega

Teie andmetes kuvatud aadressid võivad olla struktureerimata, mittetäielikud või valed. Kasutage Microsofti mudeleid aadresside normaliseerimiseks ja rikastamiseks [Common Data Model vormingusse,](/common-data-model/schema/core/applicationcommon/address) et saada paremat täpsust ja ülevaadet.

Samuti [saate rikastada andmeallikate](data-sources-enrichment.md) aadresse, et parandada vaste täpsust andmete ühendamise protsessis. 

## <a name="how-we-enhance-addresses"></a>Kuidas me aadresse täiustame

Meie mudel läbib aadressi täiustamiseks kaheastmelise protsessi. Esiteks sõelub see aadressi oma komponentide tuvastamiseks ja paneb need struktureeritud vormingusse. Seejärel kasutame AI-d aadressi väärtuste parandamiseks, lõpuleviimiseks ja standardismiseks.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Näide

Aadressiteave võib olla ebastandartses vormingus ja sisaldada õigekirjavigu. Mudel saab need probleemid lahendada ja luua ühtsetes kliendiprofiilides järjepidevaid aadresse.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Piirangud

Täiustatud aadressid töötavad ainult väärtustega, mis on teie allaneelatud aadressiandmetes juba olemas. Mudel ei ole:

1. Kontrollige, kas aadress on kehtiv aadress.
2. Kontrollige, kas mõni väärtustest (nt sihtnumbrid või tänavanimed) on kehtiv.
3. Muutke väärtusi, mida ta ei tunne.

Mudel kasutab aadresside täiustamiseks masinõppel põhinevaid tehnikaid. Nagu iga masinõppel põhineva mudeli puhul, ei ole 100-protsendiline täpsus tagatud.

## <a name="supported-countries-or-regions"></a>Toetatud riikides või regioonides

Praegu toetame aadresside rikastamist nendes riikides või piirkondades:

- Austraalia
- Kanada
- Prantsusmaa
- Saksamaa
- Itaalia
- Jaapan
- Suurbritannia
- Ameerika Ühendriigid

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **Rikasta minu andmeid** paanil **Täiustatud aadressid** .

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Paani Täiustatud aadressid kuvatõmmis.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. **Valige kliendi andmestik** ja valige profiil või segment, mida soovite rikastada. Olem *Klient* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

1. Valige, kuidas aadresse teie andmekogumis vormindatakse. Valige **Ühe atribuudi aadress** kui teie andmetes kasutatavad aadressid kasutavad ühte välja. Valige **Mitme atribuudi aadress** kui teie andmetes kasutatavad aadressid rohkem kui ühte andmevälja.

1. Valige **Edasi** ja vastendage oma ühtse kliendiolemi aadressiväljad.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Täiustatud aadressivälja vastendamise leht.":::

   > [!NOTE]
   > Riik/piirkond on kohustuslik nii ühe atribuudi kui ka mitme atribuudiga aadressidel. Aadresse, mis ei sisalda kehtivaid või toetatud riigi/regiooni väärtusi, ei rikastata.

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. **Sisestage rikastamise ja** olemi **Väljund nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

## <a name="enrichment-results"></a>Rikastamise tulemused

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Põlluga **rikastatud** klientide arv tagab iga rikastatud välja katvuse süvitsimise.

### <a name="overview-card"></a>Ülevaatekaart

Kliendimuudatuste **ülevaatekaardil** kuvatakse üksikasjad rikastamise katvuse kohta:

- **Töödeldud ja muudetud** aadressid: kliendiprofiilide arv, mille aadressid on edukalt rikastatud.
- **Töödeldud ja muutmata** aadressid: kliendiprofiilide arv aadressidega, mis tuvastati, kuid mida ei muudetud. Tavaliselt juhtub see siis, kui sisendandmed on kehtivad ja rikastamine ei saa neid parandada.
- **Aadressid, mida pole töödeldud ja mida pole muudetud**: profiilide arv aadressidega, mida ei tuvastatud. Tavaliselt sisendandmete puhul, mis on kehtetud või rikastamine seda ei toeta.

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
