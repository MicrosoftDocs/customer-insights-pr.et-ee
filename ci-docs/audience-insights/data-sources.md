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
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887889"
---
# <a name="data-sources-overview"></a><span data-ttu-id="d392e-103">Andmeallikate ülevaade</span><span class="sxs-lookup"><span data-stu-id="d392e-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d392e-104">Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioon ühendub andmetega, mis on pärit paljudest allikatest.</span><span class="sxs-lookup"><span data-stu-id="d392e-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="d392e-105">Andmeallikaga ühendamist nimetatakse sageli *andmete sisestamiseks*.</span><span class="sxs-lookup"><span data-stu-id="d392e-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="d392e-106">Pärast andmete sisestamist saate need [ühendada](data-unification.md) ja nendega toiminguid teha.</span><span class="sxs-lookup"><span data-stu-id="d392e-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="d392e-107">Lisa andmeallikas</span><span class="sxs-lookup"><span data-stu-id="d392e-107">Add a data source</span></span>

<span data-ttu-id="d392e-108">Vaadake üksikasjalikke artikleid selle kohta, kuidas andmeallikat lisada, olenevalt sellest, millise suvandi te valite.</span><span class="sxs-lookup"><span data-stu-id="d392e-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="d392e-109">Saate andmeallikat lisada kolmel peamisel viisil.</span><span class="sxs-lookup"><span data-stu-id="d392e-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="d392e-110">Kümnete Power Query konnektorite kaudu</span><span class="sxs-lookup"><span data-stu-id="d392e-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="d392e-111">Common Data Modeli kaustast</span><span class="sxs-lookup"><span data-stu-id="d392e-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="d392e-112">Enda Common Data Service’i andmejärvest</span><span class="sxs-lookup"><span data-stu-id="d392e-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="d392e-113">Andmete lisamine asutusesisene andmeallikatest</span><span class="sxs-lookup"><span data-stu-id="d392e-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="d392e-114">Kohalike andmeallikate andmete sisestamine vaatajaskonna statistikas toetub Power Platform andmevoogudele.</span><span class="sxs-lookup"><span data-stu-id="d392e-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="d392e-115">Andmevooge saab lubada Customer Insights kaudu [pakkudes Microsoft Dataverse keskkonna URL-i](manage-environments.md#create-an-environment-in-an-existing-organization) keskkonna seadistamisel.</span><span class="sxs-lookup"><span data-stu-id="d392e-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="d392e-116">Andmeallikad, mis luuakse pärast keskkonna Dataverse seostamist Customer Insights, kasutavad [Power Platform andmevooge](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) vaikimisi.</span><span class="sxs-lookup"><span data-stu-id="d392e-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="d392e-117">Andmevood toetavad kohapealset ühenduvust andmelüüside abil.</span><span class="sxs-lookup"><span data-stu-id="d392e-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="d392e-118">Eemaldage ja looge uuesti andmeallikad, mis olid olemas enne seda, kui Dataverse keskkond seostati asutusesisese andmelüüside kasutamisega.</span><span class="sxs-lookup"><span data-stu-id="d392e-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="d392e-119">Andmevõrgud olemasolevast Power BI või Power Apps keskkonnast on nähtavad ja saate neid uuesti kasutada jaotises Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d392e-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="d392e-120">Andmeallikate lehel kuvatakse lingid, et minna Power Platform keskkonda, kus te saate vaadata ja konfigureerida asutusesiseseid andmelüüse.</span><span class="sxs-lookup"><span data-stu-id="d392e-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="Andmeallikate lehe kuvatõmmis, kus on kuvatud Power Platform keskkonda viivad lingid.":::

## <a name="review-ingested-data"></a><span data-ttu-id="d392e-122">Sisestatud andmete läbivaatus</span><span class="sxs-lookup"><span data-stu-id="d392e-122">Review ingested data</span></span>

