---
title: Uued ja tulevased funktsioonid
description: Teave uute funktsioonide, täiustuste ja veaparanduste kohta.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 355dc22ac381145b231848830cefc47eda7968f4
ms.sourcegitcommit: 6944c1592877eb92ec789df5f2e0dbecef638837
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/15/2021
ms.locfileid: "6263246"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Mis on uut Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioonis?

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Meil on hea meel teatada uusimatest värskendustest. Selles artiklis võetakse kokku avaliku eelversiooni funktsioonid, üldise kättesaadavuse täiustused ja funktsiooni värskendused. Pikaajaliste funktsiooni plaane vaadake teemast [Dynamics 365 ja Power Platformi väljaandeplaanid](/dynamics365/release-plans/).

Avaldame värskendusi regioonipõhiselt. Seega teatud regioonid võivad näha funktsioone enne teisi. Kui see pole teisiti määratud teisiti, ei pea te tegema mingeid toiminguid ja värskendame rakendust automaatselt ilma seisakuteta.

> [!TIP]
> Funktsioonitaotluste ja tootesoovituste esitamiseks ning hääletamiseks minge [Dynamics 365 portaali Application Ideas](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="may-2021-updates"></a>Mai 2021 värskendused

2021. aasta mai värskendused sisaldavad mitmeid funktsioone, jõudluse versiooniuuendusi ja veaparandusi.

### <a name="data-ingestion"></a>Andmete valmendamine

- **Metaandmete või olemite määratluste vaatamine või muutmine andmete manustamise ajal oma Azure Data Lake Storage** andmetest. Saate nüüd metaandmeid või olemi määratlusi vaadata ja redigeerida sihtrühma ülevaadetes, kui manustada oma Azure Data Lake Storage kaustas Common Data Model andmed. See võimalus annab reaalajas tagasisidet, mudeli valideerimist ja tõrkekontrolli. See võimaldab teil sujuvalt redigeerida nii mudelit.json kui manifest.json faili.

### <a name="extensibility"></a>Laiendatavus

- **Täiustatud segmendiekspordid, kohandatud ajakava ja duplitseerimine**: Saate nüüd [vaadata kõiki kindla segmendi eksporte](export-destinations.md#view-exports-and-export-details) loendis. See uus vaade aitab hallata kindla segmendi kasutamist ja kohandada olemasolevaid või luua uusi eksporte.    
  Saate [kohandatud värskendusgraafikuid määratleda](export-destinations.md#schedule-and-run-exports) nii üksiku ekspordi kui ka mitme ekspordi jaoks korraga. Kuni praeguseni käitatakse kogu eksporti iga süsteemivärskendusega.    
  Selle asemel, et luua uus eksport algusest peale, võite aja säästmiseks alustada olemasoleva ekspordiga.

- **Microsoft Advertising ekspordi segmendid** Oleme laiendanud oma ekspordi sihtkohti kaasates Microsoft Advertisingu. Looge oma koondatud kliendiprofiiliandmetega Microsoft Advertisingus kliendivaste sihtrühmasid ja kasutage neid oma reklaamikampaaniates. Lisateavet leiate teemast [Segmentide eksportimine rakendusse Microsoft Advertising](export-microsoft-advertising.md).

- **Segmentide eksportimine LinkedIn Adsi**. Oleme laiendanud meie ekspordiga seotud kaasates LinkedIn Adsi ja võimaldada teil avada kontaktide sihtimist ja ettevõtte sihtimist LinkedIni kaudu, eksportides oma ühendatud kliendiprofiili andmed. Lisateavet leiate teemast [Segmentide eksportimine rakendusse LinkedIn Ads](export-linkedin-ads.md).


- **Omnisend ekspordi segmendid** Oleme laiendanud oma ekspordi sihtkohti kaasates Omnisendi. Kasutage Omnisendiga kampaaniate loomiseks, meiliturunduse pakkumiseks ja konkreetsetelt kliendirühmade kasutamiseks sihtrühma ülevaates loodud segmente. Lisateavet leiate teemast [Segmentide eksportimine rakendusse Omnisend](export-omnisend.md)

### <a name="predictions"></a>Prognoosid

- **Sisendandmete kasutatavuse aruanne**. Sisendandmete kasutatavuse aruanne annab sisestatud vaate tõrgetest ja hoiatustest, mida teie "karbist väljas" prognoosid võivad põhjustada. See annab ka soovitusi, kuidas mudeli tulemuslikkust parandada.    
  Aruanne on saadaval pärast seda, kui mudel on oma treeninguprotsessi lõpetanud. See luuakse iga mudeli jaoks eraldi, olenemata sellest, kas see õnnestus või mitte.
  See funktsioon on praegu saadaval ainult mudeliga Transaction Churn. Lisateavet leiate teemast [Sisendandmete kasutusaruanne](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Suhtlused

- **Seose visualiseerija**. Seose visualiseerija võimaldab näha kõiki olemasolevaid seoseid olemite ja nende kardiaalsust. Seosed on nüüd korraldatud rühmadena: kasutaja loodud, süsteemi ja päritud seosed. Vaate saate eksportida ka pildina. Lisateavet leiate teemast [Kuva seosed](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Aprill 2021 värskendused

2021. aasta aprilli värskendused sisaldavad mitmeid funktsioone, jõudluse versiooniuuendusi ja veaparandusi.

### <a name="data-unification"></a>Andmete koondamine
 
- **Täiustatud ühendamiskogemus andmete ühendamiseks**    
  
   Meil on nüüd täiustatud kasutajakogemus andmete ühendamise protsessi ühendamise konfiguratsioonis. Muudatused hõlmavad ühendatud väljade intuitiivset tellimist ning üksikasjalikku statistikat kombineeritud ja üksikväljade kohta.

- **Olemi kordustellimine ja kõigi lähtekirjete konfigureerimine KCustomer entity -sse**  
      
   Saate olemeid ümberjärjestada ja eemaldada olemasolevast liitmisplaanist andmete ühendamise protsessis. See annab paindlikkuse sobitamisprotsessis olevate üksuste ümberkorraldamine vastavalt ärivajadustele. Lisaks lubame kaasata kõik vastendamata kirjed lõpliku *Kliendi* olemisse, mis võimaldab neil määratleda oma kliendiprofiili andmekogumi määratluse.

### <a name="enrichments"></a>Rikastamised

 - **Uus rikastamine: Aadresside täiustamine**    
  
   Meil on hea meel tutvustada uut rikastamist, et parandada aadresse teie kliendiandmetes. Teie andmetes kuvatud aadressid võivad olla struktureerimata, mittetäielikud või valed. See funktsioon kasutab Microsofti mudeleid, et normaliseerida ja rikastada teie andmed Common Data Model vormingusse, et saada paremat täpsust ja ülevaadet.
 
   Lisateavet leiate teemast [Kliendiprofiilide rikastamine täiustatud aadressidega](enrichment-enhanced-addresses.md).

- **Juhendav konfiguratsioonikogemus rikastamiseks**    
  
   Me vaatasime konfiguratsioonikogemuse rikastamiseks üle lihtsa, juhendatud kogemusega. Nüüd on teil rikastamise loomiseks ja redigeerimiseks selge samm-sammult protsess.
 
   Lisaks eraldasime ühenduste konfiguratsiooni muude tootjate rikastamiseks, et sama ühendust kasutataks mitmeks rikastamiseks. Uusi ühendusi saavad konfigureerida ainult administraatorid, kuid loodud ühendused on alati saadaval nii administraatoritele kui ka kaastöötajatele.    

   Lisateavet leiate teemast [Ühenduste ülevaade](connections.md).

- **Mitu sama tüüpi rikastust**    
  
   Lubame kasutajatel nüüd luua ja hallata mitut sama rikastustüübi rikastustüüpi. Näiteks saate nüüd luua kaks eraldi aadressi rikastamiseks, et rikastada kahte erinevat kliendisegmenti. Piirangud kehtivad sama tüüpi rikastusastmete arvule ja need võivad sõltuvalt rikastustüübist olla erinevad.
  
   Lisateavet vaadake teemast [Kliendiprofiilide rikastamine](enrichment-hub.md).

## <a name="march-2021-updates"></a>Märts 2021 värskendused

2021. aasta märtsi värskendused sisaldavad mitmeid funktsioone, jõudluse versiooniuuendusi ja veaparandusi.

### <a name="activities"></a>Tegevused 

- **Tegevuseviisard ja semantilised tüübid**

   Olme tiustanud ja värskendanud tegevuse kaardistamise kogemust, et juhendada ja lihtsustada tegevuse kaardistamise loomist. Selles uues kogemuses saavad kasutajad juhendatud kogemuse, et aidata protsessi iga etapi lõpuleviimist. Tegevuse kaardistamise etapis saab kasutaja lisaks paljude tegevusetüüpide vahel valimisele valida andmete semantilise kaardistamise järgnevaks: *Tellimus* ja/või *Müügitellimusye rida* tegevusvaldkonna standardsetele skeemidele, mida saab kasutada edaspidise tarbimise jaoks.   

   Lisateavet vt teemast [Klienditegevused](activities.md).

### <a name="data-ingestion"></a>Andmete valmendamine

- **Looge ühendus asutusesiseste andmeallikatega, kasutades Power Platform andmevoogu ja väravaid** Meil on hea meel teatada Power Platform andme voogude ja asutusesisese ühenduvuse kasutamise väravate eelvaatest Customer Insights'is, seostatud Power Platform või Dataverse keskkonnaga. Mis tahes uued Customer Insights keskkonnas lingitud Dataverse keskkonnaga loodud andmeallikad on vaikimisi Power Platform andmevood, mis toovad kaasa asutusesisene ja rikkaliku pistikute ja muundamisvõimaluste komplekti.

### <a name="extensibility"></a>Laiendatavus

- **Ekspordid, mis on korraldatud ühenduste ja ekspordiga** Oleme muutnud lehe **Ekspordi sihtkohad** nime **Ühendused** ja lisanud **Ekspordi** jaoks eraldi lehe. Selle värskenduse osana teisaldame olemasoleva ekspordi ühenduse paarideks ja selle ühenduse abil eksportimiseks. Administraatoritel on nüüd väljaminevate andmete osas rohkem selgust **Ühendused** lehel. Kõigil kasutajarollidel on juurdepääs lehele **Ekspordid**, kuid ainult administraatorid saavad valida, kas kaastöötajad saavad jagatud ühendustega redigeerida teatud eksporti.     
  Lisateavet leiate teemast [Ühenduste ülevaade](connections.md) ja [ja ekspordi ülevaade](export-destinations.md).

- **Campaign Monitor eksportige segmendid** Oleme laiendanud oma ekspordi sihtkohti kaasates Campaign Monitori. Nüüd saate eksportida segmente Customer Insights Campaign Monitor loenditesse ja kasutada neid oma turunduskampaaniate lähteandmetena.    
   Lisateavet leiate teemast [Eksportimine Campaign Monitori](export-campaign-monitor.md).

- **Constant Contact ekspordi segmendid** Oleme laiendanud oma ekspordi sihtkohti kaasates Constant Contacti. Nüüd saate eksportida segmente Customer Insights Constant Contact loenditesse ja kasutada neid oma turunduskampaaniate lähteandmetena.   
   Lisateavet leiate teemast [Eksportimine Constant Contacti](export-constant-contact.md).

- **RollWorks ekspordi segmendid** Oleme laiendanud oma ekspordi sihtkohti kaasates RollWorksi. Nüüd saate eksportida segmente Customer Insights RollWorks publikule ja kasutada neid oma B2B turunduskampaaniate lähteandmetena.    
   Lisateavet leiate teemast [Eksportimine RollWorksi ](export-rollworks.md).

- **Snapchat ekspordi segmendid** Oleme laiendanud oma ekspordi sihtkohti kaasates Snapchati. Nüüd saate eksportida segmente Customer Insights Snapchat publikule ja kasutada neid oma turunduskampaaniate lähteandmetena.     
   Lisateavet leiate teemast [Eksportimine Snapchati](export-snapchat.md).

### <a name="predictions"></a>Prognoosid

- **Tootefiltrite kasutamine prognoosivas toote soovituses** Oleme lisanud võimaluse kasutada tootefiltreid meie toote soovitusmudelis. Nüüd saate luua prognoosi, mis kasutab ainult teie toodete alamhulka.    
   Lisateavet leiate teemast [Tootefiltrite konfigureerimine](predict-product-recommendation.md#configure-product-filters).

- **Segmentide loomine prognoosimudelile** Oleme lisanud kiire viisi segmentide loomiseks, kasutades prognoosimudelit. Mudelitulemite lehel saate hõlpsasti luua uue segmendi, valides uue suvandi **Loo segment**.    
  Lisateavet leiate teemast [Segmendi loomine prognoosimudeli põhjal](prediction-based-segment.md).

- **Tootesoovituste seletused** Oleme lisanud teavet, mis selgitab peamisi tegureid, mida tehisintellekti mudel on tootesoovituste loomiseks õppinud, ja seda, mil määral need tegurid aitavad tootesoovitustele kaasa. See teave lisatakse mudelitulemite kuvale.    
   Lisateavet leiate teemast [Prognoos oleku ja tulemuste läbivaatamine](predict-product-recommendation.md#review-a-prediction-status-and-results).

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




[!INCLUDE[footer-include](../includes/footer-banner.md)]