---
title: Mõõdikute loomine ja haldamine
description: Määratleda ettevõtte äritegevuse analüüsimiseks ja kajastamiseks vajalikud näitajad.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049245"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="0fe1e-103">Meetmete määratlemine ja haldamine</span><span class="sxs-lookup"><span data-stu-id="0fe1e-103">Define and manage measures</span></span>

<span data-ttu-id="0fe1e-104">See aitab teil paremini mõista kliendi käitumist ja äritegevust.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="0fe1e-105">Nad vaatavad asjakohaseid [ühendatud profilide](data-unification.md) väärtusi.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="0fe1e-106">Näiteks soovib ettevõte näha *kogukulu kliendile*, et mõista üksikkliendi ostuajalugu või mõõta *ettevõtte kogumüüki*, et saada aru kogu ettevõtte müügituludest.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="0fe1e-107">Näitajad luuakse meetmete ehitaja abil, mis on erinevate tehtemärkide ja lihtsate vastendussuvanditega andmepäringu platvorm.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="0fe1e-108">See võimaldab filtreerida andmeid, rühmitada tulemusi, tuvastada [olemite seoseteid](relationships.md) ja kuvada väljundi eelvaadet.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="0fe1e-109">Kasutage äritegevuste plaanimiseks näitaja ehitajat, pärides kliendiandmeid ja väljastades ülevaateid.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="0fe1e-110">Näiteks *kogukulu ühe kliendi kohta* ja *kogutulu ühe kliendi kohta* loomine aitab tuvastada suure kulutamise, kuid suure tootlusega klientide rühm.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="0fe1e-111">Saate [luua segmendi](segments.md), mis aitab teil teha järgmist.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="0fe1e-112">Isikliku voo loomine puhtalt lehelt</span><span class="sxs-lookup"><span data-stu-id="0fe1e-112">Build your own measure from scratch</span></span>

<span data-ttu-id="0fe1e-113">Selles jaotises tutvustatakse uue näitaja loomist nullist.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="0fe1e-114">Saate ehitada näitaja andmeatribuutidega andmeüksustelt, millel on kliendi olemiga ühenduse loomiseks suhe loodud.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="0fe1e-115">Avage sihtrühmaülevaadetes jaotis **Näitajad**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="0fe1e-116">Valige **Uus** ja valige **Looge ise**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="0fe1e-117">Valige **Redigeeri nimi** ja sisestage näitaja **Nimi**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="0fe1e-118">Kui teie uuel mõõtühiku konfiguratsioonil on ainult kaks välja (nt CustomerID ja üks arvutus), lisatakse väljund uue veeruna süsteemi genereeritud olemile nimega Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="0fe1e-119">Näete näitaja väärtust ühtses kliendiprofiilis.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="0fe1e-120">Muud näitajad loovad oma olemeid.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="0fe1e-121">Valige konfiguratsioonialas koondamisfunktsioon ripploendist **Vali funktsioon**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="0fe1e-122">Koondamisfunktsioonid on järgmised.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="0fe1e-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="0fe1e-123">**Sum**</span></span>
   - <span data-ttu-id="0fe1e-124">**Keskmine**</span><span class="sxs-lookup"><span data-stu-id="0fe1e-124">**Average**</span></span>
   - <span data-ttu-id="0fe1e-125">**Loenda**</span><span class="sxs-lookup"><span data-stu-id="0fe1e-125">**Count**</span></span>
   - <span data-ttu-id="0fe1e-126">**Kordumatu arv**</span><span class="sxs-lookup"><span data-stu-id="0fe1e-126">**Count Unique**</span></span>
   - <span data-ttu-id="0fe1e-127">**Maks.**</span><span class="sxs-lookup"><span data-stu-id="0fe1e-127">**Max**</span></span>
   - <span data-ttu-id="0fe1e-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="0fe1e-128">**Min**</span></span>
   - <span data-ttu-id="0fe1e-129">**Esimene**: võtab andmekirje esimese väärtuse</span><span class="sxs-lookup"><span data-stu-id="0fe1e-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="0fe1e-130">**Viimane**: võtab andmekirjesse lisatud viimase väärtuse</span><span class="sxs-lookup"><span data-stu-id="0fe1e-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Tehtemärgid näitaja arvutamiseks.":::

