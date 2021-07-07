---
title: Segmendid publiku ülevaates
description: Ülevaade segmentidest ning kuidas neid luua ja hallata.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306252"
---
# <a name="segments-overview"></a><span data-ttu-id="31c06-103">Segmentide ülevaade</span><span class="sxs-lookup"><span data-stu-id="31c06-103">Segments overview</span></span>

<span data-ttu-id="31c06-104">Segmentide abil saate oma kliente rühmitada demograafiliste, tehingupõhiste või käitumuslike atribuutide põhjal.</span><span class="sxs-lookup"><span data-stu-id="31c06-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="31c06-105">Segmentide abil saate sihtida reklaamikampaaniaid, müügitegevusi ja klienditoe ttoiminguid oma ärieesmärkide saavutamiseks.</span><span class="sxs-lookup"><span data-stu-id="31c06-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="31c06-106">Kliendiprofiile, mis vastavad segmendi määratluse filtritele, nimetatakse segmendi *liikmeteks* .</span><span class="sxs-lookup"><span data-stu-id="31c06-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="31c06-107">Kehtivad [teenusepiirangud](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="31c06-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="31c06-108">Looge uus segment</span><span class="sxs-lookup"><span data-stu-id="31c06-108">Create a new segment</span></span>

<span data-ttu-id="31c06-109">Uue segmendi loomiseks on mitu võimalust.</span><span class="sxs-lookup"><span data-stu-id="31c06-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="31c06-110">Keerukas segment segmendi ehitajaga: [Tühi segment](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="31c06-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="31c06-111">Lihtsad segmendid ühe tehtega: [Kiirsegment](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="31c06-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="31c06-112">AI-powered viis sarnaste klientide leidmiseks: [Sarnased Kliendid](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="31c06-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="31c06-113">AI-powered soovitused, mis põhinevad mõõtmistel või atribuutidel: [Soovitatavad segmendid mõõtmiste parendamiseks](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="31c06-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="31c06-114">Tegevustel põhinevad soovitused: [Klienditegevusel põhinevad soovitatavad segmendid](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="31c06-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="31c06-115">Olemasolevate segmentide haldamine</span><span class="sxs-lookup"><span data-stu-id="31c06-115">Manage existing segments</span></span>

<span data-ttu-id="31c06-116">Minge lehele **Segmendid** et vaadata ja hallata kõiki oma salvestatud segmente.</span><span class="sxs-lookup"><span data-stu-id="31c06-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="31c06-117">Igat segmenti esindab rida, mis sisaldab segmendi kohta täiendavat teavet.</span><span class="sxs-lookup"><span data-stu-id="31c06-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valitud segment suvandite ripploendi ja saadaolevate suvanditega.":::

<span data-ttu-id="31c06-119">Segmendi valimisel on saadaval järgmised tegevused.</span><span class="sxs-lookup"><span data-stu-id="31c06-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="31c06-120">Segmendi üksikasjade **Vaatamine**, sealhulgas liikmete arvu suundumist, segmendi liikmete ülevaadet.</span><span class="sxs-lookup"><span data-stu-id="31c06-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="31c06-121">Segmendi **Redigeerimine** atribuutide muutmiseks.</span><span class="sxs-lookup"><span data-stu-id="31c06-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="31c06-122">Segmendi **Duplikaadi loomine**.</span><span class="sxs-lookup"><span data-stu-id="31c06-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="31c06-123">Saate selle atribuute kohe redigeerida või lihtsalt duplikaadi salvestada.</span><span class="sxs-lookup"><span data-stu-id="31c06-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="31c06-124">Segmendi **Värskendamine** viimaste andmete kaasamiseks.</span><span class="sxs-lookup"><span data-stu-id="31c06-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="31c06-125">Segmendi **Aktiveerimine** või **Desaktiveerimine**.</span><span class="sxs-lookup"><span data-stu-id="31c06-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="31c06-126">Segmentidel on kaks võimalikku olekut – aktiivne või passiivne.</span><span class="sxs-lookup"><span data-stu-id="31c06-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="31c06-127">Nendest olekutest on kasu segmendi redigeerimise ajal.</span><span class="sxs-lookup"><span data-stu-id="31c06-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="31c06-128">Passiivsete segmentide puhul segmendi määratlus on olemus, kuid see ei sisalda ühtegi klienti.</span><span class="sxs-lookup"><span data-stu-id="31c06-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="31c06-129">Kui aktiveerite segmendi, siis selle olekuks muutub valikult passiivne valikule aktiivne ja see hakkab otsima kliente, mis vastavad segmendi määratlusele.</span><span class="sxs-lookup"><span data-stu-id="31c06-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="31c06-130">Kui [plaanitud värskendus](system.md#schedule-tab) on konfigureeritud, on passiivsete segmentide **olekuks** **Vahele jäetud**, mis näitab, et värskendamist isegi ei proovitud.</span><span class="sxs-lookup"><span data-stu-id="31c06-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="31c06-131">Kui passiivne segment aktiveeritakse, värskendatakse seda ja lisatakse plaanitud värskendustesse.</span><span class="sxs-lookup"><span data-stu-id="31c06-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="31c06-132">Teise võimalusena saate kasutada ripploendi **Aktiveeri/desaktiveeri** funktsiooni **Ajasta hiljem**, et määrata kindla segmendi aktiveerimise ja desaktiveerimise tulevane kuupäev ja kellaaeg.</span><span class="sxs-lookup"><span data-stu-id="31c06-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="31c06-133">Segmendi **Ümbernimetamine**.</span><span class="sxs-lookup"><span data-stu-id="31c06-133">**Rename** the segment.</span></span>
- <span data-ttu-id="31c06-134">Liikmete loendi **Allalaadimine** CSV-failina.</span><span class="sxs-lookup"><span data-stu-id="31c06-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="31c06-135">**Eksportide haldamine** suvand ekspordiga seotud segmendi kuvamiseks ja haldamiseks.</span><span class="sxs-lookup"><span data-stu-id="31c06-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="31c06-136">Lisateave eksportide kohta.</span><span class="sxs-lookup"><span data-stu-id="31c06-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="31c06-137">Segmendi **Kustutamine**.</span><span class="sxs-lookup"><span data-stu-id="31c06-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="31c06-138">Segmentide värskendamine</span><span class="sxs-lookup"><span data-stu-id="31c06-138">Refresh segments</span></span>

<span data-ttu-id="31c06-139">Saate kõiki segmente korraga värskendada, valides lehel **Segmendid** suvandi **Värskenda kõik** või saate ühte või mitut segmenti värskendada, kui valite need ja valite suvandite hulgast **Värskenda**.</span><span class="sxs-lookup"><span data-stu-id="31c06-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="31c06-140">Teise võimalusena saate konfigureerida korduva värskendamise, valides **Administraator** > **Süsteem** > **Ajasta**.</span><span class="sxs-lookup"><span data-stu-id="31c06-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="31c06-141">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="31c06-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="31c06-142">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="31c06-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="31c06-143">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="31c06-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="31c06-144">Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="31c06-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="31c06-145">Ekspordi segmendid</span><span class="sxs-lookup"><span data-stu-id="31c06-145">Export segments</span></span>

<span data-ttu-id="31c06-146">Segmenti saate eksportida segmentide lehelt või [ekspordilehelt](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="31c06-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="31c06-147">Minge lehele **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="31c06-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="31c06-148">Valige **Kuva rohkem [....]** segmendile, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="31c06-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="31c06-149">Valige **Ekspordi haldamine** tegevuste ripploendist.</span><span class="sxs-lookup"><span data-stu-id="31c06-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="31c06-150">Avaneb **Segmendi ekspordid (eelvaade)** leht.</span><span class="sxs-lookup"><span data-stu-id="31c06-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="31c06-151">Näete kõiki konfigureeritud eksporte, mis on rühmitatud praegust segmenti sisaldavate või seda mitte sisaldavate ekspordite järgi.</span><span class="sxs-lookup"><span data-stu-id="31c06-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="31c06-152">Valitud segmendi lisamiseks ekspordile valige loendist eksport ja valige **Lisa segment**.</span><span class="sxs-lookup"><span data-stu-id="31c06-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="31c06-153">Valitud segmendiga uue ekspordi loomiseks valige **Lisa eksport**.</span><span class="sxs-lookup"><span data-stu-id="31c06-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="31c06-154">Lisateavet ekspordi loomise kohta leiate teemast [Uue ekspordi häälestamine](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="31c06-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="31c06-155">Segmentide põhilehele naasmiseks klõpsake nuppu **Tagasi**.</span><span class="sxs-lookup"><span data-stu-id="31c06-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="31c06-156">Vaadake töötlemise ajalugu ja segmendi liikmeid</span><span class="sxs-lookup"><span data-stu-id="31c06-156">View processing history and segment members</span></span>

<span data-ttu-id="31c06-157">Segmendi koondandmete nägemiseks vaadake üle selle üksikasjad.</span><span class="sxs-lookup"><span data-stu-id="31c06-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="31c06-158">Lehel **Segmendid** valige ülevaadatav segment.</span><span class="sxs-lookup"><span data-stu-id="31c06-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="31c06-159">Lehe ülaosa sisaldab suundumuse trendigraafikut, mis visualiseerib liikmete arvu muudatused.</span><span class="sxs-lookup"><span data-stu-id="31c06-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="31c06-160">Hoidke kursorit andmepunktide kohal, et näha liikmete arvu kindlal kuupäeval.</span><span class="sxs-lookup"><span data-stu-id="31c06-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="31c06-161">Saate uuendada visualiseerimise ajavahemikku.</span><span class="sxs-lookup"><span data-stu-id="31c06-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="31c06-162">![Segmendi ajavahemik](media/segment-time-range.png "Segmendi ajavahemik")</span><span class="sxs-lookup"><span data-stu-id="31c06-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="31c06-163">Alaosa sisaldab segmendi liikmete loendit.</span><span class="sxs-lookup"><span data-stu-id="31c06-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="31c06-164">Selle loendi väljad põhinevad segmendi olemite atribuutidel.</span><span class="sxs-lookup"><span data-stu-id="31c06-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="31c06-165">Loend on eelvaade kattuvatest segmendi liikmetest ja näitab segmendi 100 esimest kirjet, et saaksite vajadusel kiiresti seda hinnata ja kontrollida selle määratlusi.</span><span class="sxs-lookup"><span data-stu-id="31c06-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="31c06-166">Kõikide kattuvate kirjete nägemiseks peate [eksportima segmendi](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="31c06-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
