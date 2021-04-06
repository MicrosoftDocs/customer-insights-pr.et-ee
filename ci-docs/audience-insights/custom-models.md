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
ms.openlocfilehash: 87fb517e9f0b380f9721f77470dceb3bcb7e5616
ms.sourcegitcommit: 55c00ea61c78db7b3b54894c01afb3246dff31c8
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/22/2021
ms.locfileid: "5700663"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="dbe36-103">Kohandatud masinõppe mudelid</span><span class="sxs-lookup"><span data-stu-id="dbe36-103">Custom machine learning models</span></span>

<span data-ttu-id="dbe36-104">Jaotises **Ärianalüüs** > **Kohandatud mudelid** saate hallata töövooge Azure'i masinõppe mudelite põhjal.</span><span class="sxs-lookup"><span data-stu-id="dbe36-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="dbe36-105">Töövood aitavad teil valida andmed, mille põhjal soovite ülevaateid luua, ja vastendada tulemused teie koondatud kliendiandmetega.</span><span class="sxs-lookup"><span data-stu-id="dbe36-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="dbe36-106">Lisateavet kohandatud masinõppemudelite loomise kohta leiate teemast [Azure'i masinaõppe põhiste mudelite kasutamine](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="dbe36-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="dbe36-107">Vastutustundlik tehisintellekt</span><span class="sxs-lookup"><span data-stu-id="dbe36-107">Responsible AI</span></span>

<span data-ttu-id="dbe36-108">Prognoosid pakuvad võimalusi klientidele paremate kogemuste loomiseks ning ärivõimaluste ja tulu parandamiseks.</span><span class="sxs-lookup"><span data-stu-id="dbe36-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="dbe36-109">Soovitame teil oma prognoosi väärtuse hindamisel võtta eetiliselt arvesse selle mõju ja kallutusi, milleni see võib viia.</span><span class="sxs-lookup"><span data-stu-id="dbe36-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="dbe36-110">Lugege lisateavet selle kohta, kuidas Microsoft [käsitleb vastutustundlikku tehisintellekti](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="dbe36-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="dbe36-111">Samuti saate tutvuda Azure'i masinõppega seotud [vastutustundliku masinõppe meetodite ja protsessidega](/azure/machine-learning/concept-responsible-ml).</span><span class="sxs-lookup"><span data-stu-id="dbe36-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dbe36-112">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="dbe36-112">Prerequisites</span></span>

- <span data-ttu-id="dbe36-113">See funktsioon toetab praegu veebiteenuseid, mis on avaldatud [masinõppe stuudio (klassikaline)](https://studio.azureml.net) ja [Azure'i masinõppe partiikonveierite](/azure/machine-learning/concept-ml-pipelines) kaudu.</span><span class="sxs-lookup"><span data-stu-id="dbe36-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="dbe36-114">Selle funktsiooni kasutamiseks on vaja Azure Data Lake Gen2 salvestuskontot, mis on seotud teie Azure Studio eksemplariga.</span><span class="sxs-lookup"><span data-stu-id="dbe36-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="dbe36-115">Lisateavet leiate teemast [Azure Data Lake Storage Gen2 salvestuskonto loomine](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="dbe36-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="dbe36-116">Azure'i masinõppe konveieritega tööruumide jaoks on teil vaja Azure'i masinõppe tööruumi omaniku või kasutajajuurdepääsu administraatori õigusi.</span><span class="sxs-lookup"><span data-stu-id="dbe36-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dbe36-117">Andmed edastatakse teie Customer Insightsi eksemplaride ja töövoos valitud Azure'i veebiteenuste või konveierite vahel.</span><span class="sxs-lookup"><span data-stu-id="dbe36-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="dbe36-118">Andmete edastamisel Azure'i teenusele veenduge, et teenus oleks konfigureeritud andmeid töötlema vajalikul viisil ja kohas, mis vastaks mis tahes juriidilistele või regulatiivsetele nõuetele nende andmete puhul teie organisatsioonis.</span><span class="sxs-lookup"><span data-stu-id="dbe36-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="dbe36-119">Uue töövoo lisamine</span><span class="sxs-lookup"><span data-stu-id="dbe36-119">Add a new workflow</span></span>

1. <span data-ttu-id="dbe36-120">Avage jaotis **Ärianalüüs** > **Kohandatud mudelid** ja valige **Uus töövoog**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="dbe36-121">Sisestage väljale **Nimi** oma kohandatud mudeli äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="dbe36-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dbe36-122">![Uue töövoo paani kuvatõmmis](media/new-workflowv2.png "Uue töövoo paani kuvatõmmis")</span><span class="sxs-lookup"><span data-stu-id="dbe36-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="dbe36-123">Valige veebiteenust sisaldav organisatsioon jaotises **Teie veebiteenust sisaldav rentnik**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="dbe36-124">Kui teie Azure'i masinõppe kordustellimus on mõnes muus rentnikus kui Customer Insights, valige suvand **Logi sisse** oma valitud organisatsiooni mandaadiga.</span><span class="sxs-lookup"><span data-stu-id="dbe36-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="dbe36-125">Valige oma veebiteenusega seotud **tööruumid**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="dbe36-126">Seal on kaks jaotist, üks Azure'i masinõppe v1 (masinõppe stuudio (klassikaline)) ja üks Azure'i masinõppe v2 (Azure'i masinõpe) jaoks.</span><span class="sxs-lookup"><span data-stu-id="dbe36-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="dbe36-127">Kui te pole kindel, milline tööruum on teie masinõppe stuudio (klassikaline) veebiteenuse jaoks õige, valige **Suvaline**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="dbe36-128">Valige masinõppe stuudio (klassikaline) veebiteenus või Azure'i masinõppe konveier ripploendis **Veebiteenus, mis sisaldab teie mudelit**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="dbe36-129">Seejärel valige suvand **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="dbe36-130">Lugege lisateavet [veebiteenuse avaldamise kohta masinõppe stuudios (klassikaline)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="dbe36-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="dbe36-131">Lugege lisateavet [konveieri avaldamise kohta Azure'i masinõppes kujundaja abil](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) või [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk) kohta.</span><span class="sxs-lookup"><span data-stu-id="dbe36-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="dbe36-132">Teie konveier peab olema avaldatud [konveieri lõpp-punktis](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="dbe36-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="dbe36-133">Valige iga **veebiteenuse sisendi** kohta sihtrühmaülevaadetest vastav **Olem** ja valige **Järgmine**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="dbe36-134">Kohandatud mudeli töövoog rakendab heuristikat veebiteenuse sisendväljade vastendamiseks olemiatribuutidele, võttes aluseks välja nime ja andmetüübi.</span><span class="sxs-lookup"><span data-stu-id="dbe36-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="dbe36-135">Kui veebiteenuse välja ei saa olemile vastendada, kuvatakse tõrge.</span><span class="sxs-lookup"><span data-stu-id="dbe36-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dbe36-136">![Konfigureeri töövoog](media/intelligence-screen2-updated.png "Konfigureeri töövoog")</span><span class="sxs-lookup"><span data-stu-id="dbe36-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="dbe36-137">Määrake etapis **Mudeli väljundi parameetrid** järgmised atribuudid.</span><span class="sxs-lookup"><span data-stu-id="dbe36-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="dbe36-138">Masinõppe stuudio (klassikaline)</span><span class="sxs-lookup"><span data-stu-id="dbe36-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="dbe36-139">Sisestage väljundi **Olemi nimi**, millesse soovite veebiteenuse väljundi tulemusi salvestada.</span><span class="sxs-lookup"><span data-stu-id="dbe36-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="dbe36-140">Azure’i masinõpe</span><span class="sxs-lookup"><span data-stu-id="dbe36-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="dbe36-141">Sisestage väljundi **Olemi nimi**, millesse soovite konveieri väljundi tulemusi salvestada.</span><span class="sxs-lookup"><span data-stu-id="dbe36-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="dbe36-142">Valige oma partiikonveieri ripploendist **Väljundi andmesalve parameetri nimi**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="dbe36-143">Valige oma partiikonveieri ripploendist **Väljundi tee parameetri nimi**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="dbe36-144">![Mudeli väljundi parameetri paan](media/intelligence-screen3-outputparameters.png "Mudeli väljundi parameetri paan")</span><span class="sxs-lookup"><span data-stu-id="dbe36-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="dbe36-145">Valige ripploendist **Kliendi ID tulemustes** ühtiv atribuut, mis tuvastab kliendid, ja seejärel **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-145">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dbe36-146">![Tulemuste seostamine paanil „Kliendiandmed“](media/intelligence-screen4-relatetocustomer.png "Tulemuste seostamine paanil „Kliendiandmed“")</span><span class="sxs-lookup"><span data-stu-id="dbe36-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="dbe36-147">Teile kuvatakse töövoo üksikasjadega kuva **Töövoog salvestatud**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="dbe36-148">Kui olete konfigureerinud Azure'i masinõppe konveieri jaoks töövoo, lisatakse sihtrühmaülevaated tööruumi, mis sisaldab konveierit.</span><span class="sxs-lookup"><span data-stu-id="dbe36-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="dbe36-149">Sihtrühmaülevaadetele antakse Azure'i tööruumis roll **Kaasautor**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="dbe36-150">Valige nupp **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-150">Select **Done**.</span></span>

1. <span data-ttu-id="dbe36-151">Nüüd saate töövoo käivitada lehel **Kohandatud mudelid**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="dbe36-152">Töövoo redigeerimine</span><span class="sxs-lookup"><span data-stu-id="dbe36-152">Edit a workflow</span></span>

1. <span data-ttu-id="dbe36-153">Valige lehel **Kohandatud mudelid** eelnevalt loodud töövoo kõrval kolm vertikaalset punkti veerus **Toimingud** ja valige suvand **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="dbe36-154">Saate värskendada oma töövoo nime väljal **Kuvatav nimi**, kuid te ei saa muuta konfigureeritud veebiteenust või konveierit.</span><span class="sxs-lookup"><span data-stu-id="dbe36-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="dbe36-155">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-155">Select **Next**.</span></span>

1. <span data-ttu-id="dbe36-156">Iga **veebiteenuse sisendi** korral saate värskendada sihtrühmaülevaadetes ühtivat **olemit**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="dbe36-157">Seejärel valige suvand **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="dbe36-158">Määrake etapis **Mudeli väljundi parameetrid** järgmised atribuudid.</span><span class="sxs-lookup"><span data-stu-id="dbe36-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="dbe36-159">Masinõppe stuudio (klassikaline)</span><span class="sxs-lookup"><span data-stu-id="dbe36-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="dbe36-160">Sisestage väljundi **Olemi nimi**, millesse soovite veebiteenuse väljundi tulemusi salvestada.</span><span class="sxs-lookup"><span data-stu-id="dbe36-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="dbe36-161">Azure’i masinõpe</span><span class="sxs-lookup"><span data-stu-id="dbe36-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="dbe36-162">Sisestage väljundi **Olemi nimi**, millesse soovite konveieri väljundi tulemusi salvestada.</span><span class="sxs-lookup"><span data-stu-id="dbe36-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="dbe36-163">Valige oma proovikonveierile **Väljundi andmesalve parameetri nimi**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="dbe36-164">Valige oma proovikonveierile **Väljundi tee parameetri nimi**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="dbe36-165">Valige ripploendist **Kliendi ID tulemustes** ühtiv atribuut, mis tuvastab kliendid, ja seejärel **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-165">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="dbe36-166">Valige tuletuse väljundist atribuut, mille väärtused on sarnased kliendiolemi veeru „Kliendi ID“ omadega.</span><span class="sxs-lookup"><span data-stu-id="dbe36-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="dbe36-167">Kui teie andmekogumis pole sellist veergu, valige atribuut, mis tuvastab rea unikaalselt.</span><span class="sxs-lookup"><span data-stu-id="dbe36-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="dbe36-168">Töövoo käitamine</span><span class="sxs-lookup"><span data-stu-id="dbe36-168">Run a workflow</span></span>

1. <span data-ttu-id="dbe36-169">Valige lehel **Kohandatud mudelid** eelnevalt loodud töövoo kõrval kolm vertikaalset punkti veerus **Toimingud**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="dbe36-170">Valige **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-170">Select **Run**.</span></span>

<span data-ttu-id="dbe36-171">Teie töövoog käivitub automaatselt ka iga ajastatud värskendamise korral.</span><span class="sxs-lookup"><span data-stu-id="dbe36-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="dbe36-172">Lisateave [ajastatud värskenduste häälestamise kohta](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dbe36-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="dbe36-173">Töövoo kustutamine</span><span class="sxs-lookup"><span data-stu-id="dbe36-173">Delete a workflow</span></span>

1. <span data-ttu-id="dbe36-174">Valige lehel **Kohandatud mudelid** eelnevalt loodud töövoo kõrval kolm vertikaalset punkti veerus **Toimingud**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="dbe36-175">Valige käsk **Kustuta** ja kinnitage kustutamine.</span><span class="sxs-lookup"><span data-stu-id="dbe36-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="dbe36-176">Teie töövoog kustutatakse.</span><span class="sxs-lookup"><span data-stu-id="dbe36-176">Your workflow will be deleted.</span></span> <span data-ttu-id="dbe36-177">Töövoo loomisel loodud [olem](entities.md) jääb alles ning seda saab näha lehel **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="dbe36-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="dbe36-178">Tulemid</span><span class="sxs-lookup"><span data-stu-id="dbe36-178">Results</span></span>

<span data-ttu-id="dbe36-179">Töövoo tulemused talletatakse mudeli väljundparameetri sisendi ajal konfigureeritud olemis.</span><span class="sxs-lookup"><span data-stu-id="dbe36-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="dbe36-180">Neile andmetele pääsete juurde [olemite lehelt](entities.md) või [API-juurdepääsuga](apis.md).</span><span class="sxs-lookup"><span data-stu-id="dbe36-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="dbe36-181">API-juurdepääs</span><span class="sxs-lookup"><span data-stu-id="dbe36-181">API Access</span></span>

<span data-ttu-id="dbe36-182">Kindla OData päringu andmete toomiseks kohandatud mudeli olemist kasutage järgmist vormingut.</span><span class="sxs-lookup"><span data-stu-id="dbe36-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="dbe36-183">Asendage `<your instance id>` oma Customer Insightsi keskkonna ID-ga, mille leiate brauseri aadressiribalt, kui avate Customer Insightsi.</span><span class="sxs-lookup"><span data-stu-id="dbe36-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="dbe36-184">Asendage `<custom model output entity>` kohandatud mudeli konfiguratsiooni mudeliväljundiparameetrite etapil esitatud olemi nimega.</span><span class="sxs-lookup"><span data-stu-id="dbe36-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="dbe36-185">Asendage `<guid value>` selle kliendi ID-ga, mille kirjele soovite juurde pääseda.</span><span class="sxs-lookup"><span data-stu-id="dbe36-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="dbe36-186">Tavaliselt leiate selle ID [kliendiprofiilide lehel](customer-profiles.md)väljalt Kliendi ID.</span><span class="sxs-lookup"><span data-stu-id="dbe36-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="dbe36-187">Korduma kippuvad küsimused</span><span class="sxs-lookup"><span data-stu-id="dbe36-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="dbe36-188">Miks ei saa kohandatud mudeli töövoo seadistamisel konveierit vaadata?</span><span class="sxs-lookup"><span data-stu-id="dbe36-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="dbe36-189">Selle probleemi põhjuseks on sageli konveieri konfiguratsiooniprobleem.</span><span class="sxs-lookup"><span data-stu-id="dbe36-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="dbe36-190">Veenduge, [et sisendparameeter oleks](azure-machine-learning-experiments.md#dataset-configuration)konfigureeritud ning konfigureeritud on ka [väljundandmesalve ja tee parameetrid](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).</span><span class="sxs-lookup"><span data-stu-id="dbe36-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="dbe36-191">Mida tähendab tõrge „Ei saanud ärianalüüsi töövoogu salvestada“?</span><span class="sxs-lookup"><span data-stu-id="dbe36-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="dbe36-192">Kasutajad näevad seda tõrketeadet tavaliselt juhul, kui neil pole tööruumis omaniku- või kasutajajuurdepääsu administraatori õigusi.</span><span class="sxs-lookup"><span data-stu-id="dbe36-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="dbe36-193">Kasutajal on vaja õiguste kõrgemat taset, et võimaldada Customer Insightsil töövoogu teenusena töödelda, mitte kasutada kasutaja identimisteavet töövoo järgmisteks töövoogudeks.</span><span class="sxs-lookup"><span data-stu-id="dbe36-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
