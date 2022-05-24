---
title: Tootesoovituse ennustamine
description: Prognoosige tooteid, mida klient tõenäoliselt ostab või millega suhtleb.
ms.date: 05/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 9b3e60c49d294d031f43ef0594cb69707bb64019
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762727"
---
# <a name="product-recommendation-prediction"></a>Tootesoovituse ennustamine

Tootesoovituste mudel loob ennustavate tootesoovituste komplekti. Soovitused põhinevad varasemal ostukäitumisel ja sarnase ostumustriga klientidel. Uue tootesoovituse ennetava teabe saate luua lehel **Intelligents** > **Prognoosid**. Muude loodud prognooside kuvamiseks valige **Minu prognoosid**.

Toote soovituste suhtes võidakse kohaldada kohalikke seadusi ja määrusi ning klientide ootusi, mida mudel pole spetsiaalselt arvesse võetud.  Selle prognoosimisvõimaluse kasutajana **peate enne klientidele kohaletoimetamist need soovitused üle vaatama**, et tagada, et järgite kõiki kohalduvaid õigusakte ning kliendi ootusi selle kohta, mida soovitate.

Lisaks annab selle mudeli väljund teile soovitusi toote ID põhjal. Teie kohaletoimetamise mehhanism peab kaardistama prognoositud toote ID-d sobiva sisuga, et teie kliendid saaksid arvestada lokaliseerimise, pildisisu ja muu ettevõttespetsiifilise sisu või käitumisega.

## <a name="sample-guide"></a>Näidisjuhend

