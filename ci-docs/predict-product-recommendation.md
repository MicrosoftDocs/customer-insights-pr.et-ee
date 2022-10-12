---
title: Tootesoovituse prognoosimine
description: Prognoosige tooteid, mida klient tõenäoliselt ostab või millega suhtleb.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610277"
---
# <a name="predict-product-recommendations"></a>Tootesoovituse prognoosimine

Tootesoovituste mudel loob ennustavate tootesoovituste komplekti. Soovitused põhinevad varasemal ostukäitumisel ja sarnase ostumustriga klientidel. See mudel on mõeldud üksiktarbijatele (B-kuni-C).

Teil peavad olema äriteadmised oma ettevõtte erinevat tüüpi toodetest ja sellest, kuidas teie kliendid nendega suhtlevad. Toetame teie klientide poolt varem ostetud toodete soovitamist või uute toodete soovitamist.

Toote soovituste suhtes võidakse kohaldada kohalikke seadusi ja määrusi ning klientide ootusi, mida mudel pole spetsiaalselt arvesse võetud. Seetõttu peate soovitused enne klientidele **edastamist üle vaatama,** et veenduda, et järgite kõiki kohaldatavaid seadusi või määrusi ja klientide ootusi selle kohta, mida võite soovitada.

Selle mudeli väljund annab toote ID põhjal soovitusi. Teie tarnemehhanism peab kaardistama prognoositavad toote ID-d sobiva sisuga, et teie kliendid saaksid arvestada lokaliseerimise, pildisisu ja muu ettevõttespetsiifilise sisu või käitumisega.

