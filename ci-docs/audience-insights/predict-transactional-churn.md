---
title: Tehinguvoolavuse prognoos
description: Prognoosige, kas on oht, et klient ei osta enam teie ettevõtte tooteid või teenuseid.
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af461d290c69687fb47bacfcff446a0c62978383
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268313"
---
# <a name="transactional-churn-prediction-preview"></a>Tehinguvoolavuse prognoos (eelversioon)

Tehinguvoolavuse prognoos aitab ennustada, kas klient on lõpetanud kindlal perioodil teie toodete või teenuste ostmise. Saate luua uusi voolavusprognoose, liikudes **Ärianalüüs** > **Prognoosid**. Muude loodud prognooside kuvamiseks valige **Minu prognoosid**.

> [!TIP]
> Proovige järgmist näidisandmetega tehinguvoolavuse prognoosi õppetükki: [Tehinguvoolavuse prognoosi (eelversioon) näidisjuhend](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Eeltingimused

- Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.
- Äriteadmised voolavuse tähendusest teie ettevõttes. Toetame ajapõhiseid voolavuse määratlusi, mis tähendab, et klient loetakse loobunuks, kui ta pole mingi perioodi jooksul oste teinud.
- Andmed teie tehingute/ostude ja nende ajaloo kohta.
    - Tehinguidentifikaatorid, et eristada oste/tehinguid.
    - Kliendiidentifikaatorid, et ühitada tehingud teie klientidega.
    - Tehingusündmuse kuupäevad, mis määratlevad tehingu toimumise kuupäevad.
    - Ostude/tehingute semantilise andmeskeemi jaoks on vajalik järgmine teave.
        - **Tehingu ID:** ostu või tehingu ainuidentifikaator.
        - **Tehingu kuupäev:** ostu või tehingu kuupäev.
        - **Tehingu väärtus:** tehingu/kauba rahalise/numbrilise väärtuse summa.
        - (Valikuline) **Kordumatu toote ID:** ostetud toote või teenuse ID, kui teie andmed on reakauba tasemel.
        - (Valikuline) **Kas see tehing oli tagastamine:** tõene/väär väli, mis määrab, kas tehingu puhul oli tegemist tagastamisega või mitte. Kui **Tehingu väärtus** on negatiivne, kasutame seda teavet samuti tagastamise järeldamiseks.
- (Valikuline) Andmed klienditegevuste kohta.
    - Tegevuse identifikaatorid, mis eristavad sama tüüpi tegevusi.
    - Kliendi identifikaatorid, mis vastendavad teie klientide tegevusi.
    - Tegevuse teave, mis sisaldab tegevuse nime ja kuupäeva.
    - Kliendi tegevuste semantiline andmete skeem sisaldab järgmist.
        - **Primaarvõti:** tegevuse ainuidentifikaator. Näiteks veebisaidikülastus või kasutuskirje, mis näitab, et klient proovis teie toote näidist.
        - **Ajatempel:** primaarvõtmega tuvastatud sündmuse kuupäev ja kellaaeg.
        - **Sündmus:** sündmuse nimi, mida soovite kasutada. Näiteks väli nimega „UserAction“ võid toidupoe korral märkida, et klient kasutas kupongi.
        - **Üksikasjad:** sündmuse üksikasjalik teave. Näiteks väli nimega „CouponValue“ võib olla toidupoes kupongi rahaline väärtus.

## <a name="create-a-transactional-churn-prediction"></a>Tehinguvoolavuse prognoosi loomine

1. Avage teenuses Customer Insights jaotised **Ärianalüüs** > **Prognoosid**.

1. Valige paan **Kliendivoolavuse mudel (eelversioon)** ja seejärel suvand **Kasuta seda mudelit**.
   
1. Valige paanil **Kliendivoolavuse mudel** suvand **Tehingupõhine** ja seejärel **Alusta**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Kuvatõmmis paanil „Kliendivoolavuse mudel“ valitud tehingupõhisest suvandist.":::

### <a name="name-model"></a>Mudelile nime panemine

1. Sisestage mudelile nimi, et eristada seda teistest mudelitest.

1. Sisestage väljundolemi nimi, kasutades ainult tähti ja numbreid, ilma tühikuteta. Seda nime kasutab mudeli olem. 

1. Tehke valik **Edasi**.

### <a name="define-customer-churn"></a>Määratlege kliendi teenusest loobumine

1. Sisestage loobumise ennustamiseks kasutatav päevade arv väljale **Tuvasta kliendid, kes võivad loobuda ajavahemikus**. Näiteks ennustage oma klientide voolavusriski järgmise 90 päeva jooksul, et kohandada oma klientide säilitamise jõupingutusi. Voolavusriski ennustamine pikema või lühema ajavahemiku jooksul võib raskendada voolavusriski tekitavate tegurite käsitlemist, kuid see sõltub teie ettevõtte vajadustest. 
   >[!TIP]
   > Saate igal hetkel valida **Salvesta ja sule**, et salvestada prognoos mustandina. Prognoosi mustandi leiate vahekaardilt **Minu prognoosid** selle jätkamiseks.

1. Sisestage voolavuse määratlemiseks päevade arv väljale **Klient on loobunud, kui ta pole teinud ühtegi ostu ajavahemikus**. Näiteks kui klient pole viimase 30 päeva jooksul oste teinud, võib neid pidada teie ettevõttest loobunuks. 

1. Jätkamiseks valige **Edasi**

### <a name="add-required-data"></a>Lisage nõutud andmed

1. Valige jaotises **Ostuajalugu** suvand **Lisa andmeid** ja valige olem, mis sisaldab tehingu-/ostuajaloo teavet, nagu on kirjeldatud [eeltingimustes](#prerequisites).

1. Vastendage semantilised väljad oma ostuajaloo olemi atribuutidega ja valige **Järgmine**. Väljade kirjelduste kohta vaadake teavet [eeltingimustes](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Ostuolemi semantiliste väljade vastendamine.":::

1. Kui allolevad väljad pole täidetud, konfigureerige oma ostuajaloo olemis seos kliendiolemiga.
    1. Valige **Ostuajaloo olem**.
    1. Valige **Väli**, mis tuvastab kliendi ostuajaloo olemis. See peab olema seostatud teie kliendiolemi esmase kliendi ID-ga.
    1. Valige **Kliendi olem**, mis vastab teie peamisele kliendiolemile.
    1. Tippige seost kirjeldav nimi.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Ostuajaluu leht, millel on näha kliendiga seose loomine.":::
   
1. Tehke valik **Edasi**.

1. Soovi korral valige jaotises **Klienditegevused** suvand **Lisa andmed**. Valige olem, mis sisaldab klienditegevuse teavet, nagu on kirjeldatud eeltingimustes.

1. Vastendage semantilised väljad oma klienditegevuse olemi atribuutidega ja valige **Järgmine**. Väljade kirjelduste kohta vaadake teavet [eeltingimustes](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Kliendiväljade vastendamine tehinguandmete saamiseks.":::

1. Valige tegevuse tüüp, mis vastab konfigureeritavale kliendi tegevuse tüübile. Valige **Loo uus** ja valige saadaolev tegevusetüüp või looge uus tüüp.

1. Peate konfigureerima kliendiolemile seose kliendi tegevuse olemist.
    1. Valige väli, mis tuvastab kliendi klienditegevuse tabelis. See võib olla otse kliendiolemi peamise kliendi-ID-ga.
    1. Valige kliendi olem, mis vastab teie peamisele kliendi olemile
    1. Tippige seost kirjeldav nimi.

1. Valige **Salvesta**.

1. Kui teil on mõni muu klienditegevus, mida soovite kaasata, korrake ülaltoodud samme.

1. Tehke valik **Edasi**.

### <a name="set-schedule-and-review-configuration"></a>Ajakava seadistamine ja konfiguratsiooni ülevaatamine

1. Määrake oma mudeli ümberõppe sagedus. See säte on oluline, et värskendada prognooside täpsust uute andmete valmendamisel. Suur osa ettevõtteid saavad teha ümberõpet kord kuus ja saavutavad täpsed prognoosid.

1. Tehke valik **Edasi**.

1. Vaadake prognoosi konfiguratsiooni üle. Saate tagasi minna eelmiste etappide juurde, valides kuvatud väärtuse all **Redigeeri**. Saate ka valida edenemise näidikust konfiguratsiooni etapi.

1. Kui kõik väärtused on õigesti konfigureeritud, valige pognoosimisprotsessi alustamiseks suvand **Salvesta ja käivita**. Vahekaardil **Minu prognoosid** kuvatakse teie prognooside olekut. Selle protsessi lõpule viimiseks võib kuluda mitu tundi, olenevalt prognoosis kasutatud andmete hulgast.

## <a name="review-a-prediction-status-and-results"></a>Prognoosi oleku ja tulemuste läbivaatamine

1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.

1. Valige prognoos, mille soovite üle vaadata.
   - **Prognoosi nimi:** prognoosi loomisel sellele pandud nimi.
   - **Prognoosi tüüp:** prognoosi jaoks kasutatud mudeli tüüp
   - **Väljundolem:** olemi nimi, kuhu talletatakse prognoosi väljund. Selle nimega olemi leiate jaotisest **Andmed** > **Olemid**.
   - **Prognoositav väli:** see väli täidetakse ainult kindlat tüüpi prognooside korral ja seda ei kasutata voolavuse prognoosimisel.
   - **Olek:** prognoosi käitamise olek.
        - **Järjekorras:** prognoos ootab muude protsesside käivitamist.
        - **Värskendamine:** prognoos töötab praegu, et luua tulemusi, mis sisestatakse väljundolemisse.
        - **Nurjunud:** prognoosi käitamine nurjus. Lisateabe saamiseks [vaadake üle logid](#troubleshoot-a-failed-prediction).
        - **Õnnestus:** prognoos on õnnestunud. Valige prognoosi läbivaatamiseks **Vaade** vertikaalse kolmikpunkti juures
   - **Redigeeritud:** prognoosi konfiguratsiooni muutmise kuupäev.
   - **Viimati värskendatud:** kuupäev, mil prognoos värskendas tulemusi väljundolemis.

1. Valige vertikaalne kolmikpunkt prognoosi kõrval, mille tulemusi soovite läbivaadata ja valige **Vaade**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Juhtelement „Kuva“ prognoosi tulemuste vaatamiseks.":::   

1. Tulemuste lehel on kolm peamist andmete jaotist.
    1. **Koolituse mudeli jõudlus:** võimalikud punktisummad on A, B või C. See skoor näitab prognoosi jõudlust ja aitab teil otsustada, kas kasutada väljundolemis talletatud tulemusi. Skoorid määratletakse järgmiste reeglite alusel.
         
         - **A**, kui vähemalt 50% kõikidest prognoosidest olid täpsed ja kui täpsete loobunud klientide prognooside protsent on alusmäärast vähemalt 10% suurem.
            
         - **B**, kui vähemalt 50% kõikidest prognoosidest olid täpsed ja kui täpsete loobunud klientide prognooside protsent on alusmäärast kuni 10% suurem.
            
         - **C**, kui vähem kui 50% kõikidest prognoosidest olid täpsed või kui täpsete loobunud klientide prognooside protsent on alusmäärast väiksem.
               
         - **Aluse** jaoks võetakse mudeli prognoosiajavahemiku sisend (näiteks üks aasta) ja luuakse eri ajalõigud, jagades ajavahemikku kahega, kuni see on üks kuu või väiksem. Mudel kasutab neid ajalõike, et luua ärireegel klientidele, kes pole selles ajavahemikus oste teinud. Need kliendid loetakse loobunuks. Alusmudeliks valitakse ajapõhine ärireegel, mis ennustab kõige täpsemini, kes võib loobuda.
            
    1. **Voolavuse tõenäosus (klientide arv):** kliendirühmad nende prognoositud voolavuse riski põhjal. Need andmed aitavad teil hiljem soovi korral luua kõrge voolavuse riskiga klientide segmendi. Sellised segmendid aitavad mõista, kus segmendi liikmelisuse sulgemiskuupäev peaks olema.
       
    1. **Kõige mõjukamad tegurid:** prognoosi loomisel võetakse arvesse paljusid tegureid. Mudeli loodavate koondprognooside jaoks arvutatakse iga teguri olulisus. Nende tegurite abil saate oma prognoosi tulemusi kinnitada. Samuti saate seda teavet hiljem kasutada [segmentide loomiseks](segments.md), mis võiksid aidata mõjutada kliendivoolavuse ohtu.

## <a name="troubleshoot-a-failed-prediction"></a>Nurjunud prognoosi tõrkeotsing

1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.

1. Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mille tõrkelogisid soovite vaadata.

1. Valige **Logid**.

1. Kõikide tõrgete läbivaatamine. Esineda võib mitmesuguseid tüüpe tõrkeid ja need kirjeldavad, mis olukord selle tõrke tekitad. Näiteks tõrge, et täpse prognoosi tegemiseks pole piisavalt andmeid, lahendatakse tavaliselt täiendavate andmete laadimisel Customer Insightsis.

## <a name="refresh-a-prediction"></a>Prognoosi värskendamine

Prognoose värskendatakse automaatselt [teie andmete värskendamiste ajakava](system.md#schedule-tab) järgi, mis on sätetes konfigureeritud. Neid saab värskendada ka käsitsi.

1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.

1. Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mida soovite värskendada.

1. Valige **Värskenda**.

## <a name="delete-a-prediction"></a>Prognoosi kustutamine

Prognoosi kustutamisel eemaldatakse ka selle väljundolem.

1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.

1. Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mida soovite kustutada.

1. Valige **Kustuta**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]