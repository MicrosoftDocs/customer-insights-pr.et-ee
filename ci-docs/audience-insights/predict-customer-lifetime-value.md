---
title: Kliendi eluea väärtuse (CLV) prognoos
description: Prognoosige tulevikus aktiivsete klientide tulupotentsiaali.
ms.date: 02/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 740d6a5a749e156414b0e80193334051b7f2632fe4d1f4291d74b99250f35bc2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035364"
---
# <a name="customer-lifetime-value-clv-prediction-preview"></a>Kliendi eluea väärtus (CLV) prognoosimine (eelversioon)

Prognoosige potentsiaalset väärtust (tulu), mille üksikud aktiivsed kliendid teie ettevõttesse toovad, määratletud tulevase ajavahemiku jooksul. Antud funktsioon aitab teil saavutada mitmesuguseid eesmärke. 
- Tehke kindlaks kõrge väärtusega kliendid ja töötlege seda ülevaadet
- Luua strateegilisi kliendisegmente, mis põhinevad nende potentsiaalsel väärtusel käitada isikupärastatud kampaaniaid sihipärase müügi, turunduse ja tugiteenuste abil
- Tootearenduse juhendamine, keskendudes funktsioonidele, mis suurendaksid kliendi väärtust
- Müügi- või turundusstrateegia optimeerimine ja eelarve täpsem sidutamine kliendi väljamüügi jaoks
- Tunnustada ja premeerida väärtuslikke kliente lojaalsus- või preemiaprogrammide abil 

## <a name="prerequisites"></a>Eeltingimused

Enne alustamist meenutage, mida CLV teie ettevõtte jaoks tähendab. Praegu toetame tehingupõhiseid CLV-prognoose. Kliendi prognoositav väärtus põhineb äritehingute ajalool. Prognoosi loomiseks vajate vähemalt [osalise](permissions.md) õigusi.

Kuna CLV mudeli konfigureerimine ja käitamine ei võta palju aega, kaaluge erinevate sisendi eelistustega mudeli loomist ja võrrelge mudelitulemusi, et näha, milline mudelistsenaarium sobib teie ärivajadustega kõige paremini.

###  <a name="data-requirements"></a>Andmenõuded

Järgmised andmed on vajalikud ja kui need on märgitud valikulised, soovituslikult mudeli parema jõudluse saavutamiseks. Mida rohkem andmeid mudel saab töödelda, seda täpsem prognoos on. Seetõttu soovitame teil võimaluse korral kasutada rohkem kliendi tegevuse andmeid.

- Kliendi identifikaator: tehingute ja üksikkliendi vastendamise ainuidentifikaator

- Kannete ajalugu: varasemate kannete logi allpoololeva semantilise andmeskeemiga
    - **Tehingu ID**: Iga tehingu ainuidentifikaator
    - **Kande kuupäev**: Kuupäev, soovitatavalt iga tehingu ajatempel
    - **Kandesumma**: Iga kande rahaline väärtus (nt tulu või kasumimarginaal)
    - **Tagastamisele määratud silt** (valikuline): Loogikaväärtus, mis näitab, kas tegemist on tagastusega 
    - **Toote ID** (valikuline): tehinguga seotud toote ID

- Lisaandmed (valikuline); näiteks
    - Veebitegevused: veebisaidikülastuse ajalugu, meiliajalugu
    - Lojaalsustegevused: lojaalsuspunktide kogunemise ja kasutamise ajalugu
    - Klienditeenindus logi, teeninduskõnede, kaebuste või tagastamiste ajalugu
- Andmed klienditegevuste kohta (valikuline).
    - Tegevuse identifikaatorid, mis eristavad sama tüüpi tegevusi
    - Kliendi identifikaatorid, mis vastendavad teie klientide tegevusi
    - Tegevuse teave, mis sisaldab tegevuse nime ja kuupäeva
    - Tegevuste semantilise andmeskeemi alla kuuluvad järgmised. 
        - **Primaarvõti:**: Tegevuse ainuidentifikaator
        - **Ajatempel**: Primaarvõtmega tuvastatud sündmuse kuupäev ja kellaaeg
        - **Sündmus (tegevuse nimi)**: Soovitud sündmuse nimi
        - **Üksikasjad (summa või väärtus)**: Klienditegevuse üksikasjad

