---
title: Aadressi täiustamise rikastamine (sisaldab videot)
description: Rikastage ja normaliseerige kliendiprofiilide aadressiteavet Microsofti mudelitega.
ms.date: 12/16/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: afb1a6b4805702697889bb91ca36a96a714cba3d
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934918"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Kliendiprofiilide rikastamine täiustatud aadressidega

Teie andmetes kuvatud aadressid võivad olla struktureerimata, mittetäielikud või valed. Kasutage Microsofti mudeleid aadresside normaliseerimiseks ja rikastamiseks [Common Data Model vormingusse,](/common-data-model/schema/core/applicationcommon/address) et saada paremat täpsust ja ülevaadet.

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

Täiustatud aadressid töötavad ainult väärtustega, mis on teie sissetoodud aadressiandmetes juba olemas. Mudel ei ole: 

1. Kontrollige, kas aadress on kehtiv aadress.
2. Kontrollige, kas mõni väärtustest (nt sihtnumbrid või tänavanimed) on kehtiv.
3. Muutke väärtusi, mida ta ei tunne.

Mudel kasutab aadresside täiustamiseks masinõppel põhinevaid tehnikaid. Kuigi mudeli sisendväärtuse muutmisel rakendame kõrget usalduskünnist, nagu iga masinõppepõhise mudeli puhul, pole 100-protsendiline täpsus tagatud.

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

Aadressid peavad sisaldama riigi/regiooni väärtust. Me ei töötle nende riikide või piirkondade aadresse, mida ei toetata, ja aadresse, millel pole riiki ega regiooni.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage **Andmed** > **Rikastamine**.

1. Valige **Rikasta minu andmeid** paanil **Täiustatud aadressid** .

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Paani Täiustatud aadressid kuvatõmmis.":::

1. Valige **Kliendi andmekogum** ja klõpsake olemit, mis sisaldab aadresse, mida soovite rikastada. Saate valida olemi *Klient*, et rikastada aadresse kõigis oma kliendiprofiilides, või valida segmendi olemi aadresside rikastamiseks ainult selles segmendis sisalduvates kliendiprofiilides.

1. Valige, kuidas aadresse teie andmekogumis vormindatakse. Valige **Ühe atribuudi aadress** kui teie andmetes kasutatavad aadressid kasutavad ühte välja. Valige **Mitme atribuudi aadress** kui teie andmetes kasutatavad aadressid rohkem kui ühte andmevälja.

   > [!NOTE]
   > Riik/piirkond on kohustuslik nii ühe atribuudi kui ka mitme atribuudiga aadressidel. Aadresse, mis ei sisalda kehtivaid või toetatud riigi/regiooni väärtusi, ei rikastata.

1.  Kaardistage ühendatud kliendiolemi aadressiväljad.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Täiustatud aadressivälja vastendamise leht.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Sisestage rikastamise nimi ja väljundolemi nimi.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

## <a name="enrichment-results"></a>Rikastamise tulemused

Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**. Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab). Töötlemisaeg sõltub teie kliendiandmete mahust.

Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt. Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.

Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.

### <a name="overview-card"></a>Ülevaate kaart

Ülevaatekaardil kuvatakse üksikasjad rikastamise katvuse kohta. 

* **Kliendid töödeldud ja muudetud** : edukalt rikastatud kliendiprofiilide arv.

* **Kliendid, keda töödeldi ja mida ei** muudetud: tuvastatud, kuid muutmata kliendiprofiilide arv. Tavaliselt juhtub see siis, kui sisendandmed on kehtivad ja rikastamine ei saa neid parandada.

* **Kliendid, keda ei töödeldud ega muudetud** : tuvastamata profiilide arv. Tavaliselt sisendandmete puhul, mis on kehtetud või mida rikastamine ei toeta.

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
