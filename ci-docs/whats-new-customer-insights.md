---
title: Mida on uut rakenduses Dynamics 365 Customer Insights
description: Teave uute funktsioonide, täiustuste ja veaparanduste kohta.
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 4b5b95d1774d22827b3c08c2b6ccbb7858f1b04b
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054013"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Mida on uut rakenduses Dynamics 365 Customer Insights

Meil on hea meel teatada uusimatest värskendustest. Selles artiklis võetakse kokku avaliku eelversiooni funktsioonid, üldise kättesaadavuse täiustused ja funktsiooni värskendused. Pikaajaliste funktsiooni plaane vaadake teemast [Dynamics 365 ja Power Platformi väljaandeplaanid](/dynamics365/release-plans/).

Avaldame värskendusi regioonipõhiselt. Seega teatud regioonid võivad näha funktsioone enne teisi. Kui see pole teisiti määratud teisiti, ei pea te tegema mingeid toiminguid ja värskendame rakendust automaatselt ilma seisakuteta.

> [!TIP]
> Funktsioonitaotluste ja tootesoovituste esitamiseks ning hääletamiseks minge [Dynamics 365 portaali Application Ideas](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="may-2022-updates"></a>Mai 2022 värskendused

2022. aasta mai värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="updated-data-unification-experience"></a>Värskendatud andmete ühendamise kogemus

 Andmete ühendamine võimaldab teil ühendada kord erinevad andmeallikad üheks põhiandmestikuks, mis pakub nendest andmetest ühtset ülevaadet. Andmeid saab ühendada ühes olemis või mitmes olemis. Esmalt valite olemid ja lähteväljad [,](map-entities.md) eemaldate [duplikaatkirjed](remove-duplicates.md), määrate reeglid sobivate tingimuste jaoks [ja määratlete](match-entities.md), milliseid [välju ühtsetesse kliendiprofiilidesse kaasata](merge-entities.md).

Lisateavet leiate teemast [Andmete ühendamise ülevaade](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Värskendatud avaleht Customer Insightsis

**Home** juhendab teid põhifunktsioonide konfiguratsiooniprotsessis ning annab ülevaate segmentidest, mõõtudest ja rikastamisandmetest. Oleme värskendanud kogemust, et pakkuda lühidalt asjakohasemat teavet.

Lisateavet leiate teemast [Customer Insightsi](home.md) uurimine.

### <a name="track-usage-of-a-segment"></a>Segmendi kasutamise jälgimine

Nüüd [saate jälgida segmendi](segments.md#track-usage-of-a-segment) kasutamist rakendustes, mis põhinevad Customer Insightsiga ühendatud organisatsioonil Dataverse. Dynamics 365 Marketingi [kliendireisidel kasutatavate Customer Insightsi segmentide puhul](/dynamics365/marketing/real-time-marketing-ci-profile) teavitab süsteem teid selle segmendi kasutamisest.

### <a name="export-to-criteo"></a>Eksport Criteosse

Criteo on veebiplatvorm, mis aitab kasutajatel digitaalset reklaami hallata. Nüüd saate eksportida ühtsete kliendiprofiilide segmente kampaaniate loomiseks, e-posti turunduse pakkumiseks ja Criteoga konkreetsete kliendirühmade kasutamiseks.

Lisateavet vt teemast [Export segments to Criteo (preview)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Täiustatud dokumentatsiooni struktuur keskkonna loomiseks

Oleme uuesti üle vaadanud Customer Insightsis keskkondade loomise ja haldamisega seotud spikridokumendid. Artiklid on nüüd rühmitatud sisukorra sõlme Environments alla. Ümberkorraldatud artiklid annavad rohkem juhiseid erinevate keskkondade loomise viiside kohta ja selgema struktuuriga. Kui teil on tagasisidet jagada, andke meile sellest juhtelementide kaudu teada abiartiklite lõpus.

Lisateavet leiate teemast [Kuidas: Luua uus keskkond](create-environment.md).

## <a name="april-2022-updates"></a>Aprill 2022 värskendused

2022. aasta aprilli värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet rikastamine (Preview)

Dun & Bradstreet pakub ettevõtetele äriandmeid, analüütikat ja teadmisi. See võimaldab ettevõtetel kliendi koondprofiilidega klientide andmeid rikastada. Rikastamine hõlmab selliseid atribuute nagu DUNS-i number, ettevõtte suurus, asukoht, tööstus ja palju muud.

Lisateavet vt teemast [Ettevõtte profiilide rikastamine Dun & Bradstreet'iga (Preview)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Mõõtude tüübi määratlemine uue mõõdu loomisel

Nüüd saate eristada üksikute profiilide ja meetmete meetmeid kogu oma ettevõttes. Kuigi ärimeetmed kuvatakse Customer Insightsi avalehel, kuvatakse kliendi mõõdud üksikasjalikel kliendivaadetel.

Lisateavet vt teemast [Use measure builder, et luua meetmeid nullist](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Customer Insightsi dokumentatsiooni konsolideerimine

Oleme oma dokumentatsiooniartiklid uuesti üle vaadanud ja eemaldanud kaasamise ülevaated ja vaatajaskonna ülevaated. Edasi liikudes viitame rakenduse põhifunktsioonidest kirjutades järjekindlalt tootenimele Customer Insights. See muudatus toob kaasa ka sisukorra, URL-i struktuuri ja aluseks oleva dokumentatsioonihoidla failiteede olulise ümberkorraldamise. Kõik teie järjehoidjad või olemasolevad lingid jätkavad tööd ja suunavad need värskendatud URL-idele.

Kui soovite meile teada anda, kuidas te seda muutust tajute või märkate midagi, mis ei tööta ootuspäraselt, andke meile [selle lehe](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**) kohta tagasisidet.

## <a name="march-2022-updates"></a>Märts 2022 värskendused

2022. aasta märtsi värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec rikastamine (Eelvaade)

LiveRamp pakub identiteedilahendust ja kliendiandmete konsolideerimist. Saate vastendada kliendiandmetes olevad isikuidentifikaatorid AbiliTeci identiteedigraafikuga ja saada AbiliTeci ID-d. Seejärel saate neid ID-sid kasutada oma kliendiandmete paremaks ühendamiseks.

Lisateavet leiate teemast [Kliendiprofiilide rikastamine LiveRampi identiteediandmetega (Eelvaade)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Segmentide ja mõõtude korraldamine siltide ja filtritega

Kui teie organisatsioonil on palju segmente või meetmeid, võib õige leidmine mõnikord tunduda keeruline. See uus funktsioon võimaldab korraldada loendeid siltide ja veergude abil. See aitab leida andmeid kiiresti ja lihtsalt ning kohandada vaateid.

Lisateavet leiate teemast [Siltide ja veergudega](work-with-tags-columns.md) töötamine.

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Andmete jagamise Dataverse lubamine oma salvestuskonto kasutamisel

Kui teie keskkond kasutab Azure Data Lake Storage Customer Insightsi andmete talletamiseks, vajab andmete jagamine Microsoft Dataverse mõne lisakonfiguratsiooni.
Varem saite andmete jagamise lubada ainult siis Dataverse, kui teie andmed salvestati meie hallatavasse andmejärve.

Lisateavet leiate teemast [Andmete ühiskasutuse lubamine iseendaga Dataverse Azure Data Lake Storage (eelvaade)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Uued ekspordi sihtkohad: Iterable ja Braze

Jätkame ekspordisihtkohtade ökosüsteemi laiendamist uute ühendustega. Nüüd saate eksportida segmente Iterable'i ja Braze'i, et kasutada nende aktiveerimisteenuseid.

Lisateavet vt teemadest [Segmentide eksportimine iterable'i (eelvaade)](export-iterable.md) ja [segmentide eksportimine braze'i (eelvaade)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Marketo ja Google Adsi ekspordi täiustused

Ühendatud teenuste API-de muutmine toob kaasa konnektorite värskendused, mis töötavad usaldusväärselt ja sujuvalt. Oleme välja andnud mõned värskendused turu- ja Google Adsi teenustesse eksportimiseks.

- Google Ads: Google Adsi ekspordikonnektori uus versioon lihtsustab autentimiskogemust ja võimaldab nüüd automaatselt luua uusi Google Adsi vaatajaskondi. 
- Marketo: Marketo ekspordikonnektori uus versioon toetab Marketo ID-d, mis võimaldab teil vältida andmete dubleerimist, värskendada olemasolevaid kirjeid ja luua Marketos uusi kirjeid. 

## <a name="february-2022-updates"></a>2022. aasta veebruari värskendused

2022. aasta veebruari värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="general-availability-for-prediction-models"></a>Prognoos mudelite üldine kättesaadavus

Out-of-the-box prognoos mudelid, sealhulgas **tellimuse churn**, **tehingu churn** ja **kliendi eluaegne väärtus (CLV),** muutuvad customer Insightsi osana üldiselt kättesaadavaks. 

Lisateavet vt teemast [Predictions overview](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Uus andmeallikas: integratsioon Azure Synapse Analytics (eelvaade)

Azure Synapse Analytics on ettevõtte analüüsiteenus, mis kiirendab aega andmeladude ja suurandmete süsteemide ülevaateks.

Juba kasutatavad Azure Synapse Analytics organisatsioonid saavad need andmed Customer Insightsi alla neelata. 

Lisateavet leiate teemast [Andmeallikas ühendamine Azure Synapse (eelvaade)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRampi rikastamine (eelvaade)

LiveRamp pakub identiteedilahendust ja kliendiandmete konsolideerimist. Saate vastendada kliendiandmetes olevad isikuidentifikaatorid AbiliTeci identiteedigraafikuga ja saada AbiliTeci ID-d. Seejärel saate neid ID-sid kasutada oma kliendiandmete paremaks ühendamiseks.

Lisateavet leiate teemast [Kliendiprofiilide rikastamine LiveRampi identiteediandmetega (Eelvaade)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Andmeallikate rikastamine (Eelvaade)

Kasutage andmeid sellistest allikatest nagu Microsoft ja teised partnerid, et rikastada oma kliendiandmeid enne andmete ühendamist. Andmeallikas rikastamine aitab luua suuremat andmete täielikkust ja kvaliteeti, mis aitab pärast andmete ühendamist saavutada paremaid tulemusi.

Lisateavet vt teemast [Enrichment for Data sources (Preview)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Keskkonna omaniku muutmine

Kuigi customer Insightsis võivad administraatoriõigused olla mitmel kasutajal, on keskkonna omanik ainult üks kasutaja. Täiustatud kogemus võimaldab teil muuta keskkonna omanikke ja nõuda omandiõigust, kui endine omanik organisatsioonist lahkub. 

Lisateavet leiate teemast [Keskkonna](manage-environments.md#change-the-owner-of-an-environment) omaniku muutmine.

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Andmete ettevalmistamise protsess loetleb rikutud kirjete korruptsioonipõhjuse

Andmete ettevalmistamine näitab nüüd korruptsiooni põhjust kõigi rikutud andmetega väljade puhul. Teave esitatakse individuaalsel kirjetasemel, et neid oleks lihtne tuvastada. 

Lisateavet vt teemast [Corrupted andmeallikad](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Kaasamisülevaadete võimaluse aruandlusfunktsioonide eelvaate lõpp

Kaasamise Dynamics 365 Customer Insights ülevaatevõime eelvaade lõppes 15. veebruaril 2022.  
See muudatus tähendab, et Customer Insightsi prooviversioon ei sisalda enam võimalust luua lehtreid ega muid aruandlusfunktsioone.

Kutsume teid üles uurima ja hindama Paljusid teisi Customer [Insightsi](https://dynamics.microsoft.com/ai/customer-insights/), Microsofti kliendiandmete platvormi (CDP) funktsioone.    
 
Üleminekuperioodil on olemasolevatel eelvaates osalejatel endiselt juurdepääs mõnele eelvaatefunktsioonile ja funktsioonile.

- Hankige kood veebisaidi või mobiilirakenduse jaoks vahendite tagamiseks 
- Sündmuste ja sündmuse atribuutide kuvamine 
- Täiustage allaneelatud ja rafineeritud sündmustega ühtseid profiile, et saada kasu nende kliendiandmete täielikust väärtusest
  
Üleminekuperioodil voogesitatakse jäädvustatud sündmused endiselt ühendatud Andmejärve. Kui see funktsioon on välja lülitatud, siis andmete jagamine peatub ja ühendatud salvestusruumile uusi sündmusi ei saadeta.
Võtke otse ühendust oma Microsofti konto meeskonnaga, kui teil on küsimusi võimaluste eelvaate lõppemise kohta. Teie konto meeskond hoiab teid kursis tulevaste käivitamistega. 

## <a name="january-2022-updates"></a>2022. a jaanuari värskendus

2022. aasta jaanuari värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Teie kliendi tagasiside sentimentaalne analüüs

Customer Insights pakub uut tehisintellektil põhinevat funktsiooni, et sünteesida klientide tundeid ja tuvastada konkreetseid äriaspekte kui sihipärase täiustamise võimalusi. Analüüsides oma klientide kirjalikku tagasisidet, saate täpse ülevaate odavalt. Sentimenti analüüs, mis põhineb loomuliku keele töötlemise (NLP) mudelitel, mis genereerivad iga kliendi ID jaoks kaks tuletatud ülevaadet. Sentiment skoor (–5 kuni 5) ja nimekiri kohaldatavatest äriaspektidest. 

Lisateavet leiate teemast [Tunnete analüüsimine klientide tagasisides (Eelvaade)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]