---
title: Mida on uut rakenduses Dynamics 365 Customer Insights
description: Teave uute funktsioonide, täiustuste ja veaparanduste kohta.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: dcee60a73e0c32278553253040478c31e45237ae
ms.sourcegitcommit: 618ef15b434de0a68213383b6521ce2a60753afb
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 10/07/2022
ms.locfileid: "9638346"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Mida on uut rakenduses Dynamics 365 Customer Insights

Meil on hea meel teatada uusimatest värskendustest. Selles artiklis võetakse kokku avaliku eelversiooni funktsioonid, üldise kättesaadavuse täiustused ja funktsiooni värskendused. Pikaajaliste funktsiooni plaane vaadake teemast [Dynamics 365 ja Power Platformi väljaandeplaanid](/dynamics365/release-plans/).

Avaldame värskendusi regioonipõhiselt. Seega teatud regioonid võivad näha funktsioone enne teisi. Kui pole teisiti määratud, ei pea te midagi tegema, värskendame rakendust automaatselt ilma seisakuteta.

> [!TIP]
> Funktsioonitaotluste ja tootesoovituste esitamiseks ning hääletamiseks minge [Dynamics 365 portaali Application Ideas](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="september-2022-updates"></a>2022. aasta septembri uuendused

2022. aasta septembri värskendused hõlmavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="export-data-to-hubspot"></a>Andmete eksportimine HubSpoti

Eksportige ühendatud kliendiprofiilide segmendid HubSpoti ja kasutage neid meiliturunduses.

Lisateavet vaadake jaotisest [Segmentide eksportimine HubSpoti](export-hubspot.md).

### <a name="remove-a-unified-field-or-entity-from-data-unification"></a>Ühendatud välja või olemi eemaldamine andmete ühendamisest

Väljad ja olemid saate andmete ühendamise protsessist eemaldada.

Lisateavet leiate teemast [Ühtse välja eemaldamine](data-unification-update.md#remove-a-unified-field).

### <a name="manage-unknown-customer-profiles"></a>Tundmatute kliendiprofiilide haldamine

Meeldejääv isikupärastamine sõltub teie kliendiandmete rikkusest ja täielikkusest ning Customer Insights aitab teil neid eesmärke saavutada. Saate hallata nende kasutajate kliendiprofiile, kelle kohta teil pole muud teavet peale ID.

Lisateavet vaadake jaotisest [Tundmatute profiilide haldamine Customer Insightsi abil](manage-unknown-profiles.md).

## <a name="august-2022-updates"></a>2022. aasta augusti värskendused

2022. aasta augusti värskendused hõlmavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="contact-unification-in-b-to-b-environments"></a>Kontaktide ühendamine B-B keskkondades

Customer Insightsi B-to-B keskkonnad toetavad nüüd täiustatud andmete ühendamise kogemust.

Nüüd saate lisaks kontodele ka kontakte ühendada, et saada täielik ülevaade oma ärikontaktidest. Ühtsed kontaktid seostatakse ühendatud kontodega ja on nüüd loetletud kliendikaartidel. 

Lisateavet leiate teemast [Ühtse kontaktiprofiili loomine](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>Segmentide loomine ja eksportimine ühtsete kontaktide põhjal

Tänu uuele kontaktide ühendamisele saate luua kontaktisegmente, kasutades kas kontaktide, kontode või mõlema kriteeriume. Neid segmente saab eksportida aktiveerimiseks teistes teenustes.

Lisateavet leiate teemast [Ekspordi ülevaade](export-destinations.md).

### <a name="deployment-regions-aligned-with-microsoft-dataverse"></a>Juurutuspiirkonnad, mis on joondatud Microsoft Dataverse

Uue Customer Insightsi keskkonna loomisel saate valida piirkonna, kus soovite teenust juurutada ja majutada. Oleme värskendanud piirkonna valikut, et see oleks kooskõlas Microsoft Dataverse ja Power Platform.

Nüüd saate hõlpsasti valida sama piirkonna, mis on teie olemasolev Microsoft Dataverse keskkond või Azure Data Lake’i salvestusruumikonto (kui valite selle suvandi), sõltuvalt sellest, kas Customer Insights on selles piirkonnas saadaval.

Lisateavet leiate teemadest [Uue keskkonna](create-environment.md) loomine ja [Toote saadavus geograafia](https://dynamics.microsoft.com/availability-reports/) järgi.

## <a name="july-2022-updates"></a>2022. aasta juuli värskendused

2022. aasta juuli värskendused hõlmavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="export-to-moengage"></a>Eksport MoEngage’i

Eksportige ühtsete kliendiprofiilide segmendid MoEngage’i ja kasutage neid MoEngage’is e-posti turunduseks.

Lisateavet vaadake jaotisest [Segmentide eksportimine MoEngage’i](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>SSH toetus SFTP-põhisele ekspordile

Valige, kas soovite autentida SSH või kasutajanime/parooli kaudu SFTP ekspordisihtkohtadega ühenduse loomiseks.

Lisateavet vaadake jaotisest [Andmete eksportimine SFTP-hostidesse](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Kasutuskogemuse isikupärastamine teadaolevate ja tundmatute kasutajate andmetega

Kliendiandmete haldamine ei ole uus väljakutse, kuid see muutub üha keerulisemaks, kuna kasutajad navigeerivad erinevates digitaalsetes kanalites, mida kaubamärgid pakuvad. Kasutaja, kes on ühes kanalis tuntud (autenditud), muutub teises kanalis tundmatuks (autentimata), kui ta pole sisse logitud. Sageli on probleem selles, et autentimata (tundmatutel) kasutajatel pole ühist ID-d. Seda saab kasutada tähendusrikaste profiilide atribuutide seostamiseks ja ühtsete kliendiprofiilide loomiseks. Customer Insights aitab seda probleemi lahendada, neelates lähtesüsteemides jälgimismeetodite andmeid.

Lisateavet vaadake jaotisest [Kasutuskogemuse isikupärastamine teadaolevate ja tundmatute kasutajate](unknown-to-known.md) andmetega.

## <a name="june-2022-updates"></a>2022. juuni värskendused

2022. aasta juuni värskendused hõlmavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Andmeallikate ja andmete allaneelamise värskendatud kasutuskogemus

Andmete importimine paljudest andmeallikatest on aluseks kliendiandmete konsolideerimisele rakendusse Dynamics 365 Customer Insights. Vaatasime andmeallikate importimiseks ja ühendamiseks kasutajakogemuse üle. Selle värskenduse eesmärk on hõlbustada andmete sisestamist Customer Insightsi.

Lisateavet leiate teemast [Andmeallikate ülevaade](data-sources.md).

### <a name="export-to-inmobi"></a>Ekspordi InMobi

InMobi aitab brändidel tarbijaid mõista, tuvastada, kaasata ja omandada. Saate eksportida segmente ja muid andmeid InMobi teenusesse Azure’i bloobimälu kontode kaudu.

Lisateavet vaadake jaotisest [Eksport InMobisse (eelvaade)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Turvaboksi tugi Customer Insightsis

Kliendi turvahoidla pakub liidest andmetele juurdepääsu taotluste läbivaatamiseks ja kinnitamiseks (või tagasilükkamiseks). Need päringud tekivad siis, kui tugiteenusejuhtumi lahendamiseks on vaja juurdepääsu andmetele kliendiandmetele.

Lisateavet vaadake jaotisest [Turvaline juurdepääs kliendiandmetele kliendi turvahoidla abil (eelvaade)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview)).

### <a name="connect-to-your-data-using-azure-private-link"></a>Andmetega ühenduse loomine Azure’i privaatlingi abil

Azure Private Link võimaldab Customer Insightsil luua ühenduse teie Azure Data Lake Storage kontoga virtuaalses võrgus asuva privaatse lõpp-punkti kaudu. Salvestusruumi kontol olevate andmete puhul, mis ei ole avatud avalikule Internetile, võimaldab Private Link ühenduse selle piiratud võrguga.

Lisateavet vaadake jaotisest [Privaatse lingi kasutamine Customer Insightsis](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>Mai 2022 värskendused

2022. aasta mai värskendused hõlmavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="updated-data-unification-experience"></a>Värskendatud andmete ühendamise kogemus

 Andmete ühendamine võimaldab teil ühendada ühekordselt erinevad andmeallikad üheks koondandmekogumiks, mis annab nendest andmetest ühtse vaate. Andmeid saab ühendada ühe olemi või mitme olemiga. Esmalt saate valida olemid ja lähteväljad [, eemaldada duplikaatkirjed](map-entities.md), määrata vastendustingimuste [reeglid](remove-duplicates.md) ja määratleda [,](match-entities.md) millised [väljad ühtsetesse kliendiprofiilidesse](merge-entities.md) kaasata.

Lisateavet leiate teemast [Andmete ühendamise ülevaade](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Värskendatud avaleht Customer Insightsis

**Home** juhendab teid põhifunktsioonide konfigureerimisprotsessis ning annab ülevaate segmentidest, mõõtudest ja rikastamisandmetest. Oleme värskendanud kasutuskogemust, et pakkuda lühidalt asjakohasemat teavet.

Lisateavet leiate teemast [Kliendistatistika uurimine](home.md).

### <a name="track-usage-of-a-segment"></a>Lõigu kasutamise jälgimine

Nüüd [saate jälgida segmendi](segments.md#track-usage-of-a-segment) kasutamist rakendustes, mis põhinevad Dataverse Customer Insightsiga ühendatud organisatsioonil. Dynamics 365 Marketingi [klienditeekondades kasutatavate Customer Insightsi segmentide puhul](/dynamics365/marketing/real-time-marketing-ci-profile) teavitab süsteem teid selle segmendi kasutamisest.

### <a name="export-to-criteo"></a>Eksport Criteosse

Criteo on veebiplatvorm, mis aitab kasutajatel hallata digitaalset reklaami. Nüüd saate eksportida ühtsete kliendiprofiilide segmente, et luua kampaaniaid, pakkuda e-posti turundust ja kasutada Criteo abil konkreetseid kliendirühmi.

Lisateavet vaadake jaotisest [Segmentide eksportimine Criteosse (eelvaade)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Täiustatud dokumentatsioonistruktuur keskkonna loomiseks

Vaatasime üle Customer Insightsi keskkondade loomise ja haldamisega seotud abidokumendid. Artiklid on nüüd rühmitatud sisukorras sõlme Keskkonnad alla. Ümberstruktureeritud artiklid annavad rohkem juhiseid keskkondade loomise erinevate viiside kohta ja neil on selgem struktuur. Kui teil on tagasisidet, mida jagada, andke meile sellest juhtelementide kaudu teada spikriartiklite lõpus.

Lisateavet leiate teemast [Kuidas: uue keskkonna](create-environment.md) loomine.

## <a name="april-2022-updates"></a>Aprill 2022 värskendused

2022. aasta aprilli värskendused hõlmavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="dun--bradstreet-enrichment-preview"></a>Dun & Bradstreet rikastamine (eelvaade)

Dun & Bradstreet pakub ettevõtetele äriandmeid, analüütikat ja ülevaateid. See võimaldab ettevõtetel kliendi koondprofiilidega klientide andmeid rikastada. Rikastamised hõlmavad selliseid atribuute nagu DUNS-i number, ettevõtte suurus, asukoht, tööstus ja palju muud.

Lisateavet vaadake jaotisest [Ettevõtte profiilide rikastamine Dun & Bradstreet’ga (eelvaade)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Meetme tüübi määratlemine uue mõõdu loomisel

Nüüd saate eristada üksikute profiilide ja kogu ettevõtte meetmeid. Kui ettevõtte mõõdikud kuvatakse Customer Insightsi avalehel, siis kliendi mõõdud kuvatakse üksikasjalikes kliendivaadetes.

Lisateavet vaadake jaotisest [Mõõtude koostaja kasutamine mõõtude loomiseks nullist](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Customer Insightsi dokumentatsiooni konsolideerimine

Vaatasime üle oma dokumentatsiooniartiklid ning eemaldasime kaasamise statistika ja vaatajaskonna statistika võimaluste mainimised. Edasi liikudes viitame rakenduse põhifunktsioonidest kirjutades järjekindlalt tootenimele Customer Insights. See muudatus toob kaasa ka sisukorra, URL-i struktuuri ja failiteede olulise ümberkorraldamise aluseks olevas dokumentatsioonihoidlas. Kõik teie järjehoidjad või olemasolevad lingid töötavad edasi ja suunavad ümber värskendatud URL-idele.

Kui soovite meile teada anda, kuidas tajute seda muutust või märkate midagi, mis ei tööta ootuspäraselt, andke meile sellest teada, esitades [selle lehe](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**) kohta tagasisidet.

## <a name="march-2022-updates"></a>Märts 2022 värskendused

2022. aasta märtsi värskendused hõlmavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="liveramp-abilitec-enrichment-preview"></a>LiveRamp AbiliTeci rikastamine (eelvaade)

LiveRamp pakub identiteedi lahendamist ja kliendiandmete konsolideerimist. Saate kaardistada oma kliendiandmetes olevad isiklikud identifikaatorid AbiliTeci identiteedigraafikuga ja saada AbiliTeci ID-sid. Seejärel saate neid ID-sid kasutada oma kliendiandmete paremaks ühendamiseks.

Lisateavet leiate teemast [Kliendiprofiilide rikastamine LiveRampi identiteediandmetega (eelvaade)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Segmentide ja mõõtude korraldamine siltide ja filtritega

Kui teie organisatsioonil on palju segmente või meetmeid, võib õige leidmine mõnikord tunduda keeruline. See uus funktsioon võimaldab teil korraldada loendeid siltide ja veergude abil. See aitab andmeid kiiresti ja lihtsalt leida ning vaateid kohandada.

Lisateavet leiate teemast [Siltide ja veergudega](work-with-tags-columns.md) töötamine.

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Andmete jagamise Dataverse lubamine oma salvestusruumi konto kasutamisel

Kui teie keskkond salvestab Azure Data Lake Storage Customer Insightsi andmeid, vajab andmete jagamine Microsoft Dataverse täiendavat konfigureerimist.
Varem saite andmete jagamise lubada ainult siis, kui Dataverse teie andmed salvestati meie hallatavate andmete järve.

Lisateavet vaadake teemast [Andmete ühiskasutuse Dataverse lubamine oma (Azure Data Lake Storage eelvaade)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)).

### <a name="new-export-destinations-iterable-and-braze"></a>Uued ekspordisihtkohad: Iterable ja Braze

Jätkame oma ekspordisihtkohtade ökosüsteemi laiendamist uute ühendustega. Nüüd saate segmente eksportida iterable’i ja Braze’i, et kasutada nende aktiveerimisteenuseid.

Lisateavet leiate teemadest [Segmentide eksportimine iterable’i (eelvaade) ja](export-iterable.md) Segmentide eksportimine Braze’i (eelvaade) [...](export-braze.md)).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Marketo ja Google Adsi ekspordi täiustused

Ühendatud teenuste API-de muutmine toob kaasa värskendused, et konnektorid töötaksid usaldusväärselt ja sujuvalt. Andsime välja mõned värskendused Marketo ja Google Adsi teenustesse eksportimise kohta.

- Google Ads: Google Adsi ekspordikonnektori uus versioon lihtsustab autentimiskogemust ja võimaldab teil nüüd automaatselt luua uusi Google Adsi vaatajaskondi. 
- Marketo: Marketo ekspordikonnektori uus versioon toetab Marketo ID-d, võimaldades teil vältida andmete dubleerimist, värskendada olemasolevaid kirjeid ja luua Marketos uusi kirjeid. 

## <a name="february-2022-updates"></a>2022. aasta veebruari värskendused

2022. aasta veebruari värskendused hõlmavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="general-availability-for-prediction-models"></a>Prognoos mudelite üldine kättesaadavus

Valmiskujul prognoos mudelid, sealhulgas **tellimus,** **tehinguhind** ja **kliendi eluaegne väärtus (CLV),** muutuvad Customer Insightsi osana üldiselt kättesaadavaks. 

Lisateavet leiate teemast [Prognooside ülevaade](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Uus andmeallikas: integratsioon Azure Synapse Analytics (eelvaade)

Azure Synapse Analytics on ettevõtte analüütikateenus, mis kiirendab andmeladude ja suurandmesüsteemide ülevaadete tegemise aega.

Organisatsioonid, kes juba kasutavad Azure Synapse Analytics, saavad need andmed Customer Insightsi alla neelata. 

Lisateavet leiate teemast [andmeallikas ühendamine Azure Synapse (eelvaade)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>LiveRampi rikastamine (eelvaade)

LiveRamp pakub identiteedi lahendamist ja kliendiandmete konsolideerimist. Saate kaardistada oma kliendiandmetes olevad isiklikud identifikaatorid AbiliTeci identiteedigraafikuga ja saada AbiliTeci ID-sid. Seejärel saate neid ID-sid kasutada oma kliendiandmete paremaks ühendamiseks.

Lisateavet leiate teemast [Kliendiprofiilide rikastamine LiveRampi identiteediandmetega (eelvaade)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Andmeallikate rikastamine (eelvaade)

Kasutage sellistest allikatest pärit andmeid nagu Microsoft ja teised partnerid, et rikastada oma kliendiandmeid enne andmete ühendamist. Andmeallikas rikastamised aitavad saavutada andmete täielikkust ja kvaliteeti, mis võib aidata saavutada paremaid tulemusi, kui olete oma andmed ühendanud.

Lisateavet leiate teemast [Andmeallikate rikastamine (eelvaade)](data-sources-enrichment.md)).

### <a name="change-owner-of-environment"></a>Keskkonna omaniku muutmine

Kuigi Customer Insightsis võivad administraatoriõigused olla mitmel kasutajal, on keskkonna omanik ainult üks kasutaja. Täiustatud kasutuskogemus võimaldab teil vahetada keskkonna omanikku ja nõuda omandiõigust, kui endine omanik organisatsioonist lahkub. 

Lisateavet leiate teemast [Keskkonna](manage-environments.md#change-the-owner-of-an-environment) omaniku muutmine.

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>Andmete ettevalmistamise protsess loetleb rikutud kirjete korruptsioonipõhjuse

Andmete ettevalmistamine näitab nüüd korruptsiooni põhjust kõigi rikutud andmetega väljade puhul. Teave esitatakse individuaalsel kirjetasemel, et seda oleks lihtne tuvastada.

Lisateavet leiate teemast [Andmeallikate](data-sources.md#corrupt-data-sources) rikkumine.

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Kaasamise ülevaate võimaluse aruandlusfunktsioonide eelvaate lõpp

Kaasamise Dynamics 365 Customer Insights ülevaadete võimsuse eelvaade lõppes 15. veebruaril 2022.  
See muudatus tähendab, et Customer Insightsi prooviversioon ei hõlma enam lehtrite loomise võimalust ega muid aruandlusfunktsioone.

Kutsume teid üles uurima ja hindama paljusid muid funktsioone [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), Microsofti kliendiandmete platvorm (CDP).    
 
Üleminekuperioodil on olemasolevatel eelvaates osalejatel endiselt juurdepääs mõnele eelvaate võimalusele ja funktsioonile.

- Hankige kood veebisaidi või mobiilirakenduse jaoks vahendite tagamiseks 
- Vaadake sündmusi ja sündmuse atribuute 
- Täiustage ühtseid profiile allaneelatud ja rafineeritud sündmustega, et saada kasu nende kliendiandmete täielikust väärtusest
  
Üleminekuperioodil voogesitatakse jäädvustatud sündmusi endiselt ühendatud andmejärve. Kui see funktsioon on välja lülitatud, peatub andmete jagamine ja ühendatud salvestusruumi ei saadeta uusi sündmusi.
Võtke otse ühendust oma Microsofti konto meeskonnaga, kui teil on küsimusi võimaluste eelvaate lõppemise kohta. Teie konto meeskond hoiab teid tulevaste lansseerimistega kursis. 

## <a name="january-2022-updates"></a>2022. a jaanuari värskendus

2022. aasta jaanuari värskendused hõlmavad uusi funktsioone, jõudluse täiendusi ja veaparandusi.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Teie kliendi tagasiside sentimentanalüüs

Customer Insights pakub uut tehisintellektil põhinevat funktsiooni, et sünteesida klientide meeleolu ja tuvastada konkreetsed äriaspektid sihipäraste täiustuste võimalustena. Analüüsides oma klientide kirjalikku tagasisidet, saate täpse ülevaate madalate kuludega. Sentimentanalüüs, mida toetavad loomuliku keele töötlemise (NLP) mudelid, mis loovad iga kliendi ID kohta kaks tuletatud ülevaadet. Meeleolu skoor (–5 kuni 5) ja kohaldatavate äriaspektide loetelu. 

Lisateavet leiate teemast [Meeleolu analüüsimine klientide tagasisides (eelvaade)](sentiment-analysis.md)).


[!INCLUDE [footer-include](includes/footer-banner.md)]