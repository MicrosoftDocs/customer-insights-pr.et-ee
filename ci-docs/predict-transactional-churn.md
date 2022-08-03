---
title: Tehingute prognoos (sisaldab videot)
description: Prognoosige, kas on oht, et klient ei osta enam teie ettevõtte tooteid või teenuseid.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b8216b5a739964fdfff8cad7e6d6d7ce3f5308b5
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171090"
---
# <a name="transaction-churn-prediction"></a>Tehinguvoolavuse prognoos

Tehinguvoolavuse prognoos aitab ennustada, kas klient on lõpetanud kindlal perioodil teie toodete või teenuste ostmise. Saate luua uusi voolavusprognoose, liikudes **Ärianalüüs** > **Prognoosid**. Muude loodud prognooside kuvamiseks valige **Minu prognoosid**. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Ärikontodel põhinevate keskkondade puhul võime ennustada ettevõtte jaoks tehinguvoolavust, samuti ettevõtte ja muu taseme teabe nagu tootekategooria kombinatsiooni. Mõõtme lisamine võib aidata välja selgitada, kui tõenäoline on, et konto „Contoso” lõpetab tootekategooria „kontoritarbed” ostmise. Lisaks võime ärikontode puhul kasutada AI-d ka potentsiaalsete põhjuste loendi loomiseks, miks ettevõte võib teise taseme teabe kategoorias tõenäoliselt liikuda.

