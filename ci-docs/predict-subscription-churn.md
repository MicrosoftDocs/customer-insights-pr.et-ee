---
title: Tellimuse tükeldamise prognoos (sisaldab videot)
description: Saate prognoosida, kas on oht, et klient ei kasuta enam teie ettevõtte kordustellimuse tooteid või teenuseid.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 415cd5d675512b4f434998afaa8265c8e45c562b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642872"
---
# <a name="subscription-churn-prediction"></a>Tellimise voolavuse prognoos

Kordustellimuse voolavuse prognoos aitab prognoosida, kas on oht, et klient ei kasuta enam teie ettevõtte kordustellimuse tooteid või teenuseid. Saate luua uue kordustellimuse voolavuse prognoosi lehel **Ärianalüüs** > **Prognoosid**. Muude loodud prognooside kuvamiseks valige **Minu prognoosid**.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Proovige järgmist näidisandmetega tellimusevoolavuse prognoosi õppetükki: [Tellimusevoolavuse prognoosi näidisjuhend](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Eeltingimused

- Vähemalt [kaasautori õigused](permissions.md).
- Äriteadmised voolavuse tähendusest teie ettevõttes. Toetame ajapõhiseid voolavuse määratlusi, mis tähendab, et kliendivoolavus on toimunud teatud aja jooksul pärast kordustellimuse lõppu.
- Andmed teie kordustellimuste ja nende ajaloo kohta.
    - Kordustellimuse identifikaatorid nende eristamiseks.
    - Kliendi identifikaatorid, mis vastavad teie klientide kordustellimustele.
    - Kordustellimuse sündmuse kuupäevad, mis määratlevad algus- ja lõppkuupäevad ning kordustellimuse sündmuste toimumise kuupäevi.
    - Kordustellimuse teave, mis määratleb, kas see kordustellimus on korduv ja kui tihti seda uuendatakse.
    - Kordustellimuste semantiline andmete skeem nõuab järgmist teavet.
        - **Kordustellimuse ID:** kordustellimuse ainuidentifikaator.
        - **Kordustellimuse lõppkuupäev:** kuupäev, mil kliendi kordustellimus aegub.
        - **Kordustellimuse alguskuupäev:** kuupäev, mil kliendi kordustellimus algab.
        - **Kande kuupäev:** kordustellimuse vahetuse toimumise kuupäev. Näiteks klient ostab või tühistab kordustellimuse.
        - **Kas see kordustellimus on korduv:** loogiline väli tõene/väär, mis määratleb, kas kordustellimus pikeneb sama kordustellimuse ID-ga ilma kliendi sekkumiseta
        - **Korduvuse vahemik (kuudes):** korduvate kordustellimuste puhul on see kordustellimuse pikendamise periood. See on väljendatud kuudes. Näiteks aastane kordustellimus, mis uueneb kliendi jaoks automaatselt igal aastal, selle väärtuseks on 12.
        - (Valikuline) **Kordustellimuse summa:** summa valuutas, millega klient kordustellimuse uuendamisel maksab. See võib aidata tuvastada erinevate kordustellimuste tasemete mustreid.
- Kliendi tegevuste andmed.
    - Tegevuse identifikaatorid, mis eristavad sama tüüpi tegevusi.
    - Kliendi identifikaatorid, mis vastendavad teie klientide tegevusi.
    - Tegevuse teave, mis sisaldab tegevuse nime ja kuupäeva.
    - Kliendi tegevuste semantiline andmete skeem sisaldab järgmist.
        - **Primaarvõti:** tegevuse ainuidentifikaator. Näiteks veebisaidi külastus või kasutuse kirje, mis näitab, et klient vaatas teleseriaali osa.
        - **Ajatempel:** primaarvõtmega tuvastatud sündmuse kuupäev ja kellaaeg.
        - **Sündmus:** sündmuse nimi, mida soovite kasutada. Näiteks nimega „UserAction” video voogesituse teenuse väljal võiks olla väärtus „Vaadatud”.
        - **Üksikasjad:** sündmuse üksikasjalik teave. Näiteks nimega „ShowTitle” video voogesituse teenuse väljal võiks olla kliendi vaadatud video väärtus.
- Soovitatavad andmete omadused:
    - Piisavad ajaloolised andmed: Tellimuse andmed vähemalt kahekordistatud valitud ajaaknas. Eelistatavalt kahe kuni kolme aasta tellimisandmed.
    - Tellimuse olek: andmed sisaldavad iga kliendi jaoks aktiivseid ja mitteaktiivseid tellimusi, nii et kliendi ID kohta on mitu kirjet.
    - Klientide arv: Vähemalt 10 kliendiprofiili, eelistatuult rohkem kui 1000 erinevat klienti. Mudel nurjub, kui kliente on vähem kui 10 ja puuduvad varasemad andmed.
    - Andmete täielikkus: esitatud olemi andmeväljal on puuduvaid väärtuseid vähem kui 20%.
   
   > [!NOTE]
   > Teil on vaja vähemalt kahte tegevuse kirjet 50%-le klientidest, kelle voolavust soovite välja arvutada.

## <a name="create-a-subscription-churn-prediction"></a>Kordustellimuse voolavuse prognoosi loomine

1. Minge aadressile **IntelligencePredictions** > **·**.
1. **Valige paan Tellimuse churn mudel** ja valige **Kasuta seda mudelit**.
   > [!div class="mx-imgBorder"]
   > ![Kordustellimuse voolavuse mudeli paan nupuga Kasuta seda mudelit.](media/subscription-churn-usethismodel.PNG "Kordustellimuse voolavuse mudeli paan nupuga Kasuta seda mudelit")

### <a name="name-model"></a>Mudelile nime panemine

1. Sisestage mudelile nimi, et eristada seda teistest mudelitest.
1. Sisestage väljundolemi nimi, kasutades ainult tähti ja numbreid, ilma tühikuteta. Seda nime kasutab mudeli olem. Seejärel valige suvand **Edasi**.

### <a name="define-customer-churn"></a>Määratlege kliendivoolavus

1. Sisestage arv **Päevi möödunud kordustellimuse lõppemisest**, mida teie ettevõte peab olekuks, mil kliendivoolavus on toimunud. Tavaliselt on see periood seotud äritegevustega, nagu pakkumised või muud turundusega seotud pingutused, mis püüavad ära hoida kliendi kaotsiminekut.
1. Sisestage **päevade arv tulevikus, mille põhjal voolavust prognoosida**, et määrata aken voolavuse prognoosiks. Näiteks selleks, et ennustada järgmise 90 päeva klientide voolavuse riski oma säilitusturunduse jõupingutuste vastavusse viimiseks. Pöördumisriski ennustamine pikemaks või lühemaks perioodiks võib muuta pöördumisriski profiili tegurite käsitlemise keerulisemaks, sõltuvalt teie konkreetsetest ärinõuetest. Jätkamiseks valige **Edasi**
   >[!TIP]
   > Prognoos mustandina salvestamiseks saate igal ajal valida **Salvesta mustand**. Prognoosi mustandi leiate vahekaardilt **Minu prognoosid** selle jätkamiseks.

### <a name="add-required-data"></a>Lisa nõutud andmed

1. Valige suvandis **Kordustellimuse ajalugu** **Lisa andmed** ja valige olem, mis pakub kordustellimuse ajaloo teavet, nagu on kirjeldatud [eeltingimustes](#prerequisites).
1. Kui allolevad väljad pole asustatud, konfigureerige kliendiolemile seos oma kordustellimuse ajaloo olemist.
    1. Valige **Kordustellimuse ajaloo olem**.
    1. Valige **Väli**, mis tuvastab kliendi kordustellimuse ajaloo olemis. See peab olema seostatud teie kliendiolemi esmase kliendi ID-ga.
    1. Valige **Kliendi olem**, mis vastab teie peamisele kliendiolemile.
    1. Tippige seost kirjeldav nimi.
       > [!div class="mx-imgBorder"]
       > ![Tellimuse ajaloo leht, mis kuvab seose loomist kliendile.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Kordustellimuse ajaloo leht, mis kuvab seose loomist kliendile")
1. Tehke valik **Edasi**.
1. Vastendage semantilised väljad oma kordustellimuse ajalugoo olemi atribuutidega ja valige **Salvesta**. Väljade kirjelduste kohta vaadake teavet [eeltingimustes](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Tellimuse ajaloo leht kuvab semantilisi atribuute, mis on kaardistatud valitud tellimuste ajaloo üksuste väljadele.](media/subscription-churn-subscriptionhistorymapping.PNG "Kordustellimuse ajaloo leht kuvab semantilisi atribuute, mis on vastendatud valitud kordustellimuse ajaloo olemi väljadega")
1. Valige suvandis **Kliendi tegevused** **Lisa andmed** ja valige olem, mis pakub kliendi tegevuse teavet, nagu on kirjeldatud eeltingimustes.
1. Valige tegevuse tüüp, mis vastab konfigureeritavale kliendi tegevuse tüübile.  Valige **Loo uus** ja sisestage nimi, kui teile ei kuvata soovitud tegevuse tüübiga sobivat suvandit.
1. Peate konfigureerima kliendiolemile seose kliendi tegevuse olemist.
    1. Valige väli, mis tuvastab kliendi selles kliendi tegevuse tabelis, mis võib olla otseselt seotud teie kliendiolemi esmase kliendi ID-ga.
    1. Valige kliendi olem, mis vastab teie peamisele kliendi olemile
    1. Tippige seost kirjeldav nimi.
1. Tehke valik **Edasi**.
1. Vastendage semantilised väljad oma kliendi tegevuse olemi atribuutidega ja valige **Salvesta**. Väljade kirjelduste kohta vaadake teavet [eeltingimustes](#prerequisites).
1. (Valikuline) Kui soovite kaasata mõnda muud kliendi tegevust, korrake ülaltoodud juhiseid.
   > [!div class="mx-imgBorder"]
   > ![Olemi seose määratlemine.](media/subscription-churn-customeractivitiesmapping.PNG "Kliendi tegevuste leht kuvab semantilisi atribuute, mis on vastendatud valitud kliendi tegevuse olemi väljadega")
1. Tehke valik **Edasi**.

### <a name="set-schedule-and-review-configuration"></a>Ajakava seadistamine ja konfiguratsiooni ülevaatamine

1. Määrake oma mudeli ümberõppe sagedus. See säte on oluline ennustuste täpsuse värskendamiseks, kuna Customer Insightsis neelatakse uusi andmeid. Suur osa ettevõtteid saavad teha ümberõpet kord kuus ja saavutavad täpsed prognoosid.
1. Tehke valik **Edasi**.
1. Konfiguratsiooni läbivaatamine. Saate naasta prognoosi mis tahes osasse, valides suvandi **Redigeeri** kuvatud väärtuse juures. Saate ka valida edenemise näidikust konfiguratsiooni etapi.
1. Kui kõik väärtused on õigesti konfigureeritud, valige pognoosimisprotsessi alustamiseks suvand **Salvesta ja käivita**. Vahekaardil **Minu prognoosid** kuvatakse teie prognooside olekut. Selle protsessi lõpule viimiseks võib kuluda mitu tundi, olenevalt prognoosis kasutatud andmete hulgast.

## <a name="review-a-prediction-status-and-results"></a>Prognoosi oleku ja tulemuste läbivaatamine

1. Avage jaotises **Ärianalüüs** > **Prognoosid** vahekaart **Minu prognoosid**.
   > [!div class="mx-imgBorder"]
   > ![Lehe Minu prognoosid vaade.](media/subscription-churn-mypredictions.PNG "Lehe Minu prognoosid vaade")
1. Valige prognoos, mille soovite üle vaadata.
   - **Prognoosi nimi:** selle prognoosi loomisel pandud nimi.
   - **Prognoosi tüüp:** prognoosi jaoks kasutatav mudeli tüüp
   - **Väljundolem:** olemi nimi, kuhu talletatakse prognoosi väljund. Selle nimega olemi leiate jaotisest **Andmed** > **Olemid**.    
     Väljundolemis *Voolavuse tulemus* on prognoositud voolavuse tõenäosus ja *On voolavus* on binaarne märgis, mis põhineb *Voolavuse tulemusel* lävendiga 0,5. Vaikelävend ei pruugi teie stsenaariumi puhul töötada. [Looge uus segment](segments.md#create-a-new-segment) teie eelistatud lävendiga.
   - **Prognoositud väli:** see väli on asustatud ainult teatud tüüpi prognooside puhul ja seda ei kasutata kordustellimuse voolavuse prognoosides.
   - **Olek:** prognoosi käitamise praegune olek.
        - **Järjekorras:** prognoos ootab praegu muude protsesside käitamist.
        - **Värskendamine:** prognoos käitab praegu töötlemise etappi „skoor”, et saada tulemusi, mis voolavad väljundolemisse.
        - **Nurjunud:** prognoos on nurjunud. Üksikasjade saamiseks valige **Logid**.
        - **Õnnestus:** prognoos on õnnestunud. Valige prognoosi läbivaatamiseks **Vaade** vertikaalse kolmikpunkti juures
   - **Redigeeritud:** prognoosi konfiguratsiooni muutmise kuupäev.
   - **Viimati värskendatud:** kuupäev, mil prognoos värskendas tulemusi väljundolemis.
1. Valige vertikaalne kolmikpunkt prognoosi kõrval, mille tulemusi soovite läbivaadata ja valige **Vaade**.
   > [!div class="mx-imgBorder"]
   > ![Suvandite vaade prognoosi vertikaalse kolmikpunkti menüüs, sh redigeerimine, värskendamine, vaade, logid ja kustutamine.](media/subscription-churn-verticalellipses.PNG "Suvandite vaade prognoosi vertikaalse kolmikpunkti menüüs, sh redigeerimine, värskendamine, vaadet, logid ja kustutamine")
1. Tulemuste lehel on kolm peamist andmete jaotist.
    1. **Koolituse mudeli jõudlus:** võimalikud punktisummad on A, B või C. See skoor näitab prognoosi jõudlust ja aitab teil otsustada, kas kasutada väljundolemis talletatud tulemusi.
        - Skoorid määratletakse järgmiste reeglite alusel.
            - **A**, kui mudel ennustas täpselt vähemalt 50% kõikidest prognoosidest ja kui prognooside täpsuse protsent kliendivoolavuse jaoks on ajaloolisest voolavuse määrast vähemalt 10% võrra suurem.
            - **B**, kui mudel ennustas täpselt vähemalt 50% kõikidest prognoosidest ja kui prognooside täpsuse protsent kliendivoolavuse jaoks on ajaloolisest voolavuse määrast kuni 10% võrra suurem.
            - **C**, kui mudel ennustas täpselt vähem kui 50% kõikidest prognoosidest või kui prognooside täpsuse protsent kliendivoolavuse jaoks on väiksem kui ajalooline voolavuse määr.
               > [!div class="mx-imgBorder"]
               > ![Mudeli jõudluse tulemi vaade.](media/subscription-churn-modelperformance.PNG "Mudeli jõudluse tulemi vaade")
    1. **Voolavuse tõenäosus (klientide arv):** kliendirühmad nende prognoositud voolavuse riski põhjal. Need andmed aitavad teil hiljem soovi korral luua kõrge voolavuse riskiga klientide segmendi. Sellised segmendid aitavad mõista, kus segmendi liikmelisuse sulgemiskuupäev peaks olema.
       > [!div class="mx-imgBorder"]
       > ![Graafik, mis kuvab voolavuse tulemuste jaotust, jagatuna vahemikeks 0–100% vahel.](media/subscription-churn-resultdistribution.PNG "Graafik, mis kuvab voolavuse tulemuste jaotust, jagatuna vahemikeks 0–100% vahel")
    1. **Kõige mõjukamad tegurid:** prognoosi loomisel võetakse arvesse paljusid tegureid. Kõigi tegurite olulisus arvutatakse selle loodava koondprognoosi jaoks. Nende tegurite abil saate oma prognoosi tulemusi kinnitada. Samuti saate seda teavet hiljem kasutada [segmentide loomiseks](segments.md), mis võiksid aidata mõjutada kliendivoolavuse ohtu.
       > [!div class="mx-imgBorder"]
       > ![Loend mõjukate teguritega ja nende olulisus voolavuse tulemuse prognoosimisel.](media/subscription-churn-influentialfactors.PNG "Loend mõjukate teguritega ja nende olulisus voolavuse tulemuse prognoosimisel")

## <a name="manage-predictions"></a>Prognooside haldamine

Prognoose on võimalik optimeerida, tõrkeotsingut teha, värskendada või kustutada. Vaadake sisendandmete kasutatavuse aruanne üle, et teada saada, kuidas muuta prognoos kiiremaks ja usaldusväärsemaks. Lisateavet leiate teemast [Prognooside haldamine](manage-predictions.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]