---
title: Tootesoovituse ennustamine
description: Prognoosige tooteid, mida klient tõenäoliselt ostab või millega suhtleb.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270485"
---
# <a name="product-recommendation-prediction-preview"></a>Tootesoovituse ennustamine (eelvaade)

Tootesoovituste mudel loob ennustavate tootesoovituste komplekti. Soovitused põhinevad varasemal ostukäitumisel ja sarnase ostumustriga klientidel. Uue tootesoovituse ennetava teabe saate luua lehel **Intelligents** > **Prognoosid**. Muude loodud prognooside kuvamiseks valige **Minu prognoosid**.

Tootesoovitustele võivad subjektiks olla kohalikud õigusaktidest ja õigusaktidest ning kliendi ootused, mida mudelis ei ole konkreetselt arvesse võetud.  Selle ennetava võimaluse kasutajana **peate enne klientidele kohaletoimetamist need soovitused üle vaatama**, et tagada, et järgite kõiki kohalduvatest õigusaktidest või õigusaktidest ning kliendi ootusi selle kohta, mida võite soovitada. 

Lisaks annab selle mudeli väljund teile soovitusi toote ID põhjal. Teie kohaletoimetamise mehhanism peab võtma prognoositud toote ID-d ja vastendama need klientide jaoks sobiva sisuga, et arvestada lokaliseerimist, pildisisu ja muud ettevõttele omast sisu või käitumist.

## <a name="sample-guide"></a>Näidisjuhend

