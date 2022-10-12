---
title: Kliendi eluea väärtuse (CLV) prognoosimine
description: Prognoosige tulevikus aktiivsete klientide tulupotentsiaali.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610369"
---
# <a name="predict-customer-lifetime-value-clv"></a>Kliendi eluea väärtuse (CLV) prognoosimine

Prognoosige potentsiaalset väärtust (tulu), mille üksikud aktiivsed kliendid teie ettevõttesse toovad, määratletud tulevase ajavahemiku jooksul. See prognoos aitab teil:

- Tuvastage väärtuslikud kliendid ja töötlege seda ülevaadet.
- Looge strateegilisi kliendisegmente nende potentsiaalse väärtuse põhjal isikupärastatud kampaaniate käitamiseks koos sihitud müügi, turunduse ja tugiteenustega.
- Suunake tootearendust, keskendudes funktsioonidele, mis suurendavad kliendi väärtust.
- Optimeerige müügi- või turundusstrateegiat ja jaotage eelarve täpsemalt klientide teavitamiseks.
- Tunnustage ja premeerige väärtuslikke kliente lojaalsus- või preemiaprogrammide kaudu.

Tehke kindlaks, mida CLV teie ettevõtte jaoks tähendab. Toetame tehingupõhist CLV prognoos. Kliendi prognoositav väärtus põhineb äritehingute ajalool. Kaaluge mitme erineva sisendeelistusega mudeli loomist ja võrrelge mudeli tulemusi, et näha, milline mudelistsenaarium sobib teie ettevõtte vajadustega kõige paremini.

