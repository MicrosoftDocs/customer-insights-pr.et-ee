---
title: Kliendiprofiilide rikastamine Microsofti kaubamärkide ja huvide andmetega (eelvaade)
description: Microsofti varaliste andmete abil saate rikastada oma kliendiandmeid sarnasuste ja häälkäsklusega.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: e1827adca10a3b193c02a20c4abccacf73194a77
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082698"
---
# <a name="enrich-customer-profiles-with-brands-and-interests-data-from-microsoft-preview"></a>Kliendiprofiilide rikastamine Microsofti kaubamärkide ja huvide andmetega (eelvaade)

Microsofti varaliste andmete abil saate rikastada oma kliendiandmeid brändide sarnasuste, huvide sarnasuste ja hääleosaga (SoV). Need sarnasused ja SoV põhinevad teie klientidega sarnase demograafiaga inimeste andmetel. See teave aitab teil paremini mõista ja segmenteerida oma kliente, lähtudes nende afiinsusest või SoV-st konkreetsete kaubamärkide ja huvidega.

## <a name="how-we-determine-affinities-and-sov"></a>Kuidas me määrame afiinsused ja SoV

Kasutame Microsofti veebipõhiseid otsinguandmeid, et leida sarnasusi ja SoV-d kaubamärkide ja huvide jaoks erinevates demograafilistes segmentides (määratletud vanuse, soo või asukoha järgi). Brändi või huvi veebipõhine otsingumaht on aluseks afiinsuse või SoV kindlaksmääramisel. Kuid igaüks pakub oma klientide mõistmiseks erinevat perspektiivi.

- Afiinsus on demograafiliste segmentide võrdlus. Selle teabe abil saate tuvastada demograafilisi segmente, millel on antud kaubamärgi või huvi suhtes suurim afiinsus võrreldes teiste segmentidega.

- Hääleosa on teie valitud kaubamärkide või huvide võrdlev. Selle teabe abil saate tuvastada, millisel kaubamärgil või huvil on antud demograafilise segmendi jaoks suurim hääleosa võrreldes teiste valitud kaubamärkide või huvidega.

## <a name="affinity-level-and-score"></a>Ühtivuse tase ja skoor

Igal rikastatud kliendiprofiilil pakume kahte seotud väärtust: afiinsuse tase ja afiinsuse skoor. Need väärtused aitavad teil määratleda, kui suur ühtivus on selle profiili demograafilisel segmendil teatud tootemargi või huvi jaoks, võrreldes muude demograafiliste segmentidega.

*Ühtivustase* koosneb neljast tasemest ja *ühtivuse skoor* arvutatakse 100 punkti skaalal, mis vastendatakse ühtivustasemetega.

|Ühtivustase |Ühtivuse skoor  |
|---------|---------|
|Väga palju     | 85–100       |
|Suur     | 70–84        |
|Keskmine     | 35–69        |
|Väike     | 1–34        |

Sõltuvalt granulaarsusest, mida soovite ühtivuse mõõtmisel, saate kasutada ühtivuse taset või skoori. Ühtivuse skoor annab teile täpsema kontrolli.

## <a name="share-of-voice-sov"></a>Hääle osakaal (SoV)

Me arvutame SoV 100 punkti skaalal. SoV kõigi kaubamärkide või huvide kogusumma iga rikastatud kliendiprofiili kohta on kuni 100. Erinevalt sugulustest on SoV võrreldes teie valitud kaubamärkide ja huvidega. Näiteks võivad "Microsofti" soV väärtused olla erinevad, kui valitud kaubamärgid on ("Microsoft", "GitHub") versus ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Toetatud riigid/piirkonnad

