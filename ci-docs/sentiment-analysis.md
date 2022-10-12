---
title: Klientide tagasiside meeleolu analüüsimine (eelvaade)
description: Siit saate teada, kuidas kasutada sentimentanalüüsi mudelit klientide tagasiside kohta Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610458"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Sentimentide analüüsimine klientide tagasisides (eelvaade)

Sentimentanalüüs võimaldab teil sünteesida klientide meelsust ja tuvastada äriaspekte kui parendusvõimalusi. See Customer Insightsi funktsioon aitab teil mõista, mis töötab hästi ja millega peate tegelema. See aitab teil juhtida äritoiminguid, mis võimaldavad kogemusi, mille tulemuseks on kõrge kliendirahulolu ja lojaalsus.

## <a name="overview"></a>Ülevaade

Sentimentanalüüsi funktsioon loob kaks tuletatud ülevaadet kliendi ID kohta. Meeleolu skoor (-5 kuni 5) ja kohaldatavate äriaspektide (ärivaldkondade) loetelu, mis koos aitavad teil klientide tagasisidet paremini mõista.

See analüüs aitab teil:
- Saa ülevaade klientide tunnetest brändi või organisatsiooni suhtes
- Tuvastage negatiivse meelestatusega kliendid, et keskenduda oma kampaaniatele ja seotustele ning optimeerida suurema tootluse saavutamiseks  
- Äriaspektide tuvastamine klientide poolt välja toodud probleemidega  
- Segmentige kliente nende meeleolu põhjal isikupärastatud kampaaniate käitamiseks sihitud müügi-, turundus- ja tugitegevustega
- Optimeerige äritegevust, käsitledes probleemseid valdkondi või võimalusi, mida kliendid mainisid
- Tunnustage äriaspekte, millel läheb hästi, ja premeerige õnnelikke kliente lojaalsus- ja reklaamiprogrammide kaudu

Mudel sisaldab loendit sõnadest, mis mõjutasid mudeli otsust määrata tagasiside kommentaaridele konkreetne meeleoluskoor või äriaspekt.  

Kasutame kahte **loomuliku keele töötlemise (NLP) mudelit**: esimene määrab igale tagasiside kommentaarile meeleolu skoori. Teine mudel seostab iga tagasiside kõigi kohaldatavate äriaspektidega. Mudeleid koolitatakse avalike andmete põhjal, mis pärinevad sotsiaalmeedia, jaemüügi, restoranide, tarbekaupade ja autotööstuse allikatest.
  
Eelnevalt määratletud äriaspektid, mida mudel tagasisideandmetega seostab, hõlmavad järgmist:
- Kontohaldus
- Kassa ja maksmine
- Klienditugi
- Poodi järeletulemisega
- Pakendite saatmine ja toomine
- Ettetellimine
- Hind
- Privaatsus ja turve
- Kampaaniad ja preemiad
- Kviitung ja garantii
- Tagastuse vahetamine ja tühistamine
- Täitmise täpsus
- Veebisaidi/rakenduse kvaliteet

> [!NOTE]
> Praegu toetame meeleoluanalüüsi ainult inglise klientide tagasiside põhjal. Tulevikus toetatakse rohkem keeli. Kui teistes keeltes tagasiside on üles laaditud, tagastab mudel ikkagi tulemused. Kuid need tulemused ei ole täpsed.

## <a name="prerequisites"></a>eeltingimused

