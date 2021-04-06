---
title: Power BI konnektor
description: Õppige kasutama konnektorit Dynamics 365 Customer Insights Power BI-s.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596034"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="f303e-103">Power BI’i konnektor (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="f303e-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="f303e-104">Visualiseerige oma andmeid rakendusega Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="f303e-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="f303e-105">Oma ühendatud kliendiandmetega täiendavate ülevaadete ja aruannete loomine.</span><span class="sxs-lookup"><span data-stu-id="f303e-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f303e-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="f303e-106">Prerequisites</span></span>

- <span data-ttu-id="f303e-107">Teil on koondatud kliendiprofiilid.</span><span class="sxs-lookup"><span data-stu-id="f303e-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="f303e-108">Teie arvutisse on installitud [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) uusim versioon.</span><span class="sxs-lookup"><span data-stu-id="f303e-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="f303e-109">[Lisateave: Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="f303e-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="f303e-110">Konnektori konfigureerimine Power BI jaoks</span><span class="sxs-lookup"><span data-stu-id="f303e-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="f303e-111">Valige rakenduses Power BI Desktop **Fail** > **Too andmed**.</span><span class="sxs-lookup"><span data-stu-id="f303e-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="f303e-112">Valige **Kuva veel** ja otsige rakendust **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="f303e-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="f303e-113">Valige käsk **Ühenda**.</span><span class="sxs-lookup"><span data-stu-id="f303e-113">Select **Connect**.</span></span>

1. <span data-ttu-id="f303e-114">**Logige sisse** samale organisatsiooni kontole, mida kasutate Customer Insightsi jaoks, ja valige **Ühenda**.</span><span class="sxs-lookup"><span data-stu-id="f303e-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="f303e-115">Selles etapis osutavat kontot kasutatakse Customer Insightsist andmete toomiseks ja see ei pea olema sama, mille abil olete Power BI-sse sisse logitud.</span><span class="sxs-lookup"><span data-stu-id="f303e-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="f303e-116">Andmete toomiseks kasutatava konto lähtestamiseks avage Power BI ja minge jaotisse **Fail** > **Suvandid** > **Sätted** > **Andmeallika sätted**.</span><span class="sxs-lookup"><span data-stu-id="f303e-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="f303e-117">Valige andmeallikate loendist **Dynamics 365 Customer Insightsi sisselogimine** ja seejärel suvand **Tühista õigused**.</span><span class="sxs-lookup"><span data-stu-id="f303e-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="f303e-118">Dialoogiboksis **Navigaator**.</span><span class="sxs-lookup"><span data-stu-id="f303e-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="f303e-119">näete kõigi keskkondade loendit, millele teil on juurdepääs.</span><span class="sxs-lookup"><span data-stu-id="f303e-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="f303e-120">Laiendage keskkond ja avage mis tahes kaust (olemid, näitajad, segmendid, rikastamised).</span><span class="sxs-lookup"><span data-stu-id="f303e-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="f303e-121">Näiteks avage kaust **Olemid**, et näha kõiki olemeid, mida saate importida.</span><span class="sxs-lookup"><span data-stu-id="f303e-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="f303e-122">![Power BI konnektori navigaator](media/power-bi-navigator.png "Power BI konnektori navigaator")</span><span class="sxs-lookup"><span data-stu-id="f303e-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="f303e-123">Valige kaasatavate olemite kõrval olevad märkeruudud ja vajutage **Laadi**.</span><span class="sxs-lookup"><span data-stu-id="f303e-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="f303e-124">Saate valida mitu olemit erinevatest keskkondadest.</span><span class="sxs-lookup"><span data-stu-id="f303e-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="f303e-125">Olemite laadimisel näete laadivat dialoogiboksi.</span><span class="sxs-lookup"><span data-stu-id="f303e-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="f303e-126">Kui kõik teie valitud olemid on laaditud, saate Power BI funktsioone kasutada andmete visualiseerimiseks.</span><span class="sxs-lookup"><span data-stu-id="f303e-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="f303e-127">Suured andmekogumid</span><span class="sxs-lookup"><span data-stu-id="f303e-127">Large data sets</span></span>

<span data-ttu-id="f303e-128">Customer Insightsi Power BI konnektor on loodud töötama andmekogumitega, mis sisaldavad kuni 1 miljon kliendiprofiili.</span><span class="sxs-lookup"><span data-stu-id="f303e-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="f303e-129">Suurte andmekogumite importimine võib toimida, kuid see võtab kaua aega.</span><span class="sxs-lookup"><span data-stu-id="f303e-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="f303e-130">Lisaks võib protsess Power BI piirangute tõttu aeguda.</span><span class="sxs-lookup"><span data-stu-id="f303e-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="f303e-131">Lisateavet vaadake teemast [Power BI: soovitused mahukate andmekogumite jaoks](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="f303e-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="f303e-132">Andmete alamhulgaga töötamine</span><span class="sxs-lookup"><span data-stu-id="f303e-132">Work with a subset of data</span></span>

<span data-ttu-id="f303e-133">Kaaluge andmete alamhulgaga töötamist.</span><span class="sxs-lookup"><span data-stu-id="f303e-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="f303e-134">Näiteks saate luua [segmente](segments.md), selle asemel et eksportida kõik kliendikirjed Power BI-sse.</span><span class="sxs-lookup"><span data-stu-id="f303e-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f303e-135">Tõrkeotsing</span><span class="sxs-lookup"><span data-stu-id="f303e-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="f303e-136">Customer Insightsi keskkonda ei kuvata Power BI-s</span><span class="sxs-lookup"><span data-stu-id="f303e-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="f303e-137">Keskkond, millel on kahe identse olemi vahel määratletud mitu [seost](relationships.md), pole Power BI konnektoris saadaval.</span><span class="sxs-lookup"><span data-stu-id="f303e-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="f303e-138">Saate topeltseoseid tuvastada ja eemaldada.</span><span class="sxs-lookup"><span data-stu-id="f303e-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="f303e-139">Avage oma Power BI-s puuduva keskkonna sihtrühmaülevaadetes jaotis **Andmed** > **Seosed**.</span><span class="sxs-lookup"><span data-stu-id="f303e-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="f303e-140">Topeltseoste tuvastamiseks tehke järgmist.</span><span class="sxs-lookup"><span data-stu-id="f303e-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="f303e-141">Kontrollige, kas kahe sama olemi vahel on määratletud mitu seost.</span><span class="sxs-lookup"><span data-stu-id="f303e-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="f303e-142">Kontrollige, kas kahe koondamisprotsessi kaasatud olemi vahel on loodud seos.</span><span class="sxs-lookup"><span data-stu-id="f303e-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="f303e-143">Kõigi koondamisprotsessi kaasatud olemite vahel on määratletud varjatud seos.</span><span class="sxs-lookup"><span data-stu-id="f303e-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="f303e-144">Eemaldage tuvastatud topeltseosed.</span><span class="sxs-lookup"><span data-stu-id="f303e-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="f303e-145">Pärast topeltseoste eemaldamist proovige Power BI konnektor uuesti konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="f303e-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="f303e-146">Keskkond peaks olema nüüd saadaval.</span><span class="sxs-lookup"><span data-stu-id="f303e-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]