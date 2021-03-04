---
title: Segmentide loomine ja haldamine
description: Looge klientide segmente, et rühmitada neid vastavalt eri atribuutidele.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270351"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="1fe28-103">Segmentide loomine ja haldamine</span><span class="sxs-lookup"><span data-stu-id="1fe28-103">Create and manage segments</span></span>

<span data-ttu-id="1fe28-104">Segmentide abil saate oma kliente rühmitada demograafiliste, tehingupõhiste või käitumuslike atribuutide põhjal.</span><span class="sxs-lookup"><span data-stu-id="1fe28-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="1fe28-105">Segmentide abil saate sihtida reklaamikampaaniaid, müügitegevusi ja klienditoe ttoiminguid oma ärieesmärkide saavutamiseks.</span><span class="sxs-lookup"><span data-stu-id="1fe28-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="1fe28-106">Saate kliendiprofiili olemile ja sellega seotud olemitele luua keerukaid filtreid.</span><span class="sxs-lookup"><span data-stu-id="1fe28-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="1fe28-107">Pärast töötlemist loob iga segment hulga kliendi kirjeid, mille saate eksportida ja nendega toiminguid teha.</span><span class="sxs-lookup"><span data-stu-id="1fe28-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="1fe28-108">Kehtivad [teenusepiirangud](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="1fe28-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="1fe28-109">Kui ei ole teisiti öeldud, on kõik segmendid **dünaamilised segmendid**, mida värskendatakse korduva ajakava alusel.</span><span class="sxs-lookup"><span data-stu-id="1fe28-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="1fe28-110">Järgmine näide illustreerib segmenteerimise võimalust.</span><span class="sxs-lookup"><span data-stu-id="1fe28-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="1fe28-111">Oleme määratlenud segmendi klientidele, kes on tellinud vähemalt 500 USD eest kaupu viimase 90 päeva jooksul *ja* kes olid seotud klienditeeninduse kõnega, mida eskaleeriti.</span><span class="sxs-lookup"><span data-stu-id="1fe28-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1fe28-112">![Mitu rühma](media/segmentation-group1-2.png "Mitu rühma")</span><span class="sxs-lookup"><span data-stu-id="1fe28-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="1fe28-113">Looge uus segment</span><span class="sxs-lookup"><span data-stu-id="1fe28-113">Create a new segment</span></span>

<span data-ttu-id="1fe28-114">Segmente saab hallata lehel **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="1fe28-115">Avage sihtrühmaülevaadetes leht **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="1fe28-116">Valige **Uus** > **Tühi segment**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="1fe28-117">Valige paanis **Uus segment** segmendi tüüp ja sisestage **nimi**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="1fe28-118">Soovi korral sisestage segmendi tuvastamist hõlbustav näidatav nimi ja kirjeldus.</span><span class="sxs-lookup"><span data-stu-id="1fe28-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="1fe28-119">Rühma määramise lehele **Segmendikoostur** minemiseks valige **Järgmine**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="1fe28-120">Rühm on hulk kliente.</span><span class="sxs-lookup"><span data-stu-id="1fe28-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="1fe28-121">Valige olem, mis sisaldab segmenteeritavat atribuuti.</span><span class="sxs-lookup"><span data-stu-id="1fe28-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="1fe28-122">Valige atribuut, mille järgi segmenteerida.</span><span class="sxs-lookup"><span data-stu-id="1fe28-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="1fe28-123">Atribuudil võib olla üks neljast väärtuse tüübist: arvuline, string, kuupäev või Boolean.</span><span class="sxs-lookup"><span data-stu-id="1fe28-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="1fe28-124">Valige valitud atribuudi tehtemärk ja väärtus.</span><span class="sxs-lookup"><span data-stu-id="1fe28-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1fe28-125">![Kohandatud rühma filter](media/customer-group-numbers.png "Kliendi rühma filter")</span><span class="sxs-lookup"><span data-stu-id="1fe28-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="1fe28-126">Number</span><span class="sxs-lookup"><span data-stu-id="1fe28-126">Number</span></span> |<span data-ttu-id="1fe28-127">Määratlus</span><span class="sxs-lookup"><span data-stu-id="1fe28-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="1fe28-128">1</span><span class="sxs-lookup"><span data-stu-id="1fe28-128">1</span></span>     |<span data-ttu-id="1fe28-129">Entity</span><span class="sxs-lookup"><span data-stu-id="1fe28-129">Entity</span></span>          |
   |<span data-ttu-id="1fe28-130">2</span><span class="sxs-lookup"><span data-stu-id="1fe28-130">2</span></span>     |<span data-ttu-id="1fe28-131">Atribuut</span><span class="sxs-lookup"><span data-stu-id="1fe28-131">Attribute</span></span>          |
   |<span data-ttu-id="1fe28-132">3</span><span class="sxs-lookup"><span data-stu-id="1fe28-132">3</span></span>    |<span data-ttu-id="1fe28-133">Operaator</span><span class="sxs-lookup"><span data-stu-id="1fe28-133">Operator</span></span>         |
   |<span data-ttu-id="1fe28-134">4</span><span class="sxs-lookup"><span data-stu-id="1fe28-134">4</span></span>    |<span data-ttu-id="1fe28-135">Väärtus</span><span class="sxs-lookup"><span data-stu-id="1fe28-135">Value</span></span>         |

8. <span data-ttu-id="1fe28-136">Kui olem on ühtlustatud kliendi olemiga seotud läbi [seoste](relationships.md), peate määratlema seose tee kehtiva segmendi loomiseks.</span><span class="sxs-lookup"><span data-stu-id="1fe28-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="1fe28-137">Lisage olemid seose teest, kuni saate valida ripploendist olemi vormi **Klient: CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="1fe28-138">Seejärel valige iga tingimuse jaoks **Kõik kirjed**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1fe28-139">![Seose tee segmendi loomise ajal](media/segments-multiple-relationships.png "Seose tee segmendi loomise ajal")</span><span class="sxs-lookup"><span data-stu-id="1fe28-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="1fe28-140">Segmendi salvestamiseks valige nupp **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="1fe28-141">Segment salvestatakse ja töödeldakse, kui kõik nõuded on kinnitatud.</span><span class="sxs-lookup"><span data-stu-id="1fe28-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="1fe28-142">Vastasel juhul salvestatakse see mustandina.</span><span class="sxs-lookup"><span data-stu-id="1fe28-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="1fe28-143">Valige **Tagasi segmentidesse**, et naasta lehele **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="1fe28-144">Olemasolevate segmentide haldamine</span><span class="sxs-lookup"><span data-stu-id="1fe28-144">Manage existing segments</span></span>

<span data-ttu-id="1fe28-145">Lehel **Segmendid** näete kõiki salvestatud segmente ja saate neid hallata.</span><span class="sxs-lookup"><span data-stu-id="1fe28-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="1fe28-146">Igat segmenti esindab rida, mis sisaldab segmendi kohta täiendavat teavet.</span><span class="sxs-lookup"><span data-stu-id="1fe28-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="1fe28-147">Saate veeru segmente sorteerida, valides veerupäise.</span><span class="sxs-lookup"><span data-stu-id="1fe28-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="1fe28-148">Kasutage segmentide filtreerimiseks paremas ülanurgas asuvat välja **Otsing**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1fe28-149">![Olemasoleva segmendi haldamise võimalused](media/segments-selected-segment.png "Olemasoleva segmendi haldamise võimalused")</span><span class="sxs-lookup"><span data-stu-id="1fe28-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="1fe28-150">Segmendi valimisel on saadaval järgmised tegevused.</span><span class="sxs-lookup"><span data-stu-id="1fe28-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="1fe28-151">Segmendi üksikasjade **Vaatamine**, sealhulgas liikmete arvu suundumist, segmendi liikmete ülevaadet.</span><span class="sxs-lookup"><span data-stu-id="1fe28-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="1fe28-152">Segmendi **Redigeerimine** atribuutide muutmiseks.</span><span class="sxs-lookup"><span data-stu-id="1fe28-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="1fe28-153">Segmendi **Värskendamine** viimaste andmete kaasamiseks.</span><span class="sxs-lookup"><span data-stu-id="1fe28-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="1fe28-154">Segmendi **Aktiveerimine** või **Desaktiveerimine**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="1fe28-155">Segmentidel on kaks võimalikku olekut – aktiivne või passiivne.</span><span class="sxs-lookup"><span data-stu-id="1fe28-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="1fe28-156">Nendest olekutest on kasu segmendi redigeerimise ajal.</span><span class="sxs-lookup"><span data-stu-id="1fe28-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="1fe28-157">Passiivsete segmentide puhul segmendi määratlus on olemus, kuid see ei sisalda ühtegi klienti.</span><span class="sxs-lookup"><span data-stu-id="1fe28-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="1fe28-158">Kui aktiveerite segmendi, siis selle olekuks muutub valikult passiivne valikule aktiivne ja see hakkab otsima kliente, mis vastavad segmendi määratlusele.</span><span class="sxs-lookup"><span data-stu-id="1fe28-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="1fe28-159">Kui [plaanitud värskendus](system.md#schedule-tab) on konfigureeritud, on passiivsete segmentide **olekuks** **Vahele jäetud**, mis näitab, et värskendamist isegi ei proovitud.</span><span class="sxs-lookup"><span data-stu-id="1fe28-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="1fe28-160">Kui passiivne segment aktiveeritakse, värskendatakse seda ja lisatakse plaanitud värskendustesse.</span><span class="sxs-lookup"><span data-stu-id="1fe28-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="1fe28-161">Teise võimalusena saate kasutada ripploendi **Aktiveeri/desaktiveeri** funktsiooni **Ajasta hiljem**, et määrata kindla segmendi aktiveerimise ja desaktiveerimise tulevane kuupäev ja kellaaeg.</span><span class="sxs-lookup"><span data-stu-id="1fe28-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="1fe28-162">Segmendi **Ümbernimetamine**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-162">**Rename** the segment.</span></span>
- <span data-ttu-id="1fe28-163">Liikmete loendi **Allalaadimine** CSV-failina.</span><span class="sxs-lookup"><span data-stu-id="1fe28-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="1fe28-164">Suvand **Lisa** saadab segmendi kliendi ID-de loendi teises rakenduses töötlemiseks.</span><span class="sxs-lookup"><span data-stu-id="1fe28-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="1fe28-165">Segmendi **Kustutamine**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="1fe28-166">Segmentide värskendamine</span><span class="sxs-lookup"><span data-stu-id="1fe28-166">Refresh segments</span></span>

<span data-ttu-id="1fe28-167">Saate kõiki segmente korraga värskendada, valides lehel **Segmendid** suvandi **Värskenda kõik** või saate ühte või mitut segmenti värskendada, kui valite need ja valite suvandite hulgast **Värskenda**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="1fe28-168">Teise võimalusena saate konfigureerida korduva värskendamise, valides **Administraator** > **Süsteem** > **Ajasta**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="1fe28-169">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="1fe28-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="1fe28-170">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="1fe28-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="1fe28-171">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="1fe28-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="1fe28-172">Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="1fe28-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="1fe28-173">Segmentide allalaadimine ja eksportimine</span><span class="sxs-lookup"><span data-stu-id="1fe28-173">Download and export segments</span></span>

<span data-ttu-id="1fe28-174">Saate oma segmendid kas CSV-faili alla laadida või eksportida need rakendusse Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="1fe28-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="1fe28-175">Segmentide allalaadimine CSV-faili</span><span class="sxs-lookup"><span data-stu-id="1fe28-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="1fe28-176">Avage sihtrühmaülevaadetes leht **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="1fe28-177">Valige konkreetse segmendi paanil kolmikpunkt.</span><span class="sxs-lookup"><span data-stu-id="1fe28-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="1fe28-178">Valige ripploendi toimingutest käsk **Laadi alla CSV-vormingus**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="1fe28-179">Segmentide eksportimine rakendusse Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="1fe28-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="1fe28-180">Enne segmentide eksportimist rakendusse Dynamics 365 Sales peab administraator [looma ekspordi sihtkoha](export-destinations.md) rakendusele Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="1fe28-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="1fe28-181">Avage sihtrühmaülevaadetes leht **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="1fe28-182">Valige konkreetse segmendi paanil kolmikpunkt.</span><span class="sxs-lookup"><span data-stu-id="1fe28-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="1fe28-183">Valige toimingute ripploendist **Lisa** ja valige ekspordi sihtkoht, kuhu soovite andmed saata.</span><span class="sxs-lookup"><span data-stu-id="1fe28-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="1fe28-184">Segmentide mustandi režiim</span><span class="sxs-lookup"><span data-stu-id="1fe28-184">Draft mode for segments</span></span>

<span data-ttu-id="1fe28-185">Kui kõik segmendi töötlemise nõuded pole täidetud, saate salvestada segmendi mustandina ja pääsete sellele juurde lehelt **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="1fe28-186">See salvestatakse passiivse segmendina ja seda ei saa aktiveerida enne, kui see on kehtiv.</span><span class="sxs-lookup"><span data-stu-id="1fe28-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="1fe28-187">Lisage rühma täiendavaid tingimusi</span><span class="sxs-lookup"><span data-stu-id="1fe28-187">Add more conditions to a group</span></span>

<span data-ttu-id="1fe28-188">Rühmale täiendavate tingimuste lisamiseks saate kasutada kaht loogikatehet:</span><span class="sxs-lookup"><span data-stu-id="1fe28-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="1fe28-189">**AND** tehtemärk: mõlemad tingimused tuleb täita segmenteerimise võimaldamiseks.</span><span class="sxs-lookup"><span data-stu-id="1fe28-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="1fe28-190">See valik on kõige kasulikum juhul, kui määratlete eri olemite tingimusi.</span><span class="sxs-lookup"><span data-stu-id="1fe28-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="1fe28-191">**VÕI** tehtemärk: üks tingimus tuleb täita segmenteerimise võimaldamiseks.</span><span class="sxs-lookup"><span data-stu-id="1fe28-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="1fe28-192">See valik on kõige kasulikum juhul, kui määratlete sama olemi mitu tingimusi.</span><span class="sxs-lookup"><span data-stu-id="1fe28-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1fe28-193">![OR tehtemärk, kus tuleb täita üks tingimustest](media/segmentation-either-condition.png "OR tehtemärk, kus tuleb täita üks tingimustest")</span><span class="sxs-lookup"><span data-stu-id="1fe28-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="1fe28-194">Praegu saab pesastada tehtemärki **OR** tehtemärgi **AND** põhjal, ent mitte vastupidi.</span><span class="sxs-lookup"><span data-stu-id="1fe28-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="1fe28-195">Mitme rühma kombineerimine</span><span class="sxs-lookup"><span data-stu-id="1fe28-195">Combine multiple groups</span></span>

<span data-ttu-id="1fe28-196">Iga rühm toodab kindla klientide kogumi.</span><span class="sxs-lookup"><span data-stu-id="1fe28-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="1fe28-197">Neid rühmi saate kombineerida, et kaasata teie ärimudeli jaoks vajalikud kliendid.</span><span class="sxs-lookup"><span data-stu-id="1fe28-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="1fe28-198">Minge sihtrühmaülevaadetes lehele **Segmendid** ja valige segment.</span><span class="sxs-lookup"><span data-stu-id="1fe28-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="1fe28-199">Valige **Lisa rühm**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1fe28-200">![Kliendirühma lisamine](media/customer-group-add-group.png "Kliendirühma lisamine")</span><span class="sxs-lookup"><span data-stu-id="1fe28-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="1fe28-201">Valige üks järgmistest määramistehetest: **Ühend**, **Ühisosa** või **Välja arvatud**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1fe28-202">![Kliendirühma ühendi lisamine](media/customer-group-union.png "Kliendirühma ühendi lisamine")</span><span class="sxs-lookup"><span data-stu-id="1fe28-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="1fe28-203">Valige uue rühma määratlemiseks tehtemärk.</span><span class="sxs-lookup"><span data-stu-id="1fe28-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="1fe28-204">Salvestage eri rühmad, et teha kindlaks säilitatavad andmed.</span><span class="sxs-lookup"><span data-stu-id="1fe28-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="1fe28-205">**ühend** ühendab kaks rühma.</span><span class="sxs-lookup"><span data-stu-id="1fe28-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="1fe28-206">**Ühisosa** kattub kahe rühmaga.</span><span class="sxs-lookup"><span data-stu-id="1fe28-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="1fe28-207">Koondatud rühma jäetakse alles ainult andmed, mis on mõlemas rühmas *ühised*.</span><span class="sxs-lookup"><span data-stu-id="1fe28-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="1fe28-208">**Välja arvatud** kombineerib kaks rühma.</span><span class="sxs-lookup"><span data-stu-id="1fe28-208">**Except** combines the two groups.</span></span> <span data-ttu-id="1fe28-209">Alles jäetakse ainult sellised rühma A andmed, mida *ei leidu* rühmas B.</span><span class="sxs-lookup"><span data-stu-id="1fe28-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="1fe28-210">Vaadake töötlemise ajalugu ja segmendi liikmeid</span><span class="sxs-lookup"><span data-stu-id="1fe28-210">View processing history and segment members</span></span>

<span data-ttu-id="1fe28-211">Segmendi koondandmete nägemiseks vaadake üle selle üksikasjad.</span><span class="sxs-lookup"><span data-stu-id="1fe28-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="1fe28-212">Lehel **Segmendid** valige ülevaadatav segment.</span><span class="sxs-lookup"><span data-stu-id="1fe28-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="1fe28-213">Lehe ülaosa sisaldab suundumuse trendigraafikut, mis visualiseerib liikmete arvu muudatused.</span><span class="sxs-lookup"><span data-stu-id="1fe28-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="1fe28-214">Hoidke kursorit andmepunktide kohal, et näha liikmete arvu kindlal kuupäeval.</span><span class="sxs-lookup"><span data-stu-id="1fe28-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="1fe28-215">Saate uuendada visualiseerimise ajavahemikku.</span><span class="sxs-lookup"><span data-stu-id="1fe28-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1fe28-216">![Segmendi ajavahemik](media/segment-time-range.png "Segmendi ajavahemik")</span><span class="sxs-lookup"><span data-stu-id="1fe28-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="1fe28-217">Alaosa sisaldab segmendi liikmete loendit.</span><span class="sxs-lookup"><span data-stu-id="1fe28-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="1fe28-218">Selle loendi väljad põhinevad segmendi olemite atribuutidel.</span><span class="sxs-lookup"><span data-stu-id="1fe28-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="1fe28-219">Loend on eelvaade kattuvatest segmendi liikmetest ja näitab segmendi 100 esimest kirjet, et saaksite vajadusel kiiresti seda hinnata ja kontrollida selle määratlusi.</span><span class="sxs-lookup"><span data-stu-id="1fe28-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="1fe28-220">Kõikide kattuvate kirjete nägemiseks peate [eksportima segmendi](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1fe28-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="1fe28-221">Kiirsegmendid</span><span class="sxs-lookup"><span data-stu-id="1fe28-221">Quick segments</span></span>

<span data-ttu-id="1fe28-222">Lisaks segmendikujundajale on veel üks võimalus segmentide loomiseks.</span><span class="sxs-lookup"><span data-stu-id="1fe28-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="1fe28-223">Kiirsegmendid võimaldavad teil luua lihtsaid segmente (ühe operaatoriga) kiiresti ja koheste ülevaadetega.</span><span class="sxs-lookup"><span data-stu-id="1fe28-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="1fe28-224">Valige lehel **Segmendid** jaotis **Uus** > **Kiirloomise vorm**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="1fe28-225">Ühendatud kliendiprofiilil põhineva segmendi loomiseks valige valik **Profiilid**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="1fe28-226">Valige valik **Mõõtmed**, et luua varem lehel **Mõõtmed** loodud iga mõõtme kliendiatribuudi tüübi ümber segment.</span><span class="sxs-lookup"><span data-stu-id="1fe28-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="1fe28-227">Valige suvand **Ärianalüüs**, et luua segment ümber ühe väljundi olemi, mille olete loonud, kasutades kas **Prognooside** või **Kohandatud mudelite** võimalusi.</span><span class="sxs-lookup"><span data-stu-id="1fe28-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="1fe28-228">Valige dialoogiboksis **Uus kiirsegment** atribuut ripploendist **Väli**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="1fe28-229">Süsteem esitab paar täiendavat ülevaadet, mis aitavad luua klientidest paremad segmendid.</span><span class="sxs-lookup"><span data-stu-id="1fe28-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="1fe28-230">Kategooria väljade puhul näitame 10 peamist kliendi arvu.</span><span class="sxs-lookup"><span data-stu-id="1fe28-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="1fe28-231">Valige **Väärtus** ja **Ülevaatamine**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="1fe28-232">Süsteem näitab numbrilise atribuudi puhul, mis atribuudi väärtus langeb iga kliendi protsendiili alla.</span><span class="sxs-lookup"><span data-stu-id="1fe28-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="1fe28-233">Valige **Tehtemärk**, **Väärtus** ja **Ülevaatamine**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="1fe28-234">Süsteem esitab **hinnangulise segmendi mahu**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="1fe28-235">Saate valida, kas luua määratletud segment või esmalt vaadata seda uuesti, et hankida muus mahus segment.</span><span class="sxs-lookup"><span data-stu-id="1fe28-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1fe28-236">![Kiirsegmendi nimi ja hinnang](media/quick-segment-name.png "Kiirsegmendi nimi ja hinnang")</span><span class="sxs-lookup"><span data-stu-id="1fe28-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="1fe28-237">Sisestage segmendi **nimi**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="1fe28-238">Soovi korral sisestage **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="1fe28-239">Segmendi loomiseks valige käsk **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="1fe28-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="1fe28-240">Pärast segmendi töötlust saate seda vaadata nagu kõiki teisi loodud segmente.</span><span class="sxs-lookup"><span data-stu-id="1fe28-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="1fe28-241">Järgmistes olukordades soovitame kasutada segmendikoosturit, mitte soovitatavat segmentide võimalust:</span><span class="sxs-lookup"><span data-stu-id="1fe28-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="1fe28-242">Segmentide loomine filtritega kategooriliselt väljadel, kus tehtemärgiks pole **Is**</span><span class="sxs-lookup"><span data-stu-id="1fe28-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="1fe28-243">Segmentide loomine filtritega numbriliselt väljadel, kus tehtemärkideks pole **Between**, **Greater than** ja **Less than**</span><span class="sxs-lookup"><span data-stu-id="1fe28-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="1fe28-244">Filtritega segmentide loomine kuupäeva tüüpi väljadel</span><span class="sxs-lookup"><span data-stu-id="1fe28-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="1fe28-245">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="1fe28-245">Next steps</span></span>

<span data-ttu-id="1fe28-246">Kliendi taseme ülevaadete hankimiseks [eksportige segment](export-destinations.md) ja tutvuge [kliendikaardiga](customer-card-add-in.md) ning [ühendajatega](export-power-bi.md).</span><span class="sxs-lookup"><span data-stu-id="1fe28-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]