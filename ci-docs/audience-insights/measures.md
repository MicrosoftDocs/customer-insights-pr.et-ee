---
title: Mõõdikute loomine ja haldamine
description: Määratleda ettevõtte äritegevuse analüüsimiseks ja kajastamiseks vajalikud näitajad.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654727"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="64856-103">Meetmete määratlemine ja haldamine</span><span class="sxs-lookup"><span data-stu-id="64856-103">Define and manage measures</span></span>

<span data-ttu-id="64856-104">Näitajad aitavad teil paremini mõista kliendi käitumist ja ärijõudlust, tagastades [ühildatud profiilidest](data-unification.md) olulised väärtused.</span><span class="sxs-lookup"><span data-stu-id="64856-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="64856-105">Näiteks soovib ettevõte vaadata, kui palju on kulutatud *kliendi kohta*, et mõista kliendi individuaalset ostuajalugu.</span><span class="sxs-lookup"><span data-stu-id="64856-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="64856-106">Või mõõta *ettevõtte kogu müüki*, et saada aru ettevõtte kogutulu jaotust.</span><span class="sxs-lookup"><span data-stu-id="64856-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="64856-107">Näitajad luuakse meetmete ehitaja abil, mis on erinevate tehtemärkide ja lihtsate vastendussuvanditega andmepäringu platvorm.</span><span class="sxs-lookup"><span data-stu-id="64856-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="64856-108">See võimaldab filtreerida andmeid, rühmitada tulemusi, tuvastada [olemite seoseteid](relationships.md) ja kuvada väljundi eelvaadet.</span><span class="sxs-lookup"><span data-stu-id="64856-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="64856-109">Kasutage äritegevuste plaanimiseks näitaja ehitajat, pärides kliendiandmeid ja väljastades ülevaateid.</span><span class="sxs-lookup"><span data-stu-id="64856-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="64856-110">Näiteks *kogukulu ühe kliendi kohta* ja *kogutulu ühe kliendi kohta* loomine aitab tuvastada suure kulutamise, kuid suure tootlusega klientide rühm.</span><span class="sxs-lookup"><span data-stu-id="64856-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="64856-111">Saate [luua segmendi](segments.md), mis aitab teil teha järgmist.</span><span class="sxs-lookup"><span data-stu-id="64856-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="64856-112">Meetme loomine</span><span class="sxs-lookup"><span data-stu-id="64856-112">Create a measure</span></span>

<span data-ttu-id="64856-113">Selles jaotises tutvustatakse uue näitaja loomist nullist.</span><span class="sxs-lookup"><span data-stu-id="64856-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="64856-114">Saate ehitada näitaja andmeatribuutidega andmeüksustelt, millel on kliendi olemiga ühenduse loomiseks suhe loodud.</span><span class="sxs-lookup"><span data-stu-id="64856-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="64856-115">Avage sihtrühmaülevaadetes jaotis **Näitajad**.</span><span class="sxs-lookup"><span data-stu-id="64856-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="64856-116">Tehke valik **Uus**.</span><span class="sxs-lookup"><span data-stu-id="64856-116">Select **New**.</span></span>

1. <span data-ttu-id="64856-117">Valige **Redigeeri nimi** ja sisestage näitaja **Nimi**.</span><span class="sxs-lookup"><span data-stu-id="64856-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="64856-118">Kui teie uuel näitaja konfiguratsioonil on ainult kaks välja– näiteks CustomerID ja üks arvutus, lisatakse väljund uue veeruna süsteemi genereeritud olemile nimega Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="64856-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="64856-119">Näete näitaja väärtust ühtses kliendiprofiilis.</span><span class="sxs-lookup"><span data-stu-id="64856-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="64856-120">Muud näitajad loovad oma olemeid.</span><span class="sxs-lookup"><span data-stu-id="64856-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="64856-121">Valige konfiguratsioonialas koondamisfunktsioon ripploendist **Vali funktsioon**.</span><span class="sxs-lookup"><span data-stu-id="64856-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="64856-122">Koondamisfunktsioonid on järgmised.</span><span class="sxs-lookup"><span data-stu-id="64856-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="64856-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="64856-123">**Sum**</span></span>
   - <span data-ttu-id="64856-124">**Keskmine**</span><span class="sxs-lookup"><span data-stu-id="64856-124">**Average**</span></span>
   - <span data-ttu-id="64856-125">**Loenda**</span><span class="sxs-lookup"><span data-stu-id="64856-125">**Count**</span></span>
   - <span data-ttu-id="64856-126">**Kordumatu arv**</span><span class="sxs-lookup"><span data-stu-id="64856-126">**Count Unique**</span></span>
   - <span data-ttu-id="64856-127">**Maks.**</span><span class="sxs-lookup"><span data-stu-id="64856-127">**Max**</span></span>
   - <span data-ttu-id="64856-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="64856-128">**Min**</span></span>
   - <span data-ttu-id="64856-129">**Esimene**: võtab andmekirje esimese väärtuse</span><span class="sxs-lookup"><span data-stu-id="64856-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="64856-130">**Viimane**: võtab andmekirjesse lisatud viimase väärtuse</span><span class="sxs-lookup"><span data-stu-id="64856-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Tehtemärgid näitaja arvutamiseks.":::

