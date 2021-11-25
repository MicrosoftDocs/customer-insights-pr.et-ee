---
title: Kliendiprofiilide rikastamine Microsofti andmetega
description: Kasutage Microsofti varalisi andmeid, et rikastada oma kliendiandmeid afiinsuste ja hääleosaga.
ms.date: 11/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 346c79d0a4d5cd5c47e91c195a48d3a153db0dc0
ms.sourcegitcommit: 9d3c9e4eb2ce20996a4f4fb44c42e3fe020c5b48
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 11/11/2021
ms.locfileid: "7793699"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Kliendiprofiilide rikastamine afiinsuste ja hääleosaga (eelvaade)

Microsofti varaliste andmete abil saate rikastada oma kliendiandmeid brändi sarnasuste, huviga seotud sarnasuste ja hääleosaga (SoV). Need afiinsused ja soV põhinevad teie klientidega sarnase demograafiaga inimeste andmetel. See teave aitab teil oma kliente paremini mõista ja segmenteerida nende sarnasuste või soV alusel konkreetsete kaubamärkide ja huvidega.

Liikuge sihtrühmaülevaadetes jaotisse **Andmed** > **Rikastamine**, et [seadistada ja vaadata rikastamisi](enrichment-hub.md).

Brändi afiinsuse ja SoV rikastamise konfigureerimiseks minge **vahekaardile** Avasta ja **valige** **paanil Kaubamärgid suvand Rikasta minu** andmeid.

Huvide sarnasuste ja soV rikastamise konfigureerimiseks minge **vahekaardile** Avasta ja valige **paanil** Huvid suvand Rikasta minu **andmeid**.

   > [!div class="mx-imgBorder"]
   > ![Tootemarkide ja huvide paanid.](media/BrandsInterest-tile-Hub.png "Tootemarkide ja huvide paanid")

## <a name="how-we-determine-affinities-and-sov"></a>Kuidas me määrame sugulused ja SoV

Kasutame Microsofti veebiotsingu andmeid, et leida brändide ja huvidega seotud afiinsusi ja soV-d erinevates demograafilistes segmentides (määratletud vanuse, soo või asukoha järgi). Brändi või huvi veebipõhine otsingumaht on aluseks afiinsuse või SoV määramisele. Kuid igaüks pakub oma klientide mõistmiseks erinevat perspektiivi.

- Afiinsus on demograafiliste segmentide võrdlus. Selle teabe abil saate tuvastada demograafilisi segmente, millel on antud brändi või huvi suhtes teiste segmentidega võrreldes suurim afiinsus.

- Hääle jagamine on teie valitud kaubamärkide või huvide võrdlus. Selle teabe abil saate teha kindlaks, millisel brändil või huvil on antud demograafilise segmendi jaoks suurim hääl, võrreldes teiste valitud kaubamärkide või huvidega.

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

## <a name="share-of-voice-sov"></a>Hääle jagamine (SoV)

Arvutame SoV 100-punktilisel skaalal. SoV kogumaht kõigi kaubamärkide või huvide kohta iga rikastatud kliendiprofiili kohta lisab kuni 100. Erinevalt afiinsustest on SoV teie valitud kaubamärkide ja huvide suhtes. Näiteks võivad Microsofti soV-väärtused olla erinevad, kui valitud kaubamärgid on (Microsoft, GitHub) versus ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Toetatud riigid/piirkonnad

Toetame praegu järgmisi riigi/regiooni suvandeid: Austraalia, Kanada (inglise), Prantsusmaa, Saksamaa, Ühendkuningriik või Ameerika Ühendriigid (inglise).

Et valida riik või piirkond, avage **Tootemarkide rikastamine** või **Huvide rikastamine** ja valige **Muuda** **Riik/regioon** kõrval. Paanil **Riigi/piirkonna sätted** valige suvand ja valige **Rakenda**.

### <a name="implications-related-to-country-selection"></a>Riigi valikuga seotud mõjud

