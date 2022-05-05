---
title: Klientide tagasiside sentimentide analüüs
description: Siit saate teada, kuidas rakenduses kliendi tagasiside kohta tunnete analüüsi mudelit kasutada Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: e51225bbfcd445180b12661cba12256c3f042045
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642751"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analüüsige tundeid klientide tagasisides (Eelvaade)

Kliendid ootavad tänapäeval kvaliteetseid tooteid, teenuseid ja kogemusi. Eriti kliendid, kes jagavad oma tagasisidet. Organisatsioonidel on väga raske analüüsida kasvavat andmemahtu, vähendamata täpsust ja kõrgemaid tööjõukulusid. Dynamics 365 Customer Insights pakub klientide tagasiside jaoks sentimentianalüüsi mudelit, mis võimaldab organisatsioonidel oma andmeid täpsemalt ja madalama hinnaga analüüsida.

Sentimenti analüüs võimaldab teil sünteesida klientide tundeid ja tuvastada äriaspekte kui täiustamisvõimalusi. See Customer Insightsi funktsioon aitab teil mõista, mis toimib hästi ja mida peate käsitlema. Keskenduge kõige asjakohasematele ja mõjukamatele ärivaldkondadele, et parandada oma klientide kogemusi. Lõppkokkuvõttes aitab see teil juhtida äritegevust, mis võimaldab kogemusi, mille tulemuseks on suur klientide rahulolu ja lojaalsus.

## <a name="overview"></a>Ülevaade

Sentimenti analüüsi funktsioon genereerib kliendi ID kohta kaks tuletatud ülevaadet. Sentiment skoor (-5 kuni 5) ja nimekiri kohaldatavatest äriaspektidest (ärivaldkonnad) koos aitavad teil paremini mõista klientide tagasisidet. 

See teave aitab teil saavutada järgmisi tulemusi. 
- Saate ülevaate klientide tunnetest brändi või organisatsiooni suhtes
- Tuvastage negatiivse tundega kliendid, et keskenduda oma kampaaniatele ja tegevustele ning optimeerida suurema tulu saavutamiseks  
- Äriaspektide tuvastamine klientide poolt välja toodud probleemidega  
- Segment kliendid vastavalt nende tundele, et käivitada isikupärastatud kampaaniaid sihitud müügi-, turundus- ja tugitegevusega
- Optimeerige äritegevust, käsitledes probleemseid valdkondi või võimalusi, mida kliendid mainisid
- Tunnustage äriaspekte, millel läheb hästi, ja premeerige õnnelikke kliente lojaalsus- ja müügiedendusprogrammide kaudu

Selleks, et saaksite mudelite tulemusi usaldada, pakume läbipaistvat teavet selle kohta, kuidas mudelid otsuseid teevad. Saate nimekirja sõnadest, mis mõjutasid mudelite otsust määrata tagasiside kommentaaridele konkreetne sentiment skoor või äriaspekt.  

Kasutame kahte **loomuliku keele töötlemise (NLP) mudelit**: esimene määrab igale tagasiside kommentaarile sentimenti skoori. Teine mudel seostab iga tagasiside kõigi kohaldatavate äriaspektidega. Mudeleid koolitatakse avalike andmete põhjal, mis pärinevad sotsiaalmeedia, jaemüügi, restorani, tarbekaupade ja autotööstuse allikatest.    
  
Tagasisideandmetega seostatava mudeli eelnevalt määratletud äriaspektid on järgmised:
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
> Praegu toetame ainult inglise klientide tagasiside sentimenti analüüsi. Tulevikus toetatakse rohkem keeli. Kui tagasiside teistes keeltes on üles laaditud, tagastab mudel siiski tulemused. Kuid need tulemused ei ole täpsed. 

## <a name="prerequisites"></a>eeltingimused

