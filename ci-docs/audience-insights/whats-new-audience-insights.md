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
ms.openlocfilehash: 9195770255bd798636b9532d6e1ca928345b3708
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376457"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>Mis on uut Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioonis?

Meil on hea meel teatada uusimatest värskendustest. Selles artiklis võetakse kokku avaliku eelversiooni funktsioonid, üldise kättesaadavuse täiustused ja funktsiooni värskendused. Pikaajaliste funktsiooni plaane vaadake teemast [Dynamics 365 ja Power Platformi väljaandeplaanid](/dynamics365/release-plans/).

Avaldame värskendusi regioonipõhiselt. Seega teatud regioonid võivad näha funktsioone enne teisi. Kui see pole teisiti määratud teisiti, ei pea te tegema mingeid toiminguid ja värskendame rakendust automaatselt ilma seisakuteta.

> [!TIP]
> Funktsioonitaotluste ja tootesoovituste esitamiseks ning hääletamiseks minge [Dynamics 365 portaali Application Ideas](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="february-2022-updates"></a>2022. aasta veebruari värskendused

2022. aasta veebruari värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="general-availability-for-prediction-models"></a>Prognoos mudelite üldine kättesaadavus

Out-of-the-box prognoos mudelid, sealhulgas **tellimuse churn**, **tehingu churn** ja **kliendi eluaegne väärtus (CLV),** muutuvad customer Insightsi osana üldiselt kättesaadavaks. 

Lisateavet vt teemast [Predictions overview](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Uus andmeallikas: integratsioon Azure Synapse Analytics (eelvaade)

Azure Synapse Analytics on ettevõtte analüüsiteenus, mis kiirendab aega andmeladude ja suurandmete süsteemide ülevaateks.

Kui teie asutus juba kasutab andmejärvede andmebaasides saadaolevate Azure Synapse Analytics analüüsivõimaluste täiustatud analüüsivõimalusi ja salvestab selle talletamiseks, saate need andmed hõlpsalt Customer Insightsi alla neelata. Lisateavet leiate teemast [Andmeallikas ühendamine Azure Synapse (eelvaade)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRampi rikastamine (eelvaade)

LiveRamp pakub deterministlikku võrguühenduseta identiteedilahendust ja kliendiandmete konsolideerimist. Saate vastendada kliendiandmetes olevad isikuidentifikaatorid AbiliTeci identiteedigraafikuga ja saada AbiliTeci ID-d. Seejärel saate neid ID-sid kasutada oma kliendiandmete paremaks ühendamiseks.

Lisateavet leiate teemast [Kliendiprofiilide rikastamine LiveRampi identiteediandmetega (Eelvaade)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Andmeallikate rikastamine (Eelvaade)

Kasutage andmeid sellistest allikatest nagu Microsoft ja teised partnerid, et rikastada oma kliendiandmeid enne andmete ühendamist. Andmeallikas rikastamine aitab luua suuremat andmete täielikkust ja kvaliteeti, mis aitab pärast andmete ühendamist saavutada paremaid tulemusi.

Lisateavet vt teemast [Enrichment for Data sources (Preview)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Keskkonna omaniku muutmine

Kuigi customer Insightsis võivad administraatoriõigused olla mitmel kasutajal, on keskkonna omanik ainult üks kasutaja. Täiustatud kogemus võimaldab teil muuta keskkonna omanikke ja nõuda omandiõigust, kui endine omanik organisatsioonist lahkub. 

Lisateavet leiate teemast [Keskkonna](manage-environments.md#change-the-owner-of-an-environment) omaniku muutmine.

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Andmete ettevalmistamise protsess loetleb rikutud kirjete korruptsioonipõhjuse

Andmete ettevalmistamise protsess näitab nüüd korruptsiooni põhjust kõigi väljade puhul, mille puhul on rikutud andmed individuaalsel kirjetasemel, et neid oleks lihtne tuvastada. 

Lisateavet vt teemast [Corrupted andmeallikad](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Kaasamisülevaadete võimaluse aruandlusfunktsioonide eelvaate lõpp

Kaasamise Dynamics 365 Customer Insights ülevaatevõime eelvaade lõppes 15. veebruaril 2022.  
See muudatus tähendab, et Customer Insightsi prooviversioon ei sisalda enam võimalust luua lehtreid ega muid aruandlusfunktsioone.

Kutsume teid üles uurima ja hindama Paljusid teisi Customer [Insightsi](https://dynamics.microsoft.com/ai/customer-insights/), Microsofti kliendiandmete platvormi (CDP) funktsioone.    
 
Üleminekuperioodil on olemasolevatel eelvaates osalejatel endiselt juurdepääs mõnele eelvaatefunktsioonile ja funktsioonile.

- Hankige kood veebisaidi või mobiilirakenduse jaoks vahendite tagamiseks 
- Sündmuste ja sündmuse atribuutide kuvamine 
- Täiustage allaneelatud ja rafineeritud sündmustega ühtseid profiile, et saada kasu nende kliendiandmete täielikust väärtusest
  
Üleminekuperioodil voogesitatakse jäädvustatud sündmused endiselt ühendatud Andmejärve. Kui see funktsioon on välja lülitatud, lõpetatakse andmete jagamine kaasamise ülevaadete ja vaatajaskonna ülevaadete vahel ning ühendatud salvestusruumile ei saadeta uusi sündmusi.
Kui teil on küsimusi võimaluste eelvaate lõppemise kohta, võtke otse ühendust oma Microsofti konto meeskonnaga. Teie konto meeskond hoiab teid kursis tulevaste käivitamistega. 

## <a name="january-2022-updates"></a>2022. a jaanuari värskendus

2022. aasta jaanuari värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Teie kliendi tagasiside sentimentaalne analüüs

Customer Insights pakub uut tehisintellektil põhinevat funktsiooni, et sünteesida klientide tundeid ja tuvastada konkreetseid äriaspekte kui sihipärase täiustamise võimalusi. Analüüsides oma klientide kirjalikku tagasisidet, saate täpse ülevaate odavalt. Sentimenti analüüs, mis põhineb loomuliku keele töötlemise (NLP) mudelitel, mis genereerivad iga kliendi ID jaoks kaks tuletatud ülevaadet. Sentiment skoor (–5 kuni 5) ja nimekiri kohaldatavatest äriaspektidest. 

Lisateavet leiate teemast [Tunnete analüüsimine klientide tagasisides (Eelvaade)](sentiment-analysis.md).


## <a name="december-2021-updates"></a>2021. aasta detsembrikuu värskendused

2021. aasta detsembri värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>Customer Insightsi logide edasisaatmine Azure Monitori

Customer Insights pakub otsest integratsiooni Azure Monitoriga. See funktsioon hõlmab auditiüritusi ja tegevusüritusi. Azure Monitori ressursilogid võimaldavad teil jälgida ja saata logisid Azure Storageisse, Azure Log Analyticsisse või voogesitada neid Azure Event Hubsi.

Lisateavet leiate teemast [Azure Monitoriga (Preview)Dynamics 365 Customer Insights sisselogimine](diagnostics.md).

### <a name="enrich-customer-profiles-with-engagement-data"></a>Kliendiprofiilide rikastamine kaasamisandmetega

Kasutage andmeid alates Microsoft Office 365, et rikastada oma kliendikonto profiile rakenduste kaudu Office 365 seotud töövõttude kohta. Kaasamisandmed koosnevad e-posti ja koosolekutegevusest, mis koondatakse konto tasemele. Näiteks ärikontolt saadetud e-kirjade arv või kontoga seotud kohtumiste arv. Andmeid üksikute kasutajate kohta ei jagata. See rikastamine on saadaval järgmistes piirkondades: Ühendkuningriigis, Euroopas, Põhja-Ameerikas.

Lisateavet leiate teemast [Kliendiprofiilide rikastamine kaasamisandmetega (eelvaade)](enrichment-office.md).

### <a name="advanced-data-unification-features"></a>Täpsemad andmete ühendamise funktsioonid

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>Konfliktilahenduspoliitikate lubamine üksikul atribuuditasemel

Kui pühendate olemis kliendikirjeid, ei pruugi te soovida valida võitjana täielikku kirjet. Nüüd lubame teil ühendada erinevate kirjete parimad väljad, mis põhinevad iga atribuudi reeglitel. Näiteks saate valida, kas jätta kõige värskem e-kiri JA kõige täielikum aadress erinevatest kirjetest. 

Nüüd saate määratleda üksikute atribuutide jaoks eraldi koostereeglid, pühendades ja ühendades kirjeid ühes olemis. Varem lubasime teil valida ainult ühe koostereegli (arvestuse pidamine müügivõlgade andmete täielikkuse põhjal) ja see reegel rakendati kirje tasemel kõigile atribuutidele. See ei ole ideaalne, kui mõned andmed, mida soovite säilitada, on kirjes A ja muud head andmed, mis on leitud kirjest B.

Lisateavet leiate teemast [Duplikaatide eemaldamise määratlemine vastendamise olemis](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="custom-rules-for-matching"></a>Sobitamise kohandatud reeglid

On aegu, mil peate määrama erandi üldreeglitest, et kirjeid mitte sobitada. See võib juhtuda, kui mitu inimest jagavad piisavalt teavet, et süsteem vastaks neile kui ühele isikule. Näiteks sama perekonnanimi kaksikud, kes elavad samas linnas ja jagavad sünnikuupäeva.

Erandid tagavad, et andmete ühendamise eeskirjades saab käsitleda ebaõiget andmete ühendamist. Reeglile saate lisada mitu erandit.

Lisateavet leiate teemast [Reegli erandite lisamine](match-entities.md#add-exceptions-to-a-rule).

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>Täiendavate konfliktide lahendamise poliitikate pakkumine ja atribuutide rühmitamise lubamine

See funktsioon võimaldab teil käsitleda väljade rühma ühe üksusena. Näiteks kui meie kirjed sisaldavad välju Address1, Address2, City, State ja Zip. Tõenäoliselt ei soovi me ühineda teise kirje aadressiga2, arvates, et see muudaks meie andmed täielikumaks.

Nüüd saate kombineerida seostuvate väljade rühma ja rakendada rühmale ühe koostepoliitika. 

Lisateavet leiate teemast [Väljarühma ühendamine](merge-entities.md#combine-a-group-of-fields).


## <a name="november-2021-updates"></a>2021. aasta novembri värskendused

2021. aasta novembri värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="segment-membership-now-available-in-dataverse"></a>Segmendi liikmelisus on nüüd saadaval rakenduses Dataverse

Segmendi liikmelisuse teave kliendiprofiilide kohta on nüüd saadaval Dataverse koos kliendiprofiilide ja ülevaadetega. Dynamics 365 tegevusrakendused ja mudelipõhised rakendused saavad neid andmeid kasutada konkreetse kliendi segmendi liikmelisuse üksikasjade otsimiseks.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>Tegevused toetavad ärikontode kontakttaseme üksikasju

Nüüd saate konfigureerida, kuvada ja filtreerida kontaktide tegevusi oma ärikonto tegevuse ajaskaaladel, et paremini mõista, millised kontokontaktid konkreetsetes tegevustes osalesid.

## <a name="october-2021-updates"></a>2021. aasta oktoobri värskendused

2021. aasta oktoobri värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="b-to-b"></a>B-B

Alates 2021. aasta oktoobrist saate Customer Insightsis töötada ärikontode ja nendega seotud kontaktidega. Varem oli rakendus enamasti kohandatud üksikutele tarbijatele. Uuendati mitmeid funktsioonivaldkondi, et toetada B-B stsenaariume lisaks uuele keskkonnatüübile. Toetatud B-B funktsioonide kohta leiate ülevaate teemast [Ärikontodega töötamine vaatajaskonna ülevaates](work-with-business-accounts.md).

Järgmistes jaotistes tuuakse esile mõned peamised valdkonnad, mida kohandati ettevõtluskontode ja üksiktarbijate toetamiseks.

#### <a name="export-segments-based-on-business-accounts"></a>Ärikontodel põhinevate segmentide eksportimine

Kogu segmendi eksport vaatajaskonna ülevaates on saadaval ärikontode kontekstis. Enamik segmendiekspordist nõuab täiendavat konfigureerimist ja [aluseks olevates segmentides prognoositud](segment-builder.md#create-a-new-segment) kontaktandmeid ärikontode puhul kehtivaks. Lisateavet vt [teemast Export segments](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>LinkedIn Adsi ekspordi kasutamine ärikontodega

LinkedIn Adsi eksport on nüüd saadaval kontaktide ja ettevõtete sihtimiseks ärikontode kontekstis. Kui valite LinkedIni ekspordi põhifookuseks ettevõtte sihtimise, saate eksportida ärikontodele rajatud segmente, ilma et oleks vaja kontaktandmeid projitseerida. Lisateavet leiate dokumentidest LinkedIn Adsi ekspordi [ning kontaktide sihtimise](export-linkedin-ads.md) ja [ettevõtte sihtimise](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) erinevuse [kohta](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Ärikontodel ja nende hierarhial põhinevate meetmete loomine

Mõõtkoostur võimaldab teil luua ärikontode ümber meetmeid ja kasutada valikuliselt hierarhiateavet. Hierarhiateavet kasutatakse mõõtarvutuse ümberarvestamiseks konto ja kõigi sellega seotud alamkontode lõikes. Näiteks saate luua selliseid meetmeid nagu kogutulu iga ärikontode rühma jaoks, mis on nende hierarhia järgi tuvastatud. Lisateavet leiate teemast [Näitajate määratlemine ja haldamine](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Segmentide loomine ärikontode ja nende hierarhia põhjal

Segmendikoosturi võimaldab teil luua ärikontode segmente, mis sisaldavad soovi korral segmendi iga ettevõtte kontaktteavet. Kui teil on kontohierarhia häälestatud, saate segmendi loomisel kasutada kontohierarhia teavet. Lisateavet leiate teemast [Uue segmendi](segment-builder.md#create-a-new-segment) loomine.

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Säilitage oma ettevõtte kontod sügavate ülevaadetega nende churn-tendentsist

Kliendi churn prognoos mudel toetab nüüd ka ärikontosid. Saate hinnata churn'i riski mitte ainult konto, vaid ka konto ja toote või teenuse kategooria kombinatsiooni puhul, mida nad teilt ostavad. See täiendus aitab teil mõista, kas konto lõpetab tõenäolisemalt teilt ostmise üldiselt või ainult teatud kaupade või teenuste kategooria jaoks. Selle AI-mudeli täiendavaks kasutamiseks loetletakse selles ka põhjused, miks konto tõenäoliselt paisub. Lisateavet vt teemast [Transaction churn prognoos (preview)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Ärikonto kontaktide kuvamine kliendivaates

Kui ärikontod vastendatakse seotud kontodega, kuvatakse rakenduses Customer Insights need seostuvad kontaktid kliendi üksikasjade vaate osana. Lisateavet leiate teemast [Kliendiprofiilid](customer-profiles.md).


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