---
title: Keskkondade loomine ja haldamine
description: Siit leiate teavet selle kohta, kuidas teenuse kasutamiseks registreeruda ja kuidas keskkondasid hallata.
ms.date: 11/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
ms.reviewer: nimagen
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 010336445d0825a7ff82d1b7a65702fc12245788
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644128"
---
# <a name="manage-environments"></a><span data-ttu-id="52a81-103">Keskkondade haldamine</span><span class="sxs-lookup"><span data-stu-id="52a81-103">Manage environments</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="52a81-104">Selles artiklis kirjeldatakse, kuidas luua uut organisatsiooni ja kuidas keskkonda ette valmistada.</span><span class="sxs-lookup"><span data-stu-id="52a81-104">This article explains how to create a new organization and how to provision an environment.</span></span>

## <a name="sign-up-and-create-an-organization"></a><span data-ttu-id="52a81-105">Registreerumine ja organisatsiooni loomine</span><span class="sxs-lookup"><span data-stu-id="52a81-105">Sign up and create an organization</span></span>

1. <span data-ttu-id="52a81-106">Minge veebisaidile [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).</span><span class="sxs-lookup"><span data-stu-id="52a81-106">Go to the [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/) website.</span></span>

2. <span data-ttu-id="52a81-107">Seejärel valige suvand **Alustamine**.</span><span class="sxs-lookup"><span data-stu-id="52a81-107">Select **Get Started**.</span></span>

3. <span data-ttu-id="52a81-108">Valige eelistatud registreerimisstsenaarium ja vastav link.</span><span class="sxs-lookup"><span data-stu-id="52a81-108">Choose your preferred sign-up scenario and select the corresponding link.</span></span>

4. <span data-ttu-id="52a81-109">Nõustuge tingimustega ja valige suvand **Edasi**, et alustada organisatsiooni loomisega.</span><span class="sxs-lookup"><span data-stu-id="52a81-109">Accept the terms and conditions and select **Continue** to start creating the organization.</span></span>

