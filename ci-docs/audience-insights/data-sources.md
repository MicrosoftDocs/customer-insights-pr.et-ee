---
title: Andmeallikate kasutamine andmete valmendamiseks
description: Vaadake, kuidas eri allikatest andmeid importida.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304691"
---
# <a name="data-sources-overview"></a><span data-ttu-id="3d2d9-103">Andmeallikate ülevaade</span><span class="sxs-lookup"><span data-stu-id="3d2d9-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3d2d9-104">Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioon ühendub andmetega, mis on pärit paljudest allikatest.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="3d2d9-105">Andmeallikaga ühendamist nimetatakse sageli *andmete sisestamiseks*.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="3d2d9-106">Pärast andmete sisestamist saate need [ühendada](data-unification.md) ja nendega toiminguid teha.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="3d2d9-107">Lisa andmeallikas</span><span class="sxs-lookup"><span data-stu-id="3d2d9-107">Add a data source</span></span>

<span data-ttu-id="3d2d9-108">Vaadake üksikasjalikke artikleid selle kohta, kuidas andmeallikat lisada, olenevalt sellest, millise suvandi te valite.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="3d2d9-109">Saate andmeallikat lisada kolmel peamisel viisil.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="3d2d9-110">Kümnete Power Query konnektorite kaudu</span><span class="sxs-lookup"><span data-stu-id="3d2d9-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="3d2d9-111">Common Data Modeli kaustast</span><span class="sxs-lookup"><span data-stu-id="3d2d9-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="3d2d9-112">Enda Microsoft Dataverse’i andmejärvest</span><span class="sxs-lookup"><span data-stu-id="3d2d9-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="3d2d9-113">Andmete lisamine asutusesisene andmeallikatest</span><span class="sxs-lookup"><span data-stu-id="3d2d9-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="3d2d9-114">Kohalike andmeallikate andmete sisestamine vaatajaskonna statistikas toetub Microsoft Power Platform andmevoogudele.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="3d2d9-115">Andmevooge saab lubada Customer Insights kaudu [pakkudes Microsoft Dataverse keskkonna URL-i](manage-environments.md#create-an-environment-in-an-existing-organization) keskkonna seadistamisel.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="3d2d9-116">Andmeallikad, mis luuakse pärast keskkonna Dataverse seostamist Customer Insights, kasutavad [Power Platform andmevooge](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) vaikimisi.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="3d2d9-117">Andmevood toetavad kohapealset ühenduvust andmelüüside abil.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="3d2d9-118">Eemaldage ja looge uuesti andmeallikad, mis olid olemas enne seda, kui Dataverse -i keskkond seostati [asutusesisese andmelüüside kasutamisega](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="3d2d9-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="3d2d9-119">Andmevõrgud olemasolevast Power BI või Power Apps keskkonnast on nähtavad ja saate neid uuesti kasutada jaotises Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="3d2d9-120">Andmeallikate lehel kuvatakse lingid, et minna Microsoft Power Platform keskkonda, kus saate vaadata ja konfigureerida asutusesiseseid andmevõrke.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="3d2d9-121">Sisestatud andmete läbivaatus</span><span class="sxs-lookup"><span data-stu-id="3d2d9-121">Review ingested data</span></span>

<span data-ttu-id="3d2d9-122">Näete iga sisestatud andmeallika nime, selle olekut ja viimast korda, kui neid andmeid selle allika jaoks värskendati.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="3d2d9-123">Saate andmeallikate loendit iga veeru järgi sortida.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3d2d9-124">![Andmeallikas lisatud](media/configure-data-datasource-added.png "Andmeallikas lisatud")</span><span class="sxs-lookup"><span data-stu-id="3d2d9-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="3d2d9-125">Olek</span><span class="sxs-lookup"><span data-stu-id="3d2d9-125">Status</span></span>  |<span data-ttu-id="3d2d9-126">Kirjeldus</span><span class="sxs-lookup"><span data-stu-id="3d2d9-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="3d2d9-127">Õnnestunud</span><span class="sxs-lookup"><span data-stu-id="3d2d9-127">Successful</span></span>   |<span data-ttu-id="3d2d9-128">Andmeallikas valmendati edukalt juhul, kui veerus **Värskendatud** on toodud aeg.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="3d2d9-129">Pole käivitatud</span><span class="sxs-lookup"><span data-stu-id="3d2d9-129">Not started</span></span>   |<span data-ttu-id="3d2d9-130">Andmeallikas pole valmendatud andmeid või see on ikka mustandirežiimis.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="3d2d9-131">Värskendamine</span><span class="sxs-lookup"><span data-stu-id="3d2d9-131">Refreshing</span></span>    |<span data-ttu-id="3d2d9-132">Andmete sisestamine on pooleli.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-132">Data ingestion is in progress.</span></span> <span data-ttu-id="3d2d9-133">Selle toimingu tühistamiseks valige **Peata värskendamine** **Toimingute** veerus.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="3d2d9-134">Andmeallika värskendamise peatamine ennistab selle viimase värskendamise olekusse.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="3d2d9-135">Ebaõnnestus</span><span class="sxs-lookup"><span data-stu-id="3d2d9-135">Failed</span></span>     |<span data-ttu-id="3d2d9-136">Andmete sisestamisel ilmnesid tõrked.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="3d2d9-137">Üksikasjade kuvamiseks valige väärtus mis tahes andmeallika veerus **Olek**.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="3d2d9-138">Laiendage paanil **Edenemise üksikasjad** suvandit **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="3d2d9-139">Valige **Kuva üksikasjad**, et saada värskendamise oleku kohta lisateavet, sh tõrke üksikasjad ja allavooluprotsesside värskendused.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="3d2d9-140">Andmete laadimine võib võtta aega.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-140">Loading data can take time.</span></span> <span data-ttu-id="3d2d9-141">Pärast edukat värskendamist saab lisatud andmeid vaadata lehel **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="3d2d9-142">Lisateavet vt jaotisest [Olemid](entities.md).</span><span class="sxs-lookup"><span data-stu-id="3d2d9-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="3d2d9-143">Andmeallika värskendamine</span><span class="sxs-lookup"><span data-stu-id="3d2d9-143">Refresh a data source</span></span>

<span data-ttu-id="3d2d9-144">Andmeallikaid saab värskendada automaatse ajakava järgi või soovi korral käsitsi.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="3d2d9-145">Minge jaotisse **Haldus** > **Süsteem** > [**Ajastamine**](system.md#schedule-tab), et konfigureerida kõigi valmendatud andmeallikate ajastatud värskendamine.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="3d2d9-146">Andmeallika värskendamiseks mis tahes ajal toimige järgmiselt.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="3d2d9-147">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="3d2d9-148">Valige värskendatava andmeallika kõrval vertikaalne ellips ja valige **Värskenda** ripploendist.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="3d2d9-149">Andmeallika jaoks käivitatakse nüüd käsitsivärskendamine.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="3d2d9-150">Andmeallika värskendamine uuendab nii olemiskeemi kui ka kõigi andmeallikas määratud olemite andmeid.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="3d2d9-151">Kui soovite olemasoleva värskendamise tühistada, klõpsake **Lõpeta värskendamine** ja andmeallikas taastatakse viimase värskendamise olekusse.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="3d2d9-152">Andmeallika kustutamine</span><span class="sxs-lookup"><span data-stu-id="3d2d9-152">Delete a data source</span></span>

1. <span data-ttu-id="3d2d9-153">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="3d2d9-154">Valige eemaldatava andmeallika kõrval vertikaalne ellips ja valige **Kustuta** ripploendist.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="3d2d9-155">Kinnitage, et soovite kustutada.</span><span class="sxs-lookup"><span data-stu-id="3d2d9-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
