---
title: Kliendiprofiilide rikastamine Microsoft Graphiga
description: Microsoft Graphi konfidentsiaalsete andmete kasutamine, et rikastada kliendi andmeid brändi ja huvide ligitõmbavusega.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: aa46dac4f9c0d27881371877b14a92a6725710da
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596448"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Kliendiprofiilide rikastamine brändi ja huvide ligitõmbavusega (eelvaade)

Microsoft Graphi konfidentsiaalsete andmete kasutamine, et rikastada kliendi andmeid brändi ja huvide ligitõmbavusega. Need ühtivused määratakse teie klientidega sarnaste demograafiliste näitajatega inimeste andmete põhjal. See teave aitab teil paremini mõista ja segmentida oma kliente, lähtudes nende ligitõmbavusest konkreetsetele tootemarkidele ja huvidele.

Liikuge sihtrühmaülevaadetes jaotisse **Andmed** > **Rikastamine**, et [seadistada ja vaadata rikastamisi](enrichment-hub.md).

Tootemargi külgetõmbe rikastamise konfigureerimiseks minge vahekaardile **Avastamine** ja valige paanil **Tootemargid** suvand **Rikasta minu andmed**.

Huvide külgetõmbe rikastamise konfigureerimiseks minge vahekaardile **Avastamine** ja valige paanil **Huvid** suvand **Rikasta minu andmed**.

   > [!div class="mx-imgBorder"]
   > ![Tootemarkide ja huvide paanid](media/BrandsInterest-tile-Hub.png "Tootemarkide ja huvide paanid")

## <a name="about-microsoft-graph"></a>Microsoft Graphi teave

Kasutame Microsoft Graphi veebiotsingu andmeid, et leida erinevate demograafiliste segmentide (mis on määratletud vanuse, soo või asukoha järgi) brändide ja huvide ligitõmbavusi. Brändi või huvi veebiotsingu maht määratleb, kui palju ligitõmbavust on demograafilisel segmendil selle brändi või huvi suhtes võrreldes teiste segmentidega.

[Lisateave Microsoft Graphi kohta](/graph/overview).

## <a name="affinity-level-and-score"></a>Ühtivuse tase ja skoor

Igal rikastatud kliendiprofiilil pakume kahte seotud väärtust – ühtivuse tase ja skoor. Need väärtused aitavad teil määratleda, kui suur ühtivus on selle profiili demograafilisel segmendil teatud tootemargi või huvi jaoks, võrreldes muude demograafiliste segmentidega.

*Ühtivustase* koosneb neljast tasemest ja *ühtivuse skoor* arvutatakse 100 punkti skaalal, mis vastendatakse ühtivustasemetega.


|Ühtivustase |Ühtivuse skoor  |
|---------|---------|
|Väga palju     | 85–100       |
|Suur     | 70–84        |
|Keskmine     | 35–69        |
|Väike     | 1–34        |

Sõltuvalt granulaarsusest, mida soovite ühtivuse mõõtmisel, saate kasutada ühtivuse taset või skoori. Ühtivuse skoor annab teile täpsema kontrolli.

## <a name="supported-countriesregions"></a>Toetatud riigid/piirkonnad

Toetame praegu järgmisi riigi/regiooni suvandeid: Austraalia, Kanada (inglise), Prantsusmaa, Saksamaa, Ühendkuningriik või Ameerika Ühendriigid (inglise).

Riigi valimiseks avage **Tootemarkide rikastamine** või **Huvide rikastamine** ning valige suvand **Muuda** valiku **Riik/piirkond** kõrval. Paanil **Riigi/piirkonna sätted** valige suvand ja valige **Rakenda**.

### <a name="implications-related-to-country-selection"></a>Riigi valikuga seotud mõjud

