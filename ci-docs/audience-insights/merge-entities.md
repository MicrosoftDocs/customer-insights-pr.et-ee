---
title: Olemite ühendamine andmete koondamise ajal
description: Ühendage olemid, et luua koondatud kliendiprofiile.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085571"
---
# <a name="merge-entities"></a><span data-ttu-id="d2dbb-103">Olemite liitmine</span><span class="sxs-lookup"><span data-stu-id="d2dbb-103">Merge entities</span></span>

<span data-ttu-id="d2dbb-104">Liitmine on andmete ühendamise viimane etapp.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="d2dbb-105">Selle eesmärk on vastavusse viia vastuolus andmed.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="d2dbb-106">Vastuolulisteks andmeteks võivad olla kahes andmebaasis olev kliendi nimi, mida näidatakse veidi erinevalt (võrrelge: „Grant Marshall“ ja „Grant Marshal“) või erinevas vormingus telefoninumber (võrrelge: 617-803-091X ja 617803091X).</span><span class="sxs-lookup"><span data-stu-id="d2dbb-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="d2dbb-107">Nende vastuoluliste andmepunktide liitmine toimub järgmisel alusel: atribuut atribuudi järel.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Ühenda leht andmete ühtsustamise protsessiga näidates tabelit koos ühendatud väljadega, mis defineerivad ühendatud kliendiprofiili.":::

<span data-ttu-id="d2dbb-109">Pärast [vastendamisetappi](match-entities.md) algab liitmisetapp, valides lehel **Ühendamine** paani **Liitmine**.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="d2dbb-110">Vaadake üle süsteemi soovitused</span><span class="sxs-lookup"><span data-stu-id="d2dbb-110">Review system recommendations</span></span>

<span data-ttu-id="d2dbb-111">Funktsioonis **Andmed** > **Unify** > **Sulata** saate valida ja välistada atribuudid, mida soovite oma unified customer profile'i profiili sees sulatada.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="d2dbb-112">Ühendatud kliendiprofiil on andmete ühendamise protsessi tulemus.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="d2dbb-113">Osa atribuute liidab süsteem ise.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="d2dbb-114">Kui soovite vaadata atribuute, mis on kaasatud ühte teie automaatselt ühendatud atribuudisse, valige see ühendatud atribuut tabeli **Kliendi väljad** vahekaardil.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="d2dbb-115">Atribuudid, mis koostavad ühendatud atribuuti kuvatakse kahes uues rollis ühendatud atribuudi all.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="d2dbb-116">Eralda, nimeta ümber, välista ja redigeeri ühendatud väljad</span><span class="sxs-lookup"><span data-stu-id="d2dbb-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="d2dbb-117">Saate muuta, kuidas süsteem töötleb ühendatud atribuute ühtse kliendiprofiili loomiseks.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="d2dbb-118">Valige **Kuva veel** ja valige, mida soovite muuta.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Ühendatud atribuutide haldamiseks soovitud suvandid ripploendis Kuva veel.":::

<span data-ttu-id="d2dbb-120">Järgmisest jaotisest leiate lisateavet.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="d2dbb-121">Eraldaga ühendatud väljad</span><span class="sxs-lookup"><span data-stu-id="d2dbb-121">Separate merged fields</span></span>

<span data-ttu-id="d2dbb-122">Ühendatud väljade eraldamiseks leidke atribuut tabelist.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="d2dbb-123">Eraldatud väljad kuvatakse üksikute andmepunktidena ühendatud kliendi profiilil.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="d2dbb-124">Valige ühendatud väli.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="d2dbb-125">Valige **Kuva veel** ja valige **Eraldi väljad**.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="d2dbb-126">eralduse kinnitamine.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-126">Confirm the separation.</span></span>

1. <span data-ttu-id="d2dbb-127">Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .</span><span class="sxs-lookup"><span data-stu-id="d2dbb-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="d2dbb-128">Ühendatud väljade ümbernimetamine</span><span class="sxs-lookup"><span data-stu-id="d2dbb-128">Rename merged fields</span></span>

<span data-ttu-id="d2dbb-129">Muutke ühendatud atribuutide kuvatavat nime.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="d2dbb-130">Toodanguolemi nime ei saa muuta.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="d2dbb-131">Valige ühendatud väli.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="d2dbb-132">Valige **Kuva veel** ja valige **Nimeta ümber**.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="d2dbb-133">Kinnitage muudetud kuvatav nimi.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="d2dbb-134">Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .</span><span class="sxs-lookup"><span data-stu-id="d2dbb-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="d2dbb-135">Jäta ühendatud väljad välja</span><span class="sxs-lookup"><span data-stu-id="d2dbb-135">Exclude merged fields</span></span>