5. <span data-ttu-id="52a81-110">Kui keskkond on loodud, suunatakse teid lehele [Customer Insights](https://home.ci.ai.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="52a81-110">After the environment is created, you'll be redirected to [Customer Insights](https://home.ci.ai.dynamics.com).</span></span>

6. <span data-ttu-id="52a81-111">Saate kasutada demokeskkonda rakendusega tutvumiseks või luua uue keskkonna järgmises jaotises kirjeldatud juhiste järgi.</span><span class="sxs-lookup"><span data-stu-id="52a81-111">Use the demo environment to explore the app, or create a new environment by following the steps in the next section.</span></span>

7. <span data-ttu-id="52a81-112">Pärast keskkonna sätete määratlemist valige **Loo**.</span><span class="sxs-lookup"><span data-stu-id="52a81-112">After specifying the environment settings, select **Create**.</span></span>

8. <span data-ttu-id="52a81-113">Teid logitakse sisse pärast seda, kui keskkonna loomine õnnestus.</span><span class="sxs-lookup"><span data-stu-id="52a81-113">You'll be signed in after the environment was created successfully.</span></span>

## <a name="create-an-environment-in-an-existing-organization"></a><span data-ttu-id="52a81-114">Keskkonna loomine olemasolevasse organisatsiooni</span><span class="sxs-lookup"><span data-stu-id="52a81-114">Create an environment in an existing organization</span></span>

<span data-ttu-id="52a81-115">Uue keskkonna loomiseks on kaks võimalust.</span><span class="sxs-lookup"><span data-stu-id="52a81-115">There are two ways to create a new environment.</span></span> <span data-ttu-id="52a81-116">Saate määrata kas täiesti uue konfiguratsiooni või kopeerida teatud konfiguratsioonisätteid olemasolevast keskkonnast.</span><span class="sxs-lookup"><span data-stu-id="52a81-116">You can either specify an entirely new configuration, or you can copy some configuration settings from an existing environment.</span></span>

<span data-ttu-id="52a81-117">Uue keskkonna loomine.</span><span class="sxs-lookup"><span data-stu-id="52a81-117">To create an environment:</span></span>

1. <span data-ttu-id="52a81-118">Valige rakenduse päises sümbol **Sätted**.</span><span class="sxs-lookup"><span data-stu-id="52a81-118">Select the **Settings** symbol in the header of the app.</span></span>

1. <span data-ttu-id="52a81-119">Valige suvand **Uus keskkond**.</span><span class="sxs-lookup"><span data-stu-id="52a81-119">Select **New environment**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="52a81-120">![Keskkonnasätted](media/environment-settings-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="52a81-120">![Environment settings](media/environment-settings-dialog.png)</span></span>

1. <span data-ttu-id="52a81-121">Valige dialoogist **Uue keskkonna loomine** suvand **Uus keskkond**.</span><span class="sxs-lookup"><span data-stu-id="52a81-121">In the **Create new environment** dialog, select **New environment**.</span></span>

   <span data-ttu-id="52a81-122">Kui soovite [praegusest keskkonnast andmeid kopeerida](#additional-considerations-for-copy-configuration-preview), valige suvand **Kopeeri olemasolevast keskkonnast**.</span><span class="sxs-lookup"><span data-stu-id="52a81-122">If you want to [copy data from the current environment](#additional-considerations-for-copy-configuration-preview), select **Copy from existing environment**.</span></span> <span data-ttu-id="52a81-123">Näete teie ettevõtte kõigi saadaolevate keskkondade loendit, kust saate andmeid kopeerida.</span><span class="sxs-lookup"><span data-stu-id="52a81-123">You'll see a list of all available environments in your organization where you can copy data from.</span></span>

1. <span data-ttu-id="52a81-124">Esitage järgmised andmed.</span><span class="sxs-lookup"><span data-stu-id="52a81-124">Provide the following details:</span></span>
   - <span data-ttu-id="52a81-125">**Nimi**: selle keskkonna nimi.</span><span class="sxs-lookup"><span data-stu-id="52a81-125">**Name**: The name for this environment.</span></span> <span data-ttu-id="52a81-126">Olemasolevast keskkonnast kopeerides on see väli juba täidetud, kuid saate seda muuta.</span><span class="sxs-lookup"><span data-stu-id="52a81-126">This field is already filled in if you've copied an existing environment, but you can change it.</span></span>
   - <span data-ttu-id="52a81-127">**Piirkond**: piirkond, kus teenus juurutatakse ja majutatakse.</span><span class="sxs-lookup"><span data-stu-id="52a81-127">**Region**: The region into which the service is deployed and hosted.</span></span>
   - <span data-ttu-id="52a81-128">**Tüüp**: valige, kas soovite luua töö- või liivakastikeskkonna.</span><span class="sxs-lookup"><span data-stu-id="52a81-128">**Type**: Select whether you want to create a Production or Sandbox environment.</span></span>

2. <span data-ttu-id="52a81-129">Soovi korral saate valida ka suvandi **Täpsemad sätted**.</span><span class="sxs-lookup"><span data-stu-id="52a81-129">Optionally, you can select **Advanced settings**:</span></span>

   - <span data-ttu-id="52a81-130">**Salvesta kõik andmed**: määrab, kuhu soovite Customer Insightsist loodud väljundandmed talletada.</span><span class="sxs-lookup"><span data-stu-id="52a81-130">**Save all data to**: Specifies where you want to store the output data generated from Customer Insights.</span></span> <span data-ttu-id="52a81-131">Selleks on kaks võimalust: **Customer Insightsi salvestusruum** (Customer Insightsi meeskonna hallatav Azure Data Lake) ja **Azure Data Lake Storage Gen2** (teie isiklik Azure Data Lake Storage).</span><span class="sxs-lookup"><span data-stu-id="52a81-131">You'll have two options: **Customer Insights storage** (an Azure Data Lake managed by the Customer Insights team) and **Azure Data Lake Storage Gen2** (your own Azure Data Lake Storage).</span></span> <span data-ttu-id="52a81-132">Vaikimisi on valitud Customer Insightsi salvestusruumi suvand.</span><span class="sxs-lookup"><span data-stu-id="52a81-132">By default, the Customer Insights storage option is selected.</span></span>

   > [!NOTE]
   > <span data-ttu-id="52a81-133">Andmete salvestamisel teenusesse Azure Data Lake Storage nõustute, et andmed edastatakse ja talletatakse selle Azure'i salvestusruumi konto asjakohases geograafilises asukohas, mis võib erineda rakendusse Dynamics 365 Customer Insights talletatud andmete salvestuskohast.</span><span class="sxs-lookup"><span data-stu-id="52a81-133">By saving data to Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="52a81-134">Lisateavet leiate Microsofti usalduskeskusest.</span><span class="sxs-lookup"><span data-stu-id="52a81-134">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)
   >
   > <span data-ttu-id="52a81-135">Praegu salvestatakse sisestatud olemid alati Customer Insightsi hallatavasse andmejärve.</span><span class="sxs-lookup"><span data-stu-id="52a81-135">Currently, ingested entities are always stored in the Customer Insights managed data lake.</span></span>
   > <span data-ttu-id="52a81-136">Toetame ainult Azure Data Lake Gen2 salvestuskontosid, mis asuvad samas Azure'i regioonis, mille valisite keskkonna loomisel.</span><span class="sxs-lookup"><span data-stu-id="52a81-136">We support only Azure Data Lake Gen2 storage accounts from the same Azure region you selected when creating the environment.</span></span>
   > <span data-ttu-id="52a81-137">Toetame ainult salvestuskontosid, kus on lubatud Azure Data Lake Gen 2 hierarhiline nimeruum (HNS).</span><span class="sxs-lookup"><span data-stu-id="52a81-137">We support only Azure Data Lake Gen2 Hierarchical Name Space (HNS) enabled storage accounts.</span></span>

   - <span data-ttu-id="52a81-138">Azure Data Lake Storage Gen2 korral saate autentimiseks valida ressursipõhise ja tellimusepõhise valiku vahel.</span><span class="sxs-lookup"><span data-stu-id="52a81-138">For the Azure Data Lake Storage Gen2 option, you can choose between a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="52a81-139">Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="52a81-139">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="52a81-140">**Konteineri** nime ei saa muuta ja see on „customerinsights“.</span><span class="sxs-lookup"><span data-stu-id="52a81-140">The **Container** name can't be changed and will be "customerinsights".</span></span>
   
   - <span data-ttu-id="52a81-141">Kui soovite kasutada [prognoose](predictions.md), sisestage Common Data Service'i eksemplari URL väljale **Serveri aadress**, mis asub jaotises **Prognooside kasutamine**.</span><span class="sxs-lookup"><span data-stu-id="52a81-141">If you want to use [predictions](predictions.md), enter the Common Data Service instance URL in the **Server address** field under **Use predictions**.</span></span>

   <span data-ttu-id="52a81-142">Protsesside käitamisel, näiteks andmete valmendamisel või segmendi loomisel, luuakse asjaomased kaustad eespool määratud salvestuskontol.</span><span class="sxs-lookup"><span data-stu-id="52a81-142">When you run processes, such as data ingestion or segment creation, corresponding folders will be created in the storage account you specified above.</span></span> <span data-ttu-id="52a81-143">Luuakse andmefailid ja model.json failid ning need lisatakse teie käitatavate protsesside põhjal vastavatesse alamkaustadesse.</span><span class="sxs-lookup"><span data-stu-id="52a81-143">Data files and model.json files will be created and added to the respective subfolders based on the process you run.</span></span>

   <span data-ttu-id="52a81-144">Kui loote mitu Customer Insightsi keskkonda ja soovite salvestada väljundolemid nendest keskkondadest oma salvestuskontole, luuakse eraldi kaustad iga keskkonna jaoks, mille konteineris on ci_<environmentid>.</span><span class="sxs-lookup"><span data-stu-id="52a81-144">If you create multiple environments of Customer Insights and choose to save the output entities from those environments in your storage account, separate folders will be created for each environment with ci_<environmentid> in the container.</span></span>

### <a name="additional-considerations-for-copy-configuration-preview"></a><span data-ttu-id="52a81-145">Lisakaalutlused konfiguratsiooni kopeerimise puhul (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="52a81-145">Additional considerations for copy configuration (preview)</span></span>

<span data-ttu-id="52a81-146">Kopeeritakse järgmised konfiguratsioonisätted.</span><span class="sxs-lookup"><span data-stu-id="52a81-146">The following configuration settings are copied:</span></span>

- <span data-ttu-id="52a81-147">Funktsiooni konfiguratsioonid</span><span class="sxs-lookup"><span data-stu-id="52a81-147">Feature configurations</span></span>
- <span data-ttu-id="52a81-148">Valmendatud/imporditud andmeallikad</span><span class="sxs-lookup"><span data-stu-id="52a81-148">Inegsted/imported data sources</span></span>
- <span data-ttu-id="52a81-149">Andmete ühtlustamiskonfiguratsioon (kaardistamine, vastendamine, ühendamine)</span><span class="sxs-lookup"><span data-stu-id="52a81-149">Data unification (Map, Match, Merge) configuration</span></span>
- <span data-ttu-id="52a81-150">Segmendid</span><span class="sxs-lookup"><span data-stu-id="52a81-150">Segments</span></span>
- <span data-ttu-id="52a81-151">Meetmed</span><span class="sxs-lookup"><span data-stu-id="52a81-151">Measures</span></span>
- <span data-ttu-id="52a81-152">Seosed</span><span class="sxs-lookup"><span data-stu-id="52a81-152">Relationships</span></span>
- <span data-ttu-id="52a81-153">Tegevused </span><span class="sxs-lookup"><span data-stu-id="52a81-153">Activities</span></span>
- <span data-ttu-id="52a81-154">Otsingu ja filtri register</span><span class="sxs-lookup"><span data-stu-id="52a81-154">Search & filter Index</span></span>
- <span data-ttu-id="52a81-155">Ekspordisihtkohad</span><span class="sxs-lookup"><span data-stu-id="52a81-155">Export destinations</span></span>
- <span data-ttu-id="52a81-156">Ajastatud värskendamine</span><span class="sxs-lookup"><span data-stu-id="52a81-156">Scheduled refresh</span></span>
- <span data-ttu-id="52a81-157">Rikastamised</span><span class="sxs-lookup"><span data-stu-id="52a81-157">Enrichments</span></span>
- <span data-ttu-id="52a81-158">Mudeli haldus</span><span class="sxs-lookup"><span data-stu-id="52a81-158">Model management</span></span>
- <span data-ttu-id="52a81-159">Rolli määramised</span><span class="sxs-lookup"><span data-stu-id="52a81-159">Role assignments</span></span>

<span data-ttu-id="52a81-160">Järgmisi sätteid *ei* kopeerita.</span><span class="sxs-lookup"><span data-stu-id="52a81-160">The following settings are *not* copied:</span></span>

- <span data-ttu-id="52a81-161">Kliendiprofiilid.</span><span class="sxs-lookup"><span data-stu-id="52a81-161">Customer profiles.</span></span>
- <span data-ttu-id="52a81-162">Andmeallika identimisteave.</span><span class="sxs-lookup"><span data-stu-id="52a81-162">Data source credentials.</span></span> <span data-ttu-id="52a81-163">Peate sisestama identimisteabe iga andmeallika jaoks ja värskendama andmeallikaid käsitsi.</span><span class="sxs-lookup"><span data-stu-id="52a81-163">You'll have to provide the credentials for every data source and refresh the data sources manually.</span></span>
- <span data-ttu-id="52a81-164">Andmeallikad kaustast Ühine andmemudel ja Common Data Service’i hallatavast järvest.</span><span class="sxs-lookup"><span data-stu-id="52a81-164">Data sources from Common Data Model folder and Common Data Service managed lake.</span></span> <span data-ttu-id="52a81-165">Peate need andmeallikad looma käsitsi sama nimega kui lähtekeskkond.</span><span class="sxs-lookup"><span data-stu-id="52a81-165">You'll have to create those data sources manually with the same name as in the source environment.</span></span>

<span data-ttu-id="52a81-166">Keskkonna kopeerimisel näete kinnitusteadet, et loodi uus keskkond.</span><span class="sxs-lookup"><span data-stu-id="52a81-166">When you copy an environment, you'll see a confirmation message that the new environment has been created.</span></span> <span data-ttu-id="52a81-167">Andmeallikate loendi nägemiseks valige suvand **Ava andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="52a81-167">Select **Go to data sources** to see the list of data sources.</span></span>

<span data-ttu-id="52a81-168">Kõik andmeallikad kuvavad olekut **Mandaat nõutav**.</span><span class="sxs-lookup"><span data-stu-id="52a81-168">All the data sources will show a **Credentials Required** status.</span></span> <span data-ttu-id="52a81-169">Redigeerige andmeallikaid ja sisestage nende värskendamiseks identimisteave.</span><span class="sxs-lookup"><span data-stu-id="52a81-169">Edit the data sources and enter the credentials to refresh them.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="52a81-170">![Andmeallikad kopeeritud](media/data-sources-copied.png)</span><span class="sxs-lookup"><span data-stu-id="52a81-170">![Data sources copied](media/data-sources-copied.png)</span></span>

<span data-ttu-id="52a81-171">Pärast andmeallikate värskendamist avage jaotis **Andme** > **Ühendamine**.</span><span class="sxs-lookup"><span data-stu-id="52a81-171">After refreshing the data sources, go to **Data** > **Unify**.</span></span> <span data-ttu-id="52a81-172">Siit leiate lähtekeskkonna sätted.</span><span class="sxs-lookup"><span data-stu-id="52a81-172">Here you'll find settings from the source environment.</span></span> <span data-ttu-id="52a81-173">Redigeerige neid vastavalt vajadusele või valige **Käivita**, et käivitada andmete ühendamise protsess ja luua ühtne kliendi olem.</span><span class="sxs-lookup"><span data-stu-id="52a81-173">Edit them as needed or select **Run** to start the data unification process and create the unified customer entity.</span></span>

<span data-ttu-id="52a81-174">Kui andmete ühendamine on lõpetatud, avage **Meetmed** ja **Segmendid**, et neid samuti värskendada.</span><span class="sxs-lookup"><span data-stu-id="52a81-174">When the data unification is complete, go to **Measures** and **Segments** to refresh them too.</span></span>

## <a name="edit-an-existing-environment"></a><span data-ttu-id="52a81-175">Olemasoleva keskkonna redigeerimine</span><span class="sxs-lookup"><span data-stu-id="52a81-175">Edit an existing environment</span></span>

<span data-ttu-id="52a81-176">Saate muuta olemasolevate keskkondade teatud üksikasju.</span><span class="sxs-lookup"><span data-stu-id="52a81-176">You can edit some of the details of existing environments.</span></span>

1. <span data-ttu-id="52a81-177">Avage suvandid **Administraator** > **Süsteem** > **Teave**.</span><span class="sxs-lookup"><span data-stu-id="52a81-177">Go to **Admin** > **System** > **About**.</span></span>

2. <span data-ttu-id="52a81-178">Valige **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="52a81-178">Select **Edit**.</span></span>

3. <span data-ttu-id="52a81-179">Saate värskendada keskkonna **Kuvatavat nime**, kuid te ei saa muuta **Piirkonda** ega **Tüüpi**.</span><span class="sxs-lookup"><span data-stu-id="52a81-179">You can update the environment's **Display name**, but you can't change the **Region** or **Type**.</span></span>

4. <span data-ttu-id="52a81-180">Kui keskkonna andmete salvestusruumiks on konfigureeritud Azure Data Lake Storage Gen2, siis saate uuendada suvandit **Kontovõti**.</span><span class="sxs-lookup"><span data-stu-id="52a81-180">If an environment is configured to store data in Azure Data Lake Storage Gen2, you can update the **Account key**.</span></span> <span data-ttu-id="52a81-181">Kuid te ei saa muuta **Ettevõtte nime** ja **Konteineri** nime.</span><span class="sxs-lookup"><span data-stu-id="52a81-181">However, you can't change the **Account name** or **Container** name.</span></span>

5. <span data-ttu-id="52a81-182">Soovi korral saate kasutada kontovõtmepõhise ühenduse asemel ressursipõhist või tellimusepõhist ühendust.</span><span class="sxs-lookup"><span data-stu-id="52a81-182">Optionally, you can update from an account key based connection to a resource-based or subscription-based connection.</span></span> <span data-ttu-id="52a81-183">Pärast selle tegemist ei saa te värskenduse järel hakata uuesti kontovõtit kasutama.</span><span class="sxs-lookup"><span data-stu-id="52a81-183">Once upgraded, you cannot revert to account key after the update.</span></span> <span data-ttu-id="52a81-184">Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="52a81-184">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="52a81-185">Ühenduse värskendamisel ei saa te muuta **konteineri** teavet.</span><span class="sxs-lookup"><span data-stu-id="52a81-185">You can't change **Container** information when updating the connection.</span></span>

## <a name="reset-an-existing-environment"></a><span data-ttu-id="52a81-186">Olemasoleva keskkonna lähtestamine</span><span class="sxs-lookup"><span data-stu-id="52a81-186">Reset an existing environment</span></span>

<span data-ttu-id="52a81-187">Kui soovite kustutada kõik konfiguratsioonid ja eemaldada valmendatud andmed, saate keskkonna lähtestada nii, et see oleks täiesti tühi.</span><span class="sxs-lookup"><span data-stu-id="52a81-187">You can reset an environment to an empty state if you want to delete all configurations and remove the ingested data.</span></span>

1.  <span data-ttu-id="52a81-188">Avage suvandid **Administraator** > **Süsteem** > **Teave**.</span><span class="sxs-lookup"><span data-stu-id="52a81-188">Go to **Admin** > **System** > **About**.</span></span>

2.  <span data-ttu-id="52a81-189">Valige **Lähtesta**.</span><span class="sxs-lookup"><span data-stu-id="52a81-189">Select **Reset**.</span></span> 

3.  <span data-ttu-id="52a81-190">Kustutamise kinnitamiseks sisestage keskkonna nimi ja valige **Lähtesta**.</span><span class="sxs-lookup"><span data-stu-id="52a81-190">To confirm the deletion, enter the environment name and select **Reset**.</span></span>


## <a name="delete-an-existing-environment"></a><span data-ttu-id="52a81-191">Olemasoleva keskkonna kustutamine</span><span class="sxs-lookup"><span data-stu-id="52a81-191">Delete an existing environment</span></span>

1. <span data-ttu-id="52a81-192">Avage suvandid **Administraator** > **Süsteem** > **Teave**.</span><span class="sxs-lookup"><span data-stu-id="52a81-192">Go to **Admin** > **System** > **About**.</span></span>

1. <span data-ttu-id="52a81-193">Valige **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="52a81-193">Select **Delete**.</span></span>

1. <span data-ttu-id="52a81-194">Kustutamise kinnitamiseks sisestage soovitud keskkonna nimi ja valige **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="52a81-194">To confirm the deletion, enter the environment name and select **Delete**.</span></span>
