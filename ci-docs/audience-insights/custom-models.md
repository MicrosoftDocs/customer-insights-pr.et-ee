---
title: Kohandatud masinõppe mudelid | Microsoft Docs
description: Azure'i masinõppe kohandatud mudelitega töötamine rakenduses Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305622"
---
# <a name="custom-machine-learning-models"></a>Kohandatud masinõppe mudelid

Jaotises **Ärianalüüs** > **Kohandatud mudelid** saate hallata töövooge Azure'i masinõppe mudelite põhjal. Töövood aitavad teil valida andmed, mille põhjal soovite ülevaateid luua, ja vastendada tulemused teie koondatud kliendiandmetega. Lisateavet kohandatud masinõppemudelite loomise kohta leiate teemast [Azure'i masinaõppe põhiste mudelite kasutamine](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Vastutustundlik tehisintellekt

Prognoosid pakuvad võimalusi klientidele paremate kogemuste loomiseks ning ärivõimaluste ja tulu parandamiseks. Soovitame teil oma prognoosi väärtuse hindamisel võtta eetiliselt arvesse selle mõju ja kallutusi, milleni see võib viia. Lugege lisateavet selle kohta, kuidas Microsoft [käsitleb vastutustundlikku tehisintellekti](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Samuti saate tutvuda Azure'i masinõppega seotud [vastutustundliku masinõppe meetodite ja protsessidega](/azure/machine-learning/concept-responsible-ml).

## <a name="prerequisites"></a>Eeltingimused

- See funktsioon toetab praegu veebiteenuseid, mis on avaldatud [masinõppe stuudio (klassikaline)](https://studio.azureml.net) ja [Azure'i masinõppe partiikonveierite](/azure/machine-learning/concept-ml-pipelines) kaudu.

- Selle funktsiooni kasutamiseks on vaja Azure Data Lake Gen2 salvestuskontot, mis on seotud teie Azure Studio eksemplariga. Lisateavet leiate teemast [Azure Data Lake Storage Gen2 salvestuskonto loomine](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Azure'i masinõppe konveieritega tööruumide jaoks on teil vaja Azure'i masinõppe tööruumi omaniku või kasutajajuurdepääsu administraatori õigusi.

   > [!NOTE]
   > Andmed edastatakse teie Customer Insightsi eksemplaride ja töövoos valitud Azure'i veebiteenuste või konveierite vahel. Andmete edastamisel Azure'i teenusele veenduge, et teenus oleks konfigureeritud andmeid töötlema vajalikul viisil ja kohas, mis vastaks mis tahes juriidilistele või regulatiivsetele nõuetele nende andmete puhul teie organisatsioonis.

## <a name="add-a-new-workflow"></a>Uue töövoo lisamine

1. Avage jaotis **Ärianalüüs** > **Kohandatud mudelid** ja valige **Uus töövoog**.

1. Sisestage väljale **Nimi** oma kohandatud mudeli äratuntav nimi.

   > [!div class="mx-imgBorder"]
   > ![Uue töövoo paani kuvatõmmis](media/new-workflowv2.png "Uue töövoo paani kuvatõmmis")

1. Valige veebiteenust sisaldav organisatsioon jaotises **Teie veebiteenust sisaldav rentnik**.

1. Kui teie Azure'i masinõppe kordustellimus on mõnes muus rentnikus kui Customer Insights, valige suvand **Logi sisse** oma valitud organisatsiooni mandaadiga.

1. Valige oma veebiteenusega seotud **tööruumid**. Seal on kaks jaotist, üks Azure'i masinõppe v1 (masinõppe stuudio (klassikaline)) ja üks Azure'i masinõppe v2 (Azure'i masinõpe) jaoks. Kui te pole kindel, milline tööruum on teie masinõppe stuudio (klassikaline) veebiteenuse jaoks õige, valige **Suvaline**.

1. Valige masinõppe stuudio (klassikaline) veebiteenus või Azure'i masinõppe konveier ripploendis **Veebiteenus, mis sisaldab teie mudelit**. Seejärel valige suvand **Edasi**.
   - Lugege lisateavet [veebiteenuse avaldamise kohta masinõppe stuudios (klassikaline)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Lugege lisateavet [konveieri avaldamise kohta Azure'i masinõppes kujundaja abil](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) või [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) kohta. Teie konveier peab olema avaldatud [konveieri lõpp-punktis](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Valige iga **veebiteenuse sisendi** kohta sihtrühmaülevaadetest vastav **Olem** ja valige **Järgmine**.
   > [!NOTE]
   > Kohandatud mudeli töövoog rakendab heuristikat veebiteenuse sisendväljade vastendamiseks olemiatribuutidele, võttes aluseks välja nime ja andmetüübi. Kui veebiteenuse välja ei saa olemile vastendada, kuvatakse tõrge.

   > [!div class="mx-imgBorder"]
   > ![Konfigureeri töövoog](media/intelligence-screen2-updated.png "Konfigureeri töövoog")

1. Määrake etapis **Mudeli väljundi parameetrid** järgmised atribuudid.
   - Masinõppe stuudio (klassikaline)
      1. Sisestage väljundi **Olemi nimi**, millesse soovite veebiteenuse väljundi tulemusi salvestada.
   - Azure’i masinõpe
      1. Sisestage väljundi **Olemi nimi**, millesse soovite konveieri väljundi tulemusi salvestada.
      1. Valige oma partiikonveieri ripploendist **Väljundi andmesalve parameetri nimi**.
      1. Valige oma partiikonveieri ripploendist **Väljundi tee parameetri nimi**.

      > [!div class="mx-imgBorder"]
      > ![Mudeli väljundi parameetri paan](media/intelligence-screen3-outputparameters.png "Mudeli väljundi parameetri paan")

1. Valige ripploendist **Kliendi ID tulemustes** vastav atribuut, mis tuvastab kliendid ka valige **Salvesta**.

   > [!div class="mx-imgBorder"]
   > ![Tulemuste seostamine paanil „Kliendiandmed“](media/intelligence-screen4-relatetocustomer.png "Tulemuste seostamine paanil „Kliendiandmed“")

1. Teile kuvatakse töövoo üksikasjadega kuva **Töövoog salvestatud**.    
   Kui olete konfigureerinud Azure'i masinõppe konveieri jaoks töövoo, lisatakse sihtrühmaülevaated tööruumi, mis sisaldab konveierit. Sihtrühmaülevaadetele antakse Azure'i tööruumis roll **Kaasautor**.

1. Valige nupp **Valmis**.

1. Nüüd saate töövoo käivitada lehel **Kohandatud mudelid**.

## <a name="edit-a-workflow"></a>Töövoo redigeerimine

1. Valige lehel **Kohandatud mudelid** eelnevalt loodud töövoo kõrval kolm vertikaalset punkti veerus **Toimingud** ja valige suvand **Redigeeri**.

1. Saate värskendada oma töövoo nime väljal **Kuvatav nimi**, kuid te ei saa muuta konfigureeritud veebiteenust või konveierit. Tehke valik **Edasi**.

1. Iga **veebiteenuse sisendi** korral saate värskendada sihtrühmaülevaadetes ühtivat **olemit**. Seejärel valige suvand **Edasi**.

1. Määrake etapis **Mudeli väljundi parameetrid** järgmised atribuudid.
   - Masinõppe stuudio (klassikaline)
      1. Sisestage väljundi **Olemi nimi**, millesse soovite veebiteenuse väljundi tulemusi salvestada.
   - Azure’i masinõpe
      1. Sisestage väljundi **Olemi nimi**, millesse soovite konveieri väljundi tulemusi salvestada.
      1. Valige oma proovikonveierile **Väljundi andmesalve parameetri nimi**.
      1. Valige oma proovikonveierile **Väljundi tee parameetri nimi**.

1. Valige ripploendist **Kliendi ID tulemustes** vastav atribuut, mis tuvastab kliendid ka valige **Salvesta**.
   Valige tuletuse väljundist atribuut, mille väärtused on sarnased kliendiolemi veeru „Kliendi ID“ omadega. Kui teie andmekogumis pole sellist veergu, valige atribuut, mis tuvastab rea unikaalselt.

## <a name="run-a-workflow"></a>Töövoo käitamine

1. Valige lehel **Kohandatud mudelid** eelnevalt loodud töövoo kõrval kolm vertikaalset punkti veerus **Toimingud**.

1. Valige **Käivita**.

Teie töövoog käivitub automaatselt ka iga ajastatud värskendamise korral. Lisateave [ajastatud värskenduste häälestamise kohta](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Töövoo kustutamine

1. Valige lehel **Kohandatud mudelid** eelnevalt loodud töövoo kõrval kolm vertikaalset punkti veerus **Toimingud**.

1. Valige käsk **Kustuta** ja kinnitage kustutamine.

Teie töövoog kustutatakse. Töövoo loomisel loodud [olem](entities.md) jääb alles ning seda saab näha lehel **Olemid**.

## <a name="results"></a>Tulemid

Töövoo tulemused talletatakse mudeli väljundparameetri sisendi ajal konfigureeritud olemis. Neile andmetele pääsete juurde [olemite lehelt](entities.md) või [API-juurdepääsuga](apis.md).

### <a name="api-access"></a>API-juurdepääs

Kindla OData päringu andmete toomiseks kohandatud mudeli olemist kasutage järgmist vormingut.

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Asendage `<your instance id>` oma Customer Insightsi keskkonna ID-ga, mille leiate brauseri aadressiribalt, kui avate Customer Insightsi.

1. Asendage `<custom model output entity>` kohandatud mudeli konfiguratsiooni mudeliväljundiparameetrite etapil esitatud olemi nimega.

1. Asendage `<guid value>` selle kliendi ID-ga, mille kirjele soovite juurde pääseda. Tavaliselt leiate selle ID [kliendiprofiilide lehel](customer-profiles.md)väljalt Kliendi ID.

## <a name="frequently-asked-questions"></a>Korduma kippuvad küsimused

- Miks ei saa kohandatud mudeli töövoo seadistamisel konveierit vaadata?    
  Selle probleemi põhjuseks on sageli konveieri konfiguratsiooniprobleem. Veenduge, [et sisendparameeter oleks](azure-machine-learning-experiments.md#dataset-configuration)konfigureeritud ning konfigureeritud on ka [väljundandmesalve ja tee parameetrid](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).

- Mida tähendab tõrge „Ei saanud ärianalüüsi töövoogu salvestada“?    
  Kasutajad näevad seda tõrketeadet tavaliselt juhul, kui neil pole tööruumis omaniku- või kasutajajuurdepääsu administraatori õigusi. Kasutajal on vaja õiguste kõrgemat taset, et võimaldada Customer Insightsil töövoogu teenusena töödelda, mitte kasutada kasutaja identimisteavet töövoo järgmisteks töövoogudeks.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
