---
title: Uued ja tulevased funktsioonid
description: Teave uute funktsioonide, täiustuste ja veaparanduste kohta.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 25c6e2897d836854408871b2c74afa16ecba7435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642831"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Mida on uut rakenduses Dynamics 365 Customer Insights

Meil on hea meel teatada uusimatest värskendustest. Selles artiklis võetakse kokku avaliku eelversiooni funktsioonid, üldise kättesaadavuse täiustused ja funktsiooni värskendused. Pikaajaliste funktsiooni plaane vaadake teemast [Dynamics 365 ja Power Platformi väljaandeplaanid](/dynamics365/release-plans/).

Avaldame värskendusi regioonipõhiselt. Seega teatud regioonid võivad näha funktsioone enne teisi. Kui see pole teisiti määratud teisiti, ei pea te tegema mingeid toiminguid ja värskendame rakendust automaatselt ilma seisakuteta.

> [!TIP]
> Funktsioonitaotluste ja tootesoovituste esitamiseks ning hääletamiseks minge [Dynamics 365 portaali Application Ideas](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Märts 2022 värskendused

2022. aasta märtsi värskendused sisaldavad uusi funktsioone, jõudluse uuendamist ja veaparandusi.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec rikastamine (Eelvaade)

LiveRamp pakub identiteedilahendust ja kliendiandmete konsolideerimist. Saate vastendada kliendiandmetes olevad isikuidentifikaatorid AbiliTeci identiteedigraafikuga ja saada AbiliTeci ID-d. Seejärel saate neid ID-sid kasutada oma kliendiandmete paremaks ühendamiseks.

Lisateavet leiate teemast [Kliendiprofiilide rikastamine LiveRampi identiteediandmetega (Eelvaade)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Segmentide ja mõõtude korraldamine siltide ja filtritega
Kui teie organisatsioonil on palju segmente või meetmeid, võib õige leidmine mõnikord tunduda keeruline. See uus funktsioon võimaldab korraldada loendeid siltide ja veergude abil. See aitab leida andmeid kiiresti ja lihtsalt ning kohandada vaateid.

Lisateavet leiate teemast [Siltide ja veergudega töötamine](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Andmete jagamise Dataverse lubamine oma salvestuskonto kasutamisel

Kui teie keskkond kasutab Azure Data Lake Storage Customer Insightsi andmete talletamiseks, vajab andmete jagamine Microsoft Dataverse mõne lisakonfiguratsiooni.
Varem saite andmete jagamise lubada ainult siis Dataverse, kui teie andmed salvestati meie hallatavasse andmejärve. 

Lisateavet leiate teemast [Andmete ühiskasutuse lubamine iseendaga Dataverse Azure Data Lake Storage (eelvaade)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Uued ekspordi sihtkohad: Iterable ja Braze

Jätkame ekspordisihtkohtade ökosüsteemi laiendamist uute ühendustega. Nüüd saate eksportida segmente Iterable'i ja Braze'i, et kasutada nende aktiveerimisteenuseid.

Lisateavet vt teemadest [Segmentide eksportimine Iterable'i (eelvaade)](export-iterable.md) ja [Segmentide eksportimine Braze'i (eelvaade)](export-braze.md).

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

Kasutage andmeid sellistest allikatest nagu Microsoft ja teised partnerid, et rikastada oma kliendiandmeid enne andmete ühendamist. Andmeallikas rikastamine aitab saavutada suuremat andmete täielikkust ja kvaliteeti, mis aitab saavutada paremaid tulemusi pärast andmete ühendamist.

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