1. <span data-ttu-id="0fe1e-132">Valige **Lisa atribuut**, et valida andmed, mida selle näitaja loomiseks vajate.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="0fe1e-133">Valige vaheleht **Attribuudid**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="0fe1e-134">Andmeolem: valige olem, mis sisaldab mõõdetavat atribuuti.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="0fe1e-135">Andmeatribuut: valige atribuut, mida soovite näitaja arvutamiseks koondamisfunktsioonis kasutada.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="0fe1e-136">Korraga saate valida ainult ühe atribuudi.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="0fe1e-137">Olemasolevast näitajast andmeatribuudi valimiseks klõpsake vahekaarti **Näitajad** või otsige olemi või näitaja nime.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="0fe1e-138">Valige **Lisa**, et lisada atribuut näitajale.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Valige arvutuses soovitud atribuut.":::

1. <span data-ttu-id="0fe1e-140">Keerukamate näitajate loomiseks võite lisada mõõtmisfunktsioonile rohkem atribuute või kasutada matemaatilisi tehtemärke.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Keerukama näitaja loomine tehtemärkidega.":::

1. <span data-ttu-id="0fe1e-142">Filtrite lisamiseks valige konfiguratsiooniala **Filtreeri**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="0fe1e-143">Valige paani **Filtrid** jaotisest **Lisa atribuut** atribuut, mida soovite filtrite loomiseks kasutada.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="0fe1e-144">Määrake filtritehted iga valitud atribuudi filtri määratlemiseks.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="0fe1e-145">Valige **Rakenda**, et lisada filtrid näitajale.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="0fe1e-146">Dimensioonide lisamiseks valige konfiguratsioonialas **Dimensioon**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="0fe1e-147">Dimensioonid kuvatakse näitaja väljundolemis veergudena.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="0fe1e-148">Valige **Redigeeri dimensioonid**, et lisada andmeatribuute, mille järgi soovite näitaja väärtusi rühmitada.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="0fe1e-149">Näiteks linn või sugu.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-149">For example, city or gender.</span></span> <span data-ttu-id="0fe1e-150">*Klienditaseme näitajate loomiseks* valitakse vaikimisi *CustomerID* dimensioon.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="0fe1e-151">Kui soovite luua *äritaseme näitajaid*, saate vaikeeelise eemaldada.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="0fe1e-152">Valige **Valmis**, et lisada dimensioonid näitajale.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="0fe1e-153">Kui teie andmetes on väärtusi, mida peate täisarvuga asendama , nt pange *null* asemel *0*, valige **Reeglid**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="0fe1e-154">Konfigureerige reegel ja veenduge, et valite asendusena ainult täisnumbrid.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="0fe1e-155">Kui vastendatud andme- ja olemi *Klient* vahel on mitu teed, peate valima ühe tuvastatud [olemi suhte teedest](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="0fe1e-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="0fe1e-156">Näitaja tulemused võivad sõltuvalt valitud teest erineda.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="0fe1e-157">Valige **andmeelistused** ja seejärel olemi tee, mida tuleks oma näitaja tuvastamiseks kasutada.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="0fe1e-158">Kui olemi *Klient* juurde on ainult üks tee, siis seda juhtelementi ei näidata.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="0fe1e-159">Valiku rakendamiseks valige suvand **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Saate valida näitajale olemi tee.":::

1. <span data-ttu-id="0fe1e-161">Kui soovite näitajat veel arvutada, valige **Uus arvutus**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="0fe1e-162">Uute arvutuste jaoks saate kasutada ainult samal olemiteel olevaid üksusi.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="0fe1e-163">Täiendavad arvutused kuvatakse näitaja väljundolemis uute veergudena.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="0fe1e-164">Valige näitajast arvutuse **Duplitseerimiseks**, **Ümber nimetamiseks** või **Eemaldamiseks** **...**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="0fe1e-165">**Eelvaatealal** näete näitaja väljundolemi andmeskeemi (sh filtreid ja dimensioone).</span><span class="sxs-lookup"><span data-stu-id="0fe1e-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="0fe1e-166">Eelvaade reageerib dünaamiliselt konfiguratsiooni muudatustele.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="0fe1e-167">Konfigureeritud näitaja tulemuste arvutamiseks valige **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="0fe1e-168">Kui soovite praeguse konfiguratsiooni säilitada ja näitajat hiljem käitada, valige **Salvesta ja sule**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="0fe1e-169">Vastloodud näitaja nägemiseks loendis, valige **Näitajad**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="0fe1e-170">Malli abil mõõdu loomine</span><span class="sxs-lookup"><span data-stu-id="0fe1e-170">Use a template to build a measure</span></span>