1. <span data-ttu-id="64856-132">Valige **Lisa atribuut**, et valida andmed, mida selle näitaja loomiseks vajate.</span><span class="sxs-lookup"><span data-stu-id="64856-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="64856-133">Valige vaheleht **Attribuudid**.</span><span class="sxs-lookup"><span data-stu-id="64856-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="64856-134">Andmeolem: valige olem, mis sisaldab mõõdetavat atribuuti.</span><span class="sxs-lookup"><span data-stu-id="64856-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="64856-135">Andmeatribuut: valige atribuut, mida soovite näitaja arvutamiseks koondamisfunktsioonis kasutada.</span><span class="sxs-lookup"><span data-stu-id="64856-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="64856-136">Korraga saate valida ainult ühe atribuudi.</span><span class="sxs-lookup"><span data-stu-id="64856-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="64856-137">Olemasolevast näitajast andmeatribuudi valimiseks klõpsake vahekaarti **Näitajad** või otsige olemi või näitaja nime.</span><span class="sxs-lookup"><span data-stu-id="64856-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="64856-138">Valige **Lisa**, et lisada atribuut näitajale.</span><span class="sxs-lookup"><span data-stu-id="64856-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Valige arvutuses soovitud atribuut.":::

1. <span data-ttu-id="64856-140">Keerukamate näitajate loomiseks võite lisada mõõtmisfunktsioonile rohkem atribuute või kasutada matemaatilisi tehtemärke.</span><span class="sxs-lookup"><span data-stu-id="64856-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Keerukama näitaja loomine tehtemärkidega.":::

