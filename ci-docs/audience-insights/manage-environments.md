---
title: Keskkondade loomine ja haldamine
description: Siit leiate teavet selle kohta, kuidas teenuse kasutamiseks registreeruda ja kuidas keskkondasid hallata.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598288"
---
# <a name="manage-environments"></a><span data-ttu-id="b86f6-103">Keskkondade haldamine</span><span class="sxs-lookup"><span data-stu-id="b86f6-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b86f6-104">Selles artiklis kirjeldatakse, kuidas luua uut organisatsiooni ja kuidas keskkonda ette valmistada.</span><span class="sxs-lookup"><span data-stu-id="b86f6-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="b86f6-105">Registreerumine ja organisatsiooni loomine</span><span class="sxs-lookup"><span data-stu-id="b86f6-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="b86f6-106">Minge veebisaidile [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="b86f6-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="b86f6-107">Seejärel valige suvand **Alustamine**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="b86f6-108">Valige eelistatud registreerimisstsenaarium ja vastav link.</span><span class="sxs-lookup"><span data-stu-id="b86f6-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="b86f6-109">Nõustuge tingimustega ja valige suvand **Edasi**, et alustada organisatsiooni loomisega.</span><span class="sxs-lookup"><span data-stu-id="b86f6-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="b86f6-110">Kui keskkond on loodud, suunatakse teid lehele [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="b86f6-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="b86f6-111">Saate kasutada demokeskkonda rakendusega tutvumiseks või luua uue keskkonna järgmises jaotises kirjeldatud juhiste järgi.</span><span class="sxs-lookup"><span data-stu-id="b86f6-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="b86f6-112">Pärast keskkonna sätete määratlemist valige **Loo**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="b86f6-113">Teid logitakse sisse pärast seda, kui keskkonna loomine õnnestus.</span><span class="sxs-lookup"><span data-stu-id="b86f6-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="b86f6-114">Keskkonna loomine olemasolevasse organisatsiooni</span><span class="sxs-lookup"><span data-stu-id="b86f6-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="b86f6-115">Uue keskkonna loomiseks on kaks võimalust.</span><span class="sxs-lookup"><span data-stu-id="b86f6-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="b86f6-116">Saate määrata kas täiesti uue konfiguratsiooni või kopeerida teatud konfiguratsioonisätteid olemasolevast keskkonnast.</span><span class="sxs-lookup"><span data-stu-id="b86f6-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="b86f6-117">Uue keskkonna loomine.</span><span class="sxs-lookup"><span data-stu-id="b86f6-117">To create an environment:</span></span>

1. <span data-ttu-id="b86f6-118">Valige rakenduse päises valija **Environment** (Keskkond).</span><span class="sxs-lookup"><span data-stu-id="b86f6-118">Select the **Environment** picker in the header of the app.</span></span>

