---
title: Mida on uut rakenduses Dynamics 365 Customer Insights
description: Teave uute funktsioonide, täiustuste ja veaparanduste kohta.
ms.date: 08/03/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: a9bb254736ae70589afb267bf0a60206a18a3385
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246006"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Mida on uut rakenduses Dynamics 365 Customer Insights

Meil on hea meel teatada uusimatest värskendustest. Selles artiklis võetakse kokku avaliku eelversiooni funktsioonid, üldise kättesaadavuse täiustused ja funktsiooni värskendused. Pikaajaliste funktsiooni plaane vaadake teemast [Dynamics 365 ja Power Platformi väljaandeplaanid](/dynamics365/release-plans/).

Avaldame värskendusi regioonipõhiselt. Seega teatud regioonid võivad näha funktsioone enne teisi. Kui te pole teisiti määranud, ei pea te midagi tegema, värskendame rakendust automaatselt ilma seisakuteta.

> [!TIP]
> Funktsioonitaotluste ja tootesoovituste esitamiseks ning hääletamiseks minge [Dynamics 365 portaali Application Ideas](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="july-2022-updates"></a>2022. aasta juuli värskendused

2022. aasta juuli värskendused sisaldavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="export-to-moengage"></a>Ekspordi MoEngage’i

Eksportige ühtsete kliendiprofiilide segmendid MoEngage’i ja kasutage neid MoEngage’is e-posti turunduseks.

Lisateavet vaadake jaotisest [Segmentide eksportimine MoEngage’i](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>SSH tugi SFTP-põhisele ekspordile

Valige, kas soovite autentida SSH või kasutajanime/parooli kaudu ühenduste jaoks SFTP ekspordi sihtkohtadega.

Lisateavet vaadake jaotisest [Andmete eksportimine SFTP-hostidesse](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Kogemuste isikupärastamine teadaolevate ja tundmatute kasutajate andmetega

Kliendiandmete haldamine ei ole uus väljakutse, kuid see muutub üha keerulisemaks, kuna kasutajad navigeerivad erinevates digitaalsetes kanalites, mida kaubamärgid pakuvad. Ühes kanalis tuntud (autenditud) kasutaja muutub teises kanalis tundmatuks (autentimata), kui ta pole sisse logitud. Probleem on sageli selles, et autentimata (tundmatutel) kasutajatel pole ühist ID-d. Seda saab kasutada tähendusrikaste profiiliatribuutide seostamiseks ja ühtsete kliendiprofiilide loomiseks. Customer Insights aitab seda probleemi lahendada, neelates andmeid teie lähtesüsteemide jälgimismeetoditest.

Lisateavet leiate teemast [Kasutuskogemuse isikupärastamine teadaolevate ja tundmatute kasutajate andmetega](unknown-to-known.md).

## <a name="june-2022-updates"></a>2022. juuni värskendused

2022. aasta juunis toimuvad värskendused sisaldavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Andmeallikate ja andmete allaneelamise värskendatud kasutuskogemus

Andmete importimine paljudest andmeallikatest on aluseks teie kliendiandmete konsolideerimisele Dynamics 365 Customer Insights. Vaatasime üle kasutajakogemuse andmeallikate importimiseks ja ühendamiseks. Selle värskenduse eesmärk on hõlbustada andmete allaneelamist Customer Insightsi.

Lisateavet leiate teemast [Andmeallikate ülevaade](data-sources.md).

### <a name="export-to-inmobi"></a>Ekspordi InMobisse

InMobi aitab brändidel tarbijaid mõista, tuvastada, kaasata ja omandada. Segmente ja muid andmeid saate eksportida InMobi teenusesse Azure’i bloobimälu kontode kaudu.

Lisateavet vaadake jaotisest [Eksport InMobisse (eelvaade)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Lukustuskasti tugi Customer Insightsis

Kliendi turvahoidla pakub liidest andmetele juurdepääsu taotluste läbivaatamiseks ja kinnitamiseks (või tagasilükkamiseks). Need päringud tekivad siis, kui tugiteenusejuhtumi lahendamiseks on vaja andmetele juurdepääsu.

Lisateavet leiate teemast [Turvaline juurdepääs kliendiandmetele kliendi turvahoidla abil (eelvaade)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Andmetega ühenduse loomine Azure Private Linki abil

Azure Private Link võimaldab Customer Insightsil luua teie kontoga ühenduse teie Azure Data Lake Storage virtuaalse võrgu privaatse lõpp-punkti kaudu. Salvestuskontol olevate andmete puhul, mis ei ole avatud avalikule internetile, võimaldab Private Link ühenduse selle piiratud võrguga.

Lisateavet vaadake jaotisest [Privaatse lingi kasutamine Customer Insightsis](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>Mai 2022 värskendused

2022. aasta mai värskendused sisaldavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="updated-data-unification-experience"></a>Värskendatud andmete ühendamise kogemus

 Andmete ühendamine võimaldab teil ühendada üks kord erinevad andmeallikad üheks koondandmestikuks, mis pakub nendest andmetest ühtset vaadet. Andmeid saab ühendada ühe või mitme olemiga. Esmalt valite olemid ja lähteväljad [, eemaldate duplikaatkirjed](map-entities.md), määrate vastendustingimuste [reeglid](remove-duplicates.md) ja määratlete [, millised](match-entities.md) väljad ühtsesse kliendiprofiili [kaasata](merge-entities.md).

Lisateavet leiate teemast [Andmete ühendamise ülevaade](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Värskendatud avaleht Customer Insightsis

**Avaleht** juhendab teid põhifunktsioonide konfigureerimisprotsessis ja annab ülevaate segmentidest, mõõtudest ja rikastamisandmetest. Värskendasime kogemust, et pakkuda lühidalt asjakohasemat teavet.

Lisateavet vaadake jaotisest [Customer Insightsi avastamine](home.md).

### <a name="track-usage-of-a-segment"></a>Segmendi kasutamine rööbasteel

Nüüd saate [jälgida segmendi](segments.md#track-usage-of-a-segment) kasutamist rakendustes, mis põhinevad Customer Insightsiga ühendatud organisatsioonil Dataverse. Rakenduse Dynamics 365 Marketing [klienditeekondades kasutatavate Customer Insightsi segmentide puhul](/dynamics365/marketing/real-time-marketing-ci-profile) teavitab süsteem teid selle segmendi kasutamisest.

### <a name="export-to-criteo"></a>Ekspordi Criteosse

Criteo on veebiplatvorm, mis aitab kasutajatel hallata digitaalset reklaami. Nüüd saate Criteo abil eksportida ühtsete kliendiprofiilide segmente kampaaniate loomiseks, e-posti turunduse pakkumiseks ja konkreetsete kliendirühmade kasutamiseks.

Lisateavet leiate teemast [Segmentide eksportimine Criteosse (eelvaade)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Täiustatud dokumentatsioonistruktuur keskkonna loomiseks

Vaatasime üle Customer Insightsi keskkondade loomise ja haldamisega seotud spikridokumendid. Artiklid on nüüd sisukorras rühmitatud sõlme Keskkonnad alla. Ümberstruktureeritud artiklid annavad rohkem juhiseid erinevate keskkondade seadistamise viiside kohta ja neil on selgem struktuur. Kui teil on jagamiseks tagasisidet, andke meile sellest teada spikriartiklite lõpus olevate juhtelementide kaudu.

Lisateavet vaadake jaotisest [Kuidas: uue keskkonna](create-environment.md) loomine.

## <a name="april-2022-updates"></a>Aprill 2022 värskendused

2022. aasta aprilli värskendused sisaldavad uusi funktsioone, jõudluse ja veaparandusi.

### <a name="dun--bradstreet-enrichment-preview"></a>Dun ja Bradstreet rikastamine (eelvaade)

Dun ja Bradstreet pakub ettevõtetele äriandmeid, analüütikat ja teadmisi. See võimaldab ettevõtetel kliendi koondprofiilidega klientide andmeid rikastada. Rikastamised hõlmavad selliseid atribuute nagu DUNS-i number, ettevõtte suurus, asukoht, tööstus ja palju muud.

Lisateavet vaadake jaotisest [Ettevõtte profiilide rikastamine Dun ja Bradstreet’iga (eelvaade)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Mõõdutüübi määratlemine uue mõõdu loomisel

Nüüd saate eristada üksikute profiilide ja kogu ettevõtte mõõtude mõõtu. Kui ettevõtte mõõdud kuvatakse Customer Insightsi avalehel, siis kliendi mõõdud kuvatakse üksikasjalikes kliendivaadetes.

Lisateavet vaadake jaotisest [Mõõtude koostaja kasutamine mõõtude loomiseks nullist](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Customer Insightsi dokumentatsiooni konsolideerimine

Vaatasime üle oma dokumentatsiooniartiklid ning eemaldasime kaasamisstatistika ja vaatajaskonna ülevaadete võimalused. Edasi liikudes viitame rakenduse põhifunktsioonidest kirjutades järjekindlalt tootenimele Customer Insights. See muudatus toob kaasa ka sisukorra, URL-i struktuuri ja alusdokumentide hoidla failiteede olulise ümberkorraldamise. Kõik teie järjehoidjad või olemasolevad lingid töötavad edasi ja suunavad ümber värskendatud URL-idele.

Kui soovite meile teada anda, kuidas te seda muutust tajute või märkate midagi, mis ei tööta ootuspäraselt, andke meile sellest teada, esitades [selle lehe kohta tagasiside](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

## <a name="march-2022-updates"></a>Märts 2022 värskendused

2022. aasta märtsi värskendused sisaldavad uusi funktsioone, jõudluse ja veaparandusi.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTec rikastamine (eelvaade)

LiveRamp pakub identiteedi lahendamist ja kliendiandmete konsolideerimist. Saate vastendada oma kliendiandmetes olevaid isiklikke identifikaatoreid AbiliTeci identiteedigraafikuga ja saada AbiliTeci ID-sid. Seejärel saate neid ID-sid kasutada oma kliendiandmete paremaks ühendamiseks.

Lisateavet vaadake jaotisest [Kliendiprofiilide rikastamine identiteediandmetega rakendusest LiveRamp (eelvaade)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Segmentide ja mõõtude korraldamine siltide ja filtrite abil

Kui teie organisatsioonis on palju segmente või meetmeid, võib õige leidmine mõnikord tunduda keeruline. See uus funktsioon võimaldab teil loendeid siltide ja veergude abil korraldada. See aitab andmeid kiiresti ja lihtsalt leida ning vaateid kohandada.

Lisateavet leiate teemast [Siltide ja veergudega töötamine](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Andmete jagamise lubamine Dataverse oma salvestusruumikonto kasutamisel

Kui teie keskkond kasutab Azure Data Lake Storage Customer Insightsi andmete salvestamiseks, vajab andmete jagamine Microsoft Dataverse täiendavat konfigureerimist.
Varem saite andmete jagamise Dataverse lubada ainult siis, kui teie andmed salvestati meie hallatavasse andmejärve.

Lisateavet leiate teemast Andmete ühiskasutuse [lubamine omaenda Dataverse kaudu (eelvaade)Azure Data Lake Storage.](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)

### <a name="new-export-destinations-iterable-and-braze"></a>Uued ekspordisihtkohad: Iterable ja Braze

Jätkame oma ekspordisihtkohtade ökosüsteemi laiendamist uute ühendustega. Nüüd saate segmente eksportida Iterable’i ja Braze’i, et kasutada nende aktiveerimisteenuseid.

Lisateavet vaadake teemadest [Segmentide eksportimine iterable’i (eelvaade)](export-iterable.md) ja [segmentide eksportimine Braze’i (eelvaade)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Marketo ja Google Adsi ekspordi täiustused

Ühendatud teenuste API-de muutmine toob kaasa konnektorite värskendused, mis töötavad usaldusväärselt ja sujuvalt. Oleme välja andnud mõned värskendused Marketo ja Google Adsi teenuste ekspordi kohta.

- Google Ads: Google Adsi ekspordikonnektori uus versioon lihtsustab autentimiskogemust ja võimaldab teil nüüd automaatselt luua uusi Google Adsi vaatajaskondi. 
- Marketo: Marketo ekspordikonnektori uus versioon toetab Marketo ID-d, võimaldades teil vältida andmete dubleerimist, värskendada olemasolevaid kirjeid ja luua Marketos uusi kirjeid. 

## <a name="february-2022-updates"></a>2022. aasta veebruari värskendused

2022. aasta veebruari värskendused sisaldavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="general-availability-for-prediction-models"></a>Prognoos mudelite üldine kättesaadavus

Valmiskujul prognoos mudelid, sh **tellimus,** **tehingumaht** ja **kliendi eluaegne väärtus (CLV),** muutuvad Customer Insightsi osana üldiselt kättesaadavaks. 

Lisateavet vaadake jaotisest [Ennustuste ülevaade](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Uus andmeallikas: integreerimine rakendusega Azure Synapse Analytics (eelvaade)

Azure Synapse Analytics on ettevõtte analüüsiteenus, mis kiirendab andmeladude ja suurandmete süsteemide ülevaadete tegemist.

Juba kasutavad Azure Synapse Analytics organisatsioonid saavad need andmed Customer Insightsi alla neelata. 

Lisateavet leiate teemast [andmeallikas ühendamine Azure Synapse (eelvaade)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRamp rikastamine (eelvaade)

LiveRamp pakub identiteedi lahendamist ja kliendiandmete konsolideerimist. Saate vastendada oma kliendiandmetes olevaid isiklikke identifikaatoreid AbiliTeci identiteedigraafikuga ja saada AbiliTeci ID-sid. Seejärel saate neid ID-sid kasutada oma kliendiandmete paremaks ühendamiseks.

Lisateavet vaadake jaotisest [Kliendiprofiilide rikastamine identiteediandmetega rakendusest LiveRamp (eelvaade)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Andmeallikate rikastamine (eelvaade)

Kasutage kliendiandmete rikastamiseks enne andmete ühendamist sellistest allikatest nagu Microsoft ja muud partnerid pärinevaid andmeid. Andmeallikas rikastamine aitab luua suuremat andmete täielikkust ja kvaliteeti, mis võib aidata saavutada paremaid tulemusi, kui olete oma andmed ühendanud.

Lisateavet leiate teemast [Andmeallikate rikastamine (eelvaade)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Keskkonna omaniku muutmine

Kuigi Customer Insightsis võivad administraatoriõigused olla mitmel kasutajal, on keskkonna omanik ainult üks kasutaja. Täiustatud kogemus võimaldab teil vahetada keskkonna omanikke ja nõuda omandiõigust, kui endine omanik organisatsioonist lahkub. 

Lisateavet vaadake jaotisest [Keskkonna](manage-environments.md#change-the-owner-of-an-environment) omaniku muutmine.

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Andmete ettevalmistamise protsess loetleb rikutud kirjete korruptsiooni põhjused

Andmete ettevalmistamine näitab nüüd kõigi rikutud andmetega väljade korruptsiooni põhjust. Teave esitatakse individuaalse registreerimise tasandil, et seda oleks lihtne tuvastada. 

Lisateavet leiate teemast [Rikutud andmeallikad](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Aruandlusfunktsioonide eelvaate lõpp kaasamise ülevaadete võimaluses

Kaasamisülevaadete Dynamics 365 Customer Insights võimaluse eelvaade lõppes 15. veebruaril 2022.  
See muudatus tähendab, et Customer Insightsi proovikogemus ei sisalda enam lehtrite loomise võimalust ega muid aruandlusfunktsioone.

Kutsume teid uurima ja hindama Microsofti kliendiandmete platvormi (CDP) [Customer Insightsi](https://dynamics.microsoft.com/ai/customer-insights/) paljusid muid funktsioone.    
 
Üleminekuperioodil on olemasolevatel eelvaates osalejatel endiselt juurdepääs mõnele eelvaatefunktsioonile ja -funktsioonile.

- Hankige kood veebisaidi või mobiilirakenduse jaoks vahendite tagamiseks 
- Sündmuste ja sündmuste atribuutide vaatamine 
- Täiustage allaneelatud ja täiustatud sündmustega ühtseid profiile, et saada kasu oma kliendiandmete täielikust väärtusest
  
Üleminekuperioodil edastatakse jäädvustatud sündmusi endiselt ühendatud andmejärve. Kui see funktsioon on välja lülitatud, peatub andmete jagamine ja ühendatud salvestusruumi ei saadeta uusi sündmusi.
Võtke otse ühendust oma Microsofti konto meeskonnaga, kui teil on küsimusi võimaluste eelvaate lõpu kohta. Teie konto meeskond hoiab teid eelseisvate käivitamistega kursis. 

## <a name="january-2022-updates"></a>2022. a jaanuari värskendus

2022. aasta jaanuari värskendused sisaldavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Teie kliendi tagasiside sentimentanalüüs

Customer Insights pakub uut tehisintellektil põhinevat funktsiooni, et sünteesida klientide meelsust ja tuvastada konkreetsed äriaspektid kui võimalused sihipärasteks täiustusteks. Analüüsides oma klientide kirjalikku tagasisidet, saate täpse ülevaate madala hinnaga. Sentimentanalüüs, mida toetavad loomuliku keele töötlemise (NLP) mudelid, mis loovad iga kliendi ID kohta kaks tuletatud ülevaadet. Meeleolu skoor (–5–5) ja kohaldatavate äriaspektide loetelu. 

Lisateavet leiate teemast [Meeleolu analüüsimine klientide tagasisides (eelvaade)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]