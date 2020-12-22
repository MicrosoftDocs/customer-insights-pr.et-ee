---
title: Kohandatud masinõppe mudelid | Microsoft Docs
description: Azure'i masinõppe kohandatud mudelitega töötamine rakenduses Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668898"
---
# <a name="custom-machine-learning-models"></a>Kohandatud masinõppe mudelid

Jaotises **Ärianalüüs** > **Kohandatud mudelid** saate hallata töövooge Azure'i masinõppe mudelite põhjal. Töövood aitavad teil valida andmed, mille põhjal soovite ülevaateid luua, ja vastendada tulemused teie koondatud kliendiandmetega. Lisateavet kohandatud masinõppemudelite loomise kohta leiate teemast [Azure'i masinaõppe põhiste mudelite kasutamine](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>Vastutustundlik tehisintellekt

Prognoosid pakuvad võimalusi klientidele paremate kogemuste loomiseks ning ärivõimaluste ja tulu parandamiseks. Soovitame teil oma prognoosi väärtuse hindamisel võtta eetiliselt arvesse selle mõju ja kallutusi, milleni see võib viia. Lugege lisateavet selle kohta, kuidas Microsoft [käsitleb vastutustundlikku tehisintellekti](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Samuti saate tutvuda Azure'i masinõppega seotud [vastutustundliku masinõppe meetodite ja protsessidega](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml).

## <a name="prerequisites"></a>Eeltingimused

- See funktsioon toetab praegu veebiteenuseid, mis on avaldatud [masinõppe stuudio (klassikaline)](https://studio.azureml.net) ja [Azure'i masinõppe partiikonveierite](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) kaudu.

- Selle funktsiooni kasutamiseks on vaja Azure Data Lake Gen2 salvestuskontot, mis on seotud teie Azure Studio eksemplariga. Lisateavet leiate teemast [Azure Data Lake Storage Gen2 salvestuskonto loomine](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Uue töövoo lisamine

1. Avage jaotis **Ärianalüüs** > **Kohandatud mudelid** ja valige **Uus töövoog**.

1. Sisestage väljale **Nimi** oma kohandatud mudeli äratuntav nimi.

   > [!div class="mx-imgBorder"]
   > ![Uue töövoo paani kuvatõmmis](media/new-workflowv2.png "Uue töövoo paani kuvatõmmis")

1. Valige veebiteenust sisaldav organisatsioon jaotises **Teie veebiteenust sisaldav rentnik**.

1. Kui teie Azure'i masinõppe kordustellimus on mõnes muus rentnikus kui Customer Insights, valige suvand **Logi sisse** oma valitud organisatsiooni mandaadiga.

1. Valige oma veebiteenusega seotud **tööruumid**. Seal on kaks jaotist, üks Azure'i masinõppe v1 (masinõppe stuudio (klassikaline)) ja üks Azure'i masinõppe v2 (Azure'i masinõpe) jaoks. Kui te pole kindel, milline tööruum on teie masinõppe stuudio (klassikaline) veebiteenuse jaoks õige, valige **Suvaline**.

1. Valige masinõppe stuudio (klassikaline) veebiteenus või Azure'i masinõppe konveier ripploendis **Veebiteenus, mis sisaldab teie mudelit**. Seejärel valige suvand **Edasi**.
   - Lugege lisateavet [veebiteenuse avaldamise kohta masinõppe stuudios (klassikaline)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Lugege lisateavet [konveieri avaldamise kohta Azure'i masinõppes kujundaja abil](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) või [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) kohta. 
     > [!NOTE]
     > Teie konveier peab olema avaldatud [konveieri lõpp-punktis](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Valige iga **veebiteenuse sisendi** kohta sihtrühmaülevaadetest vastav **Olem** ja valige **Järgmine**.

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

1. Valige ripploendist **Kliendi ID tulemustes** ühtiv atribuut, mis tuvastab kliendid, ja seejärel **Salvesta**.
   
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

1. Valige ripploendist **Kliendi ID tulemustes** ühtiv atribuut, mis tuvastab kliendid, ja seejärel **Salvesta**.
   Teil tuleb valida tuletuse väljundist atribuut, mille väärtused on sarnased kliendiolemi veeru „Kliendi ID“ omadega. Kui teie andmekogumis pole sellist veergu, valige atribuut, mis tuvastab rea unikaalselt.

## <a name="run-a-workflow"></a>Töövoo käitamine

1. Valige lehel **Kohandatud mudelid** eelnevalt loodud töövoo kõrval kolm vertikaalset punkti veerus **Toimingud**.

1. Valige **Käivita**.

Teie töövoog käivitub automaatselt ka iga ajastatud värskendamise korral. Lisateave [ajastatud värskenduste häälestamise kohta](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Töövoo kustutamine

1. Valige lehel **Kohandatud mudelid** eelnevalt loodud töövoo kõrval kolm vertikaalset punkti veerus **Toimingud**.

1. Valige käsk **Kustuta** ja kinnitage kustutamine.

Teie töövoog kustutatakse. Töövoo loomisel loodud [olem](entities.md) jääb alles ning seda saab näha lehel **Olemid**.