- Soovitatavad andmete omadused:
    - Piisavad varasemad andmed: Vähemalt ühe aasta tehinguandmeid. Eelistatavalt kahe kuni kolme aasta tehinguandmed, et ennustada CLV-d ühe aasta jooksul.
    - Mitu ostu kliendi kohta: Ideaaljuhul vähemalt kaks kuni kolm tehingut kliendi ID kohta, eelistatavalt mitme kuupäeva jooksul.
    - Klientide arv: Vähemalt 100 unikaalset klienti, eelistatuult rohkem kui 10 000 klienti. Mudel nurjub, kui kliente on vähem kui 100 ja puuduvad varasemad andmed
    - Andmete täielikkus: Sisendandmete nõutavatel väljadel on vähem kui 20% puuduvaid väärtusi   

> [!NOTE]
> - Mudeli jaoks on vaja teie klientide tehingute ajalugu. Praegu saab konfigureerida ainult ühe kannete ajaloo olemi. Kui ostuolemeid on mitu, tuleb need liita Power Query'ga enne andmete sisestamist.
> - Täiendavate klienditegevuse andmete jaoks (valikuline) saate siiski lisada nii palju kliendi tegevuse olemeid, kui soovite mudeliga kaaluda.

## <a name="create-a-customer-lifetime-value-prediction"></a>Kliendi eluea väärtuse (CLV) loomine

1. Avage sihtrühmaülevaadetes jaotis **Ärianalüüs** > **Prognoosid**.

1. Valige paan **Kliendi eluea väärtus** ja seejärel **Kasuta mudelit**. 

1. Valige paanil **Kliendi eluea väärtus (eelvaade)** suvand **Alustamine**.

1. **Nimeta see mudel** ja **Väljundi olemi nimi**, et neid muudest mudelitest või olemitest eristada.

1. Tehke valik **Edasi**.

### <a name="define-model-preferences"></a>Mudeli eelistuste määratlemine

1. Määrake **Prognoosi ajaperiood**, et määrata, kui palju tulevikku te soovite CLV-d prognoosida.    
   Vaikimisi on ühikuks seatud kuud. Saate selle muuta aastateks, et kaugemale tulevikku vaadata.

   > [!TIP]
   > Määratletud ajaperioodi CLV täpseks ennustamiseks vajate võrreldavat ajalooliste andmete perioodi. Kui soovite näiteks prognoosida CLV -i järgmise12 kuu lõikes, on soovitatav kasutada vähemalt 18–24 kuud varasemaid andmeid.

1. Määrake, mida **Aktiivsed kliendid** teie ettevõtte jaoks tähendavad. Määrake ajavahemik, mille jooksul peab kliendil olema olnud vähemalt üks tehing, mida loetakse aktiivseks. Mudel prognoosib, ainult aktiivsete klientide CLV-d. 
   - **Mudelil on soovitatav arvutada ostuperiood (soovitatav)**: mudel analüüsib teie andmeid ja määratleb varasematel ostuaegadel põhineva ajavahemiku.
   - **Seadke intervall käsitsi**: kui teil on aktiivse kliendi kindel ärimääratlus, valige see suvand ja määrake vastavalt ajavahemik.

