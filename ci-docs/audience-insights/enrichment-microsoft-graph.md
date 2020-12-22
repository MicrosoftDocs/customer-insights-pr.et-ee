---
title: Kliendiprofiilide rikastamine Microsoft Graphiga
description: Microsoft Graphi konfidentsiaalsete andmete kasutamine, et rikastada kliendi andmeid brändi ja huvide ligitõmbavusega.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405534"
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

[Lisateave Microsoft Graphi kohta](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Ligitõmbavuse skoor ja usaldus

**Ligitõmbavuse skoor** arvutatakse 100-punkti skaalal, kusjuures 100 esindab segmenti, millel on kaubamärgi või huvi suhtes kõige suurem ligitõmbavus.

**Ligitõmbavuse usaldus** arvutatakse samuti 100-punkti skaalal. See näitab süsteemi usalduse taset, et segmendil on ligitõmbavus brändi või huvi suhtes. Usalduse tase põhineb segmendi suurusel ja segmendi granulaarsusel. Segmendi suuruse määrab antud segmendi jaoks olemas olevate andmete hulk. Segmendi granuaalsus tehakse kindlaks vastavalt sellele, kui palju atribuute (vanus, sugu, asukoht) on profiilis saadaval.

Me ei normaliseeri teie andmekogumi punktisummasid. Seetõttu ei pruugi te näha oma andmekomplekti jaoks kõiki võimalikke ligitõmbavuse skoori väärtuseid. Näiteks ei pruugi teie andmete hulgas olla ühtegi rikastatud kliendiprofiili, mille ligitõmbavuse skoor oleks 100. See on võimalik juhul, kui demograafilised segmendis, mis sai antud brändi või huvi kohta skoori 100, pole kliente.

> [!TIP]
> Kui [loote segmente](segments.md) kasutades ligitõmbavuse skoore, vaadake üle oma andmekomplektide ligitõmbavuse skooride jaotus enne, kui langetate otsuse sobiva punktisumma künnise kohta. Näiteks ligitõmbavuse skoori 10 saab lugeda oluliseks andmekomplektis, kus kõrgeim ligitõmbavuse skoor antud kaubamärgi või huvi jaoks on ainult 25.

## <a name="supported-countriesregions"></a>Toetatud riigid/piirkonnad

Toetame praegu järgmisi riigi/regiooni suvandeid: Austraalia, Kanada (inglise), Prantsusmaa, Saksamaa, Ühendkuningriik või Ameerika Ühendriigid (inglise).

Riigi valimiseks avage **Tootemarkide rikastamine** või **Huvide rikastamine** ning valige suvand **Muuda** valiku **Riik/piirkond** kõrval. Paanil **Riigi/piirkonna sätted** valige suvand ja valige **Rakenda**.

### <a name="implications-related-to-country-selection"></a>Riigi valikuga seotud mõjud

- [Oma tootemarkide valimisel](#define-your-brands-or-interests) anname soovitusi vastavalt valitud riigile/piirkonnale.

- [Valdkonna valimisel](#define-your-brands-or-interests) tuvastame valitud riigi/regiooni põhjal kõige asjakohasemad tootemargid või huvid.

- [Väljade vastendamisel](#map-your-fields), kui välja riik/piirkond pole vastendatud, kasutame teie klientide profiilide rikastamiseks valitud riigi/regiooni Microsoft Graphi andmeid. Samuti kasutame seda valikut, et rikastada teie kliendiprofiile, millel pole riigi/piirkonna andmeid saadaval.

- [Profiilide rikastamisel](#refresh-enrichment) rikastame kõiki kliendiprofiile, mille jaoks meil on valitud kaubamärkidele ja huvidele Microsoft Graphi andmed saadaval, sh profiilid, mis pole valitud riigis/regioonis. Näiteks kui valisite Saksamaa, rikastame Ameerika Ühendriikides asuvaid profiile, kui meil on Microsoft Graph'i andmed saadaval valitud kaubamärkide ja huvide kohta USAs.

## <a name="configure-enrichment"></a>Rikastamise konfigureerimine

Tootemarkide või huvide rikastamise konfigureerimine koosneb kahest etapist.

### <a name="define-your-brands-or-interests"></a>Määratlege oma tootemargid või huvid

Valige üks järgmistest suvanditest.

- **Tööstus** : süsteem tuvastab peamised teie tööstuse jaoks asjakohased tootemargid või huvid ning rikastab nendega teie kliendiandmeid.
- **Valige enda oma**: valige tootemarkide või huvide loendist viis üksust, mis on teie organisatsiooni jaoks kõige asjakohasemad.

Brändi või huvi lisamiseks sisestage see sisendi alasse, et saada sobivate terminite soovitusi. Kui me ei loetle otsitavaid brände või huvisid, saatke meile tagasisidet, kasutades linki **Soovita**.

### <a name="map-your-fields"></a>Väljade vastendamine

Vastendage oma ühtlustatud kliendi olemi väljad vähemalt kahe atribuudiga, et määratleda, millist demograafilist segmenti soovite teie kliendiandmete rikastamiseks kasutada. Valige suvand **Redigeeri**, et määratleda väljade vastendamine, ja valige suvand **Rakenda**, kui olete lõpetanud. Väljavastenduse lõpule viimiseks valige **Salvesta**.

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