Sentimenti analüüs põhineb teksti tagasiside andmetel, mis on läbinud [andmete ühendamise protsessi](data-unification.md). Soovitame tagasiside andmeolemid [eelnevalt konfigureerida semantiliste tegevusolemitena](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (tagasiside tüüp). 

Tundeanalüüsi mudeli konfigureerimiseks on vaja vähemalt [kaasautori](permissions.md) õigusi.

Customer Insights saab töödelda kuni 10 miljonit tagasisidekirjet ühe mudeli käivitamise kohta. Mudel saab analüüsida tagasiside kommentaare kuni 128 sõna. Kui tagasiside kommentaar on pikem, võetakse analüüsis arvesse ainult esimest 128 sõna.

### <a name="data-requirements"></a>Andmenõuded
  
Vaja on järgmisi andmeatribuute.
- Ühtne kliendi ID (UCID), et sobitada teksti tagasiside andmekirjed konkreetse kliendiga. See ID on andmete ühendamise protsessi [tulemus](data-unification.md).
- Tagasiside ID
- Tagasiside ajatempel
- Tagasiside tekst   

> [!TIP]
> Sentiment analüüs nõuab teksti tagasisidet oma klientidele. Praegu saab konfigureerida ainult ühte tagasisideolemit. Kui tagasisideolemeid on mitu, saate need Power Query enne andmete allaneelamise algust ühendada.

## <a name="configure-a-sentiment-analysis"></a>Tundeanalüüsi konfigureerimine 

1. Avage teenuses Customer Insights jaotised **Ärianalüüs** > **Prognoosid**.

1. Valige paanil **Kliendi** tundeanalüüs **väärtus Kasuta mudelit**.

1. Valige paanil **Kliendi tundeanalüüs (eelvaade)** käsk **Alustamine**.

1. Sisestage juhises **Mudeli** nimi **oma analüüsi jaoks nimi**. 

1. **Esitage ettevõtte aspektiväljundi olemi nimi** ja **Sentimenti skoori väljundi olemi nimi**, seejärel valige **Edasi**.

1. Valige toimingus **Nõutav** andmesuvand **Lisa andmed**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Lisage andmevoog sentimentianalüüsi mudelisse.":::

1. Valige paanil **Andme** lisamine loendist semantiline tüüp **Tagasiside**.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfiguratsioonietapp tagasiside tegevuste valimiseks tunnete analüüsiks.":::

1. Valige selle tundeanalüüsi jaoks kasutatavad tegevused ja seejärel valige **Edasi**.
 
1. Vastendage oma andmete atribuudid mudeli atribuutidega. Valikute rakendamiseks valige **Salvesta**. 

1. Näete andmete vastendamise olekut. Jätkamiseks valige **Edasi**. 

1. **Kinnitage oma tunnete analüüsi konfiguratsiooni jaotises Mudeli üksikasjade** ülevaatamine oma tundeanalüüsi konfiguratsioon. Võite minna tagasi prognoos konfiguratsiooni mis tahes osa juurde. Analüüsi alustamiseks valige **Salvesta ja käivita.** 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Vaadake üle kõik konfigureeritud üksused kuvava tundemudeli etapp.":::

1. Konfiguratsioonikogemusest lahkumiseks valige **Valmis**. Protsessi lõpuleviimiseks võib kuluda mitu tundi, sõltuvalt kasutatud andmete hulgast. 

## <a name="review-analysis-status"></a>Analüüsi oleku ülevaatamine

1.  Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.
2.  Valige prognoos, mille soovite üle vaadata.
- **Prognoosi nimi**: prognoosi loomisel sellele pandud nimi.
- **prognoos tüüp**: prognoos jaoks kasutatava mudeli tüüp.
- **Väljundolem**: olemi nimi, kuhu talletatakse prognoosi väljund. Selle nimega olemi otsimiseks minge asukohta **Andmed** > **Olemid**.
- **Prognoositav väli**: see väli täidetakse ainult kindlat tüüpi prognooside korral ja seda ei kasutata kliendi eluea väärtuse prognoosimisel.
- **Olek**: prognoosi käitamise olek.
  - **Järjekorras**: prognoos ootab muude protsesside lõpetamist.
  - **Värskendamine**: prognoos töötab praegu, et luua tulemusi, mis sisestatakse väljundolemisse.
  - **Nurjunud**: prognoosi käitamine nurjus. Lisateabe saamiseks vaadake üle logid.
  - **Õnnestus**: prognoos on õnnestunud. Valige vertikaalsete kolmikpunktide alt suvand Kuva, et vaadata prognoos tulemusi.
- **Redigeeritud**: prognoosi konfiguratsiooni muutmise kuupäev.
- **Viimati värskendatud**: kuupäev, mil prognoos väljundiolemis värskendas tulemusi.

## <a name="manage-sentiment-analysis"></a>Tunnete analüüsi haldamine

Ennustusi saate optimeerida, tõrkeotsingut, värskendada või kustutada. Vaadake sisendandmete kasutatavuse aruanne üle, et teada saada, kuidas muuta prognoos kiiremaks ja usaldusväärsemaks. Lisateavet leiate teemast [Prognooside haldamine](manage-predictions.md).

## <a name="review-analysis-results"></a>Analüüsi tulemuste ülevaatamine
 
1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**. 
1. Valige selle prognoos nimi, mille puhul soovite tulemusi üle vaadata. Sellisel juhul valige tunnete analüüs, mida soovite üle vaadata. 

### <a name="summary-tab"></a>Vahekaart Kokkuvõte

Tulemuste lehel on neli peamist andmejaotist. 

- **Keskmine tunnete skoor**: aitab teil mõista üldist tunnet kõigis klientides. Sentiment skoorid on rühmitatud kolme kategooriasse: 
  1.    Negatiivne (-5 > 2)
  2.    Neutraalne (-1 > 1)
  3.    Positiivne (2> 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Üldise klienditunde visuaalne esitus.":::

- **Klientide jagamine sentimenti skoori** järgi: kliendid liigitatakse negatiivsetesse, neutraalsetesse ja positiivsetesse rühmadesse vastavalt nende tundetulemustele. Hõljutage histogrammi baaride kohal, et näha klientide arvu ja keskmist meeleolu skoori igas rühmas. Need andmed aitavad teil [luua klientide](segments.md) segmente nende tunnete skooride põhjal.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Lintdiagramm, mis näitab kliendi tundeid kolmes sentimentaalses rühmas.":::

- **Keskmine sentiment skoor aja** jooksul: Klientide meeleolu võib aja jooksul muutuda. Pakume trende teie klientide tunnetes teie andmete ajavahemiku kohta. See vaade aitab teil hinnata hooajaliste kampaaniate, tooteesitluste või muude ajaliselt piiritletud sekkumiste mõju klientide meeleolule. Graafiku vaatamiseks valige rippmenüüst huviaasta. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Ajaloo diagramm, mille tunnete skoor on aja jooksul esitatud reana.":::
 
- **Tunded kõigis äriaspektides**: selles tabelis on loetletud keskmine meeleolu äriaspektide lõikes. See aitab teil hinnata, millised teie ettevõtte aspektid juba rahuldavad kliente või aspekte, mis vajavad rohkem tähelepanu. Tagasisidekirjed, mis ei ühti ühegi toetatud äriaspektiga, liigitatakse jaotisse **Muu**. Tabel sorditakse vaikimisi tähestikulises järjekorras. Sortimist saate muuta, valides tabelipäise.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Äriaspektide loend koos sellega seotud tundeväärtuse ja seda mainivate klientide arvuga.":::
 
  Valige ettevõtte aspekti nimi, et näha lisateavet selle kohta, kuidas mudel ettevõtte aspekti tuvastab. Sellel paanil on kaks osa: 

  - **Mõjukad sõnad**: kuvab peamised sõnad, mis mõjutasid tehisintellekti mudeli äriaspekti tuvastamist klientide tagasisides. 
    **Solvavate sõnade** kuvamine: võimaldab teil lisada loendisse solvavaid sõnu klientide tagasiside algsetest andmetest. Vaikimisi on see välja lülitatud.  Solvav sõna maskeerimine on varustatud AI mudeliga ja ei pruugi tuvastada kõiki solvavaid sõnu. Jätkame klassifikaatori itereerimist ja koolitamist optimaalse jõudluse saavutamiseks. Kui avastate solvava sõna, mida ei filtreeritud ootuspäraselt, andke meile sellest teada. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Nimekiri mõjukatest sõnadest, millel on tumbler, et näidata või peita solvavaid sõnu.":::
 
  - **Tagasiside näidised**: kuvab teie andmetes tegelikud tagasisidekirjed. Sõnad on värvikoodiga vastavalt nende mõjule ettevõtte aspekti tuvastamisele. 


### <a name="influential-words-analysis-tab"></a>Vahekaart Mõjukate sõnade analüüs

Täiendava teabe osas on kolm osa, mis selgitavad, kuidas sentiment mudel töötab.
  
1. **Peamised sõnad, mis aitavad kaasa positiivsele tundele**: näitab tippsõnu, mis mõjutasid AI-mudeli positiivse tunde tuvastamist klientide tagasisides.  
2. **Peamised sõnad, mis aitavad kaasa negatiivsele tundele**: näitab peamisi sõnu, mis mõjutasid AI-mudeli negatiivse tunde tuvastamist klientide tagasisides.  
3. **Tagasiside näidised**: Kuvab tegelikud tagasisidekirjed, millest üks on negatiivse tundega ja teine positiivse tundega. Tagasisidekirjetes olevad sõnad tõstetakse esile vastavalt nende panusele määratud tundeskoori. Sõnad, mis aitavad kaasa positiivsele meeleolu skoorile, tõstetakse esile roheliselt. Negatiivsele skoorile kaasa aitavad sõnad tõstetakse esile punaselt.
   Valige **Kuva rohkem**, et laadida rohkem tagasisidenäidiseid, mis annavad lisateavet ja konteksti selle kohta, kuidas sentimentimudel töötab.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Näited klientide tagasiside sentimenti analüüsist.":::
 
**Solvavate sõnade** kuvamine: võimaldab teil lisada loendisse solvavaid sõnu klientide tagasiside algsetest andmetest. Vaikimisi on see välja lülitatud.  Solvav sõna maskeerimine on varustatud AI mudeliga ja ei pruugi tuvastada kõiki solvavaid sõnu. Jätkame klassifikaatori itereerimist ja koolitamist optimaalse jõudluse saavutamiseks. Kui avastate solvava sõna, mida ei filtreeritud ootuspäraselt, andke meile sellest teada. 

## <a name="act-on-analysis-results"></a>Analüüsitulemuste seadus

Tundeanalüüsi tulemuste lehelt saate hõlpsalt alustada uute kliendisegmentide loomist, valides **mudeli tulemilehe ülaosas suvandi Loo segmendid**.

:::image type="content" source="media/create-segment-model.png" alt-text="Käsuriba koos prognoos mudelite suvanditega.":::
 
## <a name="potential-bias"></a>Potentsiaalne kallutatus

Nagu iga omaduse puhul, mis kasutab ennustavat tehisintellekti, peaksite olema teadlik võimalikust kallutatusest andmetes, mida kasutate klientide meeleolu ennustamiseks. Näiteks kui kogute tagasisidet ainult digitaalselt, võite jääda ilma tagasisidest klientidelt, kes tegelevad teiega peamiselt isiklikult, mis võib mõjutada funktsiooni väljundit.

Kuna see funktsioon kasutab andmete hindamiseks ja nende põhjal prognooside tegemiseks automatiseeritud vahendeid, on tal seega võimalus kasutada profiilide koostamise meetodina, kuna see mõiste on määratletud isikuandmete kaitse üldmäärusega (GDPR). Selle funktsiooni kasutamise kohta andmete töötlemisel võib kehtida kas GDPR või muud seadused või määrused. Teie vastutate Dynamics 365 Customer Insights selle eest, et teie (sh tunnete analüüs) kasutamine oleks kooskõlas kõigi kohaldatavate seaduste ja määrustega, sealhulgas privaatsuse, isikuandmete, biomeetriliste andmete, andmekaitse ja suhtluse konfidentsiaalsusega seotud seadustega.

[!INCLUDE [footer-include](includes/footer-banner.md)]

