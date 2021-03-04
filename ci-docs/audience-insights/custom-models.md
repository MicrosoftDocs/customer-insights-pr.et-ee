---
title: Kohandatud masinõppe mudelid | Microsoft Docs
description: Azure'i masinõppe kohandatud mudelitega töötamine rakenduses Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267229"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="1c1cc-103">Kohandatud masinõppe mudelid</span><span class="sxs-lookup"><span data-stu-id="1c1cc-103">Custom machine learning models</span></span>

<span data-ttu-id="1c1cc-104">Jaotises **Ärianalüüs** > **Kohandatud mudelid** saate hallata töövooge Azure'i masinõppe mudelite põhjal.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="1c1cc-105">Töövood aitavad teil valida andmed, mille põhjal soovite ülevaateid luua, ja vastendada tulemused teie koondatud kliendiandmetega.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="1c1cc-106">Lisateavet kohandatud masinõppemudelite loomise kohta leiate teemast [Azure'i masinaõppe põhiste mudelite kasutamine](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="1c1cc-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="1c1cc-107">Vastutustundlik tehisintellekt</span><span class="sxs-lookup"><span data-stu-id="1c1cc-107">Responsible AI</span></span>

<span data-ttu-id="1c1cc-108">Prognoosid pakuvad võimalusi klientidele paremate kogemuste loomiseks ning ärivõimaluste ja tulu parandamiseks.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="1c1cc-109">Soovitame teil oma prognoosi väärtuse hindamisel võtta eetiliselt arvesse selle mõju ja kallutusi, milleni see võib viia.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="1c1cc-110">Lugege lisateavet selle kohta, kuidas Microsoft [käsitleb vastutustundlikku tehisintellekti](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="1c1cc-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="1c1cc-111">Samuti saate tutvuda Azure'i masinõppega seotud [vastutustundliku masinõppe meetodite ja protsessidega](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml).</span><span class="sxs-lookup"><span data-stu-id="1c1cc-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1c1cc-112">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="1c1cc-112">Prerequisites</span></span>

- <span data-ttu-id="1c1cc-113">See funktsioon toetab praegu veebiteenuseid, mis on avaldatud [masinõppe stuudio (klassikaline)](https://studio.azureml.net) ja [Azure'i masinõppe partiikonveierite](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines) kaudu.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="1c1cc-114">Selle funktsiooni kasutamiseks on vaja Azure Data Lake Gen2 salvestuskontot, mis on seotud teie Azure Studio eksemplariga.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="1c1cc-115">Lisateavet leiate teemast [Azure Data Lake Storage Gen2 salvestuskonto loomine](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="1c1cc-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="1c1cc-116">Uue töövoo lisamine</span><span class="sxs-lookup"><span data-stu-id="1c1cc-116">Add a new workflow</span></span>

1. <span data-ttu-id="1c1cc-117">Avage jaotis **Ärianalüüs** > **Kohandatud mudelid** ja valige **Uus töövoog**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="1c1cc-118">Sisestage väljale **Nimi** oma kohandatud mudeli äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1c1cc-119">![Uue töövoo paani kuvatõmmis](media/new-workflowv2.png "Uue töövoo paani kuvatõmmis")</span><span class="sxs-lookup"><span data-stu-id="1c1cc-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="1c1cc-120">Valige veebiteenust sisaldav organisatsioon jaotises **Teie veebiteenust sisaldav rentnik**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="1c1cc-121">Kui teie Azure'i masinõppe kordustellimus on mõnes muus rentnikus kui Customer Insights, valige suvand **Logi sisse** oma valitud organisatsiooni mandaadiga.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="1c1cc-122">Valige oma veebiteenusega seotud **tööruumid**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="1c1cc-123">Seal on kaks jaotist, üks Azure'i masinõppe v1 (masinõppe stuudio (klassikaline)) ja üks Azure'i masinõppe v2 (Azure'i masinõpe) jaoks.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="1c1cc-124">Kui te pole kindel, milline tööruum on teie masinõppe stuudio (klassikaline) veebiteenuse jaoks õige, valige **Suvaline**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="1c1cc-125">Valige masinõppe stuudio (klassikaline) veebiteenus või Azure'i masinõppe konveier ripploendis **Veebiteenus, mis sisaldab teie mudelit**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="1c1cc-126">Seejärel valige suvand **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="1c1cc-127">Lugege lisateavet [veebiteenuse avaldamise kohta masinõppe stuudios (klassikaline)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="1c1cc-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="1c1cc-128">Lugege lisateavet [konveieri avaldamise kohta Azure'i masinõppes kujundaja abil](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) või [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) kohta.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="1c1cc-129">Teie konveier peab olema avaldatud [konveieri lõpp-punktis](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="1c1cc-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="1c1cc-130">Valige iga **veebiteenuse sisendi** kohta sihtrühmaülevaadetest vastav **Olem** ja valige **Järgmine**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="1c1cc-131">Kohandatud mudeli töövoog rakendab heuristikat veebiteenuse sisendväljade vastendamiseks olemiatribuutidele, võttes aluseks välja nime ja andmetüübi.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="1c1cc-132">Kui veebiteenuse välja ei saa olemile vastendada, kuvatakse tõrge.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1c1cc-133">![Konfigureeri töövoog](media/intelligence-screen2-updated.png "Konfigureeri töövoog")</span><span class="sxs-lookup"><span data-stu-id="1c1cc-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="1c1cc-134">Määrake etapis **Mudeli väljundi parameetrid** järgmised atribuudid.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="1c1cc-135">Masinõppe stuudio (klassikaline)</span><span class="sxs-lookup"><span data-stu-id="1c1cc-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="1c1cc-136">Sisestage väljundi **Olemi nimi**, millesse soovite veebiteenuse väljundi tulemusi salvestada.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="1c1cc-137">Azure’i masinõpe</span><span class="sxs-lookup"><span data-stu-id="1c1cc-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="1c1cc-138">Sisestage väljundi **Olemi nimi**, millesse soovite konveieri väljundi tulemusi salvestada.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="1c1cc-139">Valige oma partiikonveieri ripploendist **Väljundi andmesalve parameetri nimi**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="1c1cc-140">Valige oma partiikonveieri ripploendist **Väljundi tee parameetri nimi**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="1c1cc-141">![Mudeli väljundi parameetri paan](media/intelligence-screen3-outputparameters.png "Mudeli väljundi parameetri paan")</span><span class="sxs-lookup"><span data-stu-id="1c1cc-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="1c1cc-142">Valige ripploendist **Kliendi ID tulemustes** ühtiv atribuut, mis tuvastab kliendid, ja seejärel **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1c1cc-143">![Tulemuste seostamine paanil „Kliendiandmed“](media/intelligence-screen4-relatetocustomer.png "Tulemuste seostamine paanil „Kliendiandmed“")</span><span class="sxs-lookup"><span data-stu-id="1c1cc-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="1c1cc-144">Teile kuvatakse töövoo üksikasjadega kuva **Töövoog salvestatud**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="1c1cc-145">Kui olete konfigureerinud Azure'i masinõppe konveieri jaoks töövoo, lisatakse sihtrühmaülevaated tööruumi, mis sisaldab konveierit.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="1c1cc-146">Sihtrühmaülevaadetele antakse Azure'i tööruumis roll **Kaasautor**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="1c1cc-147">Valige nupp **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-147">Select **Done**.</span></span>

1. <span data-ttu-id="1c1cc-148">Nüüd saate töövoo käivitada lehel **Kohandatud mudelid**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="1c1cc-149">Töövoo redigeerimine</span><span class="sxs-lookup"><span data-stu-id="1c1cc-149">Edit a workflow</span></span>

1. <span data-ttu-id="1c1cc-150">Valige lehel **Kohandatud mudelid** eelnevalt loodud töövoo kõrval kolm vertikaalset punkti veerus **Toimingud** ja valige suvand **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="1c1cc-151">Saate värskendada oma töövoo nime väljal **Kuvatav nimi**, kuid te ei saa muuta konfigureeritud veebiteenust või konveierit.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="1c1cc-152">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-152">Select **Next**.</span></span>

1. <span data-ttu-id="1c1cc-153">Iga **veebiteenuse sisendi** korral saate värskendada sihtrühmaülevaadetes ühtivat **olemit**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="1c1cc-154">Seejärel valige suvand **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="1c1cc-155">Määrake etapis **Mudeli väljundi parameetrid** järgmised atribuudid.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="1c1cc-156">Masinõppe stuudio (klassikaline)</span><span class="sxs-lookup"><span data-stu-id="1c1cc-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="1c1cc-157">Sisestage väljundi **Olemi nimi**, millesse soovite veebiteenuse väljundi tulemusi salvestada.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="1c1cc-158">Azure’i masinõpe</span><span class="sxs-lookup"><span data-stu-id="1c1cc-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="1c1cc-159">Sisestage väljundi **Olemi nimi**, millesse soovite konveieri väljundi tulemusi salvestada.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="1c1cc-160">Valige oma proovikonveierile **Väljundi andmesalve parameetri nimi**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="1c1cc-161">Valige oma proovikonveierile **Väljundi tee parameetri nimi**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="1c1cc-162">Valige ripploendist **Kliendi ID tulemustes** ühtiv atribuut, mis tuvastab kliendid, ja seejärel **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="1c1cc-163">Teil tuleb valida tuletuse väljundist atribuut, mille väärtused on sarnased kliendiolemi veeru „Kliendi ID“ omadega.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="1c1cc-164">Kui teie andmekogumis pole sellist veergu, valige atribuut, mis tuvastab rea unikaalselt.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="1c1cc-165">Töövoo käitamine</span><span class="sxs-lookup"><span data-stu-id="1c1cc-165">Run a workflow</span></span>

1. <span data-ttu-id="1c1cc-166">Valige lehel **Kohandatud mudelid** eelnevalt loodud töövoo kõrval kolm vertikaalset punkti veerus **Toimingud**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="1c1cc-167">Valige **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-167">Select **Run**.</span></span>

<span data-ttu-id="1c1cc-168">Teie töövoog käivitub automaatselt ka iga ajastatud värskendamise korral.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="1c1cc-169">Lisateave [ajastatud värskenduste häälestamise kohta](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1c1cc-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="1c1cc-170">Töövoo kustutamine</span><span class="sxs-lookup"><span data-stu-id="1c1cc-170">Delete a workflow</span></span>

1. <span data-ttu-id="1c1cc-171">Valige lehel **Kohandatud mudelid** eelnevalt loodud töövoo kõrval kolm vertikaalset punkti veerus **Toimingud**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="1c1cc-172">Valige käsk **Kustuta** ja kinnitage kustutamine.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="1c1cc-173">Teie töövoog kustutatakse.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-173">Your workflow will be deleted.</span></span> <span data-ttu-id="1c1cc-174">Töövoo loomisel loodud [olem](entities.md) jääb alles ning seda saab näha lehel **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="1c1cc-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]