<span data-ttu-id="0fe1e-171">Nende loomiseks võite kasutada tavaliselt kasutatavate meetmete ettemääratud malle.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="0fe1e-172">Mallide üksikasjalik kirjeldus ja juhendatud kogemused aitavad teil luua tõhusa mõõtmissüsteemi.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="0fe1e-173">Mallid põhinevad olemi *Ühendatud tegevus* kaardistatud andmetele.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="0fe1e-174">Seega veenduge, et olete konfigureerinud [klienditegevused](activities.md) enne malli põhjal mõõtühiku loomist.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="0fe1e-175">Saadaval mõõdumallid:</span><span class="sxs-lookup"><span data-stu-id="0fe1e-175">Available measure templates:</span></span> 
- <span data-ttu-id="0fe1e-176">Keskmine tehingu väärtus (ATV)</span><span class="sxs-lookup"><span data-stu-id="0fe1e-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="0fe1e-177">Tehingu väärtus kokku</span><span class="sxs-lookup"><span data-stu-id="0fe1e-177">Total transaction value</span></span>
- <span data-ttu-id="0fe1e-178">Päeva keskmine tulu</span><span class="sxs-lookup"><span data-stu-id="0fe1e-178">Average daily revenue</span></span>
- <span data-ttu-id="0fe1e-179">Aasta keskmine tulu</span><span class="sxs-lookup"><span data-stu-id="0fe1e-179">Average yearly revenue</span></span>
- <span data-ttu-id="0fe1e-180">Kannete arv</span><span class="sxs-lookup"><span data-stu-id="0fe1e-180">Transaction count</span></span>
- <span data-ttu-id="0fe1e-181">Teenitud püsikliendipunktid</span><span class="sxs-lookup"><span data-stu-id="0fe1e-181">Loyalty points earned</span></span>
- <span data-ttu-id="0fe1e-182">Lunastatud püsikliendipunktid</span><span class="sxs-lookup"><span data-stu-id="0fe1e-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="0fe1e-183">Püsikliendipunktide saldo</span><span class="sxs-lookup"><span data-stu-id="0fe1e-183">Loyalty points balance</span></span>
- <span data-ttu-id="0fe1e-184">Aktiivse kliendi eluiga</span><span class="sxs-lookup"><span data-stu-id="0fe1e-184">Active customer lifespan</span></span>
- <span data-ttu-id="0fe1e-185">Püsikliendi liikmestaatuse kestus</span><span class="sxs-lookup"><span data-stu-id="0fe1e-185">Loyalty membership duration</span></span>
- <span data-ttu-id="0fe1e-186">Aega viimasest ostust</span><span class="sxs-lookup"><span data-stu-id="0fe1e-186">Time since last purchase</span></span>

<span data-ttu-id="0fe1e-187">Järgmine protseduur kirjeldab etappe uue meetme loomiseks malli abil.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="0fe1e-188">Avage sihtrühmaülevaadetes jaotis **Näitajad**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="0fe1e-189">Valige **Uus** ja seejärel **Vali mall**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Rippmenüü ekraanipilt, kui luuakse mallil esiletõstetud uus mõõt.":::

1. <span data-ttu-id="0fe1e-191">Leidke teie vajadusele sobiv mall ja valige **Valige mall**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="0fe1e-192">Vaadake nõutavad andmed läbi ja valige **Alustamine**, kui kõik andmed on olemas.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="0fe1e-193">Määrake **Nime muutmine** paanil oma mõõtühiku ja väljundi olemi nimi.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="0fe1e-194">Valige nupp **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-194">Select **Done**.</span></span>

