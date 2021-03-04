---
title: Andmeallikate kasutamine andmete valmendamiseks
description: Vaadake, kuidas eri allikatest andmeid importida.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269693"
---
# <a name="data-sources-overview"></a><span data-ttu-id="df438-103">Andmeallikate ülevaade</span><span class="sxs-lookup"><span data-stu-id="df438-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="df438-104">Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioon ühendub andmetega, mis on pärit paljudest allikatest.</span><span class="sxs-lookup"><span data-stu-id="df438-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="df438-105">Andmeallikaga ühendamist nimetatakse sageli *andmete sisestamiseks*.</span><span class="sxs-lookup"><span data-stu-id="df438-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="df438-106">Pärast andmete sisestamist saate need [ühendada](data-unification.md) ja nendega toiminguid teha.</span><span class="sxs-lookup"><span data-stu-id="df438-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="df438-107">Lisa andmeallikas</span><span class="sxs-lookup"><span data-stu-id="df438-107">Add a data source</span></span>

<span data-ttu-id="df438-108">Vaadake üksikasjalikke artikleid selle kohta, kuidas andmeallikat lisada, olenevalt sellest, millise suvandi te valite.</span><span class="sxs-lookup"><span data-stu-id="df438-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="df438-109">Saate andmeallikat lisada kolmel peamisel viisil.</span><span class="sxs-lookup"><span data-stu-id="df438-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="df438-110">Kümnete Power Query konnektorite kaudu</span><span class="sxs-lookup"><span data-stu-id="df438-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="df438-111">Common Data Modeli kaustast</span><span class="sxs-lookup"><span data-stu-id="df438-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="df438-112">Enda Common Data Service’i andmejärvest</span><span class="sxs-lookup"><span data-stu-id="df438-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="df438-113">Asutusesisestest andmeallikatest ei saa veel andmeid lisada.</span><span class="sxs-lookup"><span data-stu-id="df438-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="df438-114">Sisestatud andmete läbivaatus</span><span class="sxs-lookup"><span data-stu-id="df438-114">Review ingested data</span></span>

<span data-ttu-id="df438-115">Näete iga sisestatud andmeallika nime, selle olekut ja viimast korda, kui neid andmeid selle allika jaoks värskendati.</span><span class="sxs-lookup"><span data-stu-id="df438-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="df438-116">Saate andmeallikate loendit iga veeru järgi sortida.</span><span class="sxs-lookup"><span data-stu-id="df438-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="df438-117">![Andmeallikas lisatud](media/configure-data-datasource-added.png "Andmeallikas lisatud")</span><span class="sxs-lookup"><span data-stu-id="df438-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="df438-118">Olek</span><span class="sxs-lookup"><span data-stu-id="df438-118">Status</span></span>  |<span data-ttu-id="df438-119">Kirjeldus</span><span class="sxs-lookup"><span data-stu-id="df438-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="df438-120">Õnnestunud</span><span class="sxs-lookup"><span data-stu-id="df438-120">Successful</span></span>   |<span data-ttu-id="df438-121">Andmeallikas valmendati edukalt juhul, kui veerus **Värskendatud** on toodud aeg.</span><span class="sxs-lookup"><span data-stu-id="df438-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="df438-122">Pole käivitatud</span><span class="sxs-lookup"><span data-stu-id="df438-122">Not started</span></span>   |<span data-ttu-id="df438-123">Andmeallikas pole valmendatud andmeid või see on ikka mustandirežiimis.</span><span class="sxs-lookup"><span data-stu-id="df438-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="df438-124">Värskendamine</span><span class="sxs-lookup"><span data-stu-id="df438-124">Refreshing</span></span>    |<span data-ttu-id="df438-125">Andmete sisestamine on pooleli.</span><span class="sxs-lookup"><span data-stu-id="df438-125">Data ingestion is in progress.</span></span> <span data-ttu-id="df438-126">Selle toimingu tühistamiseks valige **Peata värskendamine** **Toimingute** veerus.</span><span class="sxs-lookup"><span data-stu-id="df438-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="df438-127">Andmeallika värskendamise peatamine ennistab selle viimase värskendamise olekusse.</span><span class="sxs-lookup"><span data-stu-id="df438-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="df438-128">Ebaõnnestus</span><span class="sxs-lookup"><span data-stu-id="df438-128">Failed</span></span>     |<span data-ttu-id="df438-129">Andmete sisestamisel ilmnesid tõrked.</span><span class="sxs-lookup"><span data-stu-id="df438-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="df438-130">Üksikasjade kuvamiseks valige väärtus mis tahes andmeallika veerus **Olek**.</span><span class="sxs-lookup"><span data-stu-id="df438-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="df438-131">Laiendage paanil **Edenemise üksikasjad** suvandit **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="df438-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="df438-132">Valige **Kuva üksikasjad**, et saada värskendamise oleku kohta lisateavet, sh tõrke üksikasjad ja allavooluprotsesside värskendused.</span><span class="sxs-lookup"><span data-stu-id="df438-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="df438-133">Andmete laadimine võib veidi aega võtta.</span><span class="sxs-lookup"><span data-stu-id="df438-133">Loading data can take some time.</span></span> <span data-ttu-id="df438-134">Pärast edukat värskendamist saab lisatud andmeid vaadata lehel **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="df438-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="df438-135">Lisateavet vt jaotisest [Olemid](entities.md).</span><span class="sxs-lookup"><span data-stu-id="df438-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="df438-136">Andmeallika värskendamine</span><span class="sxs-lookup"><span data-stu-id="df438-136">Refresh a data source</span></span>

<span data-ttu-id="df438-137">Andmeallikaid saab värskendada automaatse ajakava järgi või soovi korral käsitsi.</span><span class="sxs-lookup"><span data-stu-id="df438-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="df438-138">Minge jaotisse **Haldus** > **Süsteem** > [**Ajastamine**](system.md#schedule-tab), et konfigureerida kõigi valmendatud andmeallikate ajastatud värskendamine.</span><span class="sxs-lookup"><span data-stu-id="df438-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="df438-139">Andmeallika värskendamiseks mis tahes ajal toimige järgmiselt.</span><span class="sxs-lookup"><span data-stu-id="df438-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="df438-140">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**</span><span class="sxs-lookup"><span data-stu-id="df438-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="df438-141">Valige värskendamist vajava andmeallika kõrvalt vertikaalne kolmikpunkt ja valige ripploendist **Värskenda**.</span><span class="sxs-lookup"><span data-stu-id="df438-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="df438-142">Andmeallika jaoks käivitatakse nüüd käsitsivärskendamine.</span><span class="sxs-lookup"><span data-stu-id="df438-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="df438-143">Andmeallika värskendamisel värskendatakse nii olemiskeem kui ka kõigi andmeallikas määratletud olemite andmed.</span><span class="sxs-lookup"><span data-stu-id="df438-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="df438-144">Kui soovite olemasoleva värskendamise tühistada, klõpsake **Lõpeta värskendamine** ja andmeallikas taastatakse viimase värskendamise olekusse.</span><span class="sxs-lookup"><span data-stu-id="df438-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="df438-145">Andmeallika kustutamine</span><span class="sxs-lookup"><span data-stu-id="df438-145">Delete a data source</span></span>

1. <span data-ttu-id="df438-146">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="df438-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="df438-147">Valige eemaldatava andmeallika kõrval asuv vertikaalne kolmikpunkt ja valige rippmenüüst suvand **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="df438-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="df438-148">Kinnitage, et soovite kustutada.</span><span class="sxs-lookup"><span data-stu-id="df438-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]