1. <span data-ttu-id="64856-142">Filtrite lisamiseks valige konfiguratsiooniala **Filtreeri**.</span><span class="sxs-lookup"><span data-stu-id="64856-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="64856-143">Valige paani **Filtrid** jaotisest **Lisa atribuut** atribuut, mida soovite filtrite loomiseks kasutada.</span><span class="sxs-lookup"><span data-stu-id="64856-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="64856-144">Määrake filtritehted iga valitud atribuudi filtri määratlemiseks.</span><span class="sxs-lookup"><span data-stu-id="64856-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="64856-145">Valige **Rakenda**, et lisada filtrid näitajale.</span><span class="sxs-lookup"><span data-stu-id="64856-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="64856-146">Dimensioonide lisamiseks valige konfiguratsioonialas **Dimensioon**.</span><span class="sxs-lookup"><span data-stu-id="64856-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="64856-147">Dimensioonid kuvatakse näitaja väljundolemis veergudena.</span><span class="sxs-lookup"><span data-stu-id="64856-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="64856-148">Valige **Redigeeri dimensioonid**, et lisada andmeatribuute, mille järgi soovite näitaja väärtusi rühmitada.</span><span class="sxs-lookup"><span data-stu-id="64856-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="64856-149">Näiteks linn või sugu.</span><span class="sxs-lookup"><span data-stu-id="64856-149">For example, city or gender.</span></span> <span data-ttu-id="64856-150">*Klienditaseme näitajate loomiseks* valitakse vaikimisi *CustomerID* dimensioon.</span><span class="sxs-lookup"><span data-stu-id="64856-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="64856-151">Kui soovite luua *äritaseme näitajaid*, saate vaikeeelise eemaldada.</span><span class="sxs-lookup"><span data-stu-id="64856-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="64856-152">Valige **Valmis**, et lisada dimensioonid näitajale.</span><span class="sxs-lookup"><span data-stu-id="64856-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="64856-153">Kui vastendatud andme- ja olemi *Klient* vahel on mitu teed, peate valima ühe tuvastatud [olemi suhte teedest](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="64856-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="64856-154">Näitaja tulemused võivad sõltuvalt valitud teest erineda.</span><span class="sxs-lookup"><span data-stu-id="64856-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="64856-155">Valige **andmeelistused** ja seejärel olemi tee, mida tuleks oma näitaja tuvastamiseks kasutada.</span><span class="sxs-lookup"><span data-stu-id="64856-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="64856-156">Kui olemi *Klient* juurde on ainult üks tee, siis seda juhtelementi ei näidata.</span><span class="sxs-lookup"><span data-stu-id="64856-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="64856-157">Valiku rakendamiseks valige suvand **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="64856-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Saate valida näitajale olemi tee.":::

1. <span data-ttu-id="64856-159">Kui soovite näitajat veel arvutada, valige **Uus arvutus**.</span><span class="sxs-lookup"><span data-stu-id="64856-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="64856-160">Uute arvutuste jaoks saate kasutada ainult samal olemiteel olevaid üksusi.</span><span class="sxs-lookup"><span data-stu-id="64856-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="64856-161">Täiendavad arvutused kuvatakse näitaja väljundolemis uute veergudena.</span><span class="sxs-lookup"><span data-stu-id="64856-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="64856-162">Valige näitajast arvutuse **Duplitseerimiseks**, **Ümber nimetamiseks** või **Eemaldamiseks** **...**.</span><span class="sxs-lookup"><span data-stu-id="64856-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="64856-163">**Eelvaatealal** näete näitaja väljundolemi andmeskeemi (sh filtreid ja dimensioone).</span><span class="sxs-lookup"><span data-stu-id="64856-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="64856-164">Eelvaade reageerib dünaamiliselt konfiguratsiooni muudatustele.</span><span class="sxs-lookup"><span data-stu-id="64856-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="64856-165">Konfigureeritud näitaja tulemuste arvutamiseks valige **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="64856-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="64856-166">Kui soovite praeguse konfiguratsiooni säilitada ja näitajat hiljem käitada, valige **Salvesta ja sule**.</span><span class="sxs-lookup"><span data-stu-id="64856-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="64856-167">Vastloodud näitaja nägemiseks loendis, valige **Näitajad**.</span><span class="sxs-lookup"><span data-stu-id="64856-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="64856-168">Meetmete haldamine</span><span class="sxs-lookup"><span data-stu-id="64856-168">Manage your measures</span></span>

<span data-ttu-id="64856-169">Pärast [näitaja loomist](#create-a-measure) näete lehel **Näitajad** näitajate loendit.</span><span class="sxs-lookup"><span data-stu-id="64856-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="64856-170">Leiate teavet näidiku tüübi, autori, loomise kuupäeva, staatuse ja oleku kohta.</span><span class="sxs-lookup"><span data-stu-id="64856-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="64856-171">Kui valite loendist näitaja, saate väljundit eelvaadata ja .CSV-faili alla laadida.</span><span class="sxs-lookup"><span data-stu-id="64856-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="64856-172">Kõigi oma meetmete korraga värskendamiseks valige **Värskenda kõik** ilma kindlat meedet valimata.</span><span class="sxs-lookup"><span data-stu-id="64856-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="64856-173">![Toimingud üksikute meetmete haldamiseks](media/measure-actions.png "Toimingud üksikute meetmete haldamiseks")</span><span class="sxs-lookup"><span data-stu-id="64856-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="64856-174">Valige loendist soovitud näitaja järgmiste suvandite jaoks.</span><span class="sxs-lookup"><span data-stu-id="64856-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="64856-175">Valige meetme nimi, et näha selle üksikasju.</span><span class="sxs-lookup"><span data-stu-id="64856-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="64856-176">Meetme konfiguratsiooni **Redigeerimine**.</span><span class="sxs-lookup"><span data-stu-id="64856-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="64856-177">**Värskendage** näitajat, võttes aluseks värskeimad andmed.</span><span class="sxs-lookup"><span data-stu-id="64856-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="64856-178">Meetme **Ümbernimetamine**.</span><span class="sxs-lookup"><span data-stu-id="64856-178">**Rename** the measure.</span></span>
- <span data-ttu-id="64856-179">Meetme **Kustutamine**.</span><span class="sxs-lookup"><span data-stu-id="64856-179">**Delete** the measure.</span></span>
- <span data-ttu-id="64856-180">**Aktiveeri** või **Inaktiveeri**.</span><span class="sxs-lookup"><span data-stu-id="64856-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="64856-181">Passiivseid näitajad ei värskendata [kavandatud värskenduse](system.md#schedule-tab) ajal.</span><span class="sxs-lookup"><span data-stu-id="64856-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="64856-182">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="64856-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="64856-183">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="64856-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="64856-184">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="64856-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="64856-185">Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="64856-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="64856-186">Järgmine etapp</span><span class="sxs-lookup"><span data-stu-id="64856-186">Next step</span></span>

<span data-ttu-id="64856-187">[Kliendisegmendi loomiseks](segments.md) saate kasutada olemasolevaid näitajaid.</span><span class="sxs-lookup"><span data-stu-id="64856-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]