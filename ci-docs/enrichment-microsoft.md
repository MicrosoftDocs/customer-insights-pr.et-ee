---
title: Kliendiprofiilide rikastamine Microsofti andmetega
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
ms.openlocfilehash: 5c016a394fdf485057a190d03bfed9ce5481f435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642624"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Kliendiprofiilide rikastamine sarnasuste ja hääljagamisega (eelvaade)

Microsofti varaliste andmete abil saate rikastada oma kliendiandmeid brändide sarnasuste, huvide sarnasuste ja hääleosaga (SoV). Need sarnasused ja SoV põhinevad teie klientidega sarnase demograafiaga inimeste andmetel. See teave aitab teil paremini mõista ja segmenteerida oma kliente, lähtudes nende afiinsusest või SoV-st konkreetsete kaubamärkide ja huvidega.

Rikastamiste konfigureerimiseks ja vaatamiseks avage **veebisait DataEnrichment** > **·**.[...](enrichment-hub.md)

Brändide afiinsuste ja SoV-rikastamise konfigureerimiseks minge vahekaardile **Avasta** ja valige paanil **Kaubamärgid** suvand **Rikasta minu andmeid**.

Huvide sarnasuste ja SoV-rikastamise konfigureerimiseks **avage vahekaart Avasta** ja valige paanil **Huvid** käsk **Rikasta minu andmeid**.

   > [!div class="mx-imgBorder"]
   > ![Tootemarkide ja huvide paanid.](media/BrandsInterest-tile-Hub.png "Tootemarkide ja huvide paanid")

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

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Rikastamise tulemused

Pärast rikastamise protsessi käitamist, avage jaotis **Minu rikastamised**, et vaadata üle rikastatud klientide koguarv ja kaubamärkide või huvide jagunemine rikastatud kliendiprofiilides.

:::image type="content" source="media/my-enrichments.png" alt-text="Tulemuste eelvaade pärast rikastamise protsessi käitamist.":::

Leiate diagrammi rikastatud kliendiprofiilide arvuga aja jooksul ja rikastatud olemite eelvaated. Vaadake rikastatud andmed üle, valides lisateavet **diagrammide** **Afiinsustase** või **Häälandmete** ühiskasutuse kohta. Brändide rikastatud andmed lähevad BrandAffinityFromMicrosoft **ja BrandShareOfVoiceFromMicrosoft** üksustele **·**. Huvide andmed on üksustes **InterestAffinityFromMicrosoft** ja **InterestShareOfVoiceFromMicrosoft**. Samuti leiate need olemis loetletuna rühmas **Rikastamine** suvandis **Andmed** > **Olemid**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Kliendi kaardi rikastamise andmete vaatamine

Kaubamärki ja huvi SoV-d saab vaadata ka üksikutel kliendikaartidel. Avage **Kliendid** ja valige kliendiprofiil. Kliendikaardilt leiate brändi või huvi SoV graafikud, mis põhinevad selle kliendi demograafilise profiili inimestel.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kliendi kaart rikastatud andmetega.":::

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
