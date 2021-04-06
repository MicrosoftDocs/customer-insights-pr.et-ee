---
title: Olemite ühendamine andmete koondamise ajal
description: Ühendage olemid, et luua koondatud kliendiprofiile.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597828"
---
# <a name="merge-entities"></a><span data-ttu-id="f99de-103">Olemite liitmine</span><span class="sxs-lookup"><span data-stu-id="f99de-103">Merge entities</span></span>

<span data-ttu-id="f99de-104">Liitmine on andmete ühendamise viimane etapp.</span><span class="sxs-lookup"><span data-stu-id="f99de-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="f99de-105">Selle eesmärk on vastavusse viia vastuolus andmed.</span><span class="sxs-lookup"><span data-stu-id="f99de-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="f99de-106">Vastuolulisteks andmeteks võivad olla kahes andmebaasis olev kliendi nimi, mida näidatakse veidi erinevalt (võrrelge: „Grant Marshall“ ja „Grant Marshal“) või erinevas vormingus telefoninumber (võrrelge: 617-803-091X ja 617803091X).</span><span class="sxs-lookup"><span data-stu-id="f99de-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="f99de-107">Nende vastuoluliste andmepunktide liitmine toimub järgmisel alusel: atribuut atribuudi järel.</span><span class="sxs-lookup"><span data-stu-id="f99de-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="f99de-108">Pärast [vastendamisetappi](match-entities.md) algab liitmisetapp, valides lehel **Ühendamine** paani **Liitmine**.</span><span class="sxs-lookup"><span data-stu-id="f99de-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="f99de-109">Vaadake üle süsteemi soovitused</span><span class="sxs-lookup"><span data-stu-id="f99de-109">Review system recommendations</span></span>

<span data-ttu-id="f99de-110">Lehel **Liitmine** valite ja välistate atribuudid, et liita oma ühendatud kliendiprofiili olemiga (seadistamise tulemus).</span><span class="sxs-lookup"><span data-stu-id="f99de-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="f99de-111">Osa atribuute liidab süsteem ise.</span><span class="sxs-lookup"><span data-stu-id="f99de-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="f99de-112">Vaadake ühendatud atribuute</span><span class="sxs-lookup"><span data-stu-id="f99de-112">View merged attributes</span></span>

<span data-ttu-id="f99de-113">Automaatselt liidetud atribuutide hulgast ühe vaatamiseks valige see liidetud atribuut.</span><span class="sxs-lookup"><span data-stu-id="f99de-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="f99de-114">Kaks atribuuti, millest see liidetud atribuut koosneb, kuvatakse liidetud atribuudi all eraldi kahes uues reas.</span><span class="sxs-lookup"><span data-stu-id="f99de-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f99de-115">![Valige ühendatud atribuut](media/configure-data-merge-profile-attributes.png "Valige ühendatud atribuut")</span><span class="sxs-lookup"><span data-stu-id="f99de-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="f99de-116">Eraldage liidetud atribuudid</span><span class="sxs-lookup"><span data-stu-id="f99de-116">Separate merged attributes</span></span>

<span data-ttu-id="f99de-117">Automaatselt liidetud atribuutide eraldamiseks või liitmiseks leidke tabelist **Profiili atribuudid** atribuut.</span><span class="sxs-lookup"><span data-stu-id="f99de-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="f99de-118">Valige kolmikpunkt (...).</span><span class="sxs-lookup"><span data-stu-id="f99de-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="f99de-119">Valige ripploendis suvand **Eralda väljad**.</span><span class="sxs-lookup"><span data-stu-id="f99de-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="f99de-120">Eemaldage liidetud atribuudid</span><span class="sxs-lookup"><span data-stu-id="f99de-120">Remove merged attributes</span></span>

<span data-ttu-id="f99de-121">Viimase kliendiprofiili olemi atribuudi välistamiseks leidke see tabelis **Prodiili atribuudid**.</span><span class="sxs-lookup"><span data-stu-id="f99de-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="f99de-122">Valige kolmikpunkt (...).</span><span class="sxs-lookup"><span data-stu-id="f99de-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="f99de-123">Valige ripploendis suvand **Mitte liita**.</span><span class="sxs-lookup"><span data-stu-id="f99de-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="f99de-124">Atribuut liigutatakse jaotisesse **Kliendi kirjest eemaldatud**.</span><span class="sxs-lookup"><span data-stu-id="f99de-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="f99de-125">Lisa ise ühendatud atribuut</span><span class="sxs-lookup"><span data-stu-id="f99de-125">Manually add a merged attribute</span></span>