<span data-ttu-id="d2dbb-136">Atribuudi välistamine ühtsest kliendiprofiilist.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="d2dbb-137">Kui seda välja kasutatakse muudes protsessides (nt segmendis), eemaldage see nendest protsessidest, enne selle kliendiprofiililt eemaldamist.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="d2dbb-138">Valige ühendatud väli.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="d2dbb-139">Valige **Kuva veel** ja valige **Välista**.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="d2dbb-140">Kinnitage välistamine.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="d2dbb-141">Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .</span><span class="sxs-lookup"><span data-stu-id="d2dbb-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="d2dbb-142">Lehel **Ühenda** valige **Välistatud väljad** et näha välistatud väljade loendit.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="d2dbb-143">Selle paani abil saate väljad tagasi lisada.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="d2dbb-144">Kombineeri välju käsitsi</span><span class="sxs-lookup"><span data-stu-id="d2dbb-144">Manually combine fields</span></span>

<span data-ttu-id="d2dbb-145">Määrake ühendatud atribuut käsitsi.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="d2dbb-146">Lehel **Ühenda** valige **Ühenda väljad**.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="d2dbb-147">Sisestage **Nimi** ja **Väljundvälja nimi**.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="d2dbb-148">Valige väli lisamiseks.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-148">Choose a field to add.</span></span> <span data-ttu-id="d2dbb-149">Valige **Lisa välju** et ühendada rohkem välju.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="d2dbb-150">Kinnitage välistamine.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="d2dbb-151">Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .</span><span class="sxs-lookup"><span data-stu-id="d2dbb-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="d2dbb-152">Väljade järjekorra muutmine</span><span class="sxs-lookup"><span data-stu-id="d2dbb-152">Change the order of fields</span></span>

<span data-ttu-id="d2dbb-153">Mõned olemid sisaldavad rohkem üksikasju kui teised.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-153">Some entities contain more details than others.</span></span> <span data-ttu-id="d2dbb-154">Kui olem sisaldab välja kohta värskeid andmeid, saate väärtusi ühendades prioriseerida selle teiste olemite suhtes.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="d2dbb-155">Valige ühendatud väli.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="d2dbb-156">Valige **Kuva veel** ja valige **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="d2dbb-157">Valige paanil **Väljade ühendamine** suvand **Nihutage üles/alla** et paika panna järjekord või nihutada ja asetada need soovitud kohale.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="d2dbb-158">Kinnitage muudatus.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-158">Confirm the change.</span></span>

1. <span data-ttu-id="d2dbb-159">Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .</span><span class="sxs-lookup"><span data-stu-id="d2dbb-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="d2dbb-160">Käivitage kooste</span><span class="sxs-lookup"><span data-stu-id="d2dbb-160">Run your merge</span></span>

<span data-ttu-id="d2dbb-161">Olenemata sellest, kas liidate atribuute ise või lasete seda teha süsteemil, saate alati käivitada kooste.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="d2dbb-162">Toimingu käivitamiseks valige lehel **Liitmine** valik **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d2dbb-163">![Andmete liitmine „Salvesta ja Käivita“](media/configure-data-merge-save-run.png "Andmete liitmine „Salvesta ja Käivita“")</span><span class="sxs-lookup"><span data-stu-id="d2dbb-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="d2dbb-164">Valige **Käivita ainult ühendamine** juhul, kui soovite näha ainult väljundit ühtses kliendiolemis kajastatuna.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="d2dbb-165">Järgnevad protsessid värskendatakse [vastavalt värskendusplaanile](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d2dbb-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="d2dbb-166">Vaige **Käivita Ühenda ja järgnevad protsessid** et värskendada süsteemi sinu muudatustega.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="d2dbb-167">Kõik protsessid, sh rikastamine, segmendid ja mõõtkavad, käivituvad automaatselt.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="d2dbb-168">Kui kõik järgnevad protsessid on lõpule jõudnud, kajastavad kliendiprofiilid teie tehtud muudatusi.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="d2dbb-169">Kui soovite teha rohkem muudatusi ja etapi uuesti käivitada, saate tühistada poolelioleva ühendamise.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="d2dbb-170">Valige **Värskendamine ...** ja valige nähtavale ilmuva külgpaani suvand **Tühista töö**.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="d2dbb-171">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="d2dbb-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="d2dbb-172">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="d2dbb-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="d2dbb-173">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="d2dbb-174">Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="d2dbb-175">Järgmine etapp</span><span class="sxs-lookup"><span data-stu-id="d2dbb-175">Next Step</span></span>

<span data-ttu-id="d2dbb-176">Klientide kohta täiendavate ülevaadete saamiseks seadistage [toiminguid](activities.md), [rikastamist](enrichment-hub.md) või [seosed](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="d2dbb-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="d2dbb-177">Kui olete tegevused, rikastamine või segmendid juba konfigureerinud, töödeldakse neid automaatselt, et kasutada uusimaid kliendiandmeid.</span><span class="sxs-lookup"><span data-stu-id="d2dbb-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
