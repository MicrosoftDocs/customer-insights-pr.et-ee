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
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305627"
---
# <a name="merge-entities"></a><span data-ttu-id="e253c-103">Olemite liitmine</span><span class="sxs-lookup"><span data-stu-id="e253c-103">Merge entities</span></span>

<span data-ttu-id="e253c-104">Liitmine on andmete ühendamise viimane etapp.</span><span class="sxs-lookup"><span data-stu-id="e253c-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="e253c-105">Selle eesmärk on vastavusse viia vastuolus andmed.</span><span class="sxs-lookup"><span data-stu-id="e253c-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="e253c-106">Vastuolulisteks andmeteks võivad olla kahes andmebaasis olev kliendi nimi, mida näidatakse veidi erinevalt (võrrelge: „Grant Marshall“ ja „Grant Marshal“) või erinevas vormingus telefoninumber (võrrelge: 617-803-091X ja 617803091X).</span><span class="sxs-lookup"><span data-stu-id="e253c-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="e253c-107">Nende vastuoluliste andmepunktide liitmine toimub järgmisel alusel: atribuut atribuudi järel.</span><span class="sxs-lookup"><span data-stu-id="e253c-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Ühenda leht andmete ühtsustamise protsessiga näidates tabelit koos ühendatud väljadega, mis defineerivad ühendatud kliendiprofiili.":::

<span data-ttu-id="e253c-109">Pärast [vastendamisetappi](match-entities.md) algab liitmisetapp, valides lehel **Ühendamine** paani **Liitmine**.</span><span class="sxs-lookup"><span data-stu-id="e253c-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="e253c-110">Vaadake üle süsteemi soovitused</span><span class="sxs-lookup"><span data-stu-id="e253c-110">Review system recommendations</span></span>

<span data-ttu-id="e253c-111">Funktsioonis **Andmed** > **Unify** > **Sulata** saate valida ja välistada atribuudid, mida soovite oma unified customer profile'i profiili sees sulatada.</span><span class="sxs-lookup"><span data-stu-id="e253c-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="e253c-112">Ühendatud kliendiprofiil on andmete ühendamise protsessi tulemus.</span><span class="sxs-lookup"><span data-stu-id="e253c-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="e253c-113">Osa atribuute liidab süsteem ise.</span><span class="sxs-lookup"><span data-stu-id="e253c-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="e253c-114">Kui soovite vaadata atribuute, mis on kaasatud ühte teie automaatselt ühendatud atribuudisse, valige see ühendatud atribuut tabeli **Kliendi väljad** vahekaardil.</span><span class="sxs-lookup"><span data-stu-id="e253c-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="e253c-115">Atribuudid, mis koostavad ühendatud atribuuti kuvatakse kahes uues rollis ühendatud atribuudi all.</span><span class="sxs-lookup"><span data-stu-id="e253c-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="e253c-116">Eralda, nimeta ümber, välista ja redigeeri ühendatud väljad</span><span class="sxs-lookup"><span data-stu-id="e253c-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="e253c-117">Saate muuta, kuidas süsteem töötleb ühendatud atribuute ühtse kliendiprofiili loomiseks.</span><span class="sxs-lookup"><span data-stu-id="e253c-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="e253c-118">Valige **Kuva veel** ja valige, mida soovite muuta.</span><span class="sxs-lookup"><span data-stu-id="e253c-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Ühendatud atribuutide haldamiseks rippmenüü Kuva veel valikud.":::

<span data-ttu-id="e253c-120">Järgmisest jaotisest leiate lisateavet.</span><span class="sxs-lookup"><span data-stu-id="e253c-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="e253c-121">Eraldaga ühendatud väljad</span><span class="sxs-lookup"><span data-stu-id="e253c-121">Separate merged fields</span></span>