- Vähemalt [kaasautori õigused](permissions.md)
- [Ühtse teksti](data-unification.md) tagasiside andmed. Soovitame tungivalt [konfigureerida tagasiside andmeolemid semantilist tüüpi tegevuse olemitena](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (tagasiside tüüp).
- Ühtne kliendi ID (UCID) alates andmete ühendamisest, et sobitada teksti tagasiside andmekirjed üksikkliendiga.
- Tagasiside ID
- Tagasiside ajatempel
- Tagasiside tekst

Customer Insights suudab ühe mudelijooksu jaoks töödelda kuni 10 miljonit tagasisidekirjet. Mudel suudab analüüsida tagasiside kommentaare kuni 128 sõna. Kui tagasiside kommentaar on pikem, võetakse analüüsis arvesse ainult esimest 128 sõna.

> [!NOTE]
> Konfigureerida saab ainult ühte tagasiside olemit. Kui tagasisideolemeid on mitu, ühendage need Power Query enne andmete allaneelamist.

## <a name="configure-a-sentiment-analysis"></a>Sentimentanalüüsi konfigureerimine

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil Loo** paanil Kliendi meeleolu analüüs (eelvaade) **suvand** Kasuta **mudelit**.

1. Seejärel valige suvand **Alustamine**.

1. **Nimetage** analüüs ja esitage **äriaspekti väljundüksuse nimi** ja **Sentiment score väljundüksuse nimi**.

1. Tehke valik **Edasi**.

1. Valige **Lisa andmeid** klientide tagasiside **jaoks**.

1. Valige semantilise tegevuse tüüp **Tagasiside**, mis sisaldab tagasiside andmeid. Kui tegevust pole seadistatud, valige **siin** ja looge see.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Konfiguratsioonietapp tagasisidetegevuste valimiseks sentimentanalüüsiks.":::

1. Valige selles meeleoluanalüüsis kasutatavad tegevused ja seejärel valige **Edasi**.

1. Vastendage andmetes olevad atribuudid mudeliatribuutidega. 

1. Valige **Salvesta**.

1. Tehke valik **Edasi**. Etapp **Läbivaatus ja käivitamine** näitab konfiguratsiooni kokkuvõtet ja annab võimaluse teha muudatusi enne analüüsi loomist.

1. Valige **redigeeri mis** tahes juhis, mida soovite üle vaadata ja teha muudatusi.

1. Kui olete oma valikutega rahul, valige mudeli käitamise alustamiseks Salvesta **ja käivita**. Valige nupp **Valmis**. Vahekaart Minu **ennustused** kuvatakse prognoos loomise ajal. Selle protsessi lõpule viimiseks võib kuluda mitu tundi, olenevalt prognoosis kasutatud andmete hulgast.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Analüüsitulemuste vaatamine

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil Minu ennustused** prognoos soovite vaadata.

Tulemustel on kaks vahekaarti.

### <a name="sumary-tab"></a>Tabel summaarne

Tulemuste lehel on neli peamist andmejaotist.

- **Keskmine sentimenti skoor**: sentimenti skoorid aitavad teil mõista kõigi klientide üldist meeleolu.
  - **Negatiivne** (-5 > 2)
  - **Neutraalne** (-1 > 1)
  - **Positiivne** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Üldise kliendimeeleolu visuaalne esitus.":::

- **Klientide jaotus sentimentskoori** järgi: kliendid liigitatakse nende sentimentskooride põhjal negatiivsetesse, neutraalsetesse ja positiivsetesse rühmadesse. Hõljutage kursorit histogrammi ribade kohal, et näha klientide arvu ja keskmist meeleolu skoori igas rühmas. Need andmed aitavad teil [luua kliendisegmente](prediction-based-segment.md) nende sentimenti skooride põhjal.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Tulpdiagramm, mis näitab klientide meeleolu kolmes meeleolurühmas.":::

- **Keskmine sentimenti skoor aja** jooksul: kliendi meelestatus võib aja jooksul muutuda. Pakume trende teie klientide meeleoludes teie andmete ajavahemiku kohta. See vaade aitab teil hinnata hooajaliste kampaaniate, toodete turuletoomiste või muude ajaliselt piiritletud sekkumiste mõju klientide meeleolule. Vaadake graafikut, valides rippmenüüst huvipakkuva aasta.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Ajaloo diagramm, kus sentimentide skoor aja jooksul on esindatud joonena.":::

- **Sentiment äriaspektide lõikes**: keskmine meeleolu äriaspektide lõikes aitab teil hinnata, millised teie ettevõtte aspektid juba rahuldavad kliente või vajavad rohkem tähelepanu. Tagasisidekirjed, mis ei ühti ühegi toetatud äriaspektiga, on liigitatud muu **alla**. Sortige andmeid, valides mis tahes veeru.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Äriaspektide loetelu koos sellega seotud sentimentväärtusega ja seda mainivate klientide arv.":::

  Valige äriaspekti nimi, et näha, kuidas mudel äriaspekti tuvastab.

  - **Mõjukad sõnad**: peamised sõnad, mis mõjutasid tehisintellekti mudeli äriaspekti tuvastamist klientide tagasisides.
    **Kuva solvavad sõnad**: võimaldab lisada loendisse solvavaid sõnu klientide tagasiside algandmete põhjal. Vaikimisi on see välja lülitatud.  Solvavate sõnade maskeerimine põhineb tehisintellekti mudelil ja ei pruugi tuvastada kõiki solvavaid sõnu. Kui tuvastate solvava sõna, mida ei filtreeritud ootuspäraselt, andke meile sellest teada.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Loend mõjukatest sõnadest, mille lüliti näitab või peidab solvavaid sõnu.":::

  - **Tagasiside näidised**: tegelikud tagasisidekirjed teie andmetes. Sõnad on värvikoodiga vastavalt nende mõjule äriaspekti tuvastamisele.

### <a name="influential-words-analysis-tab"></a>Mõjukate sõnade analüüsi vahekaart

On kolm osa lisateabest, mis selgitavad, kuidas meeleolumudel töötab.
  
- **Peamised sõnad, mis aitavad kaasa positiivsele meeleolule**: peamised sõnad, mis mõjutasid tehisintellekti mudeli positiivse meeleolu tuvastamist klientide tagasisides.  

- **Peamised sõnad, mis aitavad kaasa negatiivsele meeleolule**: peamised sõnad, mis mõjutasid tehisintellekti mudeli negatiivse meeleolu tuvastamist klientide tagasisides.

- **Tagasiside näidised**: tegeliku tagasiside kirjed, üks negatiivse ja teine positiivse meeleoluga. Tagasisidekirjetes olevad sõnad tõstetakse esile vastavalt nende panusele määratud tundeskoori. Sõnad, mis aitavad kaasa positiivse meeleolu skoorile, on esile tõstetud rohelisega. Negatiivsele skoorile kaasaaitavad sõnad on punasega esile tõstetud.
   Rohkemate tagasisidenäidiste laadimiseks valige **Kuva rohkem**.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Näited sentimentanalüüsist klientide tagasiside kohta.":::

**Kuva solvavad sõnad**: võimaldab lisada loendisse solvavaid sõnu klientide tagasiside algandmete põhjal. Vaikimisi on see välja lülitatud.  Solvavate sõnade maskeerimine põhineb tehisintellekti mudelil ja ei pruugi tuvastada kõiki solvavaid sõnu. Kui tuvastate solvava sõna, mida ei filtreeritud ootuspäraselt, andke meile sellest teada.

## <a name="act-on-analysis-results"></a>Analüüsitulemuste põhjal tegutsemine

Sentimentanalüüsi tulemuste põhjal uute kliendisegmentide loomiseks valige **mudeli tulemuse lehe ülaosas suvand Loo segmendid**.

## <a name="potential-bias"></a>Võimalik kallutatus

Nagu iga funktsiooni puhul, mis kasutab ennustavat tehisintellekti, võib ka klientide meeleolu ennustamiseks kasutatavates andmetes olla potentsiaalne kallutatus. Näiteks kui kogute tagasisidet ainult digitaalselt, võite jääda ilma tagasisidest klientidelt, kes teiega peamiselt isiklikult äri ajavad, mis mõjutab funktsiooni väljundit.

Kuna see funktsioon kasutab andmete hindamiseks ja nende põhjal prognooside tegemiseks automatiseeritud vahendeid, on seda võimalik kasutada profiilianalüüsi meetodina, kuna see mõiste on määratletud isikuandmete kaitse üldmääruses ("GDPR"). Selle funktsiooni kasutamise kohta andmete töötlemisel võib kehtida kas GDPR või muud seadused või määrused. Teie vastutate selle eest, et teie kasutamine Dynamics 365 Customer Insights, sealhulgas sentimentanalüüs, vastab kõigile kohaldatavatele seadustele ja määrustele, sealhulgas privaatsuse, isikuandmete, biomeetriliste andmete, andmekaitse ja side konfidentsiaalsusega seotud seadustele.

[!INCLUDE [footer-include](includes/footer-banner.md)]

