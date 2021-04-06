---
title: Azure'i masinõppe eksperimendid
description: Kasutage Azure'i masinõppel põhinevaid mudeleid rakenduses Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597414"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="6b0f5-103">Kasutage Azure'i masinõppel põhinevaid mudeleid</span><span class="sxs-lookup"><span data-stu-id="6b0f5-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="6b0f5-104">Dynamics 365 Customer Insightsis olevad koondatud andmed on allikaks masinõppemudelite loomisele, mis võivad luua täiendavaid äriülevaateid.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="6b0f5-105">Customer Insights integreerub masinõppe stuudio (klassikaline) ja Azure'i masinõppega, et saaksite kasutada omaenda kohandatud mudeleid.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="6b0f5-106">Teemast [Masinõppe stuudio (klassikaline) eksperimendid](machine-learning-studio-experiments.md) leiate näited eksperimentide kohta, mis on loodud masinõppe stuudios (klassikaline).</span><span class="sxs-lookup"><span data-stu-id="6b0f5-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="6b0f5-107">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="6b0f5-107">Prerequisites</span></span>

- <span data-ttu-id="6b0f5-108">Juurdepääs Customer Insightsi</span><span class="sxs-lookup"><span data-stu-id="6b0f5-108">Access to Customer Insights</span></span>
- <span data-ttu-id="6b0f5-109">Aktiivne Azure Enterprise'i tellimus</span><span class="sxs-lookup"><span data-stu-id="6b0f5-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="6b0f5-110">Kliendi koondprofiilid</span><span class="sxs-lookup"><span data-stu-id="6b0f5-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="6b0f5-111">[Olemi eksportimine Azure'i bloobimällu](export-azure-blob-storage.md) on konfigureeritud</span><span class="sxs-lookup"><span data-stu-id="6b0f5-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="6b0f5-112">Azure'i masinõppe tööruumi seadistamine</span><span class="sxs-lookup"><span data-stu-id="6b0f5-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="6b0f5-113">Eri võimalused tööruumi loomiseks leiate teemast [Azure'i masinõppe tööruumi loomine](/azure/machine-learning/concept-workspace#-create-a-workspace).</span><span class="sxs-lookup"><span data-stu-id="6b0f5-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="6b0f5-114">Parimate tulemuste saamiseks looge tööruum Azure'i regioonis, mis on geograafiliselt kõige lähemal teie Customer Insightsi keskkonnale.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="6b0f5-115">Avage oma tööruum [Azure'i masinõppe stuudio](https://ml.azure.com/) kaudu.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="6b0f5-116">Tööruumiga suhtlemiseks on [mitu võimalust](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction).</span><span class="sxs-lookup"><span data-stu-id="6b0f5-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="6b0f5-117">Azure'i masinõppe kujundajaga töötamine</span><span class="sxs-lookup"><span data-stu-id="6b0f5-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="6b0f5-118">Azure'i masinõppe kujundaja on visuaalne lõuend, kuhu saate lohistada andmekogumeid ja mooduleid, nii nagu masinõppe stuudioski (klassikaline).</span><span class="sxs-lookup"><span data-stu-id="6b0f5-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="6b0f5-119">Kujundajas loodud partiikonveierit saab integreerida Customer Insightsi, kui need on nii konfigureeritud.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="6b0f5-120">Azure'i masinõppe SDK-ga töötamine</span><span class="sxs-lookup"><span data-stu-id="6b0f5-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="6b0f5-121">Andmeteadlased ja tehisintellekti arendajad kasutavad [Azure'i masinõppe SDK-d](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py), et luua masinõppetöövooge.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="6b0f5-122">SDK abil treenitud mudeleid ei saa praegu otse Customer Insightsi integreerida.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="6b0f5-123">Customer Insightsiga integreerimiseks on vaja partiipõhist tuletuskonveierit, mis kasutab seda mudelit.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="6b0f5-124">Partiikonveieri nõuded Customer Insightsiga integreerimiseks</span><span class="sxs-lookup"><span data-stu-id="6b0f5-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="6b0f5-125">Andmekogumi konfiguratsioon</span><span class="sxs-lookup"><span data-stu-id="6b0f5-125">Dataset Configuration</span></span>

<span data-ttu-id="6b0f5-126">Peate looma andmekogumeid, et kasutada Customer Insightsist pärit olemiandmeid oma partiipõhises tuletuskonveieris.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="6b0f5-127">Need andmekogumid tuleb tööruumis registreerida.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="6b0f5-128">Praegu toetame ainult [tabelina esitatud andmekomplekte](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) CSV-vormingus.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="6b0f5-129">Olemiandmetele vastavad andmekomplektid peavad olema parametreeritud konveieri parameetrina.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="6b0f5-130">Andmekomplekti parameetrid kujundajas</span><span class="sxs-lookup"><span data-stu-id="6b0f5-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="6b0f5-131">Avage kujundajas **Vali andmekomplekti veerud** ja valige **Määra konveieri parameetriks**, kus saate parameetrile nime anda.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="6b0f5-132">![Andmekomplekti parametreerimine kujundajas](media/intelligence-designer-dataset-parameters.png "Andmekomplekti parametreerimine kujundajas")</span><span class="sxs-lookup"><span data-stu-id="6b0f5-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="6b0f5-133">Andmekomplekti parameeter SDK-s (Python)</span><span class="sxs-lookup"><span data-stu-id="6b0f5-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="6b0f5-134">Partiipõhine tuletuskonveier</span><span class="sxs-lookup"><span data-stu-id="6b0f5-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="6b0f5-135">Kujundajas saab kasutada tuletuskonveieri loomiseks või värskendamiseks treeningkonveierit.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="6b0f5-136">Praegu toetatakse ainult partiipõhiseid tuletuskonveiereid.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="6b0f5-137">SDK abil saate konveieri avaldada lõpp-punktis.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="6b0f5-138">Praegu integreerub Customer Insights masinõppe tööruumis oleva partiikonveieri lõpp-punktis asuva vaikekonveieriga.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="6b0f5-139">Konveieriandmete importimine Customer Insightsi</span><span class="sxs-lookup"><span data-stu-id="6b0f5-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="6b0f5-140">Kujundajas on [andmete eksportimise moodul](/azure/machine-learning/algorithm-module-reference/export-data), mis võimaldab konveieri väljundit eksportida Azure'i salvestusruumi.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="6b0f5-141">Praegu peab moodul kasutama andmesalvetüüpi **Azure'i bloobimälu** ning parametreerima **andmesalve** ja suhtelist **teed**.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="6b0f5-142">Customer Insights alistab mõlemad parameetrid konveieri käitamisel andmesalve ja teega, mis on sellele tootele juurdepääsetavad.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6b0f5-143">![Andmete eksportimise mooduli konfiguratsioon](media/intelligence-designer-importdata.png "Andmete eksportimise mooduli konfiguratsioon")</span><span class="sxs-lookup"><span data-stu-id="6b0f5-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="6b0f5-144">Kui kirjutate tuletusväljundi koodi, saate väljundi üles laadida tööruumis oleva *registreeritud andmesalve* teele.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="6b0f5-145">Kui tee ja andmesalv on konveieris parametreeritud, saab Customer Insights tuletuse väljundit lugeda ja importida.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="6b0f5-146">Praegu on toetatud ühe tabelina esitatud väljund CSV-vormingus.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="6b0f5-147">Tee peab sisaldama kataloogi ja faili nime.</span><span class="sxs-lookup"><span data-stu-id="6b0f5-147">The path must include the directory and filename.</span></span>

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