- Kui [valite oma tootemarke](#define-your-brands-or-interests), pakub süsteem valitud riigil või piirkonnal põhinevaid soovitusi.

- Kui [valite valdkonna](#define-your-brands-or-interests), saate olulisemaid tootemarke või huvisid valitud riigi või piirkonna põhjal.

- Kui [rikastate profiile](#refresh-enrichment), rikastame kõiki kliendiprofiile, mille jaoks saame valitud tootemarkide ja huvide andmeid. Sealhulgas profiilid, mis pole valitud riigis või piirkonnas. Näiteks kui valisite Saksamaa, rikastame Ameerika Ühendriikides asuvaid profiile, kui meil on Microsoft Graph'i andmed saadaval valitud kaubamärkide ja huvide kohta USAs.

## <a name="configure-enrichment"></a>Rikastamise konfigureerimine

### <a name="define-your-brands-or-interests"></a>Määratlege oma tootemargid või huvid

Valige üks järgmistest suvanditest.

- **Tööstus** : süsteem tuvastab peamised teie tööstuse jaoks asjakohased tootemargid või huvid ning rikastab nendega teie kliendiandmeid.
- **Valige enda oma**: valige tootemarkide või huvide loendist viis üksust, mis on teie organisatsiooni jaoks kõige asjakohasemad.

Brändi või huvi lisamiseks sisestage see sisendi alasse, et saada sobivate terminite soovitusi. Kui me ei loetle otsitavaid brände või huvisid, saatke meile tagasisidet, kasutades linki **Soovita**.

### <a name="review-enrichment-preferences"></a>Rikastamise eelistuste ülevaatamine

Vaadake üle oma rikastamise vaike-eelistused ja värskendage neid vastavalt vajadusele.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Rikastamise eelistuste akna kuvatõmmis.":::

### <a name="select-entity-to-enrich"></a>Valige rikastamiseks olem

Valige **Vastendatud olem** ja valige andmete kogum, mida soovite Microsoft Graphi ettevõtte andmetega rikastada. Saate valida olemi Klient, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.

### <a name="map-your-fields"></a>Väljade vastendamine

Vastendage oma ühendatud kliendiolemi väljad demograafilise segmendi määratlemiseks, mida süsteem kasutab teie kliendiandmete rikastamiseks. Vastendage riigi/piirkonna ja vähemalt sünniaja või soo atribuudid. Lisaks peate näitama kaardil vähemalt ühte linna (ja osariiki/maakonda) või sihtnumbrit. Valige suvand **Redigeeri**, et määratleda väljade vastendamine, ja valige suvand **Rakenda**, kui olete lõpetanud. Väljavastenduse lõpule viimiseks valige **Salvesta**.

Toetatakse järgmisi vorminguid ja väärtusi, kuid väärtused pole tõstutundlikud.

- **Sünniaeg**: soovitame, et sünniaeg oleks andmete valmendamisel teisendatud DateTime tüüpi. Alternatiivina võib see olla string [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) vormingus "aaaa–KK–pp" või "aaaa–KK–PPTHH:mm:ssZ".
- **Sugu**: mees, naine, teadmata
- **Sihtnumber**: viiekohaline sihtnumber USAs, standardne sihtnumber kõikjal mujal
- **Linn**: linna nimi inglise keeles
- **Osariik/maakond**: kahetäheline lühend USA ja Kanada jaoks. Kahe- või kolmetäheline lühend Austraalia jaoks. Ei kohaldata Prantsusmaa, Saksamaa ega Ühendkuningriigi korral.
- **Riik/piirkond**:

  - US: Ameerika Ühendriigid, Ühendriigid, USA, US, Ameerika
  - CA: Kanada, CA
  - GB: Ühendkuningriik, UK, Suurbritannia, GB, Suurbritannia ja Põhja-Iiri Ühendkuningriik, Suurbritannia Ühendkuningriik
  - AU: Austraalia, AU, Austraalia Commonwealth
  - FR: Prantsusmaa, FR, Prantsuse Vabariik
  - DE: Saksamaa, Saksa, Deutschland, Allemagne, DE, Saksamaa Liitvabariik, Saksamaa Vabariik

## <a name="refresh-enrichment"></a>Rikastamise värskendamine

Pärast brändide, huvide ja demograafilise väljavastenduse konfigureerimist käivitage rikastamine. Protsessi käivitamiseks valige tootemargi või huvide lehel käsk **Käivita**. Lisaks saate lasta süsteemil käitada rikastamist automaatselt ajastatud värskendamise osana.
Sõltuvalt kliendiandmete mahust võib rikastamise käitamise lõpuleviimiseks kuluda mitu minutit.

> [!TIP]
> Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types). Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies). Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku. Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.

## <a name="enrichment-results"></a>Rikastamise tulemused

Pärast rikastamise protsessi käitamist, avage jaotis **Minu rikastamised**, et vaadata üle rikastatud klientide koguarv ja kaubamärkide või huvide jagunemine rikastatud kliendiprofiilides.

:::image type="content" source="media/my-enrichments.png" alt-text="Tulemuste eelvaade pärast rikastamise protsessi käitamist":::

Rikastatud andmete ülevaatamiseks valige diagrammilt **Rikastatud andmete vaatamine**. Brändide rikastatud andmed lähevad olemisse **BrandAffinityFromMicrosoft**. Huvide andmed on olemis **InterestAffinityFromMicrosoft**. Samuti leiate need olemis loetletuna rühmas **Rikastamine** suvandis **Andmed** > **Olemid**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Kliendi kaardi rikastamise andmete vaatamine

Kaubamärgi ja huvide ühtivust saate vaadata ka eraldi kliendi kaartidel. Avage **Kliendid** ja valige kliendiprofiil. Kliendi kaardilt leiate diagrammid tootemarkide või huvide kohta, mille suhtes on külgetõmme selle kliendi demograafilise profiili inimestel.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kliendi kaart rikastatud andmetega":::

## <a name="next-steps"></a>Järgmised etapid

Rikastatud kliendiandmetele toetumine. Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [andmete eksport](export-destinations.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]