1. <span data-ttu-id="b86f6-119">Tehke valik **Uus**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-119">Select **New**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b86f6-120">![Keskkonnasätted](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="b86f6-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="b86f6-121">Valige dialoogist **Uue keskkonna loomine** suvand **Uus keskkond**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="b86f6-122">Kui soovite [praegusest keskkonnast andmeid kopeerida](#additional-considerations-for-copy-configuration-preview), valige suvand **Kopeeri olemasolevast keskkonnast**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="b86f6-123">Näete teie ettevõtte kõigi saadaolevate keskkondade loendit, kust saate andmeid kopeerida.</span><span class="sxs-lookup"><span data-stu-id="b86f6-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="b86f6-124">Esitage järgmised andmed.</span><span class="sxs-lookup"><span data-stu-id="b86f6-124">Provide the following details:</span></span>
   - <span data-ttu-id="b86f6-125">**Nimi**: selle keskkonna nimi.</span><span class="sxs-lookup"><span data-stu-id="b86f6-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="b86f6-126">Olemasolevast keskkonnast kopeerides on see väli juba täidetud, kuid saate seda muuta.</span><span class="sxs-lookup"><span data-stu-id="b86f6-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="b86f6-127">**Piirkond**: piirkond, kus teenus juurutatakse ja majutatakse.</span><span class="sxs-lookup"><span data-stu-id="b86f6-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="b86f6-128">**Tüüp**: valige, kas soovite luua töö- või liivakastikeskkonna.</span><span class="sxs-lookup"><span data-stu-id="b86f6-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="b86f6-129">Soovi korral saate valida ka suvandi **Täpsemad sätted**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="b86f6-130">**Salvesta kõik andmed**: määrab, kuhu soovite Customer Insightsist loodud väljundandmed talletada.</span><span class="sxs-lookup"><span data-stu-id="b86f6-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="b86f6-131">Selleks on kaks võimalust: **Customer Insightsi salvestusruum** (Customer Insightsi meeskonna hallatav Azure Data Lake) ja **Azure Data Lake Storage Gen2** (teie isiklik Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="b86f6-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="b86f6-132">Vaikimisi on valitud Customer Insightsi salvestusruumi suvand.</span><span class="sxs-lookup"><span data-stu-id="b86f6-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b86f6-133">Andmete salvestamisel teenusesse Azure Data Lake Storage nõustute, et andmed edastatakse ja talletatakse selle Azure'i salvestusruumi konto asjakohases geograafilises asukohas, mis võib erineda rakendusse Dynamics 365 Customer Insights talletatud andmete salvestuskohast.</span><span class="sxs-lookup"><span data-stu-id="b86f6-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="b86f6-134">Lisateavet leiate Microsofti usalduskeskusest.</span><span class="sxs-lookup"><span data-stu-id="b86f6-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="b86f6-135">Praegu salvestatakse sisestatud olemid alati Customer Insightsi hallatavasse andmejärve.</span><span class="sxs-lookup"><span data-stu-id="b86f6-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="b86f6-136">Toetame ainult Azure Data Lake Gen2 salvestuskontosid, mis asuvad samas Azure'i regioonis, mille valisite keskkonna loomisel.</span><span class="sxs-lookup"><span data-stu-id="b86f6-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="b86f6-137">Toetame ainult salvestuskontosid, kus on lubatud Azure Data Lake Gen 2 hierarhiline nimeruum (HNS).</span><span class="sxs-lookup"><span data-stu-id="b86f6-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="b86f6-138">Azure Data Lake Storage Gen2 korral saate autentimiseks valida ressursipõhise ja tellimusepõhise valiku vahel.</span><span class="sxs-lookup"><span data-stu-id="b86f6-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="b86f6-139">Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="b86f6-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="b86f6-140">**Konteineri** nime ei saa muuta ja see on „customerinsights“.</span><span class="sxs-lookup"><span data-stu-id="b86f6-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="b86f6-141">Kui soovite kasutada [ennustamise](predictions.md) funktsiooni või konfigureerida andmete jagamist Microsoft Dataverse rakenduste ja lahendustega, sisestage Microsoft Dataverse keskkonna URL jaotises **Andmete ühiskasutuse konfigureerimine rakendusega Microsoft Dataverse ja lubage täiendavad** võimalused.</span><span class="sxs-lookup"><span data-stu-id="b86f6-141">If you want to use [predictions](predictions.md) or configure data sharing with applications and solutions based on Microsoft Dataverse, provide the Microsoft Dataverse environment URL under **Configure data sharing with Microsoft Dataverse and enable additional capabilities**.</span></span> <span data-ttu-id="b86f6-142">Valige suvand **Enable data sharing** (Luba andmete ühiskasutus), et jagada Customer Insightsi väljundandmeid Microsoft Dataverse Managed Data Lake hallatava andmejärvega.</span><span class="sxs-lookup"><span data-stu-id="b86f6-142">Select **Enable data sharing** to share Customer Insights output data with a Microsoft Dataverse Managed Data Lake.</span></span>

     > [!NOTE]
     > - <span data-ttu-id="b86f6-143">Andmete jagamine rakendusega Microsoft Dataverse Managed Data Lake täna ei toetata, kui salvestate kõik andmed enda andmejärve Azure Data Lake Storage.</span><span class="sxs-lookup"><span data-stu-id="b86f6-143">Data sharing with Microsoft Dataverse Managed Data Lake is currently not supported when you save all data to your own Azure Data Lake Storage.</span></span>
     > - <span data-ttu-id="b86f6-144">[Puuduvate väärtuste ennustust olemis](predictions.md) ei toetata praegu, kui lubate andmete ühiskasutust rakendusega Microsoft Dataverse Managed Data Lake.</span><span class="sxs-lookup"><span data-stu-id="b86f6-144">[Prediction of missing values in an entity](predictions.md) is not currently supported when you enable data sharing with Microsoft Dataverse Managed Data Lake.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="b86f6-145">![Konfigureerimissuvandid andmete ühiskasutuse lubamiseks Microsoft Dataverse abil](media/Datasharing-with-DataverseMDL.png)</span><span class="sxs-lookup"><span data-stu-id="b86f6-145">![Configuration options to enable data sharing with Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)</span></span>

   <span data-ttu-id="b86f6-146">Protsesside käitamisel, näiteks andmete valmendamisel või segmendi loomisel, luuakse asjaomased kaustad eespool määratud salvestuskontol.</span><span class="sxs-lookup"><span data-stu-id="b86f6-146">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="b86f6-147">Luuakse andmefailid ja model.json failid ning need lisatakse teie käitatavate protsesside põhjal vastavatesse alamkaustadesse.</span><span class="sxs-lookup"><span data-stu-id="b86f6-147">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="b86f6-148">Kui loote mitu Customer Insightsi keskkonda ja soovite salvestada väljundolemid nendest keskkondadest oma salvestuskontole, luuakse eraldi kaustad iga keskkonna jaoks, mille konteineris on ci_<environmentid>.</span><span class="sxs-lookup"><span data-stu-id="b86f6-148">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="b86f6-149">Lisakaalutlused konfiguratsiooni kopeerimise puhul (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="b86f6-149">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="b86f6-150">Kopeeritakse järgmised konfiguratsioonisätted.</span><span class="sxs-lookup"><span data-stu-id="b86f6-150">The following configuration settings are copied:</span></span>

- <span data-ttu-id="b86f6-151">Funktsiooni konfiguratsioonid</span><span class="sxs-lookup"><span data-stu-id="b86f6-151">Feature configurations</span></span>
- <span data-ttu-id="b86f6-152">Valmendatud/imporditud andmeallikad</span><span class="sxs-lookup"><span data-stu-id="b86f6-152">Ingested/imported data sources</span></span>
- <span data-ttu-id="b86f6-153">Andmete ühtlustamiskonfiguratsioon (kaardistamine, vastendamine, ühendamine)</span><span class="sxs-lookup"><span data-stu-id="b86f6-153">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="b86f6-154">Segmendid</span><span class="sxs-lookup"><span data-stu-id="b86f6-154">Segments</span></span>
- <span data-ttu-id="b86f6-155">Meetmed</span><span class="sxs-lookup"><span data-stu-id="b86f6-155">Measures</span></span>
- <span data-ttu-id="b86f6-156">Seosed</span><span class="sxs-lookup"><span data-stu-id="b86f6-156">Relationships</span></span>
- <span data-ttu-id="b86f6-157">Tegevused </span><span class="sxs-lookup"><span data-stu-id="b86f6-157">Activities</span></span>
- <span data-ttu-id="b86f6-158">Otsingu ja filtri register</span><span class="sxs-lookup"><span data-stu-id="b86f6-158">Search & filter Index</span></span>
- <span data-ttu-id="b86f6-159">Ekspordisihtkohad</span><span class="sxs-lookup"><span data-stu-id="b86f6-159">Export destinations</span></span>
- <span data-ttu-id="b86f6-160">Ajastatud värskendamine</span><span class="sxs-lookup"><span data-stu-id="b86f6-160">Scheduled refresh</span></span>
- <span data-ttu-id="b86f6-161">Rikastamised</span><span class="sxs-lookup"><span data-stu-id="b86f6-161">Enrichments</span></span>
- <span data-ttu-id="b86f6-162">Mudeli haldus</span><span class="sxs-lookup"><span data-stu-id="b86f6-162">Model management</span></span>
- <span data-ttu-id="b86f6-163">Rolli määramised</span><span class="sxs-lookup"><span data-stu-id="b86f6-163">Role assignments</span></span>

<span data-ttu-id="b86f6-164">Järgmisi sätteid *ei* kopeerita.</span><span class="sxs-lookup"><span data-stu-id="b86f6-164">The following settings are *not* copied:</span></span>

- <span data-ttu-id="b86f6-165">Kliendiprofiilid.</span><span class="sxs-lookup"><span data-stu-id="b86f6-165">Customer profiles.</span></span>
- <span data-ttu-id="b86f6-166">Andmeallika identimisteave.</span><span class="sxs-lookup"><span data-stu-id="b86f6-166">Data source credentials.</span></span> <span data-ttu-id="b86f6-167">Peate sisestama identimisteabe iga andmeallika jaoks ja värskendama andmeallikaid käsitsi.</span><span class="sxs-lookup"><span data-stu-id="b86f6-167">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="b86f6-168">Andmeallikad kaustast Ühine andmemudel ja Common Data Service’i hallatavast järvest.</span><span class="sxs-lookup"><span data-stu-id="b86f6-168">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="b86f6-169">Peate need andmeallikad looma käsitsi sama nimega kui lähtekeskkond.</span><span class="sxs-lookup"><span data-stu-id="b86f6-169">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="b86f6-170">Keskkonna kopeerimisel näete kinnitusteadet, et loodi uus keskkond.</span><span class="sxs-lookup"><span data-stu-id="b86f6-170">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="b86f6-171">Andmeallikate loendi nägemiseks valige suvand **Ava andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-171">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="b86f6-172">Kõik andmeallikad kuvavad olekut **Mandaat nõutav**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-172">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="b86f6-173">Redigeerige andmeallikaid ja sisestage nende värskendamiseks identimisteave.</span><span class="sxs-lookup"><span data-stu-id="b86f6-173">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b86f6-174">![Andmeallikad kopeeritud](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="b86f6-174">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="b86f6-175">Pärast andmeallikate värskendamist avage jaotis **Andme** > **Ühendamine**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-175">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="b86f6-176">Siit leiate lähtekeskkonna sätted.</span><span class="sxs-lookup"><span data-stu-id="b86f6-176">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="b86f6-177">Redigeerige neid vastavalt vajadusele või valige **Käivita**, et käivitada andmete ühendamise protsess ja luua ühtne kliendi olem.</span><span class="sxs-lookup"><span data-stu-id="b86f6-177">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="b86f6-178">Kui andmete ühendamine on lõpetatud, avage **Meetmed** ja **Segmendid**, et neid samuti värskendada.</span><span class="sxs-lookup"><span data-stu-id="b86f6-178">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="b86f6-179">Olemasoleva keskkonna redigeerimine</span><span class="sxs-lookup"><span data-stu-id="b86f6-179">Edit an existing environment</span></span>

<span data-ttu-id="b86f6-180">Saate muuta olemasolevate keskkondade teatud üksikasju.</span><span class="sxs-lookup"><span data-stu-id="b86f6-180">You can edit some of the details of existing environments.</span></span>

1.  <span data-ttu-id="b86f6-181">Valige rakenduse päises valija **Environment** (Keskkond).</span><span class="sxs-lookup"><span data-stu-id="b86f6-181">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="b86f6-182">Valige ikoon **Edit** (Redigeeri).</span><span class="sxs-lookup"><span data-stu-id="b86f6-182">Select the **Edit** icon.</span></span>

3. <span data-ttu-id="b86f6-183">Väljal **Edit environment** (Redigeeri keskkonda) saate värskendada keskkonna välja **Display name** (Kuva nimi), kuid te ei saa muuta suvandeid **Region** (Regioon) või **Type** (Tüüp).</span><span class="sxs-lookup"><span data-stu-id="b86f6-183">In the **Edit environment** box, you can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="b86f6-184">Kui keskkonna andmete salvestusruumiks on konfigureeritud Azure Data Lake Storage Gen2, siis saate uuendada suvandit **Kontovõti**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-184">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="b86f6-185">Kuid te ei saa muuta **Ettevõtte nime** ja **Konteineri** nime.</span><span class="sxs-lookup"><span data-stu-id="b86f6-185">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="b86f6-186">Soovi korral saate kasutada kontovõtmepõhise ühenduse asemel ressursipõhist või tellimusepõhist ühendust.</span><span class="sxs-lookup"><span data-stu-id="b86f6-186">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="b86f6-187">Pärast selle tegemist ei saa te värskenduse järel hakata uuesti kontovõtit kasutama.</span><span class="sxs-lookup"><span data-stu-id="b86f6-187">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="b86f6-188">Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="b86f6-188">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="b86f6-189">Ühenduse värskendamisel ei saa te muuta **konteineri** teavet.</span><span class="sxs-lookup"><span data-stu-id="b86f6-189">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="b86f6-190">Olemasoleva keskkonna lähtestamine</span><span class="sxs-lookup"><span data-stu-id="b86f6-190">Reset an existing environment</span></span>

<span data-ttu-id="b86f6-191">Kui soovite kustutada kõik konfiguratsioonid ja eemaldada valmendatud andmed, saate keskkonna lähtestada nii, et see oleks täiesti tühi.</span><span class="sxs-lookup"><span data-stu-id="b86f6-191">As an administrator, you can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="b86f6-192">Valige rakenduse päises valija **Environment** (Keskkond).</span><span class="sxs-lookup"><span data-stu-id="b86f6-192">Select the **Environment** picker in the header of the app.</span></span> 

2.  <span data-ttu-id="b86f6-193">Valige keskkond, mille soovite lähtestada, ja valige kolmikpunkt **...**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-193">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="b86f6-194">Valige suvand **Reset** (Lähtesta).</span><span class="sxs-lookup"><span data-stu-id="b86f6-194">Choose the **Reset** option.</span></span> 

4.  <span data-ttu-id="b86f6-195">Kustutamise kinnitamiseks sisestage keskkonna nimi ja valige **Lähtesta**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-195">To confirm the deletion, enter the environment name and select **Reset**.</span></span>

## <a name="delete-an-existing-environment-available-only-for-admins"></a><span data-ttu-id="b86f6-196">Kustuta olemasolev keskkond (saadaval ainult administraatoritele)</span><span class="sxs-lookup"><span data-stu-id="b86f6-196">Delete an existing environment (available only for admins)</span></span>

<span data-ttu-id="b86f6-197">Administraatorina saate kustutada halduskeskkonna.</span><span class="sxs-lookup"><span data-stu-id="b86f6-197">As an administrator, you can delete an environment you administer.</span></span>

1.  <span data-ttu-id="b86f6-198">Valige rakenduse päises valija **Environment** (Keskkond).</span><span class="sxs-lookup"><span data-stu-id="b86f6-198">Select the **Environment** picker in the header of the app.</span></span>

2.  <span data-ttu-id="b86f6-199">Valige keskkond, mille soovite lähtestada, ja valige kolmikpunkt **...**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-199">Select the environment you want to reset and select the ellipsis **...**.</span></span> 

3. <span data-ttu-id="b86f6-200">Valige suvand **Delete** (Kustuta).</span><span class="sxs-lookup"><span data-stu-id="b86f6-200">Choose the **Delete** option.</span></span> 

4.  <span data-ttu-id="b86f6-201">Kustutamise kinnitamiseks sisestage soovitud keskkonna nimi ja valige **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="b86f6-201">To confirm the deletion, enter the environment name and select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]