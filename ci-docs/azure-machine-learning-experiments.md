---
title: Kasutage Azure'i masinõppel põhinevaid mudeleid
description: Kasutage Azure'i masinõppel põhinevaid mudeleid rakenduses Dynamics 365 Customer Insights.
ms.date: 09/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d9c9324ea4840b585b9af1a58d505ccaea6f18e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609820"
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

Azure Masinõpe Designer pakub visuaalset lõuendit, kuhu saate andmekogumeid ja mooduleid lohistada. Kujundajas loodud partiikonveierit saab integreerida Customer Insightsi, kui need on nii konfigureeritud. 

## <a name="working-with-azure-machine-learning-sdk"></a>Azure'i masinõppe SDK-ga töötamine

Andmeteadlased ja tehisintellekti arendajad kasutavad [Azure'i masinõppe SDK-d](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py), et luua masinõppetöövooge. SDK abil treenitud mudeleid ei saa praegu otse Customer Insightsi integreerida. Customer Insightsiga integreerimiseks on vaja partiipõhist tuletuskonveierit, mis kasutab seda mudelit.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Partiikonveieri nõuded Customer Insightsiga integreerimiseks

### <a name="dataset-configuration"></a>Andmekomplekti konfiguratsioon

Looge andmekogumid, et kasutada Customer Insightsi olemiandmeid partii järeldamise müügitoru jaoks. Registreerige need andmekogumid tööruumis. Praegu toetame ainult [tabelina esitatud andmekomplekte](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) CSV-vormingus. Parameetrige olemiandmetele vastavad andmekogumid müügitoru parameetrina.

- Andmekomplekti parameetrid kujundajas

  Avage kujundajas **Vali andmekomplekti veerud** ja valige **Määra konveieri parameetriks**, kus saate parameetrile nime anda.

  :::image type="content" source="media/intelligence-designer-dataset-parameters.png" alt-text="Andmekomplekti parametreerimine kujundajas.":::

- Andmekomplekti parameeter SDK-s (Python)

   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Partiipõhine tuletuskonveier
  
- Kasutage disaineris järelduste torujuhtme loomiseks või värskendamiseks koolitustoru. Praegu toetatakse ainult partiipõhiseid tuletuskonveiereid.

- SDK abil avaldage müügitoru lõpp-punktina. Praegu integreerub Customer Insights masinõppe tööruumis oleva partiikonveieri lõpp-punktis asuva vaikekonveieriga.

   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Konveieriandmete importimine Customer Insightsi

- Kujundajas on [andmete eksportimise moodul](/azure/machine-learning/algorithm-module-reference/export-data), mis võimaldab konveieri väljundit eksportida Azure'i salvestusruumi. Praegu peab moodul kasutama andmesalvetüüpi **Azure'i bloobimälu** ning parametreerima **andmesalve** ja suhtelist **teed**. Customer Insights alistab mõlemad parameetrid konveieri käitamisel andmesalve ja teega, mis on sellele tootele juurdepääsetavad.

  :::image type="content" source="media/intelligence-designer-importdata.png" alt-text="Andmete eksportimise mooduli konfiguratsioon.":::

- Koodi abil järeldamisväljundi kirjutamisel laadige väljund üles tööruumis registreeritud andmesalves *olevale teele*. Kui tee ja andmesalv on konveieris parametreeritud, saab Customer Insights tuletuse väljundit lugeda ja importida. Praegu on toetatud ühe tabelina esitatud väljund CSV-vormingus. Tee peab sisaldama kataloogi ja faili nime.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]