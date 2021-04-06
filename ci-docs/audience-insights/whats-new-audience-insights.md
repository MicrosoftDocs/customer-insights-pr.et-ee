---
title: Uued ja tulevased funktsioonid
description: Teave uute funktsioonide, täiustuste ja veaparanduste kohta.
ms.date: 03/08/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 96c0b871eeaaf0976e5c718f37f883f4410977dc
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598426"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Mis on uut Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioonis?

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Meil on hea meel teatada uusimatest värskendustest. Selles artiklis võetakse kokku avaliku eelversiooni funktsioonid, üldise kättesaadavuse täiustused ja funktsiooni värskendused. Pikaajaliste funktsiooni plaane vaadake teemast [Dynamics 365 ja Power Platformi väljaandeplaanid](/dynamics365/release-plans/).

Viimase kuue kuu jooksul kavandatud võimaluste kohta leiate lisateavet ka järgmistest videotest.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Avaldame värskendusi regioonipõhiselt. Seega teatud regioonid võivad näha funktsioone enne teisi. Kui see pole teisiti määratud teisiti, ei pea te tegema mingeid toiminguid ja värskendame rakendust automaatselt ilma seisakuteta.

> [!TIP]
> Funktsioonitaotluste ja tootesoovituste esitamiseks ning hääletamiseks minge [Dynamics 365 portaali Application Ideas](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="february-2021-updates"></a>2021. aasta veebruari värskendused

2021. aasta veebruari värskendused sisaldavad mitut funktsiooni, jõudlustäiendusi ja veaparandusi.

#### <a name="extensibility"></a>Laiendatavus

- **Eksportige segmente teenusesse AdRoll**

  Oleme laiendanud oma ekspordisihtkohti AdRolli kaasamiseks. Nüüd saate eksportida segmente Customer Insightsist AdRolli sihtrühmadesse ja kasutada neid oma reklaamimise lähtejoonena. Lisateavet leiate teemast [AdRolli konnektor](export-adroll.md).

#### <a name="segments"></a>Segmendid
 
- **Segmendi dubleerimine**
  
  Olemasoleval segmendil põhineva uue segmendi loomiseks saate nüüd segmendi dubleerida ja duplikaatsegmenti edasiseks täpsustamiseks redigeerida. 

- **Lisaatribuutide lisamine segmendile**

  Nüüd saate segmendiväljundile atribuute lisada kas siis, kui need atribuudid ei kuulu kliendiprofiili. Näiteks saate segmenti kaasata kordustellimuse ID-d ka siis, kui see kuulub kordustellimuse olemisse, millel on M:1 seos on kliendiolemiga. Niikaua, kui atribuut kuulub kliendiolemiga seotud olemile, saate need atribuudid nüüd lisada.  

#### <a name="predictions"></a>Prognoosid

- **Prognoosivate tootesoovituste loomine**

  Arusaam sellest, millised kliendid on huvitatud ostmisest, on üks esimesi vajalikke samme äritulu parendamiseks ning kliendi lojaalsuse kasvatamiseks isikupärastamise ja kaasatuse kaudu. Kui esitate tootesoovitusi, mis ei ole kooskõlas teie kliendi huvidega, võib see luua kliendi ja teie ettevõtte vahelise ühenduse katkestamistunde ning lõppkokkuvõttes piirata kliendi üldist potentsiaalset tulu ja kogemust. 

  Oma andmete abil saate nüüd luua prognoose toodete kohta, mida teie kliendid tulevikus tõenäoliselt ostavad. Lisateavet leiate teemast [Tootesoovituse prognoos](predict-product-recommendation.md).

#### <a name="system-administration"></a>Süsteemihaldus

- **Kopeerimiskeskkond toetab rohkem andmeallikatüüpe**

  Administraatorid saavad kopeerida keskkonnakonfiguratsioonid uude keskkonda samas organisatsioonis. See funktsioon laiendab kopeerimiskeskkonna funktsioone teenindusjuhtumite puhul, kus kasutatakse andmejärvest Common Data Service või kaustast Common Data Model pärinevaid andmeallikaid.

## <a name="january-2021-updates"></a>2021. a jaanuari värskendus

2021. aasta jaanuari värskendused sisaldavad mitut funktsiooni, jõudlustäiendusi ja veaparandusi.

#### <a name="extensibility"></a>Laiendatavus

- **SFTP-ekspordi laiendatud funktsioonid ja täiustatud jõudlus** Saate nüüd eksportida kõik väljundi olemid kliendi ülevaadetest SFTP-hosti. Varem piirdus eksport segmendiüksustega. Lisaks võimaldab SFTP-ekspordi jõudlus suurema andmemahu lühema ajaga, olenevalt teie SFTP-hostist.    
  Lisateavet leiate teemast [SFTP konnektor (eelvaade)](export-sftp.md).  

#### <a name="segments"></a>Segmendid

- **Masinõpe soovitatavad segmendid mõõdikute täiustamiseks** Uus viis segmentide avastamiseks ja loomiseks. Süsteem kasutab tehisintellekti mudeli abil segmentide väljatoomist, mis aitavad juba jälgitavat KPI-d (mõõdik) parandada. Näitame teie valitud atribuutide mõju ulatust mõõdikule või mõnele teisele põhiatribuudile. See teave aitab leida võimalikke segmente, mis pakuvad võimalusi.    
  Lisateavet leiate teemast [Soovitatud segmendid (eelvaade)](suggested-segments.md).

#### <a name="data-unification"></a>Andmete koondamine

- **Täiustatud vaste kogemus** Andmete ühendamise alal värskendati vastenduskogemust. See võimaldab teil konfigureerida ja vaadata mängureegleid, sealhulgas üksikasjalikku statistikat, et selgitada sobitamise toimimist. Vastavuse reegli keelamiseks on võimalusi, nii et see pole enam aktiivne, säilitades samas konfiguratsiooni, lohistamise vaste reeglid ja palju muud.
  Lisateavet leiate teemast [Vaste olemid](match-entities.md).

- **Vastendusprotsessi pöördduplitseerimise väljund on nüüd saadaval olemina** Pöördduplitseerimise protsessi väljundina, mis on nüüd kirjutatud edasiseks analüüsiks eraldi olemisse. See olem koosneb pöördduplikatsiooniprotsessis kasutatud väljadest ja võitja kirjest ning vastavatest alternatiivsetest kirjetest, mis liidetakse võitja kirjega.
  Lisateavet leiate teemast [Pöördduplitseerimise väljund olemina](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Süsteemihaldus

- **Andmete sujuvaks jagamiseks rakendusse Microsoft Dataverse** saate nüüd jagada Customer Insightsi väljundit Microsoft Dataverse rakendustega, kasutades Microsoft Dataverse Managed Data Lake hallatavad andmejärve. Kui olete keskkonna Dataverse Customer Insights kliendiülevaadetega seostanud, saate võimaluse andmete ühiskasutuse lubamiseks.
  Lisateavet leiate teemast [Keskkondade haldamine](manage-environments.md).


## <a name="december-2020-updates"></a>2020. aasta detsembrikuu värskendused

2020. aasta detsembri värskendused hõlmavad mitut funktsiooni, jõudlustäiendusi ja veaparandusi.

### <a name="new-and-updated-features-in-december-2020"></a>2020. aasta detsembri uued ja värskendatud funktsioonid

#### <a name="data-enrichment"></a>Andmete rikastamine

- **Täiustatud brändi ja huvi afiinsuse rikastamine**
  
  Lihtsustasime oma afiinsusskoore, et neid oleks hõlpsam mõista ja kasutada. Nüüd saate kiiresti tuvastada kliente, lähtudes sellest, kui palju on neil teatud kaubamärgi või huvi suhtes afiinsust.

  Lisaks oleme lisanud uued seadistusvõimalused, et paremini kontrollida, kuidas soovite oma kliendiprofiile rikastada. 

  Lisateavet vaadake teemast [Kliendiprofiilide rikastamine kaubamärgi ja huvide ühtivusega](enrichment-microsoft-graph.md).

- **Määrake, milliseid profiile rikastada**

  Nüüd saate rikastada ainult oma kliendiprofiilide alamhulka võimalusega valida vaikekliendi asemel segmendi olem. Looge kliendiprofiilidega segment, mida soovite rikastada ja valida kliendi andmekomplekti rikastamise konfiguratsioon.
  See funktsioon on praegu saadaval ainult rikastamiseks, mida pakuvad Experian ja HERE Technologies. Lubame sellel võimalusel varsti rohkem rikastumisi kasutada.

  Lisateavet leiate teemast [Kliendiprofiilide rikastamine demograafiliste andmetega](enrichment-experian.md) või [Expekliendist või kliendiprofiilide rikastamine HERE Technologies abil](enrichment-here.md).

#### <a name="extensibility"></a>Laiendatavus

- **Segmentide aktiveerimine Autopilot kaudu**

  Eksportige segmendid Autopiloti ja kasutage neid turustamiseesmärkidel. Lisateavet leiate teemast [Autopiloti konnektor (eelvaade)](export-autopilot.md).

- **Segmentide aktiveerimine SendGrid kaudu**

  Eksportige segmendid SendGridi ja kasutage neid turustamiseesmärkidel. Lisateavet leiate teemast [SendGrid konnektor](export-sendgrid.md).

#### <a name="system-administration"></a>Süsteemihaldus

- **Värskendatud keskkonnahalduse kogemus**
  
  Nüüd saate keskkondi luua, muuta, kustutada ja lähtestada otse rakenduse päises olevast keskkonnavalijast. 
  
  Peale selle kinnitatakse teie sooviksite keskkond keskkonnapaneeli ülaservale, et poleks vaja seda paneeli otsida.

  Lisateavet leiate teemast [Keskkondade haldamine](manage-environments.md).

## <a name="november-2020-updates"></a>2020. aasta novembri värskendused

2020. aasta novembri värskendused hõlmavad mitut funktsiooni, jõudlustäiendusi ja veaparandusi.

### <a name="new-and-updated-features-in-november-2020"></a>2020. aasta novembri uued ja värskendatud funktsioonid

#### <a name="data-enrichment"></a>Andmete rikastamine

- **Tooge oma rikastavaid andmeid turvalise failiedastusprotokolli (SFTP) põhise kohandatud importimise kaudu**
  
  SFTP-põhine kohandatud importimine võimaldab importida rikastamisandmeid, mida ei pea koondama. Lugege lisateavet SFTP-põhise kohandatud importimise kohta.

  Lisateavet leiate artiklist [Kliendiprofiilide rikastamine kohandatud andmetega (eelversioon)](enrichment-SFTP-custom-import.md).
 
- **Rikastage oma kliendiandmeid ettevõttelt HERE Technologies pärit asukohaandmetega**

  Ettevõtte HERE Technologies andmete rikastamise teenuste abil saate luua täpsema ülevaate oma klientide asukohast aadressi normaliseerimise, laius- ja pikkuskraadide ekstraktimise ning palju muu kaudu. Lugege lisateavet andmete rikastamise kohta ettevõtte HERE Technologies teenuste abil.

  Lisateavet leiate artiklist [Kliendiprofiilide rikastamine ettevõtte HERE Technologies teenuste abil](enrichment-here.md).

#### <a name="data-unification"></a>Andmete koondamine

- **Andmete profiilimise lubamine teie salvestuskontos valitud üksuste ja väljade jaoks on paindlik**

  Saate määrata, milliste Azure Data Lake'i salvestuskontol asuvas Common Data Modeli kaustas olevate andmeüksuste ja väljade korral soovite lubada andmete valmendamise protsessi osana andmete profiilimise.

  Lisateavet leiate artiklist [Common Data Modeli kaustaga ühendumine](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Laiendatavus

- **Segmentide aktiveerimine Google Adsi kaudu**

  Eksportige segmendid Google Adsi vaatajaskonna loenditesse ning kasutage neid loendeid, et näidata reklaame Google'i otsingus, Google'i Display-võrgustikus, YouTube'is ja Gmailis. Lugege lisateavet segmentide aktiveerimise kohta Google Adsi kaudu.

  Lisateavet leiate teemast [Google Adsi konnektor](export-google-ads.md).

- **Segmentide aktiveerimine Marketo kaudu**

  Eksportige segmendid Marketo sihtrühmadesse ja kasutage neid sihtrühmi turunduse automatiseerimiseks. Lugege lisateavet segmentide aktiveerimise kohta Marketo kaudu. 

  Lisateavet leiate teemast [Marketo konnektor](export-marketo.md).

- **Segmentide aktiveerimine DotDigitali kaudu**

  Eksportige segmendid DotDigitali ja kasutage neid turustamiseesmärkidel. Lugege lisateavet segmentide aktiveerimise kohta DotDigitali kaudu. 

  Lisateavet leiate teemast [DotDigitali konnektor](export-dotdigital.md).

#### <a name="predictions"></a>Prognoosid

- **Prognoosige tehinguvoolavust**

  Tehinguvoolavuse prognoosi funktsioon võimaldab teil ilma andmeteadlase abita ennustada selle tõenäosust, et klient lõpetab toodete või teenuste ostmise.  Prognoosiskoori abil saate kombineerida muud teavet oma klientide kohta (näiteks kliendi väärtus), et luua suure voolavusriskiga või väga väärtuslike klientide segmente. Kasutage seda segmenti klientide otsesihtimiseks turundustegevuste, klienditoe ja muude stsenaariumide kaudu, et vähendada voolavusriski.
 
  Konfigureerige voolavuse määratlus ajapõhise aknana, mis sobib teie ettevõttele, ja määratlege, millal loetakse kliendid loobunuks. Näiteks võib toidupood lugeda kliendi loobunuks, kui ta pole viimase 30 päeva jooksul midagi ostnud.
 
  Prognoosimise jätkamisel anname teile teada, milliseid andmeid on vaja, ning võimaldame teil vastendada oma ettevõtte andmed väljadega, mis on vajalikud teie kliendivoolavuse ennustamiseks. Samuti saate seada ajakava mudeli ümbertreenimiseks, võttes aluseks teie süsteemis oleva uue teabe, et kohanduda muutuvate ärioludega.
 
  Lisateavet leiate teemast [Tehinguvoolavuse prognoos (eelversioon)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Süsteemihaldus

- **Keskkonna lähtestamine**

  Puhtalt lehelt alustamiseks lähtestage kõik valitud eksemplari keskkonnas olevad andmed.

  Lisateavet vaadake teemast [Olemasoleva keskkonna lähtestamine](manage-environments.md#reset-an-existing-environment).


- **Azure Data Lake'i salvestuskontoga ühendumine teenusesubjekti kaudu**

  Kasutage Azure'i teenusesubjekti andmete kirjutamiseks oma salvestuskontole ja sealt andmete lugemiseks. Olemasolevate salvestuskonto ühenduste korral saab jätkuvalt kasutada kontovõtit. Samuti pakutakse täiendamisvõimalust, et kasutada edaspidi teenusesubjekti. Uute ühenduste aluseks võetakse teie salvestuskonto teenusesubjekti autentimise meetod.

  Lisateavet leiate teemast [Azure Data Lake Storage Gen2 kontoga ühendumine Azure'i teenusesubjekti kaudu sihtrühmaülevaadeteks](connect-service-principal.md).

## <a name="october-2020-updates"></a>2020. aasta oktoobri värskendused

2020. aasta oktoobri värskendused hõlmavad mitut funktsiooni, jõudlustäiendusi ja veaparandusi.

### <a name="new-and-updated-features-in-october-2020"></a>2020. aasta oktoobri uued ja värskendatud funktsioonid

#### <a name="extensibility"></a>Laiendatavus

- **Eksportimine Mailchimpi**

Eksportige segmente Mailchimpi olemasolevatesse sihtrühmaloenditesse, et pakkuda oma klientidele isikupärastatud meilikogemust.

Lisateavet leiate teemast [Mailchimpi konnektor](export-mailchimp.md).

#### <a name="data-enrichment"></a>Andmete rikastamine

- **Lähtekirjete duplikaatide eemaldamine vastendamise olemis**

Duplikaatkirjete tuvastamiseks määrake duplikaatide eemaldamise reeglid olemitele, mida kasutatakse vastendamisprotsessis. Ühendage need ühte kirjesse ja linkige kõik lähtekirjed selle ühendatud kirjega. Seejärel kasutatakse seda eemaldatud duplikaatidega kirjet olemiüleses vastendamisprotsessis.

Lisateavet leiate teemast [Duplikaatide eemaldamise määratlemine vastendamise olemis](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Süsteemihaldus

- **Korraldus: ühendamisprotsessis on uus värskendamise suvand**

Siiamaani käivitas süsteem ühendamisprotsessi käivitamisel kõik allavooluprotsessid, mis sõltusid ühendamis- ja järgnevatest protsessidest. Nüüd saate ühendamisprotsessi väljundit (koondatud kliendiolem) kontrollida enne, kui kasutate seda allavooluprotsessides, nagu segmendid või näitajad.
Ühendamislehel saate nüüd valida ainult ühendamisetapi käivitamise ja käivitada ainult selle protsessi. Kõigi allavooluprotsesside värskendamiseks saate valida ühendamis- ja allavooluprotsesside käivitamise. 

## <a name="september-2020-updates"></a>2020. aasta septembri uuendused

2020. aasta septembri värskendused sisaldavad mitut funktsiooni, jõudlustäiendusi ja veaparandusi.

### <a name="new-and-updated-features-in-september-2020"></a>2020. a septembri uued ja uuendatud funktsioonid

#### <a name="activities"></a>Tegevused 

- **Atribuutide semantika nutikas prognoos**

See uus funktsioon ennustab andmete ühendamise protsessile edastatud sisestusatribuutide semantilisi tüüpe. See kasutab masinõppe mudeleid, mis parandavad täpsust ja säästavad aega.

#### <a name="enrichments"></a>Rikastamised

- **Demograafiline rikastamine Experianilt**

Experiani demograafiline rikastamine on nüüd eelversioonis saadaval. Experian on üleilmne liider tarbijate ja ärikrediidi aruandluse ning turundusega seotud teenuste valdkonnas. [Experiani andmete rikastamise teenustega](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage) saate oma klientidest luua põhjalikuma ülevaate, rikastades klientide profiile selliste demograafiliste andmetega, nagu leibkonna suurus, sissetulek ja palju muud.

Selle funktsiooni kasutamiseks peab teil olema aktiivne Experiani tellimus.

Lisateavet vaadake teemast [Kliendi profiilide Experiani demograafiaandmetega rikastamine](enrichment-experian.md)


#### <a name="system-administration"></a>Süsteemihaldus

- **Ülesande üksikasjade paan**

Ülesande üksikasjade paan võimaldab teil vaadata süsteemis käitatavate ülesannete detaile. See on käepärane viis konfiguratsiooni probleemide tuvastamiseks ja lahenduste leidmiseks.
Vaadake tõrketeateid, et näha, kuidas ptentsiaalseid probleeme lahendada.
 
- **Enamatele lehele lisatud teabe töötlemine**

See täiustus lisab teavet teie olemite oleku kohta lehtedel **Olemid** ja **Kliendid**.
 
Lisaks leiate mõlemalt lehelt üksikasjad protsesside edenemise kohta koos toimingu üksikasjadega.

- **Süsteemi olekulehe täiustused**

Me täiustasime oleku üksikasjade tabeli struktuuri jaotises **Süsteem** > **Olek**, kui vaatasime andmeeksporrdid üle.
 
Lisaks on veerus **Üksikasjad** olevad tõrked palju üksikasjalikumad ja paremini kasutatavad. 
 
- **Tühistamine lähtestab töö tagasi eelmisesse olekusse**

Ülesande tühistamisel (nt vastendamise protsessis) naaseb see tagasi viimasesse olekusse. Näiteks kui vastendamise protsess jõudis eile lõpuni ja te täna selle tühistate, siis see naaseb eilsesse ünnestunud olekusse.


## <a name="august-2020-updates"></a>2020. aasta augusti värskendused

2020. aasta augusti värskendused sisaldavad mitut funktsiooni, jõudlustäiendusi ja veaparandusi.

### <a name="new-and-updated-features-in-august-2020"></a>2020. a augusti uued ja uuendatud funktsioonid

#### <a name="data-unification"></a>Andmete ühtlustamine

- **Andmete ühendamise vastendamise etapi täiustatud kasutuskogemus**

  Andmete ühendamise protsessi vastendamise etapi kasutuskogemus võimaldab teil valida olemeid, atribuute ja määratleda semantikat palju sujumaval viisil.

  Muudatused hõlmavad järgmist.
  
  - olemite ja väljade lisamiseks on vaja vähem suhtlusi
  - täiustatud otsinguvõimalused kaardil lehel
  - soovitatud välja tüübi visuaalne ja lihtne tuvastamine

#### <a name="enrichment"></a>Rikastamine

- **Huvide afiinsuse rikastamine on saadaval rohkematel turgudel**

  Laiendame USA-st väljapoole jäävate huvidega seotud rikastuste kättesaadavust veel viiel turul: Kanadal, Austraalias, Suurbritannias, Prantsusmaal ja Saksamaal. Selle laienduse abil saate rikastada oma kliendiandmeid nende turgude jaoks kehtivate huvidega. Me rikastame teie nendel turgudel asuvaid kliendiprofiile ka kasutades Microsoft Graphile kuuluvaid kohalikke andmeid.
  Lisateavet vaadake teemast [Kliendiprofiilide rikastamine kaubamärgi ja huvide ühtivusega](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>2020. aasta juuli värskendused

2020. aasta juuli värskendused sisaldavad mitut funktsiooni, jõudlustäiendusi ja veaparandusi.

### <a name="new-and-updated-features-in-july-2020"></a>2020. aasta juuli uued ja uuendatud funktsioonid

#### <a name="extensibility"></a>Laiendatavus

- **Power Automate’i lõpetatud ühendusprotsesside päästik**

  Meil oleme laiendanud oma Power Automate’i päästikuid ja lubame teil luua teatise või toimingu ühendamisprotsessi (kaart, vastendus, ühendamine) värskendamise järel.    
  Lisateavet vaadake teemast [Power Automate’i konnektor](export-power-automate.md)

#### <a name="enrichment"></a>Rikastamine

- **Brändi afiinsuse rikastamine on saadaval rohkematel turgudel**

  Laiendame USA-st väljapoole jäävate brandiga seotud rikastuste kättesaadavust veel viiel turul: Kanadal, Austraalias, Suurbritannias, Prantsusmaal ja Saksamaal. Selle laiendusega saate rikastada oma kliendiandmeid nende turgude kohalike kaubamärkidega. Me rikastame teie nendel turgudel asuvaid kliendiprofiile ka kasutades Microsoft Graphile kuuluvaid kohalikke andmeid.
  Lisateavet vaadake teemast [Kliendiprofiilide rikastamine kaubamärgi ja huvide ühtivusega](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>2020. juuni värskendused

2020. aasta juuni värskendused sisaldavad mitut funktsiooni, jõudlustäiendusi ja veaparandusi.

### <a name="new-and-updated-features-in-june-2020"></a>2020. aasta juuni uued ja uuendatud funktsioonid

#### <a name="enrichment"></a>Rikastamine

- **Rikastamine Leadspace’i ettevõtte andmetega**
  
  Määratlege kliendi koondprofiilides väljad, mida kasutatakse Leadspace’ist seotud ettevõtte andmete otsimiseks. Pärast rikastamisprotsessi käivitamist rikastatakse B2B profiile veel mitme atribuudiga, sealhulgas ettevõtte suurus, asukoht, tööstus ja palju muud.    
  See koostöö võimaldab teil parandada oma andmete kvaliteeti sisendiga kolmandast osapoolest teenustest. Selle rikastamise kasutamiseks on teil vaja Leadspace’i litsentsi selle B2B ettevõtte andmetele juurdepääsuks. Süsteem kasutab seda litsentsi, et teie andmeid pidevalt rikastada.    
  Lisateavet vaadake teemast [Ettevõtte profiilide rikastamine Leadspace’iga](enrichment-leadspace.md).

- **Rikastamisekeskuse leht**

  Kõik saadaolevad andmete rikastamised esimese ja kolmanda osapoole pakkujatelt konfigureeritakse samas kohas. Andmete rikastamise konfigureerimine on sujuv kogemus, mida hallatakse ühest kohast.    
  Lisateavet vaadake teemast [Kliendiprofiilide rikastamine](enrichment-hub.md).

- **Eraldi kaubamärgi ja huvi ühtivuse rikastamine**

  Kaubamärkide ja huvide ühilduvused on nüüd saadaval kahe eraldi rikastamisena. Eraldatud rikastamine annab teile paindlikkuse nende eraldi konfigureerimiseks ja haldamiseks sõltuvalt teie ettevõtte vajadustest või vajadustest.    
  Lisateavet vaadake teemast [Kliendiprofiilide rikastamine kaubamärgi ja huvide ühtivusega](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Laiendatavus

- **Ühtsete tegevuste klõpsatavad URL-id Dynamics 365 kliendikaardi lisandmoodulis**

  Kliendikaardi lisandmooduli koondatud tegevustes kuvatakse nüüd klõpsatavad URL-id, kui sellised URL-id on tegevuste konfigureerimise käigus määratletud.    
  Lisateavet vt teemast [Kliendikaardi lisandmoodul](customer-card-add-in.md).

- **Dynamics 365 kliendikaardi lisandmoodulis saadaolevad kaubamärgi ja huvide ühtivused**

  Dynamics 365 kliendikaardi lisandmooduli uus juhtelement võimaldab teil Dynamics 365 Customer Engagementi rakendustes kuvada kaubamärgi ja huvide ühtivusi.    
  Lisateavet vt teemast [Kliendikaardi lisandmoodul](customer-card-add-in.md).

- **Täiendavad Power Automate käivitajad**

  Oleme laiendanud oma Power Automate’i päästikuid ja lisanud järgmised päästikud.
  - Saage teatis või tehke toiming pärast automaatse täieliku värskendamise (andmeallikad, ühtlustamine, segmendid, mõõtmed, ekspordid) lõpetamist
  - Määratlege ärimeetme jaoks läviväärtus. Näiteks saate luua teatise, mis saadetakse pärast määratletud lävendist möödumist. Lisaks toob päästik teavet, mis võimaldab teil luua Power Automate’is keerukamaid töövoogusid.    
  Lisateavet vaadake teemast [Power Automate’i konnektor](export-power-automate.md)

- **Eksport Facebooki reklaamihaldurisse**
  
  See suvand võimaldab teil segmente eksportida Facebooki reklaamihaldurisse. Segmendid eksporditakse kohandatud sihtrühmadena, et kasutada koondatud kliendiprofiile Facebooki turunduskampaaniates ja reklaamides. Kohandatud sihtrühmi saab kasutada ka Facebooki reklaamihalduri kaudu Instagrami kampaaniate loomiseks.    
  Lisateavet vaadake teemast [Facebooki reklaamihalduri konnektor](export-facebook.md).

#### <a name="predictions"></a>Prognoosid

- **Tellimise voolavuse prognoos**

  Järgige juhiseid, et luua voolavuse prognoos tellimuste alades, nagu pilveteenused, kliendi liikmesus ja muud sektorid. 

  Tellimuse voolavuse prognoosi funktsioon võimaldab teil prognoosida kliendipoolse tellimusepõhise toote või teenuse peatamise tõenäosust ilma andmeteadlase kaasamiseta. Kasutades prognoosi skoori saate kombineerida oma kliendi kohta muud teavet, et luua kõrge voolavuse riskiga segmendid. Selle segmendi abil saate kliente otsesihtida turundus-, klienditoe- ja muudes stsenaariumides, et vähendada kindlate klientide voolavusriski ning suurendada tulu ja vähendada kulusid.

  Kasutuskogemuse raames saate konfigureerida voolavuse määratluse oma ettevõttele spetsiifilise ajapõhise aknana. Näiteks video voogesituse ettevõte, millel on kuupõhine kordustellimuse protsess, võib kaaluda kliendi voolavusena 15 päeva pärast nende tellimuse lõppemist.

  Läbi prognoosi liikumise ajal me juhendame teid seoses andmetega, mida vajate, ja võimaldame teil vastendada teie ettevõtte andmeid väljadega, mis on vajalikud teie klientide voolavuse prognoosimiseks. Kui äriteave muutub, võite määrata ajakava oma süsteemist uue teabe hankimiseks, et kohanduda muutuvate ärioludega.    
  Lisateavet vaadake teemast [Tellimuse voolavuse prognoos (eelversioon)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmendid

- **Leia sarnased kliendid**
  
  Leidke tehisintellekti kasutades oma kliendibaasist sarnaseid kliente. Kahendliigenduse masinõppemudel määrab laiendatud segmendis klientidele sarnasuse skoori. Skoor põhineb sarnasusel lähtesegmendis olevate klientidega. Sõltuvalt sarnasuse skoorist lisatakse kliendiprofiilid vastloodud segmentidesse.

  Mõnikord nimetatakse seda digitaalses turunduses näiliselt modelleerimiseks, kasutades tehisintellekti mudelit, et aidata leida kliente, kes sarnanevad teie klientide teise segmendiga, arvestades rohkem atribuute. See mitte ainult ei võimalda teil valida atribuute, vaid võimaldab ka määratleda maksimaalse arvu kliente, kes peaksid olema selles uues segmendis. Tehisintellekti mudel arvutab seejärel iga kliendi puhul teie valitud atribuutide põhjal sarnasuse skoorid ja otsib kliente, kellel on kõrgem sarnasuse skoor. Tulemuseks olev segment sisaldab kliente, kes sarnanevad teie algse segmendi klientidele.    
  Lisateavet leiate teemast [Sarnased kliendid](find-similar-customer-segments.md).

- **Segmendi kattumine ja eristajad**

  Segmendi kattumine võimaldab vaadata, kui paljudel ja millistel klientidel on kaks või rohkem segmenti sarnased. Näiteks kuidas suurel hulgal kulutajate segment kattub suure rahuololuga klientide segmendiga või kuidas voolavate klientide segment kattub madala rahuloluga klientide segmendiga. Lisaks saate analüüsida, kuidas kattuvus muutub teie valitud lisatribuudi põhjal.

  Segmentide eristajad näitavad, mis eristab ühe segmendi teie teistest klientides või teistest segmentidest. Te peate vaid tuvastama segmendi ja süsteem tuvastab profiili atribuudid ja meetmed, mis eristavad segmendi eristajate järjestatud loendi kujul, mis on järjestatud kõige tugevamast eristajast kõige nõrgemani.    
  Lisateavet vaadake teemast [Segmendi ülevaated (eelversioon)](segment-insights.md).

- **Segmendi eluiga**
  
  Määrake segmendi aktiveerimiseks või desaktiveerimiseks ajakava.    
  Lisateavet vaadake teemast [Olemasolevate segmentide haldamine](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Mai 2020 värskendused

2020. aasta mai värskendused sisaldavad mitut funktsiooni, jõudlustäiendusi ja veaparandusi.

### <a name="new-and-updated-features-in-may-2020"></a>2020. a mai uued ja värskendatud funktsioonid

#### <a name="data-ingestion"></a>Andmete valmendamine

- **Reaalajas andmete valmendamine: ajaloo vaated**

  Reaalajas värskenduste valmendamiseks meie API-d kasutades saate näha nende värskenduste kuni 30 päeva koondatud ajalugu. Teil on juurdepääs kõigi õnnestunud või ebaõnnestunud API kõnede koondandmetele (sh nende tulemustele, lähtesüsteemile ja teistele kasulikele metaandmetele).    
  Lisateabe saamiseks vt [Reaalajas andmete valmendamine](real-time-data-ingestion.md).

- **Reaalajas andmete valmendamine: profiiliuuendused**

  See reaalajas andmete valmendamise laiend võimaldab teil mõne sekundiga näha muudatusi konkreetse kasutajaprofiili väljadele.    
  Lisaks tegevuste reaalajas funktsioonidele toetab süsteem profiiliväljade värskendamist madala latentsusega. Profiili väljade reaalajas värskendustel on aegumiskuupäev ja seega see pole kavandatud värskenduste asendamiseks.    
  Lisateabe saamiseks vt [Reaalajas andmete valmendamine](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Laiendatavus

- **Kliendikaardi lisandmoodul värskendatud ajakava ja lehejaotus**

  Kliendikaardi lisandmooduli lahenduse ajaskaala ühtib tegevuse ajaskaalaga. Ajaskaala lehejaotus paranes, kuvades korraga kuni 50 tegevust. Lisaks võimaldab see ajaskaalale laadida rohkem tegevusi.    
  Lisateavet vt teemast [Kliendikaardi lisandmoodul](customer-card-add-in.md).

- **Power Automate’i segmendi muudatuste päästik**

  Käivitab, et Power Automate’i päästikud määratlevad, mille jaoks te voo vormi saate luua. Äsja lisatud päästiku abil saate määratleda segmendi lävendi. Näiteks saate luua teatise, mis saadetakse pärast määratletud lävendist möödumist.    
  Lisateavet vt teemast [Power Automate’i konnektor](export-power-automate.md).

- **Kohandatud mudelite mitmeeksemplarine tugi**

  Konfigureerige kohandatud mudelite töövood erineva Azure’i masinõppe rentniku veebiteenusega. Uue töövoo loomise korral kohandatud mudelite jaoks saate sisse logida Azure'i masinõppe rentnikusse. See võimalus on olemasoleva integreerimise võimaluse lisand koos teie kohandatud Azure’i masinõppe veebiteenusega.    
  Lisateavet vt teemast [Kohandatud masinõppemudelid](custom-models.md).

#### <a name="segments"></a>Segmendid

- **Olemi tee automatiseerimine**

  Segmendi loomisel peavad kasutajad määratlema olemi tee. See võimalus on esimene samm olemi tee määratluse automatiseerimises, et saaksite keskenduda oma väljamõeldud segmentimise kriteeriumitele.    
  Kui olem, mille kaudu soovite oma kliendid segmentida, on otseselt seotud ühtlustatud kliendi olemiga, ei pea te olemi teed enam määratlema. Samas kui olemi võimalikke teesid on rohkem kui üks, peate selle siiski käsitsi määratlema.

- **Tegevused mitme segmendiga**
  
  Kasutajad saavad valida mitu segmenti ja teha nendega ühe klõpsuga toiminguid (nt segmentide värskendamine).    

- **Segmentide värskendamine**

  Kasutajad saavad värskendada ühe segmendi või valida ainult need segmendid, mida soovivad värskendada.    

  
- **Liidetud segmentide täiustused**

  Kasutajad saavad luua, redigeerida ja kustutada teistel segmentidel põhinevaid segmente. Näiteks segment, mis loodi teise segmendi põhjal, mis loodi kolmanda segmendi põhjal.    

- **Segmentide loendi leht**

  Segmentide lehe uus kujundus asutab loendivormingut, mis laseb teil korraga kuvada rohkem segmente. Segmentide kiiresti leidmiseks on lisatud otsinguväli. Kasutajad saavad nüüd rakendada toiminguid, nagu mitme segmendi korraga allalaadimine või kustutamine. Kasutusele on võetud uus trendi kasutuskogemus, et kiiresti tuvastada segmentide muudatused.    
  Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).

#### <a name="system-administration"></a>Süsteemihaldus

- **Customer Insights on saadaval rakenduses Microsoft Dynamics 365 Online Government**

  Aina enamate suhtluskanalite olemasolu tõttu on kodanike andmed hulgaliste süsteemide vahel laiali hajutatud, mis toob kaasa punkerdunud andmed ja kodanike suhtluste teabe tükeldatud vaate. Ilma iga kodaniku kanalite ülese suhtluse täieliku ülevaateta on valitsustel sellel skaalal moderniseerimine võimatu. Microsoft on võtnud endale kohustuse toetada valitsuse tehnoloogilisi vajadusi, et säilitada kodanike ootuseid järjekindlate ja reageerivate kogemuste osas.    
  2020. aasta väljalaske 1. lainega on riigiasutuste ühispilvkeskkonna (GCC) jaoks saadaval Dynamics 365 Customer Insights, mis on loodud vastama Ameerika Ühendriikide valitsusasutuste kõrgematele vastavusvajadustele. Valitsusasutused saavad kodanikest ühtlustatud ülevaate ja kasutavad eelnevalt loodud tehisintellekti, et saada ülevaateid, mis parandavad suhtlust, toetavad töötajaid ja muudavad kogukondi, leevendades IT keerukust ja ühtides Ameerika Ühendriikide vastavuse ja turvalisuse standarditega. Dynamics 365 Government vastab USA riski- ja loahalduse föderaalkava (Federal Risk and Authorization Management Program, FedRAMP) kõrgetele nõuetele, võimaldades Ameerika Ühendriikide föderaalasutustel saada kasu Microsofti pilveteenuse kulude kokkuhoiust ja rangetest turvameetmetest.

## <a name="april-2020-updates"></a>Aprill 2020 värskendused

2020. aasta aprilli värskendused sisaldavad mitut funktsiooni, jõudlustäiendusi ja veaparandusi.

### <a name="new-and-updated-features-in-april-2020"></a>2020. a aprilli uued ja värskendatud funktsioonid

#### <a name="activities"></a>Tegevused 

- **Kaarditegevuse olem standardse tegevustüübi jaoks**
  
  Tegevuse konfigureerimine ja talletamine põhinevad staatilisel kujundusel, et kuvada need ajaskaalal. Tegevuste semantiline tähendus, millel on tehisintellekti mudelites mitme kasutusjuhtumi jaoks potentsiaali, ei ole hetkel täielikult kasutuses. Plaanime tegevuse tüübi põhjal ja tegevuste paremaks semantiliseks mõistmiseks muuta tegevuse ajaskaala palju dünaamilisemaks. Selle funktsiooni eesmärk on tuvastada tegevuse tüüp, nagu on mis tahes valmendatud tegevuse jaoks Common Data Modelis määratletud.
  Lisateavet vt teemast [Klienditegevused](activities.md).

#### <a name="data-ingestion"></a>Andmete valmendamine

- **Reaalajas andmete valmendamine: tegevused**
  
  Reaalajas andmete valmendamine pakub andmeid kohe tarbimiseks, kuni järgmine ajastatud värskendamine toob need andmed andmeallikast.    
  Lisateabe saamiseks vt [Reaalajas andmete valmendamine](real-time-data-ingestion.md).

- **Andmete ettevalmistamise täiustused**
  
  Vaadake lisateavet olemis valmendatud andmete kohta. Andmete kokkuvõttega saate mõista andmete kvaliteedi tunnuseid, mis aitavad teil teha asjakohaseid toiminguid.    
  Lisateavet vt teemast [Olemi andmetega tutvumine](entities.md#exploring-a-specific-entitys-data).

- **Analüüsiandmete valmendamine Dynamics 365-st koos teenusega Common Data Service**
  
  Common Data Service'it saab kasutada andmeallikate loomiseks. Olemasolevad Dynamics 365 kliendid saavad teenusest Common Data Service teenusesse Customer Insights valmendada analüüsiolemeid. Üks andmeallikas saab samal ajal kasutada sama Common Data Service'i hallatud järve Customer Insightsi keskkonnas.    
  Lisateavet vt teemast [Andmete ühendamine Common Data Service’i hallatavas andmejärves](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Laiendatavus

- **LiveRampi eksportimine**

  Aktiveerige oma andmed LiveRamp®-is, et luua ühendus üle 500 digi-, sotsiaal- ja teleökosüsteemi platvormiga. Kasutage LiveRampis oma andmeid reklaamikampaaniate sihtimiseks, summutamiseks ja isikupärastamiseks.    
  Lisateavet vt teemast [LiveRamp&reg;-i konnektor](export-liveramp.md).

- **Customer Insightsi Teamsi lisandmoodul**
  
  Bot pakub ühendatud kliendiprofiilide otsinguvõimalusi. See kuvab kaardi kuni 15 väljaga tulemiks olevast kliendiprofiilist. Mitu vastet tagastavad tulemite loendi, kust saate valida soovitud profiili.    
  Lisateavet vt teemast [Customer Insightsi Teamsi robot](export-teams-bot.md).

#### <a name="measures"></a>Meetmed

- **Meetmete loendi leht**
  
  Meetmete lehe täiustused hõlmavad ühe meetmega ja korraga mitme meetmega seotud tegevuste toetamist. Lisaks leiate kiirotsingu välja, et meetmeid kiiresti leida ja jälgida.    
  Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).

- **Liidetud meetmete täiustused**
  
  Kasutajad saavad luua, redigeerida ja kustutada teistel meetmetel põhinevaid meetmeid. Näiteks meede, mis loodi teise meetme põhjal, mis loodi kolmanda meetme põhjal.

#### <a name="segments"></a>Segmendid

- **Teine tehtemärk**
  
  Avaldise IN tehtemärk võimaldab klientide segmentimist mitme võimaliku stringiväärtuse põhjal. Enne selle tehtemärgi lisamist pidite looma taolised segmendid mitme OR-tingimusega. Avaldise IN tehtemärk võimaldab teil teha seda ühe tingimusega.    
  Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).

#### <a name="system-administration"></a>Süsteemihaldus

- **Konfigureerimissätete uude keskkondade kopeerimine**
  
  Kopeerige oma konfiguratsioon ühest keskkonnast teise. Uue keskkonna loomisel saate valida olemasoleva keskkonna, millest soovite konfiguratsiooni vormi kopeerida. Hetkel toetama andmeallikaid, andmete ühtlustamist, seoseid, meetmeid ja kopeeritavaid segmente. Andmeallika mandaate ega tegelikke andmeid ei kopeerita.    
  Lisateavet leiate teemast [Keskkondade haldamine](manage-environments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]