<span data-ttu-id="f99de-126">Liidetud atribuudi lisamiseks minge lehele **Liitmine**.</span><span class="sxs-lookup"><span data-stu-id="f99de-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="f99de-127">Valige **Lisa liidetud atribuut**.</span><span class="sxs-lookup"><span data-stu-id="f99de-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="f99de-128">Sisestage hiljem lehel **Liitmine** selle tuvastamiseks **nimi**.</span><span class="sxs-lookup"><span data-stu-id="f99de-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="f99de-129">Soovi korral sisestage **Kuvatav nimi**, mis ilmub ühendatud kliendiprofiili olemis.</span><span class="sxs-lookup"><span data-stu-id="f99de-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="f99de-130">Liidetavate vastendatud olemite atribuutide valimiseks seadistage **Vali duplikaatatribuudid**.</span><span class="sxs-lookup"><span data-stu-id="f99de-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="f99de-131">Samuti saate otsida atribuute.</span><span class="sxs-lookup"><span data-stu-id="f99de-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="f99de-132">Ühe atribuudi esile tõstmiseks valige **Tähtsuse järgi järjestamine**.</span><span class="sxs-lookup"><span data-stu-id="f99de-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="f99de-133">Näiteks, kui olem *WebAccountCSV* sisaldab atribuudi *Täisnimed* kõige täpsemaid andmeid, saate selle olemi ettepoole tõsta olemist *ContactCSV*, valides selleks *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="f99de-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="f99de-134">Selle tulemusel muutub *WebAccountCSV* kõige tähtsamaks, samas *ContactCSV* langeb teisele kohale atribuudi *Täisnimi* väärtuste hankimisel.</span><span class="sxs-lookup"><span data-stu-id="f99de-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="f99de-135">Käivitage kooste</span><span class="sxs-lookup"><span data-stu-id="f99de-135">Run your merge</span></span>

<span data-ttu-id="f99de-136">Olenemata sellest, kas liidate atribuute ise või lasete seda teha süsteemil, saate alati käivitada kooste.</span><span class="sxs-lookup"><span data-stu-id="f99de-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="f99de-137">Toimingu käivitamiseks valige lehel **Liitmine** valik **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="f99de-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f99de-138">![Andmete liitmine „Salvesta ja Käivita“](media/configure-data-merge-save-run.png "Andmete liitmine „Salvesta ja Käivita“")</span><span class="sxs-lookup"><span data-stu-id="f99de-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="f99de-139">Täiendavate muudatuste tegemiseks ja etapi uuesti käivitamiseks saate poolelioleva ühendamise tühistada.</span><span class="sxs-lookup"><span data-stu-id="f99de-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="f99de-140">Valige **Värskendamine ...** ja valige nähtavale ilmuva külgpaani suvand **Tühista töö**.</span><span class="sxs-lookup"><span data-stu-id="f99de-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="f99de-141">Kui tekst **Värskendamine ...** asendub tekstiga **Õnnestus**, on ühendamine lõpule jõudnud ja vastuolud on vastavalt teie määratud poliitikatele lahendatud.</span><span class="sxs-lookup"><span data-stu-id="f99de-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="f99de-142">Ühendatud ja ühendamata atribuudid kaasatakse ühendatud profiili olemisse.</span><span class="sxs-lookup"><span data-stu-id="f99de-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="f99de-143">Välja jäetud atribuute ei kaasata ühendatud profiili olemisse.</span><span class="sxs-lookup"><span data-stu-id="f99de-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="f99de-144">Kui see ei olnud esimene kord edukalt ühendamine läbi viia, käivitatakse kõik järgnevad protsessid, sealhulgas rikastamine, segmentimine ja meetmed, automaatselt.</span><span class="sxs-lookup"><span data-stu-id="f99de-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="f99de-145">Kui kõik järgnevad protsessid on uuesti läbi viidud, kajastuvad kõik tehtud muudatused kliendiprofiilidel.</span><span class="sxs-lookup"><span data-stu-id="f99de-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="f99de-146">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="f99de-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f99de-147">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f99de-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f99de-148">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="f99de-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f99de-149">Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="f99de-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="f99de-150">Järgmine etapp</span><span class="sxs-lookup"><span data-stu-id="f99de-150">Next Step</span></span>

<span data-ttu-id="f99de-151">Klientide kohta täiendavate ülevaadete saamiseks seadistage [toiminguid](activities.md), [rikastamist](enrichment-microsoft-graph.md) või [seosed](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="f99de-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="f99de-152">Kui olete juba tegevused, rikastamise või seoseid konfigureerinud või kui olete määratlenud segmendid, töödeldakse neid automaatselt, et kasutada värskeimaid kliendiandmeid.</span><span class="sxs-lookup"><span data-stu-id="f99de-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]