<span data-ttu-id="d392e-123">Näete iga sisestatud andmeallika nime, selle olekut ja viimast korda, kui neid andmeid selle allika jaoks värskendati.</span><span class="sxs-lookup"><span data-stu-id="d392e-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="d392e-124">Saate andmeallikate loendit iga veeru järgi sortida.</span><span class="sxs-lookup"><span data-stu-id="d392e-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d392e-125">![Andmeallikas lisatud](media/configure-data-datasource-added.png "Andmeallikas lisatud")</span><span class="sxs-lookup"><span data-stu-id="d392e-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="d392e-126">Olek</span><span class="sxs-lookup"><span data-stu-id="d392e-126">Status</span></span>  |<span data-ttu-id="d392e-127">Kirjeldus</span><span class="sxs-lookup"><span data-stu-id="d392e-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d392e-128">Õnnestunud</span><span class="sxs-lookup"><span data-stu-id="d392e-128">Successful</span></span>   |<span data-ttu-id="d392e-129">Andmeallikas valmendati edukalt juhul, kui veerus **Värskendatud** on toodud aeg.</span><span class="sxs-lookup"><span data-stu-id="d392e-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="d392e-130">Pole käivitatud</span><span class="sxs-lookup"><span data-stu-id="d392e-130">Not started</span></span>   |<span data-ttu-id="d392e-131">Andmeallikas pole valmendatud andmeid või see on ikka mustandirežiimis.</span><span class="sxs-lookup"><span data-stu-id="d392e-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="d392e-132">Värskendamine</span><span class="sxs-lookup"><span data-stu-id="d392e-132">Refreshing</span></span>    |<span data-ttu-id="d392e-133">Andmete sisestamine on pooleli.</span><span class="sxs-lookup"><span data-stu-id="d392e-133">Data ingestion is in progress.</span></span> <span data-ttu-id="d392e-134">Selle toimingu tühistamiseks valige **Peata värskendamine** **Toimingute** veerus.</span><span class="sxs-lookup"><span data-stu-id="d392e-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="d392e-135">Andmeallika värskendamise peatamine ennistab selle viimase värskendamise olekusse.</span><span class="sxs-lookup"><span data-stu-id="d392e-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="d392e-136">Ebaõnnestus</span><span class="sxs-lookup"><span data-stu-id="d392e-136">Failed</span></span>     |<span data-ttu-id="d392e-137">Andmete sisestamisel ilmnesid tõrked.</span><span class="sxs-lookup"><span data-stu-id="d392e-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="d392e-138">Üksikasjade kuvamiseks valige väärtus mis tahes andmeallika veerus **Olek**.</span><span class="sxs-lookup"><span data-stu-id="d392e-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="d392e-139">Laiendage paanil **Edenemise üksikasjad** suvandit **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="d392e-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="d392e-140">Valige **Kuva üksikasjad**, et saada värskendamise oleku kohta lisateavet, sh tõrke üksikasjad ja allavooluprotsesside värskendused.</span><span class="sxs-lookup"><span data-stu-id="d392e-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="d392e-141">Andmete laadimine võib veidi aega võtta.</span><span class="sxs-lookup"><span data-stu-id="d392e-141">Loading data can take some time.</span></span> <span data-ttu-id="d392e-142">Pärast edukat värskendamist saab lisatud andmeid vaadata lehel **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="d392e-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="d392e-143">Lisateavet vt jaotisest [Olemid](entities.md).</span><span class="sxs-lookup"><span data-stu-id="d392e-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="d392e-144">Andmeallika värskendamine</span><span class="sxs-lookup"><span data-stu-id="d392e-144">Refresh a data source</span></span>

<span data-ttu-id="d392e-145">Andmeallikaid saab värskendada automaatse ajakava järgi või soovi korral käsitsi.</span><span class="sxs-lookup"><span data-stu-id="d392e-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="d392e-146">Minge jaotisse **Haldus** > **Süsteem** > [**Ajastamine**](system.md#schedule-tab), et konfigureerida kõigi valmendatud andmeallikate ajastatud värskendamine.</span><span class="sxs-lookup"><span data-stu-id="d392e-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="d392e-147">Andmeallika värskendamiseks mis tahes ajal toimige järgmiselt.</span><span class="sxs-lookup"><span data-stu-id="d392e-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="d392e-148">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**</span><span class="sxs-lookup"><span data-stu-id="d392e-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="d392e-149">Valige värskendamist vajava andmeallika kõrvalt vertikaalne kolmikpunkt ja valige ripploendist **Värskenda**.</span><span class="sxs-lookup"><span data-stu-id="d392e-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="d392e-150">Andmeallika jaoks käivitatakse nüüd käsitsivärskendamine.</span><span class="sxs-lookup"><span data-stu-id="d392e-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="d392e-151">Andmeallika värskendamine uuendab nii olemiskeemi kui ka kõigi andmeallikas määratud olemite andmeid.</span><span class="sxs-lookup"><span data-stu-id="d392e-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="d392e-152">Kui soovite olemasoleva värskendamise tühistada, klõpsake **Lõpeta värskendamine** ja andmeallikas taastatakse viimase värskendamise olekusse.</span><span class="sxs-lookup"><span data-stu-id="d392e-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="d392e-153">Andmeallika kustutamine</span><span class="sxs-lookup"><span data-stu-id="d392e-153">Delete a data source</span></span>

1. <span data-ttu-id="d392e-154">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="d392e-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d392e-155">Valige eemaldatava andmeallika kõrval asuv vertikaalne kolmikpunkt ja valige rippmenüüst suvand **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="d392e-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="d392e-156">Kinnitage, et soovite kustutada.</span><span class="sxs-lookup"><span data-stu-id="d392e-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