- Kui [valite oma tootemarke](#define-your-brands-or-interests), pakub süsteem valitud riigil või piirkonnal põhinevaid soovitusi.

- Kui [valite valdkonna](#define-your-brands-or-interests), saate olulisemaid tootemarke või huvisid valitud riigi või piirkonna põhjal.

- Kui [rikastame profiile](#refresh-enrichment), rikastame kõiki kliendiprofiile, mille jaoks me saame andmeid valitud tootemarkide ja huvide jaoks, kaasaarvatud profiilid, mis ei ole valitud riigis või piirkonnas. Näiteks kui valisite Saksamaa, rikastame Ameerika Ühendriikides asuvad profiilid, kui meil on Ameerika Ühendriikides valitud kaubamärkide ja omandiõiguse andmeid.

## <a name="configure-enrichment"></a>Rikastamise konfigureerimine

Juhendatud kogemus aitab teid läbi rikastamise konfiguratsiooni. 

### <a name="define-your-brands-or-interests"></a>Määratlege oma tootemargid või huvid

Valige kuni viis kaubamärki või huvi, kasutades ühte või mõlemat järgmist valikut.

- **Tööstus**: Valige ripploendist oma valdkond ja valige siis selle valdkonna jaoks kõige populaarsem kaubamärk või huvid.
- **Valige oma nimi**. Sisestage oma ettevõtte jaoks oluline kaubamärk või huvi ja valige siis valite vastavate soovituste vahel. Kui me ei loetle otsitavaid brände või huvisid, saatke meile tagasisidet, kasutades linki **Soovita**.

### <a name="review-enrichment-preferences"></a>Rikastamise eelistuste ülevaatamine

Vaadake üle oma rikastamise vaike-eelistused ja värskendage neid vastavalt vajadusele.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Rikastamise eelistuste akna kuvatõmmis.":::

### <a name="select-entity-to-enrich"></a>Valige rikastamiseks olem

Valige **Rikastatud olem** ja valige andmekogum, mida soovite Microsofti andmetega rikastada. Saate valida olemi Klient, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.

### <a name="map-your-fields"></a>Väljade vastendamine

Vastendage oma ühendatud kliendiolemi väljad demograafilise segmendi määratlemiseks, mida süsteem kasutab teie kliendiandmete rikastamiseks. Vastendage riigi/piirkonna ja vähemalt sünniaja või soo atribuudid. Lisaks peate näitama kaardil vähemalt ühte linna (ja osariiki/maakonda) või sihtnumbrit. Valige suvand **Redigeeri**, et määratleda väljade vastendamine, ja valige suvand **Rakenda**, kui olete lõpetanud. Väljavastenduse lõpule viimiseks valige **Salvesta**.

Toetatakse järgmisi vorminguid ja väärtusi (väärtused pole tõstutundlikud):

- **Sünniaeg**: soovitame, et sünniaeg oleks andmete valmendamisel teisendatud DateTime tüüpi. Teise võimalusena võib see olla string [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formaadis "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".
- **Sugu**: mees, naine, teadmata.
- **Sihtnumber**: Ameerika Ühendriikide viiekohaline sihtnumber, standardne sihtnumber mujal.
- **Linn**: linna nimi inglise keeles.
- **Osariik/maakond**: kahetäheline lühend USA ja Kanada jaoks. Kahe- või kolmetäheline lühend Austraalia jaoks. Ei kohaldata Prantsusmaa, Saksamaa ega Ühendkuningriigi korral.
- **Riik/piirkond**:

  - US: Ameerika Ühendriigid, Ühendriigid, USA, US, Ameerika
  - CA: Kanada, CA
  - GB: Ühendkuningriik, UK, Suurbritannia, GB, Suurbritannia ja Põhja-Iiri Ühendkuningriik, Suurbritannia Ühendkuningriik
  - AU: Austraalia, AU, Austraalia Liit
  - FR: Prantsusmaa, FR, Prantsuse Vabariik
  - DE: Saksamaa, Saksa, Deutschland, Allemagne, DE, Saksamaa Liitvabariik, Saksamaa Vabariik

## <a name="review-and-name-the-enrichment"></a>Rikastamise läbivaatamine ja rikastamisele nime andmine

Lõpuks saate eelvaadata teavet ja anda rikastamisele nimi.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Omandiõiguste eelversioon ja nime leht.":::

## <a name="refresh-enrichment"></a>Rikastamise värskendamine

Pärast brändide, huvide ja demograafilise väljavastenduse konfigureerimist käivitage rikastamine. Protsessi käivitamiseks valige tootemargi või huvide lehel käsk **Käivita**. Lisaks saate lasta süsteemil käitada rikastamist automaatselt ajastatud värskendamise osana.

Sõltuvalt kliendiandmete mahust võib rikastamise käitamise lõpuleviimiseks kuluda mitu minutit.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rikastamise tulemused

Pärast rikastamise protsessi käitamist, avage jaotis **Minu rikastamised**, et vaadata üle rikastatud klientide koguarv ja kaubamärkide või huvide jagunemine rikastatud kliendiprofiilides.

:::image type="content" source="media/my-enrichments.png" alt-text="Tulemuste eelvaade pärast rikastamise protsessi käitamist.":::

Leiate diagrammi, kus on aja jooksul rikastatud kliendiprofiilide arv ja rikastatud olemite eelvaated. Vaadake rikastatud andmed üle, valides **suvandi Vaata täpsemalt** **afiinsuse tasemel** või **Hääldiagrammidel** Jaga. Brändide rikastatud andmed lähevad **BrandAffinityFromMicrosofti** ja **BrandShareOfVoiceFromMicrosofti** üksustele. Huvide andmed on **äriüksustes InterestAffinityFromMicrosoft** ja **InterestShareOfVoiceFromMicrosoft.** Samuti leiate need olemis loetletuna rühmas **Rikastamine** suvandis **Andmed** > **Olemid**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Kliendi kaardi rikastamise andmete vaatamine

Brändi ja huvi SoV saab vaadata ka üksikute kliendikaartidega. Avage **Kliendid** ja valige kliendiprofiil. Kliendikaardilt leiate brändi või huvi soV graafikud, mis põhinevad selle kliendi demograafilise profiiliga inimestel.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kliendi kaart rikastatud andmetega.":::

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