Kui olete huvitatud selle funktsiooni proovimisest, kuid teil pole andmeid allpool esitatud nõuete täitmiseks, võite [luua näidisrakenduse](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Eeltingimused

- Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.
- Äriteadmised, et mõista teie ettevõtte jaoks erinevaid tooteid ja seda, kuidas kliendid nendega suhtlevad. Toetame teie klientide poolt varem ostetud toodete soovitamist või uute toodete soovitamist.
- Andmed tehingute, ostude ja nende ajaloo kohta.
    - Tehinguidentifikaatorid, et eristada oste või tehinguid.
    - Kliendiidentifikaatorid, et vastendada tehingud teie klientidega.
    - Tehingusündmuse kuupäevad, mis määratlevad tehingu toimumise kuupäevad.
    - (valikuline) Tehingu toote ID teave.
    - (valikuline) Kui tehing on tagastatud või mitte.
    - Semantiliste andmete skeem nõuab järgmist teavet.
        - **Tehingu ID:** ostu või tehingu ainuidentifikaator.
        - **Tehingu kuupäev:** ostu või tehingu kuupäev.
        - **Tehingu väärtus:** ostu või tehingu arvuline väärtus.
        - **Kordumatu toote ID:** ostetud toote või teenuse ID, kui teie andmed on reakauba tasemel.
        - (Valikuline) **Ost või tagastus:** tõene/väär väli, mis määrab, kas tehingu puhul oli tegemist tagastamisega või mitte. Kui **Tehingu väärtus** on negatiivne, kasutame seda teavet samuti tagastamise järeldamiseks.


## <a name="create-a-product-recommendation-prediction"></a>Looge tootesoovituste prognoos

1. Avage teenuses Customer Insights jaotised **Ärianalüüs** > **Prognoosid**.

1. Valige paan **Tootesoovituste mudel (eelversioon)** ja seejärel suvand **Kasuta seda mudelit**.
   > [!div class="mx-imgBorder"]
   > ![Toote soovitusmudeli paan nupuga Kasuta seda mudelit](media/product-recommendation-usethismodel.PNG "Toote soovitusmudeli paan nupuga Kasuta seda mudelit")

1. Vaadake üle mudelinõuete teave. Kui teil on vajalikud andmed, valige **Alustamine**.

### <a name="name-model"></a>Mudelile nime panemine

1. Sisestage mudelile nimi, et eristada seda teistest mudelitest.

1. Sisestage väljundüksuse nimi, kasutades ainult tähti ja numbreid, ilma tühikuteta. Seda nime kasutab mudeli olem. Seejärel valige suvand **Edasi**.

### <a name="define-product-recommendation-configuration"></a>Tootesoovituse konfiguratsiooni määratlemine

1. Määrake kliendile soovitatavate **toodete arv**. See väärtus sõltub sellest, kuidas teie tarneviis andmeid täidab. Kui oskate soovitada kolme toodet, määrake see väärtus vastavalt.
   
   >[!TIP]
   > Saate igal hetkel valida **Salvesta ja sule**, et salvestada prognoos mustandina. Prognoosi mustandi leiate vahekaardilt **Minu prognoosid**.

1. Valige, kas soovite **soovitada tooteid, mida kliendid on hiljuti ostnud**.

1. Kui olete valinud hiljuti ostetud toodete *soovitamata* jätmise, seadistage **Tagasiminemise aken**. Antud säte määrab ajavahemiku, mida mudel kaalub enne toote kasutajale uuesti soovitamist. Näiteks saate määrata, et klient ostab sülearvuti iga 2 aasta järel. Selles aknas vaadatakse viimase 2 aasta ostude ajalugu ja kui nad leiavad üksuse, filtreeritakse see üksus soovituste hulgast.

1. Vali **Järgmine**

### <a name="add-required-data"></a>Lisage nõutud andmed

1. Valige jaotises **Kliendi tehinguajalugu** suvand **Lisa andmeid** ja valige olem, mis sisaldab tehingu-/ostuajaloo teavet, nagu on kirjeldatud [eeltingimustes](#prerequisites).

1. Vastendage semantilised väljad oma ostuajaloo olemi atribuutidega ja valige **Järgmine**. Väljade kirjelduste kohta vaadake teavet [eeltingimustes](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Olemi seose määratlemine](media/product-recommendation-purchasehistorymapping.PNG "Ostuajaloo leht, kus kuvatakse semantilised atribuudid, mis on vastendatud valitud ostuajaloo üksuse väljadele")

1. Kui väljad pole täidetud, konfigureerige oma ostuajaloo olemis seos olemiga *Klient*.
    1. Valige **Ostuajaloo olem**.
    1. Valige **Väli**, mis tuvastab kliendi ostuajaloo olemis. See peab olema seostatud teie olemiga *Klient* esmase kliendi ID-ga.
    1. Valige **Kliendi olem**, mis vastab teie peamisele kliendiolemile.
    1. Tippige seost kirjeldav nimi.
       > [!div class="mx-imgBorder"]
       > ![Ostuajaloo leht, millel on näha kliendiga seose loomine](media/model-purchase-join.png "Ostuajaloo leht, millel on näha kliendiga seose loomine")

1. Valige **Salvesta**.

1. Tehke valik **Edasi**.

### <a name="set-schedule-and-review-configuration"></a>Ajakava seadistamine ja konfiguratsiooni ülevaatamine

1. Määrake oma mudeli ümberõppe sagedus. See säte on oluline, et värskendada prognooside täpsust uute andmete importimisel Customer Insightsi. Suur osa ettevõtteid saavad teha ümberõpet kord kuus ja saavutavad täpsed prognoosid.

1. Tehke valik **Edasi**.

1. Konfiguratsiooni läbivaatamine. Saate naasta prognoosi mis tahes osasse, valides suvandi **Redigeeri** kuvatud väärtuse juures. Saate ka valida edenemise näidikust konfiguratsiooni etapi.

1. Kui kõik väärtused on õigesti konfigureeritud, valige pognoosimisprotsessi alustamiseks suvand **Salvesta ja käivita**. Vahekaardil **Minu prognoosid** kuvatakse teie prognooside olekut. Selle protsessi lõpule viimiseks võib kuluda mitu tundi, olenevalt prognoosis kasutatud andmete hulgast.

## <a name="review-a-prediction-status-and-results"></a>Prognoosi oleku ja tulemuste läbivaatamine

1. Avage jaotises **Ärianalüüs** > **Prognoosid** vahekaart **Minu prognoosid**.
   > [!div class="mx-imgBorder"]
   > ![Lehe Minu prognoosid vaade](media/product-recommendation-mypredictions.PNG "Lehe Minu prognoosid vaade")

1. Valige prognoos, mille soovite üle vaadata.
   - **Prognoosi nimi:** selle prognoosi loomisel pandud nimi.
   - **Prognoosi tüüp:** prognoosi jaoks kasutatav mudeli tüüp
   - **Väljundolem:** olemi nimi, kuhu talletatakse prognoosi väljund. Selle nimega olemi leiate jaotisest **Andmed** > **Olemid**.
   - **Prognoositav väli:** see väli täidetakse ainult kindlat tüüpi prognooside korral ja seda ei kasutata voolavuse prognoosimisel.
   - **Olek:** prognoosi käitamise praegune olek.
        - **Järjekorras:** prognoos ootab praegu muude protsesside käitamist.
        - **Värskendamine:** prognoos käitab praegu töötlemise etappi „skoor”, et saada tulemusi, mis voolavad väljundolemisse.
        - **Nurjunud:** prognoos on nurjunud. Üksikasjade saamiseks valige **Logid**.
        - **Õnnestus:** prognoos on õnnestunud. Valige prognoosi läbivaatamiseks **Vaade** vertikaalse kolmikpunkti juures
   - **Redigeeritud:** prognoosi konfiguratsiooni muutmise kuupäev.
   - **Viimati värskendatud:** kuupäev, mil prognoos värskendas tulemusi väljundolemis.

1. Valige vertikaalne kolmikpunkt prognoosi kõrval, mille tulemusi soovite läbivaadata ja valige **Vaade**.
   > [!div class="mx-imgBorder"]
   > ![Suvandite vaade prognoosi vertikaalse kolmikpunkti menüüs, sh redigeerimine, värskendamine, vaadet, logid ja kustutamine](media/product-recommendation-verticalellipses.PNG "Suvandite vaade prognoosi vertikaalse kolmikpunkti menüüs, sh redigeerimine, värskendamine, vaadet, logid ja kustutamine")

1. Tulemuste lehel on kolm peamist andmete jaotist.
    1. **Koolituse mudeli jõudlus:** võimalikud punktisummad on A, B või C. See skoor näitab prognoosi jõudlust ja aitab teil otsustada, kas kasutada väljundolemis talletatud tulemusi.
        - Skoorid määratletakse järgmiste reeglite alusel.
            - **A** Mudelit peetakse **A** kvaliteediga mõõdikuks, kui mõõdik "Õnnestusumise @ K" on vähemalt 10% baasmäärast. 
            - **B** Mudelit peetakse **B** kvaliteediga mõõdikuks, kui mõõdik "Õnnestusumise @ K" on vähemalt 0-10% baasmäärast.
            - **C** Mudelit peetakse **C** kvaliteediga mõõdikuks, kui mõõdik "Õnnestusumise @ K" on baasmäärast väiksem.
               
               > [!div class="mx-imgBorder"]
               > ![Mudeli jõudluse tulemi vaade](media/product-recommendation-modelperformance.PNG "Mudeli jõudluse tulemi vaade")
            - **Baasväärtus**: mudel võtab kõigi klientide seas kõige rohkem soovitatud tooteid ostude arvu järgi ja kasutab klientidele soovituste komplekti loomiseks mudeli tuvastatud õpitud reegleid. Seejärel võrreldakse seda prognoositava väärtusega kõige rohkem valmistatud toodetega, arvutatuna vastavalt toote ostnud klientide arvule. Kui kliendi soovitatud toodetes on vähemalt üks toode, mida oli näha ka kõige paremini ostetud toodetes, loetakse teda baasväärtuse osaks. Kui neid kliente oleks kümme, kellel oleks soovitatud toode ostetud 100 kliendi seast, oleks baasväärtus 10%.
            - **Õnnestumise @ K**: tehingute ajaperioodi valideerimiskomplekti abil luuakse kõigi klientide jaoks soovitusi ja võrreldakse neid tehingute valideerimiskomplektiga. Näiteks 12 kuu jooksul võidakse 12. kuu andmete valideerimiskomplektina kõrvale jätta. Kui mudel ennustab vähemalt üht asja, mida 12. kuu jooksul ostsid, võttes aluseks viimase 11 kuuga õpitu, suurendaks klient mõõdikut "Success @ K".
    
    1. **Enamik soovitatud tooteid (kokku):** 5 tähtsamat toodet, mis olid teie klientide jaoks ennustatud.
       > [!div class="mx-imgBorder"]
       > ![Graafik, kus on kuvatud viis tähtsamat toodet](media/product-recommendation-topproducts.PNG "Graafik, kus on kuvatud viis tähtsamat toodet")
    
    1. **Hea klienditeenindusega tootesoovitused:** klientidele antud soovituste näide, mis sisaldab teavet selle kohta, et mudel on salvestatud, ostab tõenäoliselt klient.
       > [!div class="mx-imgBorder"]
       > ![Loend, mis näitab, et üksikuid kliente saab valida kõrge täpsusega soovitustega](media/product-recommendation-highconfidence.PNG "Loend, mis näitab, et üksikuid kliente saab valida kõrge täpsusega soovitustega")

## <a name="fix-a-failed-prediction"></a>Nurjunud prognoosi parandamine

1. Avage jaotises **Ärianalüüs** > **Prognoosid** vahekaart **Minu prognoosid**.

1. Valige prognoos, mille tõrkelogisid soovite kuvada, ja valige **Logid**.

1. Kõikide tõrgete läbivaatamine. Esineda võib mitmesuguseid tüüpe tõrkeid ja need kirjeldavad, mis olukord selle tõrke tekitad. Näiteks tõrge, et täpse prognoosi tegemiseks pole piisavalt andmeid, lahendatakse tavaliselt täiendavate andmete laadimisel Customer Insightsis.

## <a name="refresh-a-prediction"></a>Prognoosi värskendamine

Prognoosimine värskendatakse automaatselt samal [ajakaval, andmeid värskendatakse](system.md#schedule-tab) sätetes konfigureeritud viisil.

1. Avage jaotises **Ärianalüüs** > **Prognoosid** vahekaart **Minu prognoosid**.

1. Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mida soovite värskendada.

1. Valige **Värskenda**.

## <a name="delete-a-prediction"></a>Prognoosi kustutamine

Prognoosi kustutamine eemaldab ka selle väljundolemi.

1. Avage jaotises **Ärianalüüs** > **Prognoosid** vahekaart **Minu prognoosid**.

1. Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mida soovite kustutada.

1. Valige **Kustuta**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]