1. <span data-ttu-id="0fe1e-195">Määrake **Sea ajaperiood** jaotises ajavahemikud andmete kasutamiseks.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="0fe1e-196">Valige, kas soovite, et uus mõõt hõlmaks kogu andmekogumit, valides suvandi **Kogu aeg**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="0fe1e-197">Või kui soovite, et mõõtühiku valikuks oleks **Kindel ajaperiood**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Kuvatõmmis ajavahemiku jaotisest, kui konfigureerite malli põhjal mõõtmise.":::

1. <span data-ttu-id="0fe1e-199">Järgmises jaotises valige **Lisa andmed**, et valida tegevused ja kaardistada oma olemi *Ühendatud tegevus* vastavad andmed.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="0fe1e-200">1. etapp: valige jaotises **Tegevuse tüüp** selle olemi tüüp, mida soovite kasutada.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="0fe1e-201">Valige **Tegevused** jaoks olemid, mida soovite kaardistada.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="0fe1e-202">2. etapp: valige atribuut olemist *Ühendatud Tegevus* valemiga nõutava komponendi jaoks.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="0fe1e-203">Näiteks keskmise tehingu väärtuse puhul on see atribuut, mis tähistab tehingu väärtust.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="0fe1e-204">Valige **Tegevuse ajatempli** jaoks atribuut olemist Ühendatud tegevus, mis tähistab tegevuse kuupäeva ja kellaaega.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="0fe1e-205">Kui andmete kaardistamine õnnestub, näete olekut **Lõpule viidud** ning kaardistatud tegevuste ja atribuutide nime.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Lõpuleviidud mõõtühikumalli konfiguratsiooni kuvatõmmis.":::

1. <span data-ttu-id="0fe1e-207">Nüüd saate valida suvandi **Käita**, et arvutada mõõtmise tulemused.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="0fe1e-208">Hiljem viimistlemiseks valige **Salvesta mustand**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="0fe1e-209">Meetmete haldamine</span><span class="sxs-lookup"><span data-stu-id="0fe1e-209">Manage your measures</span></span>

<span data-ttu-id="0fe1e-210">Meetmete loendi leiate lehelt **Meetmed**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="0fe1e-211">Leiate teavet näidiku tüübi, autori, loomise kuupäeva, staatuse ja oleku kohta.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="0fe1e-212">Kui valite loendist näitaja, saate väljundit eelvaadata ja .CSV-faili alla laadida.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="0fe1e-213">Kõigi oma meetmete korraga värskendamiseks valige **Värskenda kõik** ilma kindlat meedet valimata.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0fe1e-214">![Toimingud üksikute meetmete haldamiseks](media/measure-actions.png "Toimingud üksikute meetmete haldamiseks")</span><span class="sxs-lookup"><span data-stu-id="0fe1e-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="0fe1e-215">Valige loendist soovitud näitaja järgmiste suvandite jaoks.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="0fe1e-216">Valige meetme nimi, et näha selle üksikasju.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="0fe1e-217">Meetme konfiguratsiooni **Redigeerimine**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="0fe1e-218">**Värskendage** näitajat, võttes aluseks värskeimad andmed.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="0fe1e-219">Meetme **Ümbernimetamine**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-219">**Rename** the measure.</span></span>
- <span data-ttu-id="0fe1e-220">Meetme **Kustutamine**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-220">**Delete** the measure.</span></span>
- <span data-ttu-id="0fe1e-221">**Aktiveeri** või **Inaktiveeri**.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="0fe1e-222">Passiivseid näitajad ei värskendata [kavandatud värskenduse](system.md#schedule-tab) ajal.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="0fe1e-223">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="0fe1e-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="0fe1e-224">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="0fe1e-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="0fe1e-225">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="0fe1e-226">Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="0fe1e-227">Järgmine etapp</span><span class="sxs-lookup"><span data-stu-id="0fe1e-227">Next step</span></span>

<span data-ttu-id="0fe1e-228">[Kliendisegmendi loomiseks](segments.md) saate kasutada olemasolevaid näitajaid.</span><span class="sxs-lookup"><span data-stu-id="0fe1e-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