<span data-ttu-id="e253c-122">Ühendatud väljade eraldamiseks leidke atribuut tabelist.</span><span class="sxs-lookup"><span data-stu-id="e253c-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="e253c-123">Eraldatud väljad kuvatakse üksikute andmepunktidena ühendatud kliendi profiilil.</span><span class="sxs-lookup"><span data-stu-id="e253c-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="e253c-124">Valige ühendatud väli.</span><span class="sxs-lookup"><span data-stu-id="e253c-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="e253c-125">Valige **Kuva veel** ja valige **Eraldi väljad**.</span><span class="sxs-lookup"><span data-stu-id="e253c-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="e253c-126">eralduse kinnitamine.</span><span class="sxs-lookup"><span data-stu-id="e253c-126">Confirm the separation.</span></span>

1. <span data-ttu-id="e253c-127">Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .</span><span class="sxs-lookup"><span data-stu-id="e253c-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="e253c-128">Ühendatud väljade ümbernimetamine</span><span class="sxs-lookup"><span data-stu-id="e253c-128">Rename merged fields</span></span>

<span data-ttu-id="e253c-129">Muutke ühendatud atribuutide kuvatavat nime.</span><span class="sxs-lookup"><span data-stu-id="e253c-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="e253c-130">Toodanguolemi nime ei saa muuta.</span><span class="sxs-lookup"><span data-stu-id="e253c-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="e253c-131">Valige ühendatud väli.</span><span class="sxs-lookup"><span data-stu-id="e253c-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="e253c-132">Valige **Kuva veel** ja valige **Nimeta ümber**.</span><span class="sxs-lookup"><span data-stu-id="e253c-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="e253c-133">Kinnitage muudetud kuvatav nimi.</span><span class="sxs-lookup"><span data-stu-id="e253c-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="e253c-134">Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .</span><span class="sxs-lookup"><span data-stu-id="e253c-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="e253c-135">Jäta ühendatud väljad välja</span><span class="sxs-lookup"><span data-stu-id="e253c-135">Exclude merged fields</span></span>

<span data-ttu-id="e253c-136">Atribuudi välistamine ühtsest kliendiprofiilist.</span><span class="sxs-lookup"><span data-stu-id="e253c-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="e253c-137">Kui seda välja kasutatakse muudes protsessides (nt segmendis), eemaldage see nendest protsessidest, enne selle kliendiprofiililt eemaldamist.</span><span class="sxs-lookup"><span data-stu-id="e253c-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="e253c-138">Valige ühendatud väli.</span><span class="sxs-lookup"><span data-stu-id="e253c-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="e253c-139">Valige **Kuva veel** ja valige **Välista**.</span><span class="sxs-lookup"><span data-stu-id="e253c-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="e253c-140">Kinnitage välistamine.</span><span class="sxs-lookup"><span data-stu-id="e253c-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="e253c-141">Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .</span><span class="sxs-lookup"><span data-stu-id="e253c-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="e253c-142">Lehel **Ühenda** valige **Välistatud väljad** et näha välistatud väljade loendit.</span><span class="sxs-lookup"><span data-stu-id="e253c-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="e253c-143">Selle paani abil saate väljad tagasi lisada.</span><span class="sxs-lookup"><span data-stu-id="e253c-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="e253c-144">Kombineeri välju käsitsi</span><span class="sxs-lookup"><span data-stu-id="e253c-144">Manually combine fields</span></span>

<span data-ttu-id="e253c-145">Määrake ühendatud atribuut käsitsi.</span><span class="sxs-lookup"><span data-stu-id="e253c-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="e253c-146">Lehel **Ühenda** valige **Ühenda väljad**.</span><span class="sxs-lookup"><span data-stu-id="e253c-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="e253c-147">Sisestage **Nimi** ja **Väljundvälja nimi**.</span><span class="sxs-lookup"><span data-stu-id="e253c-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="e253c-148">Valige väli lisamiseks.</span><span class="sxs-lookup"><span data-stu-id="e253c-148">Choose a field to add.</span></span> <span data-ttu-id="e253c-149">Valige **Lisa välju** et ühendada rohkem välju.</span><span class="sxs-lookup"><span data-stu-id="e253c-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="e253c-150">Kinnitage välistamine.</span><span class="sxs-lookup"><span data-stu-id="e253c-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="e253c-151">Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .</span><span class="sxs-lookup"><span data-stu-id="e253c-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="e253c-152">Väljade järjekorra muutmine</span><span class="sxs-lookup"><span data-stu-id="e253c-152">Change the order of fields</span></span>

