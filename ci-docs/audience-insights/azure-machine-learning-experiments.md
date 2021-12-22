---
title: Azure'i masinõppe eksperimendid
description: Kasutage Azure'i masinõppel põhinevaid mudeleid rakenduses Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e37eec503c9df83ef72497e22afa1266296e642c
ms.sourcegitcommit: 58651d33e0a7d438a2587c9ceeaf7ff58ae3b648
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 12/02/2021
ms.locfileid: "7881733"
---
# <a name="use-azure-machine-learning-based-models"></a>Kasutage Azure'i masinõppel põhinevaid mudeleid

Dynamics 365 Customer Insightsis olevad koondatud andmed on allikaks masinõppemudelite loomisele, mis võivad luua täiendavaid äriülevaateid. Customer Insights integreerib Azure'i masinõppe oma kohandatud mudelite kasutamiseks.

## <a name="prerequisites"></a>Eeltingimused

- Juurdepääs Customer Insightsi
- Aktiivne Azure Enterprise'i tellimus
- [Kliendi koondprofiilid](data-unification.md)
- [Olemi eksportimine Azure'i bloobimällu](export-azure-blob-storage.md) on konfigureeritud

## <a name="set-up-azure-machine-learning-workspace"></a>Azure'i masinõppe tööruumi seadistamine

1. Eri võimalused tööruumi loomiseks leiate teemast [Azure'i masinõppe tööruumi loomine](/azure/machine-learning/concept-workspace#-create-a-workspace). Parimate tulemuste saamiseks looge tööruum Azure'i regioonis, mis on geograafiliselt kõige lähemal teie Customer Insightsi keskkonnale.

1. Avage oma tööruum [Azure'i masinõppe stuudio](https://ml.azure.com/) kaudu. Tööruumiga suhtlemiseks on [mitu võimalust](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction).

## <a name="work-with-azure-machine-learning-designer"></a>Azure'i masinõppe kujundajaga töötamine

Azure Masinõpe disainer pakub visuaalset lõuendit, kus saate andmekogumeid ja mooduleid lohistada. Kujundajas loodud partiikonveierit saab integreerida Customer Insightsi, kui need on nii konfigureeritud. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Azure'i masinõppe SDK-ga töötamine

Andmeteadlased ja tehisintellekti arendajad kasutavad [Azure'i masinõppe SDK-d](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py), et luua masinõppetöövooge. SDK abil treenitud mudeleid ei saa praegu otse Customer Insightsi integreerida. Customer Insightsiga integreerimiseks on vaja partiipõhist tuletuskonveierit, mis kasutab seda mudelit.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Partiikonveieri nõuded Customer Insightsiga integreerimiseks

### <a name="dataset-configuration"></a>Andmekogumi konfiguratsioon

Peate looma andmekogumeid, et kasutada Customer Insightsist pärit olemiandmeid oma partiipõhises tuletuskonveieris. Need andmekogumid tuleb tööruumis registreerida. Praegu toetame ainult [tabelina esitatud andmekomplekte](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) CSV-vormingus. Olemiandmetele vastavad andmekomplektid peavad olema parametreeritud konveieri parameetrina.
   
* Andmekomplekti parameetrid kujundajas
   
     Avage kujundajas **Vali andmekomplekti veerud** ja valige **Määra konveieri parameetriks**, kus saate parameetrile nime anda.

     > [!div class="mx-imgBorder"]
     > ![Andmekomplekti parametreerimine kujundajas.](media/intelligence-designer-dataset-parameters.png "Andmekomplekti parametreerimine kujundajas")
   
* Andmekomplekti parameeter SDK-s (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Partiipõhine tuletuskonveier
  
* Kujundajas saab kasutada tuletuskonveieri loomiseks või värskendamiseks treeningkonveierit. Praegu toetatakse ainult partiipõhiseid tuletuskonveiereid.

* SDK abil saate konveieri avaldada lõpp-punktis. Praegu integreerub Customer Insights masinõppe tööruumis oleva partiikonveieri lõpp-punktis asuva vaikekonveieriga.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Konveieriandmete importimine Customer Insightsi

* Kujundajas on [andmete eksportimise moodul](/azure/machine-learning/algorithm-module-reference/export-data), mis võimaldab konveieri väljundit eksportida Azure'i salvestusruumi. Praegu peab moodul kasutama andmesalvetüüpi **Azure'i bloobimälu** ning parametreerima **andmesalve** ja suhtelist **teed**. Customer Insights alistab mõlemad parameetrid konveieri käitamisel andmesalve ja teega, mis on sellele tootele juurdepääsetavad.
   > [!div class="mx-imgBorder"]
   > ![Andmete eksportimise mooduli konfiguratsioon.](media/intelligence-designer-importdata.png "Andmete eksportimise mooduli konfiguratsioon")
   
* Kui kirjutate tuletusväljundi koodi, saate väljundi üles laadida tööruumis oleva *registreeritud andmesalve* teele. Kui tee ja andmesalv on konveieris parametreeritud, saab Customer Insights tuletuse väljundit lugeda ja importida. Praegu on toetatud ühe tabelina esitatud väljund CSV-vormingus. Tee peab sisaldama kataloogi ja faili nime.

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]