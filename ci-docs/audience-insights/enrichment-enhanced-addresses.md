---
title: Aadressi täiustamise rikastamine
description: Rikastage ja normaliseerige kliendiprofiilide aadressiteavet Microsofti mudelitega.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965573"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Kliendiprofiilide rikastamine täiustatud aadressidega

Teie andmetes kuvatud aadressid võivad olla struktureerimata, mittetäielikud või valed. Kasutage Microsofti mudeleid aadresside normaliseerimiseks ja rikastamiseks [Common Data Model vormingusse,](/common-data-model/schema/core/applicationcommon/address) et saada paremat täpsust ja ülevaadet.

## <a name="how-we-enhance-addresses"></a>Kuidas me aadresse täiustame

Meie mudel läbib aadressi täiustamiseks kaheastmelise protsessi. Esiteks sõelub see aadressi oma komponentide tuvastamiseks ja paneb need struktureeritud vormingusse. Seejärel kasutame tehisintellekti aadressi väärtuste parandamiseks, täiendamiseks ja standardimiseks.

### <a name="example"></a>Näide

Aadressiteave võib olla mittestandardses vormingus ja sisaldada õigekirjavigu. Mudel saab need probleemid lahendada ja luua ühtsetes kliendiprofiilides järjepidevaid aadresse.

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

Täiustatud aadressid töötavad ainult väärtustega, mis on teie sissetoodud aadressiandmetes juba olemas. Mudel ei ole: 

1. Kontrollige, kas aadress on kehtiv aadress.
2. Kontrollige, kas mõni väärtustest (nt sihtnumbrid või tänavanimed) on kehtiv.
3. Muutke väärtusi, mida ta ei tunne.

Mudel kasutab aadresside täiustamiseks masinõppel põhinevaid tehnikaid. Kuigi me rakendame kõrget usaldusläve, kui mudel muudab sisendväärtust, nagu iga ML-põhise mudeli puhul, ei ole 100% täpsus tagatud.

## <a name="supported-countries-or-regions"></a>Toetatud riikides või regioonides

Praegu toetame aadresside rikastamist nendes riikides või piirkondades: 

- Austraalia
- Kanada
- Suurbritannia
- Ameerika Ühendriigid

Aadressid peavad sisaldama riigi/regiooni väärtust. Me ei töötle nende riikide või piirkondade aadresse, mida ei toetata, ja aadresse, millel pole riiki ega regiooni.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage **Andmed** > **Rikastamine**.

1. Valige **Rikasta minu andmeid** paanil **Täiustatud aadressid** .

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Paani Täiustatud aadressid kuvatõmmis.":::

1. Valige **Kliendi andmekogum** ja klõpsake olemit, mis sisaldab aadresse, mida soovite rikastada. Saate valida olemi *Klient*, et rikastada aadresse kõigis oma kliendiprofiilides, või valida segmendi olemi aadresside rikastamiseks ainult selles segmendis sisalduvates kliendiprofiilides.

1. Valige, kuidas aadresse teie andmekogumis vormindatakse. Valige **Ühe atribuudi aadress** kui teie andmetes kasutatavad aadressid kasutavad ühte välja. Valige **Mitme atribuudi aadress** kui teie andmetes kasutatavad aadressid rohkem kui ühte andmevälja.

   > [!NOTE]
   > Riik/Regioon on kohustuslik nii ühe- kui ka mitme atribuudi aadressis. Aadresse, mis ei sisalda kehtivaid või toetatud riigi/regiooni väärtusi, ei rikastata

1.  Kaardistage ühendatud kliendiolemi aadressiväljad.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Täiustatud aadressivälja vastendamise leht.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Sisestage rikastamise nimi ja väljundolemi nimi.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

## <a name="enrichment-results"></a>Rikastamise tulemused

Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**. Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab). Töötlemisaeg sõltub teie kliendiandmete mahust.

Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt. Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.

Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.

## <a name="next-steps"></a>Järgmised etapid

Rikastatud kliendiandmetele toetumine. Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [Ekspordi andmed](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