<span data-ttu-id="e253c-153">Mõned olemid sisaldavad rohkem üksikasju kui teised.</span><span class="sxs-lookup"><span data-stu-id="e253c-153">Some entities contain more details than others.</span></span> <span data-ttu-id="e253c-154">Kui olem sisaldab välja kohta värskeid andmeid, saate väärtusi ühendades prioriseerida selle teiste olemite suhtes.</span><span class="sxs-lookup"><span data-stu-id="e253c-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="e253c-155">Valige ühendatud väli.</span><span class="sxs-lookup"><span data-stu-id="e253c-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="e253c-156">Valige **Kuva veel** ja valige **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="e253c-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="e253c-157">Valige paanil **Väljade ühendamine** suvand **Nihutage üles/alla** et paika panna järjekord või nihutada ja asetada need soovitud kohale.</span><span class="sxs-lookup"><span data-stu-id="e253c-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="e253c-158">Kinnitage muudatus.</span><span class="sxs-lookup"><span data-stu-id="e253c-158">Confirm the change.</span></span>

1. <span data-ttu-id="e253c-159">Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .</span><span class="sxs-lookup"><span data-stu-id="e253c-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="e253c-160">Käivitage kooste</span><span class="sxs-lookup"><span data-stu-id="e253c-160">Run your merge</span></span>

<span data-ttu-id="e253c-161">Olenemata sellest, kas liidate atribuute ise või lasete seda teha süsteemil, saate alati käivitada kooste.</span><span class="sxs-lookup"><span data-stu-id="e253c-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="e253c-162">Toimingu käivitamiseks valige lehel **Liitmine** valik **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="e253c-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e253c-163">![Andmete liitmine „Salvesta ja Käivita“](media/configure-data-merge-save-run.png "Andmete liitmine „Salvesta ja Käivita“")</span><span class="sxs-lookup"><span data-stu-id="e253c-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="e253c-164">Valige **Käivita ainult ühendamine** juhul, kui soovite näha ainult väljundit ühtses kliendiolemis kajastatuna.</span><span class="sxs-lookup"><span data-stu-id="e253c-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="e253c-165">Järgnevad protsessid värskendatakse [vastavalt värskendusplaanile](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e253c-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="e253c-166">Vaige **Käivita Ühenda ja järgnevad protsessid** et värskendada süsteemi sinu muudatustega.</span><span class="sxs-lookup"><span data-stu-id="e253c-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="e253c-167">Kõik protsessid, sh rikastamine, segmendid ja mõõtkavad, käivituvad automaatselt.</span><span class="sxs-lookup"><span data-stu-id="e253c-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="e253c-168">Kui kõik järgnevad protsessid on lõpule jõudnud, kajastavad kliendiprofiilid teie tehtud muudatusi.</span><span class="sxs-lookup"><span data-stu-id="e253c-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="e253c-169">Kui soovite teha rohkem muudatusi ja etapi uuesti käivitada, saate tühistada poolelioleva ühendamise.</span><span class="sxs-lookup"><span data-stu-id="e253c-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="e253c-170">Valige **Värskendamine ...** ja valige nähtavale ilmuva külgpaani suvand **Tühista töö**.</span><span class="sxs-lookup"><span data-stu-id="e253c-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="e253c-171">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="e253c-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e253c-172">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e253c-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e253c-173">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="e253c-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e253c-174">Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="e253c-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="e253c-175">Järgmine etapp</span><span class="sxs-lookup"><span data-stu-id="e253c-175">Next Step</span></span>

<span data-ttu-id="e253c-176">Klientide kohta täiendavate ülevaadete saamiseks seadistage [toiminguid](activities.md), [rikastamist](enrichment-hub.md) või [seosed](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="e253c-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="e253c-177">Kui olete tegevused, rikastamine või segmendid juba konfigureerinud, töödeldakse neid automaatselt, et kasutada uusimaid kliendiandmeid.</span><span class="sxs-lookup"><span data-stu-id="e253c-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
