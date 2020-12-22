---
title: Common Data Modeli andmete ühendamine Azure Data Lake'i kontoga
description: Töötage Common Data Modeli andmete kallal Azure Data Lake Storage'i abil.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643453"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="7d356-103">Common Data Modeli kausta ühendamine Azure Data Lake’i kontot kasutades</span><span class="sxs-lookup"><span data-stu-id="7d356-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="7d356-104">See artikkel annab teavet selle kohta, kuidas valmendada andmeid Common Data Modeli kaustast, kasutades Azure Data Lake Storage Gen2 kontot.</span><span class="sxs-lookup"><span data-stu-id="7d356-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="7d356-105">Olulised kaalutlused</span><span class="sxs-lookup"><span data-stu-id="7d356-105">Important considerations</span></span>

- <span data-ttu-id="7d356-106">Andmed Azure Data Lake'is peavad vastama Common Data Modeli standardile.</span><span class="sxs-lookup"><span data-stu-id="7d356-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="7d356-107">Hetkel muid vorminguid ei toetata.</span><span class="sxs-lookup"><span data-stu-id="7d356-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="7d356-108">Andmete valmendamise korral toetatakse ainult Azure Data Lake *Gen2* salvestuskontosid.</span><span class="sxs-lookup"><span data-stu-id="7d356-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="7d356-109">Andmete valmendamiseks ei saa kasutada Azure Data Lake Gen1 salvestuskontosid.</span><span class="sxs-lookup"><span data-stu-id="7d356-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="7d356-110">Azure'i teenusesubjektiga autentimiseks veenduge, et see oleks teie rentnikus konfigureeritud.</span><span class="sxs-lookup"><span data-stu-id="7d356-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="7d356-111">Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="7d356-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="7d356-112">Azure Data Lake, millega soovite ühenduda ja millest andmeid valmendada, peab olema samas Azure'i regioonis nagu Dynamics 365 Customer Insightsi keskkond.</span><span class="sxs-lookup"><span data-stu-id="7d356-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="7d356-113">Ühendused Common Data Modeli kausta ja muus Azure'i regioonis oleva andmejärve vahel pole toetatud.</span><span class="sxs-lookup"><span data-stu-id="7d356-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="7d356-114">Selleks et uurida välja keskkonna Azure'i regioon, minge sihtrühmaülevaadetes jaotisse **Haldus** > **Süsteem** > **Teave**.</span><span class="sxs-lookup"><span data-stu-id="7d356-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="7d356-115">Võrguteenustes talletatud andmed võivad olla talletatud mõnes muus kohas, mis erineb kohast, kus Dynamics 365 Customer Insightsis andmeid töödeldakse või talletatakse.</span><span class="sxs-lookup"><span data-stu-id="7d356-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="7d356-116"> Kui impordite võrguteenustes talletatavaid andmeid või ühendate konto teenusega, siis nõustute, et andmeid võidakse transportida ja salvestada rakenduses Dynamics 365 Customer Insights. [Lisateavet leiate Microsofti usalduskeskusest.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="7d356-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="7d356-117">Loo ühendus Common Data Modeli kaustaga</span><span class="sxs-lookup"><span data-stu-id="7d356-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="7d356-118">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="7d356-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="7d356-119">Valige **Lisa andmeallikas**.</span><span class="sxs-lookup"><span data-stu-id="7d356-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="7d356-120">Valige **Loo ühendus Common Data Modeli kaustaga**, sisestage andmeallikale **Nimi** ja valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="7d356-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="7d356-121">Saate autentimiseks valida ressursipõhise ja tellimusepõhise valiku vahel.</span><span class="sxs-lookup"><span data-stu-id="7d356-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="7d356-122">Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="7d356-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="7d356-123">Sisestage **konteineri** teave ja valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="7d356-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7d356-124">![Dialoogiboks Azure Data Lake'i jaoks ühendusandmete sisestamiseks](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="7d356-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="7d356-125">Valige dialoogis **Common Data Modeli kausta valimine** fail model.json, kuhu andmeid importida, ja valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="7d356-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="7d356-126">Keskkonnas muu andmeallikaga seotud model.json-faile ei kuvata loendis.</span><span class="sxs-lookup"><span data-stu-id="7d356-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="7d356-127">Saadaolevate olemite loendi leiate valitud model.json-failist.</span><span class="sxs-lookup"><span data-stu-id="7d356-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="7d356-128">Saate vaadata üle ja valida saadaolevate olemite loendist ning valida suvandi **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="7d356-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="7d356-129">Kõik valitud olemid valmendatakse uuest andmeallikast.</span><span class="sxs-lookup"><span data-stu-id="7d356-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7d356-130">![Dialoogiboks, kus on esitatud model.json failist saadud olemite loetelu](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="7d356-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="7d356-131">Andmete profiilimise lubamiseks valige soovitud andmeüksused ja valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="7d356-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="7d356-132">Andmete profiilimine teeb võimalikuks analüüsi ja palju muud.</span><span class="sxs-lookup"><span data-stu-id="7d356-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="7d356-133">Saate valida kogu olemi, mis valib olemi kõik atribuudid, või valida oma soovi järgi kindlad atribuudid.</span><span class="sxs-lookup"><span data-stu-id="7d356-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="7d356-134">Vaikimisi pole olemeid andmete profiilimiseks lubatud.</span><span class="sxs-lookup"><span data-stu-id="7d356-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7d356-135">![Andmete profiilimist kuvav dialoogiboks](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="7d356-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="7d356-136">Pärast valikute salvestamist avaneb leht **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="7d356-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="7d356-137">Nüüd peaksite nägema Common Data Modeli kausta ühendust andmeallikana.</span><span class="sxs-lookup"><span data-stu-id="7d356-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="7d356-138">Faili model.json saab seostada samas keskkonnas ühe andmeallikaga.</span><span class="sxs-lookup"><span data-stu-id="7d356-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="7d356-139">Kuid sama model.json-faili saab kasutada mitmes keskkonnas andmeallikate jaoks.</span><span class="sxs-lookup"><span data-stu-id="7d356-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="7d356-140">Common Data Modeli kausta andmeallika redigeerimine</span><span class="sxs-lookup"><span data-stu-id="7d356-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="7d356-141">Saate värskendada pääsuvõtit, mis kuulub salvestuskontole, mis sisaldab Common Data Modeli kausta.</span><span class="sxs-lookup"><span data-stu-id="7d356-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="7d356-142">Samuti võite muuta model.json faili.</span><span class="sxs-lookup"><span data-stu-id="7d356-142">You may also change the model.json file.</span></span> <span data-ttu-id="7d356-143">Kui soovite luua ühenduse muu konteineriga teie salvestuskontol või muuta konto nime, siis peate looma [uue andmeallika ühenduse](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="7d356-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="7d356-144">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="7d356-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="7d356-145">Valige uuendatava andmeallika kõrval suvand kolm punkti.</span><span class="sxs-lookup"><span data-stu-id="7d356-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="7d356-146">Valige loetelust valik **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="7d356-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="7d356-147">Soovi korral saate uuendada **Pääsuvõtit** ja valida seejärel **Järgmine**.</span><span class="sxs-lookup"><span data-stu-id="7d356-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![Olemasoleva andmeallika pääsuvõtme redigeerimise ja uuendamise dialoog](media/edit-access-key.png)

5. <span data-ttu-id="7d356-149">Soovi korral saate kasutada kontovõtmepõhise ühenduse asemel ressursi- või tellimusepõhist ühendust.</span><span class="sxs-lookup"><span data-stu-id="7d356-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="7d356-150">Lisateavet leiate teemast [Sihtrühmaülevaadete ühendamine Azure Data Lake Storage Gen2 kontoga Azure'i teenusesubjekti kaudu](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="7d356-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="7d356-151">Ühenduse värskendamisel ei saa te muuta **konteineri** teavet.</span><span class="sxs-lookup"><span data-stu-id="7d356-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7d356-152">![Dialoogiboks Azure Data Lake'i jaoks ühendusandmete sisestamiseks](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="7d356-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="7d356-153">Soovi korral võite valida konteinerist muu json.faili, millel on teistsugune olemite komplekt.</span><span class="sxs-lookup"><span data-stu-id="7d356-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="7d356-154">Soovi korral saate valmendamiseks valida täiendavaid olemeid.</span><span class="sxs-lookup"><span data-stu-id="7d356-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="7d356-155">Samuti saate sõltuvuste puudumise korral eemaldada kõiki juba valitud olemeid.</span><span class="sxs-lookup"><span data-stu-id="7d356-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="7d356-156">Kui olemasoleval model.json failil ja olemite komplektil on kehtivad sõltuvused, siis kuvatakse tõrketeade ja te ei saa muud model.json faili valida.</span><span class="sxs-lookup"><span data-stu-id="7d356-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="7d356-157">Enne model.json faili muutmist tuleb sõltuvused eemaldada. Kui te ei soovi sõltuvusi eemaldada, siis saate luua uue andmeallika teie soovitud model.json failiga.</span><span class="sxs-lookup"><span data-stu-id="7d356-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="7d356-158">Soovi korral saate valida täiendavaid atribuute või olemeid, mille korral lubada andmete profiilimine, või keelata juba valitud üksused.</span><span class="sxs-lookup"><span data-stu-id="7d356-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
