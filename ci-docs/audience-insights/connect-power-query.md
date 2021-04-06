---
title: Andmete valmendamine Power Query konnektori kaudu
description: Power Query-l põhinevate andmeallikate konnektorid.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b9a1b30e37c3792aa7bdfcfc177da9e8a32c324d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596908"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="283fc-103">Power Query andmeallikaga ühendamine</span><span class="sxs-lookup"><span data-stu-id="283fc-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="283fc-104">Power Query pakub andmete valmendamiseks laia komplekti konnektoreid.</span><span class="sxs-lookup"><span data-stu-id="283fc-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="283fc-105">Enamikku nendest konnektoritest toetab Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="283fc-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="283fc-106">Power Query konnektorite põhjal andmeallikate lisamine järgib üldjoontes järgmises jaotises kirjeldatud juhiseid.</span><span class="sxs-lookup"><span data-stu-id="283fc-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="283fc-107">Olenevalt kasutatavast konnektorist on siiski vaja erinevat teavet.</span><span class="sxs-lookup"><span data-stu-id="283fc-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="283fc-108">Lisateavet üksikute konnektorite kohta leiate dokumentatsioonist [Power Query konnektorite viide](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="283fc-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="283fc-109">Loo uus andmeallikas</span><span class="sxs-lookup"><span data-stu-id="283fc-109">Create a new data source</span></span>

1. <span data-ttu-id="283fc-110">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="283fc-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="283fc-111">Valige **Lisa andmeallikas**.</span><span class="sxs-lookup"><span data-stu-id="283fc-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="283fc-112">Valige meetod **Andmete importimine** ja valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="283fc-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="283fc-113">Sisestage andmeallikale **Nimi** ja valige andmeallika loomiseks nupp **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="283fc-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="283fc-114">Nime juhised:</span><span class="sxs-lookup"><span data-stu-id="283fc-114">Name guidelines:</span></span> 
   - <span data-ttu-id="283fc-115">peab algama tähega;</span><span class="sxs-lookup"><span data-stu-id="283fc-115">Start with a letter.</span></span>
   - <span data-ttu-id="283fc-116">kasutage ainult tähti ja numbreid;</span><span class="sxs-lookup"><span data-stu-id="283fc-116">Use letters and numbers only.</span></span> <span data-ttu-id="283fc-117">erimärkide ja tühikute sisestamine pole lubatud;</span><span class="sxs-lookup"><span data-stu-id="283fc-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="283fc-118">kasutage 3–64 tähemärki.</span><span class="sxs-lookup"><span data-stu-id="283fc-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="283fc-119">Valige üks [saadaolevatest konnektoritest](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="283fc-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="283fc-120">Selles näites valime **Teksti/CSV** konnektori.</span><span class="sxs-lookup"><span data-stu-id="283fc-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="283fc-121">Sisestage valitud konnektorile jaotises **Konnektori sätted** nõutavad üksikasjad ja valige andmete üle vaatamiseks nupp **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="283fc-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="283fc-122">Valige suvand **Andmete teisendamine**.</span><span class="sxs-lookup"><span data-stu-id="283fc-122">Select **Transform data**.</span></span> <span data-ttu-id="283fc-123">Selles etapis lisate oma andmeallikale olemid.</span><span class="sxs-lookup"><span data-stu-id="283fc-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="283fc-124">Olemid on andmekogud.</span><span class="sxs-lookup"><span data-stu-id="283fc-124">Entities are datasets.</span></span> <span data-ttu-id="283fc-125">Kui teil on andmebaas, mis sisaldab mitut andmekogumit, on iga andmekomplekt omaette olem.</span><span class="sxs-lookup"><span data-stu-id="283fc-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="283fc-126">Dialoogiaken **Power Query – päringute redigeerimine** võimaldab andmeid üle vaadata ja täiustada.</span><span class="sxs-lookup"><span data-stu-id="283fc-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="283fc-127">Olemid, mida süsteemid teie valitud andmeallikas tuvastasid, kuvatakse vasakpoolsel paanil.</span><span class="sxs-lookup"><span data-stu-id="283fc-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="283fc-128">![Päringute redigeerimise dialoog](media/data-manager-configure-edit-queries.png "Päringute redigeerimise dialoog")</span><span class="sxs-lookup"><span data-stu-id="283fc-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="283fc-129">Samuti saate oma andmeid teisendada.</span><span class="sxs-lookup"><span data-stu-id="283fc-129">You can also transform your data.</span></span> <span data-ttu-id="283fc-130">Valige redigeeritav või teisendatav olem.</span><span class="sxs-lookup"><span data-stu-id="283fc-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="283fc-131">Teisenduste rakendamiseks kasutage suvandeid aknas Power Query.</span><span class="sxs-lookup"><span data-stu-id="283fc-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="283fc-132">Kõik teisendused loetletakse jaotises **Rakendatud etapid**.</span><span class="sxs-lookup"><span data-stu-id="283fc-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="283fc-133">Power Query pakub arvukalt eelvalmistatud teisendamise võimalusi.</span><span class="sxs-lookup"><span data-stu-id="283fc-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="283fc-134">Lisateavet leiate teemast [Power Query teisendused](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="283fc-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="283fc-135">Saate lisada oma andmeallikas täiendavaid olemeid, valides **Hangi andmed** dialoogis **Päringute redigeerimise**.</span><span class="sxs-lookup"><span data-stu-id="283fc-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="283fc-136">Need teisendused on väga soovitatavad.</span><span class="sxs-lookup"><span data-stu-id="283fc-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="283fc-137">Kui valmendate andmeid CSV-failist, siis esimene rida sisaldab sageli päiseid.</span><span class="sxs-lookup"><span data-stu-id="283fc-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="283fc-138">Avage **Tabeli teisendamine** ja valige suvand **Kasuta päiseid esimese reana**.</span><span class="sxs-lookup"><span data-stu-id="283fc-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="283fc-139">Veenduge, et andmetüüp oleks õigesti seadistatud.</span><span class="sxs-lookup"><span data-stu-id="283fc-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="283fc-140">Teisenduste salvestamiseks valige Power Query akna allosast **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="283fc-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="283fc-141">Pärast salvestamist leiate oma andmeallika jaotises **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="283fc-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="283fc-142">Lehel **Andmeallikad** märkate, et uus andmeallikas on olekus **Värskendamine**.</span><span class="sxs-lookup"><span data-stu-id="283fc-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="283fc-143">Saadaolevad Power Query andmeallikad</span><span class="sxs-lookup"><span data-stu-id="283fc-143">Available Power Query data sources</span></span>

<span data-ttu-id="283fc-144">Ajakohase Customer Insightsi imporditavate konnektorite loendi leiate jaotisest [Power Query konnektorite viide](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="283fc-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="283fc-145">Konnektorid, millel on märgitud veerg **Customer Insights (andmevood)**, on saadaval Power Query põhjal uute andmeallikate loomiseks.</span><span class="sxs-lookup"><span data-stu-id="283fc-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="283fc-146">Vaadake üle kindla konnektori dokumendid, et saada lisateavet selle eeltingimuste, piirangute ja muude üksikasjade kohta.</span><span class="sxs-lookup"><span data-stu-id="283fc-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="283fc-147">Power Query andmeallikate redigeerimine</span><span class="sxs-lookup"><span data-stu-id="283fc-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="283fc-148">Ei pruugi olla võimalik muuta andmeallikaid, mis on samaaegselt kasutusel mõnes rakenduse protsessis (nt *segmentimine*, *vaste* või *ühinemine*).</span><span class="sxs-lookup"><span data-stu-id="283fc-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="283fc-149">Lehe **Sätted** abil saate jälgida iga aktiivse protsessi kulgu.</span><span class="sxs-lookup"><span data-stu-id="283fc-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="283fc-150">Protsessi lõpuleviimisel saate naasta **Andmeallikate** lehele ja teha soovitud muudatused.</span><span class="sxs-lookup"><span data-stu-id="283fc-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="283fc-151">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="283fc-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="283fc-152">Valige muudetava andmeallika kõrval asuv vertikaalne kolmikpunkt ja valige rippmenüüst suvand **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="283fc-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="283fc-153">![Redigeerimise suvand](media/edit-option-data-sources.png "Redigeerimise suvand")</span><span class="sxs-lookup"><span data-stu-id="283fc-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="283fc-154">Rakendage muudatused ja teisendused dialoogiaknas **Power Query – päringute redigeerimine**, nii nagu on kirjeldatud jaotises [Uue andmeallika loomine](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="283fc-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="283fc-155">Valige pärast redigeerimist muudatuste salvestamiseks Power Querys **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="283fc-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]