> [!TIP]
> Proovige tootesoovitust prognoos kasutades näidisandmeid: [Tootesoovitus prognoos näidisjuhend](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>eeltingimused

- Vähemalt [kaasautori õigused](permissions.md)
- Vähemalt 100 klienti, soovitavalt üle 10 000 kliendi.
- Kliendi identifikaator – kordumatu identifikaator tehingute sobitamiseks üksikkliendiga
- Vähemalt üks aasta tehinguandmeid, eelistatavalt kaks kuni kolm aastat, et lisada teatav hooajalisus. Ideaaljuhul vähemalt kolm või enam tehingut kliendi ID kohta. Tehingute ajalugu peab sisaldama järgmist:
  - **Tehingu ID**: ostu või tehingu kordumatu tunnus.
  - **Tehingu kuupäev**: ostu või tehingu kuupäev.
  - **Tehingu väärtus: ostu või tehingu** numbriline väärtus.
  - **Kordumatu toote ID**: ostetud toote või teenuse ID, kui teie andmed on rea kauba tasemel.
  - **Ost või tagastamine**: kahendväärtusega tõene/väär väärtus, kus *tõene* tuvastab, et tehing oli tagastus. Kui ostu- või tagastamisandmeid mudelis ei esitata ja **tehingu** väärtus on negatiivne, järeldame tootluse.
- Tootekataloogi andmeüksus, mida kasutada tootefiltrina.

> [!NOTE]
> - Mudel nõuab teie klientide tehingute ajalugu, kus tehing on mis tahes andmed, mis kirjeldavad kasutaja ja toote vahelist suhtlust. Näiteks toote ostmine, tunnis käimine või sündmusest osa võtmine.
> - Konfigureerida saab ainult ühte kandeajaloo olemit. Kui ostuolemeid on mitu, ühendage need Power Query enne andmete allaneelamist.
> - Kui tellimus ja tellimuse üksikasjad on erinevad olemid, liitke need enne mudelis kasutamist. Mudel ei tööta ainult tellimuse ID-ga või kviitungi ID-ga olemis.

## <a name="create-a-product-recommendation-prediction"></a>Looge tootesoovituste prognoos

Valige **Salvesta mustand** igal ajal, et salvestada prognoos mustandina. Mustand prognoos kuvatakse vahekaardil **Minu ennustused**.

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil** Loo **paanil Tootesoovitused (eelvaade)** suvand Kasuta **mudelit**.

1. Seejärel valige suvand **Alustamine**.

1. **Nimeta see mudel** ja **Väljundi olemi nimi**, et neid muudest mudelitest või olemitest eristada.

1. Tehke valik **Edasi**.

### <a name="define-product-recommendation-preferences"></a>Tootesoovituste eelistuste määratlemine

1. Määrake **kliendile soovitatavate toodete** arv. See väärtus sõltub sellest, kuidas teie tarneviis andmeid täidab.

1. Valige, kas soovite kaasata tooteid, mille kliendid on varem ostnud, väljale **Eeldatavate** ostude kordamine.

1. **Seadke tagasivaatamise aken** ajavahemikuga, mida mudel arvestab, enne kui toote kasutajale uuesti soovitate. Näiteks saate määrata, et klient ostab iga kahe aasta järel sülearvuti. Mudel vaatab viimase kahe aasta ostuajalugu ja kui ta leiab kauba, filtreeritakse üksus soovitustest.

1. Vali **Järgmine**

### <a name="add-purchase-history"></a>Lisa ostuajalugu

1. Valige **Lisa andmed** kliendikannete ajaloo **jaoks**.

1. Valige semantilise tegevuse tüüp **SalesOrderLine**, mis sisaldab nõutavat kande- või ostuajaloo teavet. Kui tegevust pole seadistatud, valige **siin** ja looge see.

1. Kui tegevuste atribuudid olid tegevuse loomisel semantiliselt vastendatud, valige jaotises **Tegevused** konkreetsed atribuudid või olem, millele soovite arvutuses keskenduda. Kui semantilist vastendamist ei toimunud, valige Redigeeri **ja** vastendage oma andmed.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Kõrvalpaan, kus kuvatakse kindlate tegevuste valimine semantilise tüübi all.":::

1. Valige **Edasi** ja vaadake üle selle mudeli jaoks vajalikud atribuudid.

1. Valige **Salvesta**.

1. Tehke valik **Edasi**.

### <a name="add-product-information-and-filters"></a>Tooteteabe ja filtrite lisamine

Mõnikord on ainult teatud tooted kasulikud või sobivad teie loodud prognoosi tüübi jaoks. Kasutage tootefiltreid, et tuvastada konkreetsete omadustega toodete alamhulk, mida oma klientidele soovitada. Mudelis kasutatakse mustrite saamiseks kõiki saadaolevaid tooteid, kuid kasutatakse ainult tooteid, mis vastavad tootefiltrile selle väljundis.

1. Lisage oma tootekataloogi olem, mis sisaldab teavet iga toote kohta. Vastendage vajalik teave ja valige **Salvesta**.

1. Tehke valik **Edasi**.

1. Valige **Tootefiltrid**:

   - **Filtreid pole**: Kasutage soovituse prognoosis kõiki tooteid.

   - **Kindlate tootefiltrite määratlemine**: Kasutage soovituse prognoosis kindlaid tooteid. **Valige paanil Tootekataloogi atribuudid** oma tootekataloogi olemi atribuudid, mille soovite filtrisse kaasata.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Kõrvalpaan, kus kuvatakse tootekataloogi olemi tootefiltrite valimiseks atribuut.":::

1. Valige, kas soovite kasutada tootefiltrit **ja** või kombineerida **loogiliselt** valitud atribuute tootekataloogist.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Loogika JA pistikutega ühendatud tootefiltrite näidiskonfiguratsioon.":::

1. Tehke valik **Edasi**.

### <a name="set-update-schedule"></a>Värskendusajakava määratlemine

1. Valige oma mudeli ümberõppe sagedus. See säte on oluline prognooside täpsuse värskendamiseks, kuna Customer Insightsi lisatakse uusi andmeid. Suur osa ettevõtteid saavad teha ümberõpet kord kuus ja saavutavad täpsed prognoosid.

1. Tehke valik **Edasi**.

### <a name="review-and-run-the-model-configuration"></a>Mudeli konfiguratsiooni läbivaatamine ja käitamine

Etapp **Läbivaatus ja käivitamine** näitab konfiguratsiooni kokkuvõtet ja annab võimaluse teha muudatusi enne prognoos loomist.

1. Valige **redigeeri mis** tahes juhis, mida soovite üle vaadata ja teha muudatusi.

1. Kui olete oma valikutega rahul, valige mudeli käitamise alustamiseks Salvesta **ja käivita**. Valige nupp **Valmis**. Vahekaart Minu **ennustused** kuvatakse prognoos loomise ajal. Selle protsessi lõpule viimiseks võib kuluda mitu tundi, olenevalt prognoosis kasutatud andmete hulgast.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prognoos tulemuste vaatamine

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil Minu ennustused** prognoos soovite vaadata.

Tulemuste lehel on viis peamist andmejaotist.

- **Mudeli toimivus:** hinded A, B või C näitavad prognoos toimivust ja aitavad teil teha otsuse väljundolemisse salvestatud tulemuste kasutamise kohta.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Pilt mudeli sooritustulemusest koos hindega A.":::

  Astmed määratletakse vastavalt järgmistele reeglitele.
  - **A**, kui mõõdik "Edu @ K" on vähemalt 10% suurem kui võrdlusalus.
  - **B**, kui mõõdik "Edu @ K" on 0–10% rohkem kui võrdlusalus.
  - **C**, kui mõõdik "Edu @ K" on baasjoonest väiksem.
  - **Lähtealus**: kõige enam soovitatavad tooted ostude arvu järgi kõigi klientide lõikes + mudeliga tuvastatud õpitud reeglid = soovituste kogum klientidele. Seejärel võrreldakse seda prognoositava väärtusega kõige rohkem valmistatud toodetega, arvutatuna vastavalt toote ostnud klientide arvule. Kui kliendi soovitatud toodetes on vähemalt üks toode, mida oli näha ka kõige paremini ostetud toodetes, loetakse teda baasväärtuse osaks. Näiteks kui 10-l neist klientidest oli soovitatav toode ostetud 100-st kliendist, on võrdlusalus 10%.
  - **Edu @ K**: Soovitused luuakse kõigile klientidele ja võrreldakse tehingute valideerimisperioodiga. Näiteks 12-kuulise perioodi jooksul jäetakse 12. kuu valideerimisandmete kogumina kõrvale. Kui mudel ennustab vähemalt üht asja, mida 12. kuu jooksul ostsid, võttes aluseks viimase 11 kuuga õpitu, suurendaks klient mõõdikut "Success @ K".

- **Enamik soovitatud tooteid (kokku):** Top viis toodet, mis olid teie klientide jaoks prognoositud.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Graafik, kus on kuvatud 5 tähtsamat toodet.":::

- **Peamised soovitustegurid:** Mudel kasutab klientide tehingute ajalugu tootesoovituste tegemiseks. See õpib varasemate ostude põhjal mustreid ja leiab sarnasusi klientide ja toodete vahel. Seejärel kasutatakse neid sarnasusi tootesoovituste loomiseks.
  Mudeli loodud tootesoovitust võivad mõjutada järgmised tegurid.
  - **Varasemad tehingud**: soovitatud toode põhines varasematel ostumustritel. Näiteks võib mudel soovitada *Surface Arc Mouse'i*, kui keegi on hiljuti ostnud *Surface Book 3* ja *Surface Peni*. Mudel sai teada, et ajalooliselt olid paljud kliendid ostnud *Surface Arc Mouse'i* pärast *Surface Book 3* ja *Surface Pen'i* ostmist.
  - **Kliendi sarnasus**: Soovitatav toode on varasemalt ostetud teiste klientide poolt, kellel on sarnased ostumustrid. Näiteks Johnile soovitati osta *Surface Headphones 2*, sest Jennifer ja Brad ostsid hiljuti *Surface Headphones 2*. Mudel usub, et John sarnaneb Jenniferi ja Bradiga, kuna neil on ajalooliselt olnud sarnased ostumustrid.
  - **Toote sarnasus**: Soovitatav toode sarnaneb teiste toodetega, mille klient oli varem ostnud. Mudel peab kahte toodet sarnaseks, kui need osteti koos või sarnaste klientide poolt. Näiteks saab keegi sovituse osta *USB Storage Drive*, sest nad olid varem ostnud *USB-C to USB Adapter* ja mudel usub varasema ostumustri põhjal, et *USB Storage Drive* on sarnane *USB-C to USB Adapteriga*.

  Iga toote soovitust mõjutab üks või mitu nendest teguritest. Diagrammil visualiseeritakse soovituste protsent, kus iga mõjutegur mängis rolli. Järgmises näites on 100% soovitustest mõjutatud möödunud tehingutest, 60% klientide sarnasusest ja 22% toodete sarnasusest. Hõljutage diagrammi ribade kohal, et näha täpne protsent, kuhu mõjutegurid kaasa aitasid.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Peamised soovitustegurid, mida mudel on õppinud tootesoovituste genereerimiseks.":::

- **Andmestatistika**: ülevaade tehingute arvust, klientidest ja toodetest, mida mudel kaalus. See põhineb sisestusandmetel, mida kasutati mustrite õppimiseks ja tootesoovituste loomiseks.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Andmestatistika sisendandmete kohta, mida mudel kasutab mustrite õppimiseks.":::
  
  Mudel kasutab mustrite õppimiseks kõiki saadaolevaid andmeid. Seega, kui kasutate mudeli konfiguratsioonis toote filtreerimist, kuvatakse selles jaotises nende toodete koguarv, mida mudel analüüsis, et õppida mustreid, mis võivad erineda määratletud filtreerimiskriteeriumidele vastavate toodete arvust. Filtreerimine rakendub mudeli genereeritud väljundile.

- **Tootesoovituste näidis:** näidis soovitustest, mida klient tõenäoliselt mudeli kohaselt ostab. Tootekataloogi lisamisel asendatakse toote ID-d tootenimedega.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Loend, mis näitab, et üksikuid kliente saab valida kõrge täpsusega soovitustega.":::

> [!NOTE]
> Selle mudeli *väljundolemis näitab Score* soovituse kvantitatiivset mõõdet. Mudel soovitab tooteid, mille skoor on kõrgem enna väiksema punktisummaga tooteid. Skoori vaatamiseks minge jaotisse **Andmeüksused** > **ja** vaadake selle mudeli jaoks määratletud väljundolemi andmete vahekaarti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