Kui olete huvitatud selle funktsiooni proovimisest, kuid teil pole andmeid allpool esitatud nõuete täitmiseks, võite [luua näidisrakenduse](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Eeltingimused

- Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.

- Äriteadmised, et mõista teie ettevõtte jaoks erinevaid tooteid ja seda, kuidas kliendid nendega suhtlevad. Toetame teie klientide poolt varem ostetud toodete soovitamist või uute toodete soovitamist.

- Teie keskkond peab olema konfigureeritud üksikute tarbijate **esmase sihtrühma jaoks**.

- Andmed tehingute, ostude ja nende ajaloo kohta.
  - Tehinguidentifikaatorid, et eristada oste või tehinguid.
  - Kliendiidentifikaatorid, et vastendada tehingud teie klientidega.
  - Tehingusündmuse kuupäevad, mis määratlevad tehingu toimumise kuupäevad.
  - Tehingu toote ID teave.
  - (valikuline) Tootekataloogi andmeolem tootefiltri kasutamiseks.
  - (valikuline) Kui tehing on tagastatud või mitte.
  - Semantiliste andmete skeem nõuab järgmist teavet.
    - **Tehingu ID:** ostu või tehingu ainuidentifikaator.
    - **Tehingu kuupäev:** Ostu või tehingu kuupäev.
    - **Tehingu väärtus:** ostu või tehingu arvuline väärtus.
    - **Kordumatu toote ID:** ostetud toote või teenuse ID, kui teie andmed on reakauba tasemel.
    - (Valikuline) **Ostmine või tagastamine:** Loogikaväli, kus väärtus *tõene* tuvastab, et tehing oli tagastatud. Kui ostu või tagastamise andmeid mudelile ei esitata ja **Tehingu väärtus** on negatiivne, kasutame seda teavet ka tagastamise järeldamiseks.
- Soovitatavad andmete omadused:
  - Piisavad varasemad andmed: Vähemalt üks aasta tehinguandmeid, eelistatavalt kaks kuni kolm aastat, et lisada hooajalisust.
  - Mitu ostu kliendi kohta: kolm või enam tehingut kliendi ID kohta
  - Klientide arv: Vähemalt 100 klienti, eelistatuult rohkem kui 10 000 klienti. Mudel nurjub vähem kui 100 kliendiga.

> [!NOTE]
>
> - Mudeli jaoks on vaja teie klientide tehingute ajalugu. Tehingu määratlus on üsna paindlik. Sisendina võivad töötada kõik andmed, mis kirjeldavad kasutaja ja toote koostoimet. Näiteks toote ostmine, tunnis käimine või sündmusest osa võtmine.
> - Praegu saab konfigureerida ainult ühe kannete ajaloo olemi. Kui ostuolemeid on mitu, ühendage need Power Query enne andmete allaneelamist.
> - Kui tellimus ja tellimuse üksikasjad on erinevad olemid, liitke need enne mudelis kasutamist. Mudel ei tööta ainult tellimuse ID-ga või kviitungi ID-ga olemis.

## <a name="create-a-product-recommendation-prediction"></a>Looge tootesoovituste prognoos

1. Avage teenuses Customer Insights jaotised **Ärianalüüs** > **Prognoosid**.

1. **Valige paan Tootesoovitused** ja valige **Kasuta seda mudelit**.
   > [!div class="mx-imgBorder"]
   > ![Toote soovitusmudeli paan nupuga Kasuta seda mudelit.](media/product-recommendation-usethismodel.PNG "Toote soovitusmudeli paan nupuga Kasuta seda mudelit")

1. Vaadake üle mudelinõuete teave. Kui teil on vajalikud andmed, valige **Alustamine**.

### <a name="name-model"></a>Mudelile nime panemine

1. Sisestage mudelile nimi, et eristada seda teistest mudelitest.

1. Sisestage väljundüksuse nimi, kasutades ainult tähti ja numbreid, ilma tühikuteta. Seda nime kasutab mudeli olem. Seejärel valige suvand **Edasi**.

### <a name="define-product-recommendation-configuration"></a>Tootesoovituse konfiguratsiooni määratlemine

1. Määrake kliendile soovitatavate **toodete arv**. See väärtus sõltub sellest, kuidas teie tarneviis andmeid täidab. Kui oskate soovitada kolme toodet, määrake see väärtus vastavalt.

   >[!TIP]
   > Prognoos mustandina salvestamiseks saate igal ajal valida **Salvesta mustand**. Prognoosi mustandi leiate vahekaardilt **Minu prognoosid**.

1. Valige, kas soovite kaasata tooteid, mille kliendid on hiljuti ostnud väljale **Eeldatavate** ostude kordamine.

1. Seadke **aken** Tagasivaade. Antud säte määrab ajavahemiku, mida mudel kaalub enne toote kasutajale uuesti soovitamist. Näiteks saate määrata, et klient ostab iga kahe aasta järel sülearvuti. See aken näitab viimase kahe aasta ostuajalugu ja kui nad leitakse üksus, filtreeritakse üksus soovituste põhjal.

1. Vali **Järgmine**

### <a name="add-required-data"></a>Lisage nõutud andmed

1. Valige **Lisa andmed** ja valige tegevusetüüp, mis sisaldab nõutavat kannete või ostuajaloo teavet.

1. Valige jaotises **Tegevuste valik** valitud tegevusest konkreetsed tegevused, millele soovite oma arvutuste puhul keskenduda.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Kõrvalpaan, kus kuvatakse kindlate tegevuste valimine semantilise tüübi all.":::

1. Kui te pole tegevust veel semantilise tüübiga vastendanud, valige selleks **Redigeeri**. Avaneb juhendav kogemus semantilise tegevuse kaardismiseks. Vastendage oma andmed valitud tegevuste tüübi vastavate väljadega.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Lehe sätte tegevuse tüüp.":::

1. Pärast tegevuse vastendamist vastava semantilise tüübiga valige **jätkamiseks Nupp Edasi**.

1. Vastendage semantilised atribuudid väljadega, mis on mudeli käivitamiseks vajalikud.

1. Valige **Salvesta**.

1. Tehke valik **Edasi**.

### <a name="configure-product-filters"></a>Tootefiltrite konfigureerimine

Mõnikord on ainult teatud tooted kasulikud või sobivad teie loodud prognoosi tüübi jaoks. Tootefiltrid lasevad teil tuvastada kindlate omadustega toodete alamhulga, mida soovitada klientidele. Mudelis kasutatakse mustrite saamiseks kõiki saadaolevaid tooteid, kuid kasutatakse ainult tooteid, mis vastavad tootefiltrile selle väljundis.

1. Lisage **Lisa tooteteave** etapis oma tootekataloog koos teabega iga toote kohta. Kaardistage nõutav informatsioon valikus **Edasi**.

1. Valige etais **Tootefiltrid** üks järgmistest suvanditest.

   - **Filtreid pole**: Kasutage soovituse prognoosis kõiki tooteid.

   - **Kindlate tootefiltrite määratlemine**: Kasutage soovituse prognoosis kindlaid tooteid.

1. Tehke valik **Edasi**.

1. Kui otsustate määratleda toote filtri, peate selle määratlema kohe. Valige paanil **Tootekataloogi atribuudid** oma *Tootekataloogi olemi* atribuudid, mille soovite filtrisse kaasata.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Kõrvalpaan, kus kuvatakse tootekataloogi olemi tootefiltrite valimiseks atribuut.":::

1. Valige, kas soovite, et tootefiltris kasutataks **ja** või **või**pistikuid, et teie tootekataloogi atribuutide valik loogiliselt ühendada.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Loogika JA pistikutega ühendatud tootefiltrite näidiskonfiguratsioon.":::

1. Tehke valik **Edasi**.

### <a name="set-update-schedule-and-review-configuration"></a>Määrake värskenduste ajakava ja kontrollige konfiguratsiooni

1. Määrake oma mudeli ümberõppe sagedus. See säte on oluline, et värskendada prognooside täpsust uute andmete importimisel Customer Insightsi. Suur osa ettevõtteid saavad teha ümberõpet kord kuus ja saavutavad täpsed prognoosid.

1. Tehke valik **Edasi**.

1. Konfiguratsiooni läbivaatamine. Saate naasta prognoosi mis tahes osasse, valides suvandi **Redigeeri** kuvatud väärtuse juures. Saate ka valida edenemise näidikust konfiguratsiooni etapi.

1. Kui kõik väärtused on õigesti konfigureeritud, valige pognoosimisprotsessi alustamiseks suvand **Salvesta ja käivita**. Vahekaardil **Minu prognoosid** kuvatakse teie prognooside olekut. Selle protsessi lõpule viimiseks võib kuluda mitu tundi, olenevalt prognoosis kasutatud andmete hulgast.

## <a name="review-a-prediction-status-and-results"></a>Prognoosi oleku ja tulemuste läbivaatamine

1. Avage jaotises **Ärianalüüs** > **Prognoosid** vahekaart **Minu prognoosid**.
   > [!div class="mx-imgBorder"]
   > ![Lehe Minu prognoosid vaade.](media/product-recommendation-mypredictions.PNG "Lehe Minu prognoosid vaade")

1. Valige prognoos, mille soovite üle vaadata.
   - **Prognoosi nimi:** selle prognoosi loomisel pandud nimi.
   - **Prognoosi tüüp:** prognoosi jaoks kasutatav mudeli tüüp
   - **Väljundolem:** olemi nimi, kuhu talletatakse prognoosi väljund. Selle nimega olemi leiate jaotisest **Andmed** > **Olemid**.
      *Punktisumma* väljundüksuses on soovituse kvantitatiivne näitaja. Mudel soovitab tooteid, mille skoor on kõrgem enna väiksema punktisummaga tooteid.
   - **Prognoositud väli:** See väli asustatakse ainult teatud tüüpi prognooside korral ja seda ei kasutata Tootesoovituse prognoosis.
   - **Olek:** prognoosi käitamise praegune olek.
        - **Järjekorras:** prognoos ootab praegu muude protsesside käitamist.
        - **Värskendamine:** prognoos käitab praegu töötlemise etappi „skoor”, et saada tulemusi, mis voolavad väljundolemisse.
        - **Nurjunud:** prognoos on nurjunud. Üksikasjade saamiseks valige **Logid**.
        - **Õnnestus:** prognoos on õnnestunud. Valige prognoosi läbivaatamiseks **Vaade** vertikaalse kolmikpunkti juures
   - **Redigeeritud:** prognoosi konfiguratsiooni muutmise kuupäev.
   - **Viimati värskendatud:** kuupäev, mil prognoos värskendas tulemusi väljundolemis.

1. Valige vertikaalne kolmikpunkt prognoosi kõrval, mille tulemusi soovite läbivaadata ja valige **Vaade**.
   > [!div class="mx-imgBorder"]
   > ![Suvandite vaade prognoosi vertikaalse kolmikpunkti menüüs, sh redigeerimine, värskendamine, vaade, logid ja kustutamine.](media/product-recommendation-verticalellipses.PNG "Suvandite vaade prognoosi vertikaalse kolmikpunkti menüüs, sh redigeerimine, värskendamine, vaadet, logid ja kustutamine")

1. Tulemite lehel on viis esmast andmejaotist:
    1. **Koolituse mudeli jõudlus:** võimalikud punktisummad on A, B või C. See skoor näitab prognoosi jõudlust ja aitab teil otsustada, kas kasutada väljundolemis talletatud tulemusi.
        - Skoorid määratletakse järgmiste reeglite alusel.
            - **A** Mudelit peetakse **A** kvaliteediga mõõdikuks, kui mõõdik "Õnnestusumise @ K" on vähemalt 10% baasmäärast. 
            - **B** Mudelit peetakse **B** kvaliteediga mõõdikuks, kui mõõdik "Success @ K" on vähemalt 0% kuni 10% baasmäärast kõrgem.
            - **C** Mudelit peetakse **C** kvaliteediga mõõdikuks, kui mõõdik "Success @ K" on baasmäärast madalam.

               > [!div class="mx-imgBorder"]
               > ![Mudeli jõudluse tulemi vaade.](media/product-recommendation-modelperformance.PNG "Mudeli jõudluse tulemi vaade")
            - **Baasväärtus**: mudel võtab kõigi klientide seas kõige rohkem soovitatud tooteid ostude arvu järgi ja kasutab klientidele soovituste komplekti loomiseks mudeli tuvastatud õpitud reegleid. Seejärel võrreldakse seda prognoositava väärtusega kõige rohkem valmistatud toodetega, arvutatuna vastavalt toote ostnud klientide arvule. Kui kliendi soovitatud toodetes on vähemalt üks toode, mida oli näha ka kõige paremini ostetud toodetes, loetakse teda baasväärtuse osaks. Kui neid kliente oleks kümme, kellel oleks soovitatud toode ostetud 100 kliendi seast, oleks baasväärtus 10%.
            - **Õnnestumise @ K**: tehingute ajaperioodi valideerimiskomplekti abil luuakse kõigi klientide jaoks soovitusi ja võrreldakse neid tehingute valideerimiskomplektiga. Näiteks 12 kuu jooksul võidakse 12. kuu andmed andmete valideerimise kogumina kõrvale jätta. Kui mudel ennustab vähemalt üht asja, mida 12. kuu jooksul ostsid, võttes aluseks viimase 11 kuuga õpitu, suurendaks klient mõõdikut "Success @ K".

    1. **Enamik soovitatud tooteid (kokku):** Top viis toodet, mis olid teie klientide jaoks prognoositud.
       > [!div class="mx-imgBorder"]
       > ![Graafik, kus on kuvatud 5 tähtsamat toodet.](media/product-recommendation-topproducts.PNG "Graafik, kus on kuvatud viis tähtsamat toodet")

    1. **Peamised soovitustegurid:** Mudel kasutab klientide tehingute ajalugu tootesoovituste tegemiseks. See õpib varasemate ostude põhjal mustreid ja leiab sarnasusi klientide ja toodete vahel. Seejärel kasutatakse neid sarnasusi tootesoovituste loomiseks.
    Järgmised on tegurid, mis võivad mõjutada mudeli põhjal loodud tootesoovituste kasutamist.
        - **Varasemad tehingud**: Varem kasutatud ostumustreid on mudeli abil kasutatud tootesoovituste genereerimiseks. Näiteks võib mudel soovitada *Surface Arc Mouse'i*, kui keegi on hiljuti ostnud *Surface Book 3* ja *Surface Peni*. Mudel sai teada, et ajalooliselt olid paljud kliendid ostnud *Surface Arc Mouse'i* pärast *Surface Book 3* ja *Surface Pen'i* ostmist.
        - **Kliendi sarnasus**: Soovitatav toode on varasemalt ostetud teiste klientide poolt, kellel on sarnased ostumustrid. Näiteks Johnile soovitati osta *Surface Headphones 2*, sest Jennifer ja Brad ostsid hiljuti *Surface Headphones 2*. Mudel usub, et John sarnaneb Jenniferi ja Bradiga, kuna neil on ajalooliselt olnud sarnased ostumustrid.
        - **Toote sarnasus**: Soovitatav toode sarnaneb teiste toodetega, mille klient oli varem ostnud. Mudel peab kahte toodet sarnaseks, kui need osteti koos või sarnaste klientide poolt. Näiteks saab keegi sovituse osta *USB Storage Drive*, sest nad olid varem ostnud *USB-C to USB Adapter* ja mudel usub varasema ostumustri põhjal, et *USB Storage Drive* on sarnane *USB-C to USB Adapteriga*.

        Iga toote soovitust mõjutab üks või mitu nendest teguritest. Diagrammil visualiseeritakse soovituste protsent, kus iga mõjutegur mängis rolli. Järgmises näites on 100% soovitustest mõjutatud möödunud tehingutest, 60% klientide sarnasusest ja 22% toodete sarnasusest. Hõljutage diagrammi ribade kohal, et näha täpne protsent, kuhu mõjutegurid kaasa aitasid.

        > [!div class="mx-imgBorder"]
        > ![Soovituse peamised tegurid.](media/product-recommendation-keyrecommendationfactors.png "Mudelis tootesoovituste genereerimiseks õpitud peamised soovitustegurid")

   1. **Andmestatistika**: Annab ülevaate tehingute, klientide ja toodete arvust, mida mudel on arvesse võtnud. See põhineb sisestusandmetel, mida kasutati mustrite õppimiseks ja tootesoovituste loomiseks.

      > [!div class="mx-imgBorder"]
      > ![Andmestatistika.](media/product-recommendation-datastatistics.png "Andmete statistika sisendi kohta, mida mudel kasutab mustrite õppimiseks")

      Selles jaotises kuvatakse andmepunktide statistika, mida mudelis kasutati mustrite õppimiseks ja tootesoovituste loomiseks. Mudeli konfiguratsioonis konfigureeritud filtreerimine rakendub mudeli genereeritud väljundile. Kuid mudel kasutab mustrite õppimiseks kõiki saadaolevaid andmeid. Seetõttu, kui kasutate mudelikonfiguratsioonis tootefiltreerimist, kuvatakse selles jaotises nende toodete koguarv, mida mudelis on analüüsitud mustrite õppimiseks, mis võivad määratletud filtreerimiskriteeriumidele vastavatest toodetest erineda.

   1. **Hea klienditeenindusega tootesoovitused:** klientidele antud soovituste näide, mis sisaldab teavet selle kohta, et mudel on salvestatud, ostab tõenäoliselt klient.    
      Kui lisatakse tootekataloog, asendatakse toote ID-d tootenimedega. Tootenimed pakuvad prognooside kohta tegusamat ja intuitivsemat teavet.
       > [!div class="mx-imgBorder"]
       > ![Loend, mis näitab, et üksikuid kliente saab valida kõrge täpsusega soovitustega.](media/product-recommendation-highconfidence.PNG "Loend, mis näitab, et üksikuid kliente saab valida kõrge täpsusega soovitustega")

## <a name="manage-predictions"></a>Prognooside haldamine

Prognoose on võimalik optimeerida, tõrkeotsingut teha, värskendada või kustutada. Vaadake sisendandmete kasutatavuse aruanne üle, et teada saada, kuidas muuta prognoos kiiremaks ja usaldusväärsemaks. Lisateavet leiate teemast [Prognooside haldamine](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]