> [!TIP]
> Proovige näidisandmete abil prognoos tehingute tegemise õpetust: [Tehingu prognoos näidisjuhend](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>eeltingimused

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

- Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.
- Äriteadmised voolavuse tähendusest teie ettevõttes. Toetame ajapõhiseid voolavuse määratlusi, mis tähendab, et klient loetakse loobunuks, kui ta pole mingi perioodi jooksul oste teinud.
- Andmed teie tehingute/ostude ja nende ajaloo kohta.
    - Tehinguidentifikaatorid, et eristada oste/tehinguid.
    - Kliendiidentifikaatorid, et ühitada tehingud teie klientidega.
    - Tehingusündmuse kuupäevad, mis määratlevad tehingu toimumise kuupäevad.
    - Ostude/tehingute semantilise andmeskeemi jaoks on vajalik järgmine teave.
        - **Tehingu ID**: Ostu või tehingu ainuidentifikaator.
        - **Tehingu kuupäev**: Ostu või tehingu kuupäev.
        - **Tehingu väärtus**: Tehingu/kauba rahalise/numbrilise väärtuse summa.
        - (Valikuline) **Kordumatu toote ID**: Ostetud toote või teenuse ID, kui teie andmed on reakauba tasemel.
        - (Valikuline) **Kas see tehing oli tagastamine**: Tõene/väär väli, mis määrab, kas tehingu puhul oli tegemist tagastamisega või mitte. Kui **Tehingu väärtus** on negatiivne, kasutame seda teavet samuti tagastamise järeldamiseks.
- (Valikuline) Andmed klienditegevuste kohta.
    - Tegevuse identifikaatorid, mis eristavad sama tüüpi tegevusi.
    - Kliendi identifikaatorid, mis vastendavad teie klientide tegevusi.
    - Tegevuse teave, mis sisaldab tegevuse nime ja kuupäeva.
    - Kliendi tegevuste semantiline andmete skeem sisaldab järgmist.
        - **Primaarvõti:** tegevuse ainuidentifikaator. Näiteks veebisaidikülastus või kasutuskirje, mis näitab, et klient proovis teie toote näidist.
        - **Ajatempel:** primaarvõtmega tuvastatud sündmuse kuupäev ja kellaaeg.
        - **Sündmus:** sündmuse nimi, mida soovite kasutada. Näiteks väli nimega „UserAction“ võid toidupoe korral märkida, et klient kasutas kupongi.
        - **Üksikasjad:** sündmuse üksikasjalik teave. Näiteks väli nimega „CouponValue“ võib olla toidupoes kupongi rahaline väärtus.

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

- Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.
- Äriteadmised voolavuse tähendusest teie ettevõttes. Toetame ajapõhiseid voolavuse määratlusi, mis tähendab, et klient loetakse loobunuks, kui ta pole mingi perioodi jooksul oste teinud.
- Andmed teie tehingute/ostude ja nende ajaloo kohta.
    - Tehinguidentifikaatorid, et eristada oste/tehinguid.
    - Kliendiidentifikaatorid, et ühitada tehingud teie klientidega.
    - Tehingusündmuse kuupäevad, mis määratlevad tehingu toimumise kuupäevad.
    - Ostude/tehingute semantilise andmeskeemi jaoks on vajalik järgmine teave.
        - **Tehingu ID**: Ostu või tehingu ainuidentifikaator.
        - **Tehingu kuupäev**: Ostu või tehingu kuupäev.
        - **Tehingu väärtus**: Tehingu/kauba rahalise/numbrilise väärtuse summa.
        - (Valikuline) **Kordumatu toote ID**: Ostetud toote või teenuse ID, kui teie andmed on reakauba tasemel.
        - (Valikuline) **Kas see tehing oli tagastamine**: Tõene/väär väli, mis määrab, kas tehingu puhul oli tegemist tagastamisega või mitte. Kui **Tehingu väärtus** on negatiivne, kasutame seda teavet samuti tagastamise järeldamiseks.
- (Valikuline) Andmed klienditegevuste kohta.
    - Tegevuse identifikaatorid, mis eristavad sama tüüpi tegevusi.
    - Kliendi identifikaatorid, mis vastendavad teie klientide tegevusi.
    - Tegevuse teave, mis sisaldab tegevuse nime ja kuupäeva.
    - Kliendi tegevuste semantiline andmete skeem sisaldab järgmist.
        - **Primaarvõti:** tegevuse ainuidentifikaator. Näiteks veebisaidikülastus või kasutuskirje, mis näitab, et klient proovis teie toote näidist.
        - **Ajatempel:** primaarvõtmega tuvastatud sündmuse kuupäev ja kellaaeg.
        - **Sündmus:** sündmuse nimi, mida soovite kasutada. Näiteks väli nimega „UserAction“ võid toidupoe korral märkida, et klient kasutas kupongi.
        - **Üksikasjad:** sündmuse üksikasjalik teave. Näiteks väli nimega „CouponValue“ võib olla toidupoes kupongi rahaline väärtus.
- (Valikuline) Andmed klientide kohta:
    - Need andmed peaksid joonduma staatiliste atribuutide poole, et mudel toimiks kõige paremini.
    - Klientide andmete semantilise andmeskeemi hulka kuuluvad:
        - **KliendiID:** Kliendi kordumatu ID.
        - **Loomise kuupäev:** Kuupäev, millal klient algselt lisati.
        - **Osariik või maakond:** Kliendi osariik või maakond.
        - **Riik:** Kliendi riik.
        - **Valdkond:** Kliendi valdkonnatüüp. Näiteks kohvi röstkoja väli „Tööstus” võib näidata, kas klient oli jaemüügis.
        - **Klassifitseerimine:** Kliendi liigitus teie ettevõtte jaoks. Näiteks kohvi röstkoja väli „ValueSegment” võib olla kliendi tasand kliendi suuruse põhjal.

---

- Soovitatavad andmete omadused:
    - Piisavad ajaloolised andmed: Tellimuse andmed vähemalt kahekordistatud valitud ajaaknas. Eelistatavalt kahe kuni kolme aasta tehingute ajalugu. 
    - Mitu ostu kliendi kohta: ideaalne oleks vähemalt kaks tehingut kliendi kohta.
    - Klientide arv: Vähemalt 10 kliendiprofiili, eelistatuult rohkem kui 1000 erinevat klienti. Mudel nurjub, kui kliente on vähem kui 10 ja puuduvad varasemad andmed.
    - Andmete täielikkus: esitatud olemi andmeväljal on puuduvaid väärtuseid vähem kui 20%.

> [!NOTE]
> Ettevõtte jaoks, kelle klientide ostu sagedus on kõrge (iga paari nädala tagant), on soovitatav valida lühem prognoosiaken ja voolavuse määratlus. Ostude madal sagedus (iga paari kuu tagant või kord aastas) korral valige pikem prognoosiaken ja voolavuse määratlus.

## <a name="create-a-transaction-churn-prediction"></a>Tehinguvoolavuse prgonoosi loomine

1. Avage teenuses Customer Insights jaotised **Ärianalüüs** > **Prognoosid**.

1. **Valige paan Customer churn model** ja valige **Use this model (Kasuta seda mudelit)**.

1. Valige **Kliendivoolavuse mudelipaanil** **Tehing** ja seejärel **Alustage**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Kuvatõmmis kliendivoolavuse mudelipaanil valitud kandessuvandiga.":::
 
### <a name="name-model"></a>Mudelile nime panemine

1. Sisestage mudelile nimi, et eristada seda teistest mudelitest.

1. Sisestage väljundolemi nimi, kasutades ainult tähti ja numbreid, ilma tühikuteta. Seda nime kasutab mudeli olem. 

1. Tehke valik **Edasi**.

### <a name="define-customer-churn"></a>Määratlege kliendi teenusest loobumine

1. Seadke **prognoos aken**. Näiteks ennustage oma klientide voolavusriski järgmise 90 päeva jooksul, et kohandada oma klientide säilitamise jõupingutusi. Voolavusriski ennustamine pikema või lühema ajavahemiku jooksul võib raskendada voolavusriski tekitavate tegurite käsitlemist, kuid see sõltub teie ettevõtte vajadustest.
   >[!TIP]
   > Saate valida käsu **Salvesta mustand** igal ajal, et salvestada prognoos mustandina. Prognoosi mustandi leiate vahekaardilt **Minu prognoosid** selle jätkamiseks.

1. Sisestage väljale Churn definitsioon **päevade arv, et määratleda churn**. Näiteks kui klient pole viimase 30 päeva jooksul oste teinud, võib neid pidada teie ettevõttest loobunuks. 

1. Jätkamiseks valige **Edasi**.

### <a name="add-required-data"></a>Lisage nõutud andmed

1. Valige **Lisa andmed** ja valige tegevusetüüp, mis sisaldab nõutavat kannete või ostuajaloo teavet.

1. Valige jaotises **Tegevuste** valimine valitud tegevuse tüübist konkreetsed tegevused, millele soovite arvutuses keskenduda.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Kõrvalpaan, kus kuvatakse kindlate tegevuste valimine semantilise tüübi all.":::

   Kui te pole tegevust veel semantilise tüübiga vastendanud, valige selleks **Redigeeri**. Avaneb juhendav kogemus semantilise tegevuse kaardismiseks. Vastendage oma andmed valitud tegevuste tüübi vastavate väljadega.

1. Vastendage semantilised atribuudid väljadega, mis on mudeli käivitamiseks vajalikud. Kui allolevad väljad pole täidetud, konfigureerige oma ostuajaloo olemis seos *Kliendi* olemiga. Valige **Salvesta**.

1. **Valige etapis Nõutavate andmete** lisamine nupp **Edasi**, et jätkata, kui te ei soovi rohkem tegevusi lisada.


# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Lisage Lisaandmed (valikuline)

Konfigureerige seos oma klienditegevuse olemist *Kliendi* olemiga.

1. Valige väli, mis tuvastab kliendi klienditegevuse tabelis. See võib olla otse *Kliendi* olemi peamise kliendi-ID-ga.

1. Valige olem, mis on teie peamine *Kliendi* olem.

1. Tippige seost kirjeldav nimi.

#### <a name="customer-activities"></a>Kliendi tegevused

1. Soovi korral valige jaotises **Klienditegevused** suvand **Lisa andmed**.

1. Valige semantilise tegevuse tüüp, mis sisaldab andmeid, mida soovite kasutada, ja seejärel valige jaotises **Tegevused** üks või mitu tegevust.

1. Valige tegevuse tüüp, mis vastab konfigureeritavale kliendi tegevuse tüübile. Valige **Loo uus** ja valige saadaolev tegevusetüüp või looge uus tüüp.

1. Valige suvand **Edasi** ja seejärel **Salvesta**.

1. Kui teil on mõni muu klienditegevus, mida soovite kaasata, korrake ülaltoodud samme.

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

### <a name="select-prediction-level"></a>Valige progonoosi tase

Enamik ennustusi luuakse kliendi tasandil. Mõnes olukorras ei pruugi see olla nii suur, et see vastaks teie ärivajadustele. Seda funktsiooni saate kasutada näiteks kliendi haru ennustamiseks, mitte kliendi kui terviku jaoks.

1. Kui soovite prognoosi kliendist rohkem vormi tasandil, siis **Valige olem teisese taseme jaoks**. Kui see suvand pole saadaval, veenduge, et olete eelmise jaotise lõpule viinud.

1. Laiendage olemid, millelt soovite teisese taseme valida, või kasutage valitud suvandite filtreerimiseks otsingufiltrivälja.

1. Valige atribuut, mida soovite kasutada teisese tasemena, ja seejärel valige **Lisa**.

1. Tehke valik **Edasi**.

> [!NOTE]
> Selles jaotises saadaolevad olemid kuvatakse seetõttu, et neil on seos eelmises jaotises valitud olemiga. Kui te ei näe olemit, mida lisada soovite, siis veenduge, et sellel oleks seostes kehtiv **Seos**. Konfiguratsiooni puhul sobivad ainult üks-ühele ja mitu-ühele seosed.

### <a name="add-additional-data-optional"></a>Lisage Lisaandmed (valikuline)

Konfigureerige seos oma klienditegevuse olemist *Kliendi* olemiga.

1. Valige väli, mis tuvastab kliendi klienditegevuse tabelis. See võib olla otse *Kliendi* olemi peamise kliendi-ID-ga.

1. Valige olem, mis on teie peamine *Kliendi* olem.

1. Tippige seost kirjeldav nimi.

#### <a name="customer-activities"></a>Kliendi tegevused

1. Soovi korral valige jaotises **Klienditegevused** suvand **Lisa andmed**.

1. Valige semantilise tegevuse tüüp, mis sisaldab andmeid, mida soovite kasutada, ja seejärel valige jaotises **Tegevused** üks või mitu tegevust.

1. Valige tegevuse tüüp, mis vastab konfigureeritavale kliendi tegevuse tüübile. Valige **Loo uus** ja valige saadaolev tegevusetüüp või looge uus tüüp.

1. Valige suvand **Edasi** ja seejärel **Salvesta**.

1. Kui teil on mõni muu klienditegevus, mida soovite kaasata, korrake ülaltoodud samme.

#### <a name="customers-data"></a>Klientide andmed

1. Soovi korral tehke valik **Andmete lisamine** **Klientide andmete jaoks**.

1. Vastendage semantilised atribuudid väljadega oma kliendiandmetes vastavalt tuvastatud andmetele. Kasutatud väljade andmeid ei tohiks sageli muuta, et tagada mudeli parim jõudlus. Kui valite näiteks iga kuu muudetud välja „Klassifitseerimine”, oleks prognoosi puhul ainult viimane väärtus, ehkki sama väärtus ei pruugi ajalooliselt kehtida kliendile prognoosi loomise ajal.

1. Tehke valik **Edasi**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Esitab valikulise loendi ettevõtetest, mis on seotud kontodega

Lisage loend äriklientidest ja ettevõtetest, mida soovite kasutada kriteeriumite lisana. Saate [detailid nende võrdluskontode kohta](#review-a-prediction-status-and-results), sealhulgas nende aeglustumisskoori ja kõige mõjukamad funktsioonid, mis mõjutasid nende arvu ennustamist.

1. Valige **+ Lisa kliente**.

1. Valige võrdlusalusena tegutsevad kliendid.

1. Jätkamiseks valige **Edasi**.

---

### <a name="set-schedule-and-review-configuration"></a>Ajakava seadistamine ja konfiguratsiooni ülevaatamine

1. Määrake oma mudeli ümberõppe sagedus. See säte on oluline, et värskendada prognooside täpsust uute andmete valmendamisel. Suur osa ettevõtteid saavad teha ümberõpet kord kuus ja saavutavad täpsed prognoosid.

1. Tehke valik **Edasi**.

1. Vaadake prognoosi konfiguratsiooni üle. Saate tagasi minna eelmiste etappide juurde, valides kuvatud väärtuse all **Redigeeri**. Saate ka valida edenemise näidikust konfiguratsiooni etapi.

1. Kui kõik väärtused on õigesti konfigureeritud, valige pognoosimisprotsessi alustamiseks suvand **Salvesta ja käivita**. Vahekaardil **Minu prognoosid** kuvatakse teie prognooside olekut. Selle protsessi lõpule viimiseks võib kuluda mitu tundi, olenevalt prognoosis kasutatud andmete hulgast.

## <a name="review-a-prediction-status-and-results"></a>Prognoosi oleku ja tulemuste läbivaatamine

1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.

1. Valige prognoos, mille soovite üle vaadata.
   - **Prognoosi nimi**: prognoosi loomisel sellele pandud nimi.
   - **Prognoosi tüüp**: prognoosi jaoks kasutatud mudeli tüüp
   - **Väljundolem**: olemi nimi, kuhu talletatakse prognoosi väljund. Selle nimega olemi leiate jaotisest **Andmed** > **Olemid**.
     Väljundolemis *Voolavuse tulemus* on prognoositud voolavuse tõenäosus ja *On voolavus* on binaarne märgis, mis põhineb *Voolavuse tulemusel* lävendiga 0,5. Vaikelävend ei pruugi teie stsenaariumi puhul töötada. [Looge uus segment](segments.md#create-a-segment) teie eelistatud lävendiga.
     Kõik kliendid ei pruugi olla aktiivsed kliendid. Võimalik, et mõnel neist pole pikka aega ühtegi tegevust olnud ja neid peetakse juba "voolanuks", võttes aluseks teie voolavuse määratluse. Ennustamise risk klientide jaoks, kes juba voolasid, ei ole kasulik, kuna nemad ei ole sihtrühmas.
   - **Prognoositav väli**: See väli täidetakse ainult kindlat tüüpi prognooside korral ja seda ei kasutata voolavuse prognoosimisel.
   - **Olek**: prognoosi käitamise olek.
        - **Järjekorras**: Prognoos ootab muude protsesside käivitamist.
        - **Värskendamine**: Prognoos töötab praegu, et luua tulemusi, mis sisestatakse väljundolemisse.
        - **Nurjunud**: prognoosi käitamine nurjus. Lisateabe saamiseks [vaadake üle logid](manage-predictions.md#troubleshoot-a-failed-prediction).
        - **Õnnestus**: prognoos on õnnestunud. Valige prognoosi läbivaatamiseks **Vaade** vertikaalse kolmikpunkti juures
   - **Redigeeritud**: prognoosi konfiguratsiooni muutmise kuupäev.
   - **Viimati värskendatud**: kuupäev, mil prognoos värskendas tulemusi väljundolemis.

1. Valige vertikaalne kolmikpunkt prognoosi kõrval, mille tulemusi soovite läbivaadata ja valige **Vaade**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Juhtelement „Kuva“ prognoosi tulemuste vaatamiseks.":::

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

1. Tulemuste lehel on kolm peamist andmete jaotist.
   - **Koolituse mudeli jõudlus**: Võimalikud punktisummad on A, B või C. See skoor näitab prognoosi jõudlust ja aitab teil otsustada, kas kasutada väljundolemis talletatud tulemusi. Skoorid määratletakse järgmiste reeglite alusel. 
        - **A**, kui vähemalt 50% kõikidest prognoosidest olid täpsed ja kui täpsete loobunud klientide prognooside protsent on alusmäärast vähemalt 10% suurem.
            
        - **B**, kui vähemalt 50% kõikidest prognoosidest olid täpsed ja kui täpsete loobunud klientide prognooside protsent on alusmäärast kuni 10% suurem.
            
        - **C**, kui vähem kui 50% kõikidest prognoosidest olid täpsed või kui täpsete loobunud klientide prognooside protsent on alusmäärast väiksem.
               
        - **Aluse** jaoks võetakse mudeli prognoosiajavahemiku sisend (näiteks üks aasta) ja luuakse eri ajalõigud, jagades ajavahemikku kahega, kuni see on üks kuu või väiksem. Mudel kasutab neid ajalõike, et luua ärireegel klientidele, kes pole selles ajavahemikus oste teinud. Need kliendid loetakse loobunuks. Alusmudeliks valitakse ajapõhine ärireegel, mis ennustab kõige täpsemini, kes võib loobuda.
            
    - **Voolavuse tõenäosus (klientide arv)**: Kliendirühmad nende prognoositud voolavuse riski põhjal. Need andmed aitavad teil hiljem soovi korral luua kõrge voolavuse riskiga klientide segmendi. Sellised segmendid aitavad mõista, kus segmendi liikmelisuse sulgemiskuupäev peaks olema.
       
    - **Kõige mõjukamad tegurid**: Prognoosi loomisel võetakse arvesse paljusid tegureid. Mudeli loodavate koondprognooside jaoks arvutatakse iga teguri olulisus. Nende tegurite abil saate oma tulemuste valideerimist prognoos või saate selle teabe abil hiljem [luua segmente](segments.md), mis võivad aidata klientide puhul identimisriske mõjutada.


# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

1. Tulemuste lehel on kolm peamist andmete jaotist.
   - **Koolituse mudeli jõudlus**: Võimalikud punktisummad on A, B või C. See skoor näitab prognoosi jõudlust ja aitab teil otsustada, kas kasutada väljundolemis talletatud tulemusi. Skoorid määratletakse järgmiste reeglite alusel. 
        - **A**, kui vähemalt 50% kõikidest prognoosidest olid täpsed ja kui täpsete loobunud klientide prognooside protsent on alusmäärast vähemalt 10% suurem.
            
        - **B**, kui vähemalt 50% kõikidest prognoosidest olid täpsed ja kui täpsete loobunud klientide prognooside protsent on alusmäärast kuni 10% suurem.
            
        - **C**, kui vähem kui 50% kõikidest prognoosidest olid täpsed või kui täpsete loobunud klientide prognooside protsent on alusmäärast väiksem.
               
        - **Aluse** jaoks võetakse mudeli prognoosiajavahemiku sisend (näiteks üks aasta) ja luuakse eri ajalõigud, jagades ajavahemikku kahega, kuni see on üks kuu või väiksem. Mudel kasutab neid ajalõike, et luua ärireegel klientidele, kes pole selles ajavahemikus oste teinud. Need kliendid loetakse loobunuks. Alusmudeliks valitakse ajapõhine ärireegel, mis ennustab kõige täpsemini, kes võib loobuda.
            
    - **Voolavuse tõenäosus (klientide arv)**: Kliendirühmad nende prognoositud voolavuse riski põhjal. Need andmed aitavad teil hiljem soovi korral luua kõrge voolavuse riskiga klientide segmendi. Sellised segmendid aitavad mõista, kus segmendi liikmelisuse sulgemiskuupäev peaks olema.
       
    - **Kõige mõjukamad tegurid**: Prognoosi loomisel võetakse arvesse paljusid tegureid. Mudeli loodavate koondprognooside jaoks arvutatakse iga teguri olulisus. Nende tegurite abil saate oma tulemuste valideerimist prognoos või saate selle teabe abil hiljem [luua segmente](segments.md), mis võivad aidata klientide puhul identimisriske mõjutada.


1. Äriettevõtete jaoks leiate **Mõjutavate funktsioonide analüüsi** teabelehe. See koosneb neljast andmejaost:

    - Parempoolsel paanil valitud üksus määratleb selle lehe sisu. Valige üksus klientidest **Tippkliendid** või **Võrdlusalused kliendid**. Mõlema loendi tellimisel väheneb voolavusskoori väärtus: kas punktisumma on ainult kliendi jaoks või klientide koondskoor ja teisese taseme väärtus, näiteks tootekategooria.
        
        - **Tippkliendid**: Loetelu kümnest kliendist, kellel on nende voolavusskooride põhjal suurim ja väiksem voolavusoht. 
        - **Võrdlusalused kliendid**: Loetelu kuni kümnest kliendist, kes valiti mudeli konfigureerimisel.
 
    - **Voolavusskoor:** Kuvab parempoolsel paanil valitud üksuse skoori.
    
    - **Voolavuse ohu jaotus:** Kuvab suurklientide protsentuaalse jaotuse klientide vahel ja protsentiili, milles valitud klient on. 
    
    - **Peamised funktsioonid, mis kasvatavad ja vähendavad voolavuse riski:** Parempoolsel paanil valitud üksuse puhul on loetletud viis valikut, mis suurendasid ja vähendasid riske. Iga mõjuka funktsiooni jaoks leiate selle objekti väärtuse ja selle mõju voolavusskoorile. Samuti näidatakse iga funktsiooni keskmine väärtus nii madalate, keskmiste kui ka suurte suurustega kliendisegmentidel. See aitab valitud üksuse põhifunktsiooni väärtusi paremini kontekstueerida ja võrrelda seda madala, keskmise ja kõrge voolavusega kliendisegmentide väärtustega.

       - Madal: ettevõtted või konto- ja teisese taseme kombinatsioonid, mille voolavusskoor on 0 kuni 0.33
       - Keskmine: ettevõtted või kontode- ja teisese taseme kombinatsioonid, mille voolavusskoor on 0.33 kuni 0.66
       - Kõrge: ettevõtted või kontode- ja teisese taseme kombinatsioonid, mille voolavusskoor on rohkem kui 0.66
    
       Kui ennustate ettevõtte tasemel voolavust, võetakse kõiki kontosid arvesse voogude segmentide funktsioonide keskmiste väärtuste tuletamisel. Iga konto sekundaarse taseme voolavuse ennustuste puhul sõltub voolavuse segmentide tuletamine külgpaneelil valitud üksuse teisest tasemest. Näiteks kui üksusel on tootekategooria teine tase = kontoritarbed, siis võetakse voolavuse segmentide omaduste keskmiste väärtuste tuletamisel arvesse ainult neid tooteid, mille tootekategooriaks on kontoritarbed. Seda loogikat rakendatakse üksuse funktsiooniväärtuste ja keskmise väärtuse õiglase võrdluse tagamiseks nii väikese, keskmise kui ka kõrge voolavusega segmentides.

       Mõnel juhul on madala, keskmise või kõrge voolavusega segmentide keskmine väärtus tühi või pole saadaval, kuna vastavasse voolavuse segmenti pole ülaltoodud määratluse alusel vastavaid üksusi.
       
       > [!NOTE]
       > Keskmiselt madalate, keskmiste ja kõrgete veergude all olevate väärtuste tõlgendamine on kategooria tunnuste (nt riik või tööstus) puhul erinev. Kuna tunnuse "keskmise" väärtuse mõiste ei kehti kategooriliste funktsioonide kohta, on nendes veergudes olevad väärtused madala, keskmise või suure kliendihulgaga segmentides olevate klientide osakaal, kellel on üksuse omaga võrreldes sama kategoorilise funktsiooni väärtus külgpaneelil valitud.

---

## <a name="manage-predictions"></a>Prognooside haldamine

Prognoose on võimalik optimeerida, tõrkeotsingut teha, värskendada või kustutada. Vaadake sisendandmete kasutatavuse aruanne üle, et teada saada, kuidas muuta prognoos kiiremaks ja usaldusväärsemaks. Lisateabe saamiseks minge [Prognooside haldamine](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