1. Määrake **kõrge väärtusega kliendi** protsent, et mudel võimaldaks pakkuda teie ärimääratlustele sobivaid tulemusi.
    - **Mudeli arvutus (soovitatav)**: mudelis analüüsitakse teie andmeid ja määratletakse klientide tehinguajaloo põhjal, milline on ettevõtte jaoks kõrge väärtusega klient. Mudelis kasutatakse kõrge väärtusega klientide suhtarvu leidmiseks heuristilist reeglit (80/20 reegli või pareto põhimõtte järgi). Kliente, kes on teie ettevõtte jaoks varasematel perioodiperioodil 80% koondtulusid kogunud, loetakse kõrge väärtusega klientideks. Tavaliselt annavad 80% kumulatiivsest tulust vähem kui 30–40% klientidest. Kuid see arv võib sõltuvalt teie ettevõttest ja tööstusest olla erinev.    
    - **Protsent aktiivsetest tippklientidest**: määrake oma ettevõtte jaoks kõrge väärtusega kliendid protsendina aktiivsetest püsiklientidest. Näiteks saate antud suvandi abil määratleda kõrge väärtusega kliendid 20% tulevastest maksvatest klientidest.

    Kui ettevõte määratleb kõrge väärtusega kliente erineval viisil, [andke meile sellest teada](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Järgmise etapi juurde liikumiseks valige nupp **Järgmine**.

### <a name="add-required-data"></a>Lisage nõutud andmed

1. Valige etapis **Vajalikud andmed** jaotises **Kliendi tehinguajalugu** suvand **Lisa andmeid** ja valige olem, mis sisaldab tehinguajaloo teavet, nagu on kirjeldatud [eeltingimustes](#prerequisites).

1. Vastendage semantilised väljad oma ostuajaloo olemi atribuutidega ja valige **Järgmine**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Konfiguratsioonisamm nõutavate andmete andmeatribuutide vastendamiseks":::
 
1. Kui allolevad väljad pole täidetud, konfigureerige oma ostuajaloo olemis seos olemiga *Klient* ja valige **Salvesta**.
    1. Valige tehinguajaloo olem.
    1. Valige väli, mis tuvastab kliendi ostuajaloo olemis. See peab olema seostatud teie kliendiolemi esmase kliendi ID-ga.
    1. Valige olem, mis vastab peamise kliendi olemile.
    1. Tippige seost kirjeldav nimi.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Konfiguratsioonisammu joonis seose määratlemiseks kliendiolemiga.":::

1. Tehke valik **Edasi**.

### <a name="add-optional-data"></a>Valikuliste andmete lisamine

Andmed, mis kajastavad peamisi kliendisuhtlusi (nt veebi-, klienditeenindus- ja sündmuste logid), lisavad tehingute kirjetele konteksti. Täiendavad klienditegevuse andmetes leitud mustrid võib parendada prognoosi täpsust. 

1. Valige etapis **Lisaandmed (valikuline)** suvand **Lisa andmed**. Valige kliendi tegevuse olem, mis sisaldab klienditegevuse teavet, nagu on kirjeldatud [eeltingimustes](#prerequisites).

1. Vastendage semantilised väljad oma klienditegevuse olemi atribuutidega ja valige **Järgmine**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Konfiguratsioonisammu joonis lisaandmete vastendamiseks väljadega.":::

1. Valige tegevuse tüüp, mis vastab teie lisatava kliendi tegevuse tüübile. Valige olemasolevate tegevuste tüüpide hulgast või lisage uus.

1. Konfigureerige seos oma klienditegevuse olemist *Kliendi* olemiga.
    
    1. Valige väli, mis tuvastab kliendi klienditegevuse tabelis. See võib olla otse *Kliendi* olemi peamise kliendi-ID-ga.
    1. Valige *Kliendi* olem, mis vastab teie peamisele *Kliendi* olemile.
    1. Tippige seost kirjeldav nimi.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Konfiguratsioonivoo sammu pilt täiendavate andmete lisamiseks ja tegevuse konfigureerimiseks koos täidetud näidetega.":::

1. Valige **Salvesta**.    
    Lisage rohkem andmeid, kui soovite lisada muid klienditegevusi.

1. Tehke valik **Edasi**.

### <a name="set-update-schedule"></a>Värskendusajakava määratlemine

1. Valige **Andmete värskendamise ajakava** etapist mudeli ümberõppe sagedus võttes aluseks uusimad andmed. See säte on oluline, et värskendada prognooside täpsust uute andmete valmendamisel sihtrühmaülevaadetes. Suur osa ettevõtteid saavad teha ümberõpet kord kuus ja saavutavad täpsed prognoosid.

1. Tehke valik **Edasi**.

### <a name="review-and-run-the-model-configuration"></a>Mudeli konfiguratsiooni läbivaatamine ja käitamine

1. **Kontrollige mudeli üksikasjade** etapis ülevaatamiseks viisardi prognoos. Saate naasta prognoosi mis tahes osasse, valides suvandi **Redigeeri** kuvatud väärtuse juures. Saate ka edenemise indikaatorist valida konfiguratsiooniastme.

1. Kui kõik väärtused on õigesti konfigureeritud, valige mudeli käivitamiseks käsk **Salvesta ja käivita**. Vahekaardil **Minu prognoosid** näete protsessi prognoos. Selle protsessi lõpule viimiseks võib kuluda mitu tundi, olenevalt prognoosis kasutatud andmete hulgast.

## <a name="review-prediction-status-and-results"></a>Vaadake üle prognoosi olek ja tulemused

### <a name="review-prediction-status"></a>Prognoosi oleku ülevaatamine

1.  Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.
2.  Valige prognoos, mille soovite üle vaadata.

- **Prognoosi nimi**: prognoosi loomisel sellele pandud nimi.
- **Prognoosi tüüp**: prognoosi jaoks kasutatud mudeli tüüp
- **Väljundolem**: olemi nimi, kuhu talletatakse prognoosi väljund. Selle nimega olemi otsimiseks minge asukohta **Andmed** > **Olemid**.
- **Prognoositav väli**: see väli täidetakse ainult kindlat tüüpi prognooside korral ja seda ei kasutata kliendi eluea väärtuse prognoosimisel.
- **Olek**: prognoosi käitamise olek.
    - **Järjekorras**: prognoos ootab muude protsesside lõpetamist.
    - **Värskendamine**: prognoos töötab praegu, et luua tulemusi, mis sisestatakse väljundolemisse.
    - **Nurjunud**: prognoosi käitamine nurjus. Lisateabe saamiseks [vaadake üle logid](manage-predictions.md#troubleshoot-a-failed-prediction).
    - **Õnnestus**: prognoos on õnnestunud. Valige vertikaalsete kolmikpunktide alt suvand **Kuva**, et vaadata prognoos tulemusi.
- **Redigeeritud**: prognoosi konfiguratsiooni muutmise kuupäev.
- **Viimati värskendatud**: kuupäev, mil prognoos värskendas tulemusi väljundolemis.

### <a name="review-prediction-results"></a>Prognoosi tulemuste ülevaatamine

1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.

1. Valige prognoos, mille tulemused soovite üle vaadata.

Tulemuste lehel on kolm peamist andmete jaotist.

- **Koolitusmudeli jõudlus**: A, B või C on võimalikud astmed. See hinne näitab prognoosi toimivust ja aitab teil teha otsuse kasutada väljundolemisse salvestatud tulemusi. Valige suvand **Reave selle punktisumma kohta**, et paremini mõista mudeli jõudluse põhimõõdikuid ja lõppmudeli jõudluse klassi tuletamist.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Mudeli punktisumma teabevälja kujutis koos A-klassiga.":::

  Kasutades prognoosi konfigureerimisel esitatud suure väärtusega klientide määratlust, hindab süsteem, kuidas tehisintellekti mudel toimis suure väärtusega klientide ennustamisel võrreldes baasmudeliga.    

  Astmed määratletakse vastavalt järgmistele reeglitele.
  - **A** kui mudel ennustas täpselt vähemalt 5% kõrgema väärtusega kliente võrreldes baasmudeliga.
  - **B** kui mudel ennustas täpselt vahemikus 0-5% kõrgema väärtusega kliente võrreldes baasmudeliga.
  - **C** kui mudel ennustas täpselt vähem kõrgema väärtusega kliente võrreldes baasmudeliga.

  **Mudeli hinnangu** paanil kuvatakse täiendavad üksikasjad AI mudeli jõudluse ja baasmudeli kohta. Baasmudel kasutab tehisintellektivälist lähenemisviisi, et arvutada kliendi eluea väärtus peamiselt klientide varasemate ostude põhjal.     
  Standardvalem, mida kasutatakse CLV arvutamiseks baasmudeli alusel:    

  _**CLV iga kliendi kohta** = Kliendi tehtud keskmine kuu ost aktiivses kliendiaknas *Kuude arv CLV prognoos perioodis* Kõigi klientide üldine retentsioon*_

  AI mudelit võrreldakse kahe mudeli jõudlusemõõdikul põhineva baasmudeliga.
  
  - **Edumäär suure väärtusega klientide prognoosimisel**

    Vaadake erinevust tehisintellekti mudeli abil väärtuslike klientide ennustamisel võrreldes algmudeliga. Näiteks 84% õnnestumismäär tähendab, et kõigi koolitusandmete hea väärtusega klientide seas oli AI-mudeli täpsus 84%. Seejärel võrdleme seda õnnestumismäära baasmudeli õnnestumismääraga, et teatada suhtelisest muudatusest. Seda väärtust kasutatakse mudelile hinnajärgu määramiseks.

  - **Tõrkemõõdikud**
    
    Teine mõõdik võimaldab teil üle vaadata mudeli üldise toimivuse tulevaste väärtuste ennustamisel esinevate vigade osas. Selle vea hindamiseks kasutame mõõdikut RMSE (Root Mean Squared Error). RMSE on standardne viis mõõta viga kvantitatiivsete andmete prognoosimisel. Tehisintellekti mudeli RMSE-d võrreldakse lähtemudeli RMSE-ga ja esitatakse suhteline erinevus.

  AI-mudel prioritiseerib klientide täpse järjestuse vastavalt väärtusele, mille nad teie ettevõttele toovad. Nii et lõpliku mudeli hinde saamiseks kasutatakse ainult väärtuslike klientide ennustamise edukuse määra. RMSE mõõdik on tundlik piirmäärade suhtes. Stsenaariumites, kus teil on väike protsent kliente, kellel on erakordselt suured ostuväärtused, ei pruugi üldine RMSE mõõdik anda täielikku pilti mudeli toimivusest.   

- **Klientide väärtus protsentiili järgi**: kasutades teie kõrge väärtusega klientide määratlust, rühmitatakse kliendid nende CLV ennustamise kriteeriumide põhjal madal- ja kõrge väärtusega rühmadeks ja kuvatakse diagrammil. Histogrammi ribade kohal hõljutades näete igas rühmas klientide arvu ja selle rühma keskmist CLV-d. Need andmed võivad aidata, kui soovite [luua klientide segmente](segments.md), lähtudes nende CLV prognoosidest.

- **Enamus faktoreid on järgmised**: CLV prognoosi loomisel faktoreid, mis põhinevad AI mudelile esitatud sisendandmetel. Kõigi tegurite olulisus arvutatakse selle loodava koondprognoosi jaoks. Nende tegurite abil saate oma prognoosi tulemusi kinnitada. Need tegurid pakuvad ka rohkem teavet kõige mõjukamate tegurite kohta, mis aitasid teie klientidel CLV-d ennustada.

## <a name="manage-predictions"></a>Prognooside haldamine

Prognoose on võimalik optimeerida, tõrkeotsingut teha, värskendada või kustutada. Vaadake sisendandmete kasutatavuse aruanne üle, et teada saada, kuidas muuta prognoos kiiremaks ja usaldusväärsemaks. Lisateavet leiate teemast [Prognooside haldamine](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