> [!TIP]
> Proovige CLV-prognoos näidisandmete abil: [kliendi eluaegne väärtus (CLV) prognoos näidisjuhend](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>eeltingimused

- Vähemalt [kaasautori](permissions.md) õigused
- Vähemalt 100 unikaalset klienti, eelistatavalt üle 10 000 kliendi
- Kliendi identifikaator – kordumatu identifikaator tehingute sobitamiseks üksikkliendiga
- Vähemalt üks aasta tehingute ajalugu, eelistatavalt kaks kuni kolm aastat. Ideaalis vähemalt kaks kuni kolm tehingut kliendi ID kohta, eelistatavalt mitme kuupäeva jooksul. Tehingute ajalugu peab sisaldama järgmist:
  - **Tehingu ID**: Iga tehingu ainuidentifikaator
  - **Tehingu kuupäev**: iga tehingu kuupäev või ajatempel
  - **Kandesumma**: Iga kande rahaline väärtus (nt tulu või kasumimarginaal)
  - **Tagastustele** määratud silt: kahend-/väärväärtus, mis näitab, kas kanne on tagastus
  - **Toote ID**: tehinguga seotud toote ID
- Kliendi tegevuste andmed.
  - **Primaarvõti**: tegevuse kordumatu identifikaator
  - **Ajatempel**: primaarvõtmega tuvastatud sündmuse kuupäev ja kellaaeg
  - **Sündmus (tegevuse nimi):** sündmuse nimi, mida soovite kasutada
  - **Üksikasjad (summa või väärtus)**: Klienditegevuse üksikasjad
- Täiendavad andmed, näiteks:
  - Veebitegevused: veebisaidi külastuste ajalugu või e-posti ajalugu
  - Püsiklienditegevused: püsikliendi preemiapunktide tekke- ja lunastusajalugu
  - Klienditeenindus logi: teenusekõnede, kaebuste või tagastuste ajalugu
  - Kliendiprofiili teave
- Nõutavatel väljadel puuduvad väärtused vähem kui 20%

> [!NOTE]
> Konfigureerida saab ainult ühte kandeajaloo olemit. Kui ostu- või tehinguüksusi on mitu, ühendage need Power Query enne andmete allaneelamist.

## <a name="create-a-customer-lifetime-value-prediction"></a>Kliendi eluea väärtuse (CLV) loomine

Valige **Salvesta mustand** igal ajal, et salvestada prognoos mustandina. Mustand prognoos kuvatakse vahekaardil **Minu ennustused**.

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil** Loo **paanil Kliendi eluaegne väärtus** suvand Kasuta **mudelit**.

1. Seejärel valige suvand **Alustamine**.

1. **Nimeta see mudel** ja **Väljundi olemi nimi**, et neid muudest mudelitest või olemitest eristada.

1. Tehke valik **Edasi**.

### <a name="define-model-preferences"></a>Mudeli eelistuste määratlemine

1. Määrake **Prognoosi ajaperiood**, et määrata, kui palju tulevikku te soovite CLV-d prognoosida. Vaikimisi on ühikuks seatud kuud.

   > [!TIP]
   > Määratud ajavahemiku CLV täpseks prognoosimiseks on vaja võrreldavat ajalooliste andmete perioodi. Näiteks kui soovite ennustada CLV-d järgmiseks 12 kuuks, kasutage vähemalt 18–24 kuu ajaloolisi andmeid.

1. Määrake ajavahemik, mille jooksul peab kliendil olema olnud vähemalt üks tehing, mida loetakse aktiivseks. Mudel ennustab CLV-d ainult aktiivsetele **klientidele**.
   - **Laske mudelil arvutada ostuintervall (soovitatav):** Mudel analüüsib teie andmeid ja määrab ajalooliste ostude põhjal ajavahemiku.
   - **Määrake intervall käsitsi**: aktiivse kliendi määratluse ajaperiood.

1. Määratlege kõrge väärtusega **kliendi** protsentiil.
    - **Mudeli arvutamine (soovitatav)**: mudel kasutab 80/20 reeglit. Kliente, kes on teie ettevõtte jaoks varasematel perioodiperioodil 80% koondtulusid kogunud, loetakse kõrge väärtusega klientideks. Tavaliselt annavad 80% kumulatiivsest tulust vähem kui 30–40% klientidest. Kuid see arv võib sõltuvalt teie ettevõttest ja tööstusest olla erinev.
    - **Aktiivsete tippklientide** protsent: kõrge väärtusega kliendi konkreetne protsentiil. Näiteks sisestage **25**, et määratleda väärtuslikud kliendid tulevaste maksvate klientide 25% parimana.

    Kui ettevõte määratleb kõrge väärtusega kliente erineval viisil, [andke meile sellest teada](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Tehke valik **Edasi**.

### <a name="add-required-data"></a>Lisage nõutud andmed

1. Valige **Lisa andmed** kliendikannete ajaloo **jaoks**.

1. Valige semantilise tegevuse tüüp SalesOrder **või** **SalesOrderLine**, mis sisaldab kannete ajalugu. Kui tegevust pole seadistatud, valige **siin** ja looge see.

1. Kui tegevuste atribuudid olid tegevuse loomisel semantiliselt vastendatud, valige jaotises **Tegevused** konkreetsed atribuudid või olem, millele soovite arvutuses keskenduda. Kui semantilist vastendamist ei toimunud, valige Redigeeri **ja** vastendage oma andmed.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="CLV mudeli jaoks nõutavate andmete lisamine":::

1. Valige **Edasi** ja vaadake üle selle mudeli jaoks vajalikud atribuudid.

1. Valige **Salvesta**.

1. Lisage veel tegevusi või valige **Edasi**.

### <a name="add-optional-activity-data"></a>Valikuliste tegevuste andmete lisamine

Andmed, mis kajastavad peamisi kliendisuhtlusi (nt veebi-, klienditeenindus- ja sündmuste logid), lisavad tehingute kirjetele konteksti. Täiendavad klienditegevuse andmetes leitud mustrid võib parendada prognoosi täpsust.

1. Valige **Lisa andmeid** jaotises **Boosti mudeli ülevaated koos täiendavate tegevusandmetega**.

1. Valige tegevuse tüüp, mis vastab teie lisatava kliendi tegevuse tüübile. Kui tegevust pole seadistatud, valige **siin** ja looge see.

1. Kui jaotises **Tegevused** vastendati tegevuse atribuudid tegevuse loomisel, valige konkreetsed atribuudid või olem, millele soovite arvutuses keskenduda. Kui vastendamist ei toimunud, valige **Redigeeri** ja vastendage oma andmed.

1. Valige **Edasi** ja vaadake üle selle mudeli jaoks vajalikud atribuudid.

1. Valige **Salvesta**.

1. Tehke valik **Edasi**.

1. [Lisage valikulised kliendiandmed](#add-optional-customer-data) või valige **Edasi** ja minge jaotisse [Värskenduste ajakava](#set-update-schedule) määramine.

### <a name="add-optional-customer-data"></a>Valikuliste kliendiandmete lisamine

Valige 18 tavaliselt kasutatava kliendiprofiili atribuudi hulgast, mida mudeli sisendina lisada. Need atribuudid võivad viia teie ettevõtte kasutusjuhtumite puhul isikupärasemate, asjakohasemate ja teostatavamate mudelitulemusteni.

Näiteks: Contoso Coffee soovib ennustada kliendi eluaegset väärtust, et sihtida kõrge väärtusega kliente isikupärastatud pakkumisega, mis on seotud nende uue espressomasina turuletoomisega. Contoso kasutab CLV mudelit ja lisab kõik 18 kliendiprofiili atribuuti, et näha, millised tegurid mõjutavad nende kõrgeima väärtusega kliente. Nad leiavad, et kliendi asukoht on nende klientide jaoks kõige mõjukam tegur.
Selle teabe abil korraldavad nad espressomasina käivitamiseks kohaliku ürituse ja teevad koostööd kohalike müüjatega isikupärastatud pakkumiste ja ürituse erilise kogemuse saamiseks. Ilma selle teabeta oleksid Contoso võib-olla saatnud ainult üldisi turundusmeile ja jätnud kasutamata võimaluse isikupärastada seda kohalikku segmenti oma väärtuslikest klientidest.

1. Valige **Lisa andmeid** jaotises **Boosti mudeliülevaated veelgi koos täiendavate kliendiandmetega**.

1. Olemi **puhul** valige **Customer: CustomerInsights**, et valida ühtne kliendiprofiil, mis vastendab kliendiatribuutide andmed. Kliendi ID **jaoks** valige **System.Customer.CustomerId**.

1. Vastendage rohkem välju, kui andmed on teie ühendatud kliendiprofiilides saadaval.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Kliendiprofiili andmete vastendatud väljade näide.":::

1. Valige **Salvesta**.

1. Tehke valik **Edasi**.

### <a name="set-update-schedule"></a>Värskendusajakava määratlemine

1. Valige mudeli ümberõppe sagedus uusimate andmete põhjal. See säte on oluline prognooside täpsuse värskendamiseks, kuna Customer Insightsi lisatakse uusi andmeid. Suur osa ettevõtteid saavad teha ümberõpet kord kuus ja saavutavad täpsed prognoosid.

1. Tehke valik **Edasi**.

### <a name="review-and-run-the-model-configuration"></a>Mudeli konfiguratsiooni läbivaatamine ja käitamine

Etapp **Läbivaatus ja käivitamine** näitab konfiguratsiooni kokkuvõtet ja annab võimaluse teha muudatusi enne prognoos loomist.

1. Valige **redigeeri mis** tahes juhis, mida soovite üle vaadata ja teha muudatusi.

1. Kui olete oma valikutega rahul, valige mudeli käitamise alustamiseks Salvesta **ja käivita**. Valige nupp **Valmis**. Vahekaart Minu **ennustused** kuvatakse prognoos loomise ajal. Selle protsessi lõpule viimiseks võib kuluda mitu tundi, olenevalt prognoosis kasutatud andmete hulgast.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prognoos tulemuste vaatamine

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil Minu ennustused** prognoos soovite vaadata.

Tulemuste lehel on kolm peamist andmete jaotist.

- **Koolitusmudeli toimivus**: hinded A, B või C näitavad prognoos toimivust ja aitavad teil teha otsuse väljundolemisse salvestatud tulemuste kasutamise kohta.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Mudeli punktisumma teabevälja kujutis koos A-klassiga.":::

  Customer Insights hindab, kuidas tehisintellekti mudel toimis kõrge väärtusega klientide prognoosimisel võrreldes alusmudeliga.

  Astmed määratletakse vastavalt järgmistele reeglitele.
  - **A** kui mudel ennustas täpselt vähemalt 5% kõrgema väärtusega kliente võrreldes baasmudeliga.
  - **B** kui mudel ennustas täpselt vahemikus 0-5% kõrgema väärtusega kliente võrreldes baasmudeliga.
  - **C** kui mudel ennustas täpselt vähem kõrgema väärtusega kliente võrreldes baasmudeliga.
  
  Valige [**Suvand Lisateave selle skoori**](#learn-about-the-score) kohta, et avada **paan Mudeli hinnang**, kus kuvatakse lisateavet tehisintellekti mudeli jõudluse ja alusmudeli kohta. See aitab teil paremini mõista aluseks olevaid mudeli tulemuslikkuse mõõdikuid ja seda, kuidas mudeli lõplik toimivusklass tuletati. Baasmudel kasutab tehisintellektivälist lähenemisviisi, et arvutada kliendi eluea väärtus peamiselt klientide varasemate ostude põhjal.

- **Klientide väärtus protsentiiliga**: madala ja kõrge väärtusega kliendid kuvatakse diagrammil. Hõljutage kursorit histogrammi ribade kohal, et näha iga grupi klientide arvu ja selle grupi keskmist CLV-d. Soovi korral [looge klientide](prediction-based-segment.md) segmendid nende CLV prognooside põhjal.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Klientide väärtus protsentiiliga CLV mudeli puhul":::

- **Enamus faktoreid on järgmised**: CLV prognoosi loomisel faktoreid, mis põhinevad AI mudelile esitatud sisendandmetel. Kõigi tegurite olulisus arvutatakse selle loodava koondprognoosi jaoks. Kasutage neid tegureid oma prognoos tulemuste valideerimiseks. Need tegurid pakuvad ka rohkem teavet kõige mõjukamate tegurite kohta, mis aitasid teie klientidel CLV-d ennustada.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="CLV mudeli kõige mõjukamad tegurid":::

### <a name="learn-about-the-score"></a>Lisateave skoori kohta

Standardvalem, mida kasutatakse CLV arvutamiseks baasmudeli alusel:

 _**CLV iga kliendi** kohta = keskmine igakuine ost, mille klient on teinud aktiivse kliendi aknas * Kuude arv CLV prognoos perioodil * Kõigi klientide üldine säilitusmäär_

AI mudelit võrreldakse kahe mudeli jõudlusemõõdikul põhineva baasmudeliga.
  
- **Edumäär suure väärtusega klientide prognoosimisel**

  Vaadake erinevust tehisintellekti mudeli abil väärtuslike klientide ennustamisel võrreldes algmudeliga. Näiteks 84% õnnestumismäär tähendab, et kõigi koolitusandmete hea väärtusega klientide seas oli AI-mudeli täpsus 84%. Seejärel võrdleme seda õnnestumismäära baasmudeli õnnestumismääraga, et teatada suhtelisest muudatusest. Seda väärtust kasutatakse mudelile hinnajärgu määramiseks.

- **Tõrkemõõdikud**

  Vaadake mudeli üldist toimivust vigade osas tulevaste väärtuste prognoosimisel. Selle vea hindamiseks kasutame mõõdikut RMSE (Root Mean Squared Error). RMSE on standardne viis mõõta viga kvantitatiivsete andmete prognoosimisel. Tehisintellekti mudeli RMSE-d võrreldakse lähtemudeli RMSE-ga ja esitatakse suhteline erinevus.

AI-mudel prioritiseerib klientide täpse järjestuse vastavalt väärtusele, mille nad teie ettevõttele toovad. Nii et lõpliku mudeli hinde saamiseks kasutatakse ainult väärtuslike klientide ennustamise edukuse määra. RMSE mõõdik on tundlik piirmäärade suhtes. Stsenaariumites, kus teil on väike protsent kliente, kellel on erakordselt suured ostuväärtused, ei pruugi üldine RMSE mõõdik anda täielikku pilti mudeli toimivusest.

[!INCLUDE [footer-include](includes/footer-banner.md)]