Toetame praegu järgmisi riigi/regiooni suvandeid: Austraalia, Kanada (inglise), Prantsusmaa, Saksamaa, Ühendkuningriik või Ameerika Ühendriigid (inglise).

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

   - Brändi afiinsuste ja SoV-rikastumise konfigureerimiseks valige paanil **Kaubamärgid** suvand **Rikasta minu andmeid**.

   - Intresside afiinsuste ja SoV-rikastumise konfigureerimiseks valige paanil **Huvid** suvand **Rikasta minu andmeid**.

   > [!div class="mx-imgBorder"]
   > ![Tootemarkide ja huvide paanid.](media/BrandsInterest-tile-Hub.png "Tootemarkide ja huvide paanid")

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Riigi või regiooni muutmiseks valige valiku Riik/regioon kõrval **muuda** **.** Valige paanil **Riigi**/regiooni sätted [toetatud riik/regioon](#supported-countriesregions) ja valige **Rakenda**.

   > [!NOTE]
   > Kui valite oma tootemarke, pakub süsteem valitud riigil või piirkonnal põhinevaid soovitusi. Kui valite valdkonna, saate olulisemaid tootemarke või huvisid valitud riigi või piirkonna põhjal.

1. Valige kuni viis kaubamärki või huvi, kasutades ühte või mõlemat järgmist valikut.

   - **Tööstus**: Valige ripploendist oma valdkond ja valige siis selle valdkonna jaoks kõige populaarsem kaubamärk või huvid.
   - **Valige oma nimi**. Sisestage oma ettevõtte jaoks oluline kaubamärk või huvi ja valige siis valite vastavate soovituste vahel. Kui me ei loetle otsitavaid brände või huvisid, saatke meile tagasisidet, kasutades linki **Soovita**.

1. Valige **Edasi** ja vaadake üle oma rikastamise vaikeeelistused ning värskendage neid vastavalt vajadusele.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Rikastamise eelistuste akna kuvatõmmis.":::

1. Tehke valik **Edasi**.

1. **Valige kliendi andmestik** ja valige profiil või segment, mida soovite Microsofti andmetega rikastada. Olem *Klient* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

1. Tehke valik **Edasi**.

1. Vastendage oma väljad ühtsest kliendiolemist Microsofti andmetega.

   > [!NOTE]
   > Nõutav on vähemalt sünnikuupäev või soo atribuut. Riik/regioon ja vähemalt linn (ja osariik/provints) või postiindeks on kohustuslikud. Soovitame andmete allaneelamise ajal teisendada sünnikuupäev DateTime'i tüübiks. Teise võimalusena võib see olla string [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formaadis "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Peate rikastamise jaoks sisestama nime. Väljundi **olemi nimi** valitakse automaatselt.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Omandiõiguste eelversioon ja nime leht.":::

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Rikastamisprotsessi alustamiseks või lehele Rikastamine naasmise **lähedal** valige **Käivita**.

   Kui rikastame profiile, rikastame kõiki kliendiprofiile, mille jaoks me saame andmeid valitud tootemarkide ja huvide jaoks, kaasaarvatud profiilid, mis ei ole valitud riigis või piirkonnas. Näiteks kui valisite Saksamaa, rikastame Ameerika Ühendriikides asuvad profiilid, kui meil on Ameerika Ühendriikides valitud kaubamärkide ja omandiõiguse andmeid.

## <a name="view-enrichment-results"></a>Rikastamise tulemuste kuvamine

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Tulemuste eelvaade pärast rikastamise protsessi käitamist.":::

Tulemuseks **on Afiinsustase** või **Hääldiagrammide** ühiskasutus.

Rikastamisest loodud olemid on loetletud **andmeolemite** **rikastamisrühma** > **all**. Brändide rikastatud andmed lähevad BrandAffinityFromMicrosoft **ja BrandShareOfVoiceFromMicrosoft** üksustele **·**. Huvide andmed on üksustes **InterestAffinityFromMicrosoft** ja **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Kliendi kaardi rikastamise andmete vaatamine

Kaubamärki ja huvi SoV-d saab vaadata ka üksikutel kliendikaartidel. Avage **Kliendid** ja valige kliendiprofiil. Kliendikaardilt leiate brändi või huvi SoV graafikud, mis põhinevad selle kliendi demograafilise profiili inimestel.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kliendi kaart rikastatud andmetega.":::

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
