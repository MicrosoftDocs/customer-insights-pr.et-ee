---
title: Semantiline analüüs klientide tagasiside jaoks
description: Vaadake, kuidas kasutada tundeanalüüsi mudelit klientide tagasiside kohta Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 05e530a1bc96c5fd9c7a3bc0197563d8fe330387
ms.sourcegitcommit: cb71e39de9b891c24bd5cd9c014eb3eeb537ac24
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 01/10/2022
ms.locfileid: "7951106"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Kliendi tagasiside tunnete analüüsimine (eelvaade)

Kliendid ootavad tänapäeval kvaliteetseid tooteid, teenuseid ja kogemusi. Eriti kliendid, kes jagavad oma tagasisidet. Organisatsioonidel on väga raske analüüsida suurenevat andmemahtu, vähendamata täpsust ja kõrgemaid tööjõukulusid. Dynamics 365 Customer Insights pakub klientide tagasiside jaoks sentimentanalüüsi mudelit, mis võimaldab organisatsioonidel oma andmeid täpsemalt ja madalama hinnaga analüüsida.

Sentiment analüüs võimaldab teil sünteesida klientide tundeid ja tuvastada äriaspektid kui paranemisvõimalused. See customer Insightsi funktsioon aitab teil mõista, mis toimib hästi ja mida peate käsitlema. Keskenduge kõige asjakohasematele ja mõjukamatele ärivaldkondadele, et parandada oma klientide kogemusi. Lõppkokkuvõttes aitab see teil juhtida äritegevust, mis võimaldab kogemusi, mille tulemuseks on klientide suur rahulolu ja lojaalsus.

## <a name="overview"></a>Ülevaade

Sentiment analüüsi funktsioon loob kliendi ID kohta kaks tuletatud ülevaadet. Sentiment skoor (-5 kuni 5) ja nimekiri kohaldatavatest äriaspektidest (ärivaldkonnad) koos aitavad teil paremini mõista klientide tagasisidet. 

See teave aitab teil saavutada järgmisi tulemusi. 
- Saate ülevaate klientide tunnetest brändi või organisatsiooni suhtes
- Tuvastage negatiivse tundega kliendid, et keskenduda oma kampaaniatele ja kohustustele ning optimeerida suurema tootluse jaoks  
- Tuvastage äriaspektid klientide poolt välja toodud probleemidega  
- Segmenteerige kliente nende tunnete põhjal isikupärastatud kampaaniate käitamiseks sihitud müügi-, turundus- ja tugitegevustega
- Äritegevuse optimeerimine, käsitledes probleemseid valdkondi või võimalusi, mida kliendid mainisid
- Tunnustage äriaspekte, mis teevad hästi, ja premeerige õnnelikke kliente lojaalsus- ja müügiedendusprogrammide kaudu

Tagamaks, et saate usaldada mudelite tulemusi, pakume läbipaistvat teavet selle kohta, kuidas mudelid otsuseid teevad. Saate nimekirja sõnadest, mis mõjutasid mudelite otsust määrata tagasiside kommentaaridele konkreetne tundeskoor või äriaspekt.  

Kasutame kahte **loomuliku keele töötlemise (NLP) mudelit : esimene määrab iga tagasiside kommentaari sentiment** skoori. Teine mudel seostab iga tagasiside kõigi kohaldatavate äriaspektidega. Mudeleid koolitatakse avalike andmete põhjal, mis pärinevad sotsiaalmeedia, jaemüügi, restorani, tarbekaupade ja autotööstuse allikatest.    
  
- Mudeli eelnevalt määratletud äriaspektid tagasisideandmetega seostamiseks on järgmised.
-   Kontohaldus
-   Kassa ja maksmine
-   Klienditugi
-   Poodi järeletulemisega
-   Pakendite saatmine ja toomine
-   Ettetellimine
-   Hind
-   Privaatsus ja turve
-   Kampaaniad ja preemiad
-   Kviitung ja garantii
-   Tagastuse vahetamine ja tühistamine
-   Täitmise täpsus
-   Veebisaidi/rakenduse kvaliteet

