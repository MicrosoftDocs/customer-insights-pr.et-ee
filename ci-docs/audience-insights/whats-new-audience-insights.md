---
title: Uued ja tulevased funktsioonid
description: Teave uute funktsioonide, täiustuste ja veaparanduste kohta.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 667a984f1a2287456f4e6324eafe628fba957bf5
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232653"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Mis on uut Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioonis?



Meil on hea meel teatada uusimatest värskendustest. Selles artiklis võetakse kokku avaliku eelversiooni funktsioonid, üldise kättesaadavuse täiustused ja funktsiooni värskendused. Pikaajaliste funktsiooni plaane vaadake teemast [Dynamics 365 ja Power Platformi väljaandeplaanid](/dynamics365/release-plans/).

Avaldame värskendusi regioonipõhiselt. Seega teatud regioonid võivad näha funktsioone enne teisi. Kui see pole teisiti määratud teisiti, ei pea te tegema mingeid toiminguid ja värskendame rakendust automaatselt ilma seisakuteta.

> [!TIP]
> Funktsioonitaotluste ja tootesoovituste esitamiseks ning hääletamiseks minge [Dynamics 365 portaali Application Ideas](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="january-2022-updates"></a>2022. a jaanuari värskendus

2022. aasta jaanuari värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Kliendi tagasiside tundeanalüüs

Customer Insights pakub uut tehisintellektil põhinevat funktsiooni, et sünteesida klientide tundeid ja tuvastada konkreetsed äriaspektid sihipäraste täiustuste võimalustena. Analüüsides oma klientide kirjalikku tagasisidet, saate täpseid teadmisi madalate kuludega. Sentimenti analüüs, mis põhineb loomuliku keele töötlemise (NLP) mudelitel, mis genereerivad iga kliendi ID kohta kaks tuletatud ülevaadet. Sentiment skoor (-5 kuni 5) ja nimekiri kohaldatavatest äriaspektidest. 

Lisateavet vt teemast [Analyze sentiment in customer feedback (Preview)](sentiment-analysis.md).


## <a name="december-2021-updates"></a>2021. aasta detsembrikuu värskendused

2021. aasta detsembri värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>Customer Insightsi logide edastamine Azure Monitori

Customer Insights pakub otsest integreerimist Azure Monitoriga. See funktsioon hõlmab auditiüritusi ja tegevusüritusi. Azure Monitori ressursilogid võimaldavad teil jälgida ja saata logisid Azure Storage'i, Azure Log Analyticsisse või voogesitada neid Azure Event Hubsisse.

Lisateavet vt teemast [Log forwarding with Dynamics 365 Customer Insights Azure Monitor (Preview)](diagnostics.md).

### <a name="enrich-customer-profiles-with-engagement-data"></a>Kliendiprofiilide rikastamine kaasamisandmetega

Kasutage andmeid Microsoft Office 365, et rikastada oma kliendikonto profiile rakenduste kaudu Office 365 seotud töövõttude kohta. Töövõtuandmed koosnevad e-posti ja koosolekutegevusest, mis koondatakse konto tasandile. Näiteks ettevõttekontolt saadetud e-kirjade arv või kontoga kohtumiste arv. Üksikute kasutajate kohta andmeid ei jagata. See rikastamine on saadaval järgmistes piirkondades: Ühendkuningriik, Euroopa, Põhja-Ameerika.

Lisateavet vt teemast [Rikasta kliendiprofiile kaasamisandmetega (eelvaade)](enrichment-office.md).

### <a name="advanced-data-unification-features"></a>Täpsemad andmete ühendamise funktsioonid

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>Konflikti lahendamise poliitikate lubamine üksikul atribuuditasemel

Kliendikirjete lahutamisel olemis ei pruugi te soovida võitjana täielikku kirjet valida. Nüüd lubame teil ühendada parimad väljad erinevatest kirjetest, mis põhinevad iga atribuudi reeglitel. Näiteks saate säilitada kõige uuema e-kirja JA kõige täielikuma aadressi erinevatest kirjetest. 

Nüüd saate määratleda üksikute atribuutide eraldi koostereeglid, eraldades ja ühendades kirjeid ühes olemis. Varem lubame teil valida ainult ühe koostereegli (säilitades kirjeid recency andmete täielikkuse alusel) ja see reegel rakendati kirje tasemel kõigile atribuutidele. See pole ideaalne, kui mõned andmed, mida soovite säilitada, on leitud kirjest A ja muudest B-kirjest leitud headest andmetest.

Lisateavet leiate teemast [Duplikaatide eemaldamise määratlemine vastendamise olemis](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="custom-rules-for-matching"></a>Kohandatud reeglid sobitamiseks

On aegu, mil peate määrama erandi üldistest reeglitest, et kirjeid mitte sobitada. See võib juhtuda, kui mitu inimest jagavad piisavalt teavet, et süsteem sobiks neile ühe isikuna. Näiteks sama perekonnanimi kaksikud, kes elavad samas linnas ja jagavad sünnikuupäeva.

Erandid tagavad, et andmete ebaõiget ühendamist saab käsitleda ühtlustamiseeskirjades. Reeglile saate lisada mitu erandit.

Lisateavet leiate teemast [Reegli](match-entities.md#add-exceptions-to-a-rule) erandite lisamine.

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>Täiendavate konfliktide lahendamise poliitikate pakkumine ja atribuutide rühmitamise lubamine

See funktsioon võimaldab teil käsitleda väljade rühma ühe ühikuna. Näiteks kui meie kirjetes on väljad Aadressid1, Aadress2, Linn, Osariik ja Zip. Tõenäoliselt ei soovi me ühineda teise kirje aadressiga2, arvates, et see muudaks meie andmed täielikumaks.

Nüüd saate ühendada seostuvate väljade rühma ja rakendada rühmale ühe koostepoliitika. 

Lisateavet leiate teemast [Väljade](merge-entities.md#combine-a-group-of-fields) rühma ühendamine.


## <a name="november-2021-updates"></a>2021. aasta novembri värskendused

2021. aasta novembri värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="segment-membership-now-available-in-dataverse"></a>Segmendi liikmelisus on nüüd saadaval Dataverse

Kliendiprofiilide segmendi liikmelisuse teave on nüüd saadaval Dataverse koos kliendiprofiilide ja ülevaadetega. Dynamics 365 tegevusrakendused ja mudelipõhised rakendused saavad neid andmeid kasutada, et otsida konkreetse kliendi segmendi liikmelisuse üksikasju.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Tegevused toetavad ärikontode kontakttaseme üksikasju

Nüüd saate konfigureerida, kuvada ja filtreerida oma ettevõtte ettevõtte tegevuse ajaskaalal kontaktide tegevusi, et paremini mõista, millised kontokontaktid konkreetsetes tegevustes osalesid.

## <a name="october-2021-updates"></a>2021. aasta oktoobri värskendused

2021. aasta oktoobris sisaldavad värskendused uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="b-to-b"></a>B-B-le

Alates 2021. aasta oktoobrist saate customer Insightsis töötada ärikontode ja nendega seotud kontaktidega. Varem oli rakendus enamasti kohandatud üksiktarbijatele. B-B-stsenaariumide toetamiseks värskendati mitmeid funktsioonialasid, et toetada uut keskkonnatüüpi B-B-stsenaariume. Toetatud B-to-B funktsioonide kohta leiate ülevaate teemast [Ärikontodega töötamine vaatajaskonna ülevaates](work-with-business-accounts.md).

Järgmistes jaotistes tuuakse välja mõned peamised valdkonnad, mida kohandati ettevõtete kontode ja üksiktarbijate toetamiseks.

#### <a name="export-segments-based-on-business-accounts"></a>Ärikontodel põhinevate segmentide eksportimine

Kogu segmendi eksport vaatajaskonna ülevaates on saadaval ärikontode kontekstis. Enamik segmendieksporti nõuab, et aluseks olevates segmentides prognoositud [täiendav konfiguratsioon ja](segment-builder.md#create-a-new-segment) kontaktteave kehtiksid ärikontode jaoks. Lisateavet vt teemast [Export segments](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>LinkedIn Adsi ekspordi kasutamine ärikontodega

LinkedIn Adsi eksport on nüüd saadaval kontaktide ja ettevõtte sihtimiseks ärikontode kontekstis. Kui valite LinkedIni ekspordi põhifookuseks ettevõtte sihtimise, saate eksportida ärikontodele rajatud segmente ilma kontaktandmeid projitseerida. Lisateabe saamiseks minge LinkedIn Adsi ekspordi [ning kontaktide sihtimise](export-linkedin-ads.md) ja [ettevõtte sihtimise erinevuse kohta](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) käivate [dokumentide juurde](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Ärikontodel ja nende hierarhial põhinevate meetmete loomine

Mõõdu koostaja võimaldab teil luua ettevõttekontode ümber meetmeid ja kasutada valikuliselt hierarhiateavet. Hierarhiateavet kasutatakse mõõdu arvutamise arvestuse võtmiseks kontol ja kõigil selle seotud alamkontodel. Näiteks saate luua mõõdud, näiteks kogutulu iga nende hierarhia järgi tuvastatud ärikontode rühma jaoks. Lisateavet leiate teemast [Näitajate määratlemine ja haldamine](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Segmentide loomine ärikontode ja nende hierarhia põhjal

Segmendikoosturil on võimalik luua ärikontode segmente, mis valikuliselt sisaldavad segmendi iga ettevõtte kontaktandmeid. Kui teil on kontohierarhia seadistatud, saate segmendi loomisel kasutada kontohierarhia teavet. Lisateavet leiate teemast [Uue segmendi](segment-builder.md#create-a-new-segment) loomine.

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Säilitage oma ärikontod sügavate ülevaadete kohta nende churn-tendentsist

Kliendi churn prognoos mudel toetab nüüd ka ärikontosid. Saate hinnata mitte ainult konto, vaid ka konto ja toote või teenuse kategooria kombinatsiooni, mida nad teilt ostavad. See täiendus aitab teil mõista, kas konto lõpetab tõenäolisemalt teilt üldiselt ostmise või ainult teatud kaupade või teenuste kategooria jaoks. Selle AI-mudeli täiendavaks abistamiseks loetletakse ka põhjused, miks konto tõenäoliselt hakkab. Lisateavet vt teemast [Transaction churn prognoos (preview)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Ärikonto kontaktide kuvamine kliendivaates

Kui ärikontod on vastetatud seotud kontodega, kuvab rakendus Customer Insights need seotud kontaktid kliendi üksikasjade vaate osana. Lisateavet leiate teemast [Kliendiprofiilid](customer-profiles.md).


## <a name="september-2021-updates"></a>2021. aasta septembri uuendused

2021. aasta septembri värskendused sisaldavad uusi funktsioone, jõudluse versiooniuuendusi ja veaparandusi.

### <a name="activities"></a>Tegevused 

- **Tegevuse ajaskaala täiustused** Oleme laiendanud kliendiprofiilide tegevuse ajaskaala filtreid. Uue filtri abil saate filtreerida ka tegevusetüübi ja kuupäeva alusel. Kuupäevi saab filtreerida erinevate tingimuste abil. Lisateavet leiate teemast [Kliendiprofiilide tegevuse ajaskaala vaatamine](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Suhtlused

- **Mitme-toeline seose tugi** Tegevuste konfigureerimisel ja olemite vaheliste seoste määratlemisel saate kasutada mitme-toelisi seoseid. Mitme-toelised seosed kasutavad kahe olemi ühendamiseks vahepealset olemit. Tegevuse konfigureerimisel saate kasutada mitme-toelist seost oma tegevuse olemi ühendamiseks vahepealse olemiga ja seejärel kliendi olemiga. Saate ühendada mitme-toelised seosed mitme-teeliste seostega. Lisateavet leiate teemast [Mitme-toeline seos](relationships.md#multi-hop-relationship).

- **Mitme-teeline seose tugi** Tegevuste konfigureerimisel ja olemite vaheliste seoste määratlemisel saate kasutada mitme-teelisi seoseid. Mitme-teelised seosed seostavad lähteolemi mitme olemiga. Tegevuse konfigureerimisel saate kasutada mitme-teelist seost oma tegevuse olemi ühendamiseks rohkem kui ühe kliendi olemiga. Saate ühendada mitme-teelised seosed mitme-toeliste seostega. Lisateavet leiate teemast [Mitme-teeline seos](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>2021. aasta augusti värskendused

2021. aasta juuli ja augusti värskendused sisaldavad uut funktsiooni, jõudluse versiooniuuendusi ja veaparandusi.

### <a name="extensibility"></a>Laiendatavus

- **Eksportige segmendid Klaviyosse** Oleme laiendanud oma [ekspordi sihtkohti, et kaasata Klaviyo](export-klaviyo.md). Saate nüüd eksportida segmente üldistesse kampaaniatesse, teostada meiliturundust ja töötada koos konkreetse kliendigrupiga Klaviyoga. 


## <a name="june-2021-updates"></a>2021. juuni värskendused

2021. aasta juuni värskendused sisaldavad mitut funktsiooni, jõudlustäiendusi ja veaparandusi.

### <a name="data-ingestion"></a>Andmete valmendamine

- **Täiustatud andmete ühendamise protsessi värskendused** Saate nüüd vaadata rohkem moodulkujulisi, täiustatud dünaamilisi olekuvärskendusi [andmete ühendamise protsessi](data-unification.md) etappides. See funktsioon võimaldab teil protsessivoo mõistes jälgida üksikasjalikke edusamme ja tegutseda, kui mõnes sammus on vaja tähelepanu.

### <a name="extensibility"></a>Laiendatavus

- **Segmentide ja muude andmete eksportimine Salesforce'i turunduse pilve** on laiendatud meie ekspordisihtkohti, et lisada [Salesforce'i turunduse pilve](export-salesforce.md). Saate nüüd eksportida segmente ja muud tüüpi andmeid Saleforce turunduse pilve läbi kaubamärgiga varustatud SFTP ekspordi. Andmete importimist saab Salesforce'is täielikult automatiseerida ja kasutada tõhusamate turunduskampaaniate loomiseks.  
 
- **Eksportige segmendid aktiivsesse kampaaniasse** Oleme laiendanud oma ekspordi sihtkohti, et kaasata [aktiivne kampaania](export-active-campaign.md). Saate nüüd eksportida segmente üldistesse kampaaniatesse, teostada meiliturundust ja töötada koos konkreetse kliendigrupiga Aktiivses Kampaanias.
 
- **Eksportige segmendid Sendinbluesse** Oleme laiendanud oma ekspordi sihtkohti, et kaasata [Sendinblue](export-sendinblue.md). Saate nüüd eksportida segmente üldistesse kampaaniatesse, teostada meiliturundust ja töötada koos konkreetse kliendigrupiga Sendinbluega.
 
### <a name="ux-updates"></a>UX Värskendused 

- **Uue ja täiustatud klientide leht ja profiili üksikasjade leht** Oleme kujundanud ümber lehe Kliendid ning profiili üksikasjade lehed, et parandada kasutajakogemust ja jõudlust . Nende muudatustega saate kliente vaadata, sortida, otsida ja filtreerida. Filtrid on nüüd URL-is esitatud, et otsingutulemusi teiste kasutajatega sujuvalt ühiskasutusse anda. Otsingutulemusi saab salvestada ka segmendina.    
  Kliendiprofiilide üksikasjade leht rühmitab nüüd andmed mitmesugustes kaasates, nagu demograafilised andmed, ID-d ja muud profiiliatribuudid, et parandada loetavust. Teised jaotised profiili üksikasjade lehel on nüüd interaktiivsemad. Näiteks tegevuste jaotis võimaldab nüüd filtreerimist ja sortimist.


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

- **RollWorks ekspordi segmendid** Oleme laiendanud oma ekspordi sihtkohti kaasates RollWorksi. Nüüd saate eksportida segmente Customer Insightsist RollWorksi sihtrühmadele ja kasutada neid B2B-reklaamide lähtejoonena.    
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

  Administraatorid saavad kopeerida keskkonnakonfiguratsioonid uude keskkonda samas organisatsioonis. See funktsioon laieneb kopeerimiskeskkonna funktsioonile juhtudel, kui andmeallikad põhinevad Microsoft Dataverse-i hallataval data lake -il või Common Data Modeli kaustadel.

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