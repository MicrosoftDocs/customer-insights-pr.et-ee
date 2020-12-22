---
title: Andmete valmendamine Power Query konnektori kaudu
description: Power Query-l põhinevate andmeallikate konnektorid.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405546"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="b9366-103">Power Query andmeallikaga ühendamine</span><span class="sxs-lookup"><span data-stu-id="b9366-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="b9366-104">Power Query pakub andmete valmendamiseks laia komplekti konnektoreid.</span><span class="sxs-lookup"><span data-stu-id="b9366-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="b9366-105">Enamikku nendest konnektoritest toetab Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b9366-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="b9366-106">Power Query konnektorite põhjal andmeallikate lisamine järgib üldjoontes järgmises jaotises kirjeldatud juhiseid.</span><span class="sxs-lookup"><span data-stu-id="b9366-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="b9366-107">Olenevalt kasutatavast konnektorist on siiski vaja erinevat teavet.</span><span class="sxs-lookup"><span data-stu-id="b9366-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="b9366-108">Lisateavet üksikute konnektorite kohta leiate dokumentatsioonist [Power Query konnektorite viide](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="b9366-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="b9366-109">Loo uus andmeallikas</span><span class="sxs-lookup"><span data-stu-id="b9366-109">Create a new data source</span></span>

1. <span data-ttu-id="b9366-110">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="b9366-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="b9366-111">Valige **Lisa andmeallikas**.</span><span class="sxs-lookup"><span data-stu-id="b9366-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="b9366-112">Valige meetod **Andmete importimine** ja valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="b9366-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="b9366-113">Sisestage andmeallikale **Nimi** ja valige andmeallika loomiseks nupp **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="b9366-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="b9366-114">Valige üks [saadaolevatest konnektoritest](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="b9366-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="b9366-115">Selles näites valime **Teksti/CSV** konnektori.</span><span class="sxs-lookup"><span data-stu-id="b9366-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b9366-116">Sisestage valitud konnektorile jaotises **Konnektori sätted** nõutavad üksikasjad ja valige andmete üle vaatamiseks nupp **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="b9366-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="b9366-117">Valige suvand **Andmete teisendamine**.</span><span class="sxs-lookup"><span data-stu-id="b9366-117">Select **Transform data**.</span></span> <span data-ttu-id="b9366-118">Selles etapis lisate oma andmeallikale olemid.</span><span class="sxs-lookup"><span data-stu-id="b9366-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="b9366-119">Olemid on andmekogud.</span><span class="sxs-lookup"><span data-stu-id="b9366-119">Entities are datasets.</span></span> <span data-ttu-id="b9366-120">Kui teil on andmebaas, mis sisaldab mitut andmekogumit, on iga andmekomplekt omaette olem.</span><span class="sxs-lookup"><span data-stu-id="b9366-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="b9366-121">Dialoogiaken **Power Query – päringute redigeerimine** võimaldab andmeid üle vaadata ja täiustada.</span><span class="sxs-lookup"><span data-stu-id="b9366-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="b9366-122">Olemid, mida süsteemid teie valitud andmeallikas tuvastasid, kuvatakse vasakpoolsel paanil.</span><span class="sxs-lookup"><span data-stu-id="b9366-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b9366-123">![Päringute redigeerimise dialoog](media/data-manager-configure-edit-queries.png "Päringute redigeerimise dialoog")</span><span class="sxs-lookup"><span data-stu-id="b9366-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="b9366-124">Samuti saate oma andmeid teisendada.</span><span class="sxs-lookup"><span data-stu-id="b9366-124">You can also transform your data.</span></span> <span data-ttu-id="b9366-125">Valige redigeeritav või teisendatav olem.</span><span class="sxs-lookup"><span data-stu-id="b9366-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="b9366-126">Teisenduste rakendamiseks kasutage suvandeid aknas Power Query.</span><span class="sxs-lookup"><span data-stu-id="b9366-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="b9366-127">Kõik teisendused loetletakse jaotises **Rakendatud etapid**.</span><span class="sxs-lookup"><span data-stu-id="b9366-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="b9366-128">Power Query pakub arvukalt eelvalmistatud teisendamise võimalusi.</span><span class="sxs-lookup"><span data-stu-id="b9366-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="b9366-129">Lisateavet leiate teemast [Power Query teisendused](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="b9366-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="b9366-130">Saate lisada oma andmeallikas täiendavaid olemeid, valides **Hangi andmed** dialoogis **Päringute redigeerimise**.</span><span class="sxs-lookup"><span data-stu-id="b9366-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="b9366-131">Need teisendused on väga soovitatavad.</span><span class="sxs-lookup"><span data-stu-id="b9366-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="b9366-132">Kui valmendate andmeid CSV-failist, siis esimene rida sisaldab sageli päiseid.</span><span class="sxs-lookup"><span data-stu-id="b9366-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="b9366-133">Avage **Tabeli teisendamine** ja valige suvand **Kasuta päiseid esimese reana**.</span><span class="sxs-lookup"><span data-stu-id="b9366-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="b9366-134">Veenduge, et andmetüüp oleks õigesti seadistatud.</span><span class="sxs-lookup"><span data-stu-id="b9366-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="b9366-135">Teisenduste salvestamiseks valige Power Query akna allosast **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="b9366-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="b9366-136">Pärast salvestamist leiate oma andmeallika jaotises **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="b9366-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="b9366-137">Lehel **Andmeallikad** märkate, et uus andmeallikas on olekus **Värskendamine**.</span><span class="sxs-lookup"><span data-stu-id="b9366-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="b9366-138">Saadaolevad Power Query andmeallikad</span><span class="sxs-lookup"><span data-stu-id="b9366-138">Available Power Query data sources</span></span>

<span data-ttu-id="b9366-139">Ajakohase Customer Insightsi imporditavate konnektorite loendi leiate jaotisest [Power Query konnektorite viide](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="b9366-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="b9366-140">Konnektorid, millel on märgitud veerg **Customer Insights (andmevood)**, on saadaval Power Query põhjal uute andmeallikate loomiseks.</span><span class="sxs-lookup"><span data-stu-id="b9366-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="b9366-141">Vaadake üle kindla konnektori dokumendid, et saada lisateavet selle eeltingimuste, piirangute ja muude üksikasjade kohta.</span><span class="sxs-lookup"><span data-stu-id="b9366-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="b9366-142">Power Query andmeallikate redigeerimine</span><span class="sxs-lookup"><span data-stu-id="b9366-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="b9366-143">Ei pruugi olla võimalik muuta andmeallikaid, mis on samaaegselt kasutusel mõnes rakenduse protsessis (nt *segmentimine*, *vaste* või *ühinemine*).</span><span class="sxs-lookup"><span data-stu-id="b9366-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="b9366-144">Lehe **Sätted** abil saate jälgida iga aktiivse protsessi kulgu.</span><span class="sxs-lookup"><span data-stu-id="b9366-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="b9366-145">Protsessi lõpuleviimisel saate naasta **Andmeallikate** lehele ja teha soovitud muudatused.</span><span class="sxs-lookup"><span data-stu-id="b9366-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="b9366-146">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="b9366-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b9366-147">Valige muudetava andmeallika kõrval asuv vertikaalne kolmikpunkt ja valige rippmenüüst suvand **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="b9366-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b9366-148">![Redigeerimise suvand](media/edit-option-data-sources.png "Redigeerimise suvand")</span><span class="sxs-lookup"><span data-stu-id="b9366-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="b9366-149">Rakendage muudatused ja teisendused dialoogiaknas **Power Query – päringute redigeerimine**, nii nagu on kirjeldatud jaotises [Uue andmeallika loomine](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="b9366-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="b9366-150">Valige pärast redigeerimist muudatuste salvestamiseks Power Querys **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="b9366-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