> [!NOTE]
> Praegu toetame ainult inglise klientide tagasiside sentimentaalset analüüsi. Tulevikus toetatakse rohkem keeli. Kui teistes keeltes tagasiside üles laaditakse, tagastab mudel siiski tulemused. Kuid need tulemused ei ole täpsed. 

## <a name="prerequisites"></a>eeltingimused

Sentimenti analüüs põhineb teksti tagasiside andmetel, mis on läbinud [andmete ühendamise protsessi](data-unification.md). Soovitame tungivalt [eelnevalt konfigureerida tagasiside andmeolemid semantiliste tüüpi tegevuseolemitena](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (tagasiside tüüp). 

Tundeanalüüsi mudeli konfigureerimiseks on vaja vähemalt [kaasautori õigusi](permissions.md).

Customer Insights saab töödelda kuni 10 miljonit tagasisidekirjet ühe mudeli käivitamiseks. Mudel saab analüüsida tagasiside kommentaare kuni 128 sõna. Kui tagasiside kommentaar on pikem, võetakse analüüsis arvesse ainult esimest 128 sõna.

### <a name="data-requirements"></a>Andmenõuded
  
Vaja on järgmisi andmeatribuute.
- Ühtne kliendi ID (UCID), et sobitada teksti tagasiside andmekirjed üksiku kliendiga. See ID on andmete ühendamise protsessi [tulemus](data-unification.md).
- Tagasiside ID
- Tagasiside ajatempel
- Tagasiside tekst   

> [!TIP]
> Sentiment analüüs nõuab teie klientide teksti tagasisidet. Praegu saab konfigureerida ainult ühte tagasiside olemit. Kui tagasisideolemit on mitu, saate need Power Query enne andmete allaneelamise algust liita.

## <a name="configure-a-sentiment-analysis"></a>Sentimenti analüüsi konfigureerimine 

1. Avage teenuses Customer Insights jaotised **Ärianalüüs** > **Prognoosid**.

1. Valige **paanil Klienditunde analüüs** suvand **Kasuta mudelit**.

1. Valige **paanil Klienditunde analüüs (eelvaade)** **suvand Alustamine**.

1. Sisestage **jaotises Mudeli nimi analüüsi jaoks** **nimi**. 

1. Sisestage **äriaspekti väljundi olemi nimi** ja **sentimenti skoori väljundi olemi nimi**, seejärel valige **Edasi**.

1. Valige **jaotises Nõutavad andmed** käsk Lisa **andmed**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Lisage andmevoog sentiment analüüsi mudelisse.":::

1. Valige **paanil Andmete lisamine** loendist semantiline tüüp **Tagasiside**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfiguratsioonietapp, et valida sentimentaalse analüüsi tagasisidetegevused.":::

1. Valige tegevused, mida selle tundeanalüüsi jaoks kasutada, seejärel valige **Edasi**.
 
1. Vastendage andmete atribuudid mudeliatribuutidega. Valikute rakendamiseks valige **Salvesta**. 

1. Näete andmete vastendamise olekut. Jätkamiseks valige **Edasi**. 

1. Kinnitage **oma mudeli üksikasjade** ülevaate etapis oma tundeanalüüsi konfiguratsioon. Võite minna tagasi prognoos konfiguratsiooni mis tahes osa juurde. Analüüsi alustamiseks valige **Salvesta ja** käivita. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Vaadake üle tundemudeli etapp, mis näitab kõiki konfigureeritud üksusi.":::

1. **Konfiguratsioonikogemusest** lahkumiseks valige Valmis. Protsess võib võtta mitu tundi, sõltuvalt kasutatud andmete kogusest. 

## <a name="review-analysis-status"></a>Analüüsi oleku ülevaatamine

1.  Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.
2.  Valige prognoos, mille soovite üle vaadata.
- **Prognoosi nimi**: prognoosi loomisel sellele pandud nimi.
- **prognoos tüüp** : prognoos kasutatava mudeli tüüp.
- **Väljundolem**: olemi nimi, kuhu talletatakse prognoosi väljund. Selle nimega olemi otsimiseks minge asukohta **Andmed** > **Olemid**.
- **Prognoositav väli**: see väli täidetakse ainult kindlat tüüpi prognooside korral ja seda ei kasutata kliendi eluea väärtuse prognoosimisel.
- **Olek**: prognoosi käitamise olek.
  - **Järjekorras**: prognoos ootab muude protsesside lõpetamist.
  - **Värskendamine**: prognoos töötab praegu, et luua tulemusi, mis sisestatakse väljundolemisse.
  - **Nurjunud**: prognoosi käitamine nurjus. Lisateabe saamiseks vaadake üle logid.
  - **Õnnestus**: prognoos on õnnestunud. Valige vertikaalsete kolmikpunktide alt suvand Kuva, et vaadata prognoos tulemusi.
- **Redigeeritud**: prognoosi konfiguratsiooni muutmise kuupäev.
- **Viimati värskendatud** : kuupäev, mil prognoos oli väljundolemis värskendatud tulemusi.

## <a name="manage-sentiment-analysis"></a>Sentimenti analüüsi haldamine

Ennustusi saate optimeerida, tõrkeotsingut, värskendada või kustutada. Vaadake sisendandmete kasutatavuse aruanne üle, et teada saada, kuidas muuta prognoos kiiremaks ja usaldusväärsemaks. Lisateavet leiate teemast [Prognooside haldamine](manage-predictions.md).

## <a name="review-analysis-results"></a>Analüüsi tulemuste ülevaatamine
 
1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**. 
1. Valige selle prognoos nimi, mille tulemused üle vaadata soovite. Sel juhul valige sentimentaalne analüüs, mida soovite üle vaadata. 

### <a name="summary-tab"></a>Vahekaart Kokkuvõte

Tulemuste lehel on neli peamist andmejaotist. 

- **Keskmine sentiment skoor** : aitab teil mõista üldist tundeid kõigis klientides. Sentimenti skoorid on rühmitatud kolme kategooriasse: 
  1.    Negatiivne (-5 > 2)
  2.    Neutraalne (-1 > 1)
  3.    Positiivne (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Kliendi üldise tunde visuaalne esitus.":::

- **Klientide jaotus sentiment skoori** järgi: kliendid liigitatakse negatiivsetesse, neutraalsetesse ja positiivsetesse rühmadesse nende sentimentaalsete skooride põhjal. Hõljuge histogrammi baaride kohal, et näha klientide arvu ja keskmist sentimenti skoori igas rühmas. Need andmed aitavad teil [luua klientide segmente](segments.md) nende tundeskooride põhjal.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Lintdiagramm, mis näitab kliendi tundeid kolmes sentimentaalses rühmas.":::

- **Keskmine tundeskoor aja** jooksul: kliendi meeleolu võib aja jooksul muutuda. Pakume trende teie klientide tunnetes teie andmete ajavahemikus. See vaade aitab teil hinnata hooajaliste kampaaniate, tooteesitluste või muude ajaliste sekkumiste mõju klientide meeleolule. Vaadake graafikut, valides rippmenüüst huvipakkuva aasta. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Ajaloo diagramm, mille tundeskoor aja jooksul on esitatud joonena.":::
 
- **Sentiment kogu** äriaspektide: See tabel loetleb keskmine tunne erinevates äriaspektides. See aitab teil hinnata, millised teie ettevõtte aspektid juba rahuldavad kliente või aspekte, mis vajavad rohkem tähelepanu. Tagasisidekirjed, mis ei ühti ühegi toetatud äriaspektiga, liigitatakse jaotises **Muu**. Tabel sorditakse vaikimisi tähestikulises järjekorras. Sortimist saate muuta, valides tabeli päise.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Äriaspektide loetelu koos sellega seotud sentimentaalse väärtusega ja seda mainivate klientide arvuga.":::
 
  Valige ettevõtte aspekti nimi, et näha lisateavet selle kohta, kuidas mudel äriaspekti tuvastab. Sellel paanil on kaks osa. 

  - **Mõjukad sõnad** : näitab parimaid sõnu, mis mõjutasid AI mudeli äriaspekti tuvastamist klientide tagasisides. 
    **Kuva solvavad sõnad** : võimaldab lisada loendisse solvavaid sõnu algsetest klientide tagasiside andmetest. Vaikimisi on see välja lülitatud.  Solvav sõna maskeerimine on varustatud AI mudeliga ja ei pruugi tuvastada kõiki solvavaid sõnu. Jätkame klassifikaatori itereerimist ja koolitamist optimaalse jõudluse saavutamiseks. Kui avastate solvava sõna, mida ei filtreeritud ootuspäraselt, andke meile sellest teada. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Mõjukate sõnade loend koos tumblernupuga solvavate sõnade kuvamiseks või peitmiseks.":::
 
  - **Tagasisidenäidised** : kuvab teie andmetes tegelikud tagasisidekirjed. Sõnad on värvikoodiga vastavalt nende mõjule äriaspekti tuvastamisele. 


### <a name="influential-words-analysis-tab"></a>Vahekaart Mõjukate sõnade analüüs

On kolm osa lisateavet, mis selgitavad, kuidas sentiment mudel töötab.
  
1. **Parimad sõnad, mis aitavad kaasa positiivsele tundele** : näitab tippsõnu, mis mõjutasid AI mudeli positiivsete tunnete tuvastamist klientide tagasisides.  
2. **Peamised sõnad, mis aitavad kaasa negatiivsele tundele** : näitab tippsõnu, mis mõjutasid AI mudeli negatiivsete tunnete tuvastamist klientide tagasisides.  
3. **Tagasiside näidised** : Kuvab tegelikud tagasisidekirjed, üks negatiivse tundega ja teine positiivse tundega. Tagasisidekirjetes olevad sõnad tõstetakse esile vastavalt nende panusele määratud tundeskoori. Sõnad, mis aitavad kaasa positiivsele tundeskoorile, on esile tõstetud roheliselt. Negatiivsele skoorile kaasa aitavad sõnad on punaselt esile tõstetud.
   **Valige Vaata** rohkem, et laadida rohkem tagasisidenäidiseid, mis annavad rohkem teavet ja konteksti selle kohta, kuidas tundemudel töötab.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Näited klientide tagasiside sentimentaalsest analüüsist.":::
 
**Kuva solvavad sõnad** : võimaldab lisada loendisse solvavaid sõnu algsetest klientide tagasiside andmetest. Vaikimisi on see välja lülitatud.  Solvav sõna maskeerimine on varustatud AI mudeliga ja ei pruugi tuvastada kõiki solvavaid sõnu. Jätkame klassifikaatori itereerimist ja koolitamist optimaalse jõudluse saavutamiseks. Kui avastate solvava sõna, mida ei filtreeritud ootuspäraselt, andke meile sellest teada. 

## <a name="act-on-analysis-results"></a>Analüüsitulemuste seadus

Tunnete analüüsi tulemuste lehelt saate hõlpsasti alustada uute kliendisegmentide loomist, valides mudeli tulemilehe ülaosas suvandi **Loo** segmendid.

:::image type="content" source="media/create-segment-model.png" alt-text="Käsuriba, kus on prognoos mudelite suvandid.":::
 
## <a name="potential-bias"></a>Potentsiaalne kallutatus

Nagu iga funktsiooni puhul, mis kasutab ennustavat tehisintellekti, peaksite olema teadlik potentsiaalsest kallutatusest andmetes, mida kasutate klienditunde ennustamiseks. Näiteks kui kogute tagasisidet ainult digitaalselt, võite jätta tagasisidet klientidelt, kes tegelevad teiega peamiselt isiklikult, mis võib mõjutada funktsiooni väljundit.

Kuna see funktsioon kasutab andmete hindamiseks ja nende põhjal ennustuste tegemiseks automatiseeritud vahendeid, on tal seega võimalus kasutada profileerimismeetodina, kuna see mõiste on määratletud isikuandmete kaitse üldmääruses (GDPR). Selle funktsiooni kasutamise kohta andmete töötlemisel võib kehtida kas GDPR või muud seadused või määrused. Teie vastutate selle eest, et teie kasutamine Dynamics 365 Customer Insights, sealhulgas tundeanalüüs, vastaks kõigile kohaldatavatele seadustele ja määrustele, sealhulgas eraelu puutumatuse, isikuandmete, biomeetriliste andmete, andmekaitse ja suhtluse konfidentsiaalsusega seotud seadustele.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

