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
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085525"
---
# <a name="data-sources-overview"></a><span data-ttu-id="1f2c1-103">Andmeallikate ülevaade</span><span class="sxs-lookup"><span data-stu-id="1f2c1-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1f2c1-104">Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioon ühendub andmetega, mis on pärit paljudest allikatest.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="1f2c1-105">Andmeallikaga ühendamist nimetatakse sageli *andmete sisestamiseks*.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="1f2c1-106">Pärast andmete sisestamist saate need [ühendada](data-unification.md) ja nendega toiminguid teha.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="1f2c1-107">Lisa andmeallikas</span><span class="sxs-lookup"><span data-stu-id="1f2c1-107">Add a data source</span></span>

<span data-ttu-id="1f2c1-108">Vaadake üksikasjalikke artikleid selle kohta, kuidas andmeallikat lisada, olenevalt sellest, millise suvandi te valite.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="1f2c1-109">Saate andmeallikat lisada kolmel peamisel viisil.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="1f2c1-110">Kümnete Power Query konnektorite kaudu</span><span class="sxs-lookup"><span data-stu-id="1f2c1-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="1f2c1-111">Common Data Modeli kaustast</span><span class="sxs-lookup"><span data-stu-id="1f2c1-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="1f2c1-112">Enda Common Data Service’i andmejärvest</span><span class="sxs-lookup"><span data-stu-id="1f2c1-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="1f2c1-113">Andmete lisamine asutusesisene andmeallikatest</span><span class="sxs-lookup"><span data-stu-id="1f2c1-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="1f2c1-114">Kohalike andmeallikate andmete sisestamine vaatajaskonna statistikas toetub Power Platform andmevoogudele.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="1f2c1-115">Andmevooge saab lubada Customer Insights kaudu [pakkudes Microsoft Dataverse keskkonna URL-i](manage-environments.md#create-an-environment-in-an-existing-organization) keskkonna seadistamisel.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="1f2c1-116">Andmeallikad, mis luuakse pärast keskkonna Dataverse seostamist Customer Insights, kasutavad [Power Platform andmevooge](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) vaikimisi.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="1f2c1-117">Andmevood toetavad kohapealset ühenduvust andmelüüside abil.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="1f2c1-118">Eemaldage ja looge uuesti andmeallikad, mis olid olemas enne seda, kui Dataverse -i keskkond seostati [asutusesisese andmelüüside kasutamisega](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="1f2c1-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="1f2c1-119">Andmevõrgud olemasolevast Power BI või Power Apps keskkonnast on nähtavad ja saate neid uuesti kasutada jaotises Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="1f2c1-120">Andmeallikate lehel kuvatakse lingid, et minna Power Platform keskkonda, kus te saate vaadata ja konfigureerida asutusesiseseid andmelüüse.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="1f2c1-121">Sisestatud andmete läbivaatus</span><span class="sxs-lookup"><span data-stu-id="1f2c1-121">Review ingested data</span></span>

<span data-ttu-id="1f2c1-122">Näete iga sisestatud andmeallika nime, selle olekut ja viimast korda, kui neid andmeid selle allika jaoks värskendati.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="1f2c1-123">Saate andmeallikate loendit iga veeru järgi sortida.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1f2c1-124">![Andmeallikas lisatud](media/configure-data-datasource-added.png "Andmeallikas lisatud")</span><span class="sxs-lookup"><span data-stu-id="1f2c1-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="1f2c1-125">Olek</span><span class="sxs-lookup"><span data-stu-id="1f2c1-125">Status</span></span>  |<span data-ttu-id="1f2c1-126">Kirjeldus</span><span class="sxs-lookup"><span data-stu-id="1f2c1-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="1f2c1-127">Õnnestunud</span><span class="sxs-lookup"><span data-stu-id="1f2c1-127">Successful</span></span>   |<span data-ttu-id="1f2c1-128">Andmeallikas valmendati edukalt juhul, kui veerus **Värskendatud** on toodud aeg.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="1f2c1-129">Pole käivitatud</span><span class="sxs-lookup"><span data-stu-id="1f2c1-129">Not started</span></span>   |<span data-ttu-id="1f2c1-130">Andmeallikas pole valmendatud andmeid või see on ikka mustandirežiimis.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="1f2c1-131">Värskendamine</span><span class="sxs-lookup"><span data-stu-id="1f2c1-131">Refreshing</span></span>    |<span data-ttu-id="1f2c1-132">Andmete sisestamine on pooleli.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-132">Data ingestion is in progress.</span></span> <span data-ttu-id="1f2c1-133">Selle toimingu tühistamiseks valige **Peata värskendamine** **Toimingute** veerus.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="1f2c1-134">Andmeallika värskendamise peatamine ennistab selle viimase värskendamise olekusse.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="1f2c1-135">Ebaõnnestus</span><span class="sxs-lookup"><span data-stu-id="1f2c1-135">Failed</span></span>     |<span data-ttu-id="1f2c1-136">Andmete sisestamisel ilmnesid tõrked.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="1f2c1-137">Üksikasjade kuvamiseks valige väärtus mis tahes andmeallika veerus **Olek**.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="1f2c1-138">Laiendage paanil **Edenemise üksikasjad** suvandit **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="1f2c1-139">Valige **Kuva üksikasjad**, et saada värskendamise oleku kohta lisateavet, sh tõrke üksikasjad ja allavooluprotsesside värskendused.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="1f2c1-140">Andmete laadimine võib veidi aega võtta.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-140">Loading data can take some time.</span></span> <span data-ttu-id="1f2c1-141">Pärast edukat värskendamist saab lisatud andmeid vaadata lehel **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="1f2c1-142">Lisateavet vt jaotisest [Olemid](entities.md).</span><span class="sxs-lookup"><span data-stu-id="1f2c1-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="1f2c1-143">Andmeallika värskendamine</span><span class="sxs-lookup"><span data-stu-id="1f2c1-143">Refresh a data source</span></span>

<span data-ttu-id="1f2c1-144">Andmeallikaid saab värskendada automaatse ajakava järgi või soovi korral käsitsi.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="1f2c1-145">Minge jaotisse **Haldus** > **Süsteem** > [**Ajastamine**](system.md#schedule-tab), et konfigureerida kõigi valmendatud andmeallikate ajastatud värskendamine.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="1f2c1-146">Andmeallika värskendamiseks mis tahes ajal toimige järgmiselt.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="1f2c1-147">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**</span><span class="sxs-lookup"><span data-stu-id="1f2c1-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="1f2c1-148">Valige värskendamist vajava andmeallika kõrvalt vertikaalne kolmikpunkt ja valige ripploendist **Värskenda**.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="1f2c1-149">Andmeallika jaoks käivitatakse nüüd käsitsivärskendamine.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="1f2c1-150">Andmeallika värskendamine uuendab nii olemiskeemi kui ka kõigi andmeallikas määratud olemite andmeid.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="1f2c1-151">Kui soovite olemasoleva värskendamise tühistada, klõpsake **Lõpeta värskendamine** ja andmeallikas taastatakse viimase värskendamise olekusse.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="1f2c1-152">Andmeallika kustutamine</span><span class="sxs-lookup"><span data-stu-id="1f2c1-152">Delete a data source</span></span>

1. <span data-ttu-id="1f2c1-153">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="1f2c1-154">Valige eemaldatava andmeallika kõrval asuv vertikaalne kolmikpunkt ja valige rippmenüüst suvand **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="1f2c1-155">Kinnitage, et soovite kustutada.</span><span class="sxs-lookup"><span data-stu-id="1f2c1-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
