---
title: Segmentide loomine ja haldamine
description: Looge klientide segmente, et rühmitada neid vastavalt eri atribuutidele.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597046"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="c4259-103">Segmentide loomine ja haldamine</span><span class="sxs-lookup"><span data-stu-id="c4259-103">Create and manage segments</span></span>

<span data-ttu-id="c4259-104">Segmentide abil saate oma kliente rühmitada demograafiliste, tehingupõhiste või käitumuslike atribuutide põhjal.</span><span class="sxs-lookup"><span data-stu-id="c4259-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="c4259-105">Segmentide abil saate sihtida reklaamikampaaniaid, müügitegevusi ja klienditoe ttoiminguid oma ärieesmärkide saavutamiseks.</span><span class="sxs-lookup"><span data-stu-id="c4259-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="c4259-106">Saate kliendiprofiili olemile ja sellega seotud olemitele luua keerukaid filtreid.</span><span class="sxs-lookup"><span data-stu-id="c4259-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="c4259-107">Pärast töötlemist loob iga segment hulga kliendi kirjeid, mille saate eksportida ja nendega toiminguid teha.</span><span class="sxs-lookup"><span data-stu-id="c4259-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="c4259-108">Kehtivad [teenusepiirangud](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="c4259-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="c4259-109">Kui ei ole teisiti öeldud, on kõik segmendid **dünaamilised segmendid**, mida värskendatakse korduva ajakava alusel.</span><span class="sxs-lookup"><span data-stu-id="c4259-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="c4259-110">Järgmine näide illustreerib segmenteerimise võimalust.</span><span class="sxs-lookup"><span data-stu-id="c4259-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="c4259-111">Oleme määratlenud segmendi klientidele, kes on tellinud vähemalt 500 USD eest kaupu viimase 90 päeva jooksul *ja* kes olid seotud klienditeeninduse kõnega, mida eskaleeriti.</span><span class="sxs-lookup"><span data-stu-id="c4259-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4259-112">![Mitu rühma](media/segmentation-group1-2.png "Mitu rühma")</span><span class="sxs-lookup"><span data-stu-id="c4259-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="c4259-113">Looge uus segment</span><span class="sxs-lookup"><span data-stu-id="c4259-113">Create a new segment</span></span>

<span data-ttu-id="c4259-114">Segmente saab hallata lehel **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="c4259-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="c4259-115">Avage sihtrühmaülevaadetes leht **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="c4259-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="c4259-116">Valige **Uus** > **Tühi segment**.</span><span class="sxs-lookup"><span data-stu-id="c4259-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="c4259-117">Valige paanis **Uus segment** segmendi tüüp ja sisestage **nimi**.</span><span class="sxs-lookup"><span data-stu-id="c4259-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="c4259-118">Soovi korral sisestage segmendi tuvastamist hõlbustav näidatav nimi ja kirjeldus.</span><span class="sxs-lookup"><span data-stu-id="c4259-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="c4259-119">Rühma määramise lehele **Segmendikoostur** minemiseks valige **Järgmine**.</span><span class="sxs-lookup"><span data-stu-id="c4259-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="c4259-120">Rühm on hulk kliente.</span><span class="sxs-lookup"><span data-stu-id="c4259-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="c4259-121">Valige olem, mis sisaldab segmenteeritavat atribuuti.</span><span class="sxs-lookup"><span data-stu-id="c4259-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="c4259-122">Valige atribuut, mille järgi segmenteerida.</span><span class="sxs-lookup"><span data-stu-id="c4259-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="c4259-123">Atribuudil võib olla üks neljast väärtuse tüübist: arvuline, string, kuupäev või Boolean.</span><span class="sxs-lookup"><span data-stu-id="c4259-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="c4259-124">Valige valitud atribuudi tehtemärk ja väärtus.</span><span class="sxs-lookup"><span data-stu-id="c4259-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4259-125">![Kohandatud rühma filter](media/customer-group-numbers.png "Kliendi rühma filter")</span><span class="sxs-lookup"><span data-stu-id="c4259-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="c4259-126">Number</span><span class="sxs-lookup"><span data-stu-id="c4259-126">Number</span></span> |<span data-ttu-id="c4259-127">Määratlus</span><span class="sxs-lookup"><span data-stu-id="c4259-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="c4259-128">1</span><span class="sxs-lookup"><span data-stu-id="c4259-128">1</span></span>     |<span data-ttu-id="c4259-129">Entity</span><span class="sxs-lookup"><span data-stu-id="c4259-129">Entity</span></span>          |
   |<span data-ttu-id="c4259-130">2</span><span class="sxs-lookup"><span data-stu-id="c4259-130">2</span></span>     |<span data-ttu-id="c4259-131">Atribuut</span><span class="sxs-lookup"><span data-stu-id="c4259-131">Attribute</span></span>          |
   |<span data-ttu-id="c4259-132">3</span><span class="sxs-lookup"><span data-stu-id="c4259-132">3</span></span>    |<span data-ttu-id="c4259-133">Operaator</span><span class="sxs-lookup"><span data-stu-id="c4259-133">Operator</span></span>         |
   |<span data-ttu-id="c4259-134">4</span><span class="sxs-lookup"><span data-stu-id="c4259-134">4</span></span>    |<span data-ttu-id="c4259-135">Väärtus</span><span class="sxs-lookup"><span data-stu-id="c4259-135">Value</span></span>         |

8. <span data-ttu-id="c4259-136">Kui olem on ühtlustatud kliendi olemiga seotud läbi [seoste](relationships.md), peate määratlema seose tee kehtiva segmendi loomiseks.</span><span class="sxs-lookup"><span data-stu-id="c4259-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="c4259-137">Lisage olemid seose teest, kuni saate valida ripploendist olemi vormi **Klient: CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="c4259-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="c4259-138">Seejärel valige iga tingimuse jaoks **Kõik kirjed**.</span><span class="sxs-lookup"><span data-stu-id="c4259-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4259-139">![Seose tee segmendi loomise ajal](media/segments-multiple-relationships.png "Seose tee segmendi loomise ajal")</span><span class="sxs-lookup"><span data-stu-id="c4259-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="c4259-140">Vaikimisi genereerivad segmendid väljundolemi, mis sisaldab määratletud filtritele vastavaid kliendiprofiilide kõiki atribuute.</span><span class="sxs-lookup"><span data-stu-id="c4259-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="c4259-141">Kui segment põhineb muudel olemitel kui olem *Klient*, saate väljundolendisse lisada rohkem atribuute nendest olemitest.</span><span class="sxs-lookup"><span data-stu-id="c4259-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="c4259-142">Valige **Projekti tribuudid**, et valida väljundolemile lisatavad atribuudid.</span><span class="sxs-lookup"><span data-stu-id="c4259-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="c4259-143">Näide: segment põhineb olemil, mis sisaldab klienditegevuse andmeid, mis on seotud olemiga *Klient*.</span><span class="sxs-lookup"><span data-stu-id="c4259-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="c4259-144">Segment otsib kõiki kliente, kes on viimase 60 päeva jooksul klienditoele helistanud.</span><span class="sxs-lookup"><span data-stu-id="c4259-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="c4259-145">Saate valida kõne kestuse ja kõnede arvu lisamise kõigile väljundolemi vastavatele kliendikirjeile.</span><span class="sxs-lookup"><span data-stu-id="c4259-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="c4259-146">See teave võib kasulik olla meili saatmiseks koos kasulike linkidega võrgus asuvatele spikriartiklitele ja KKK-dele klientidele, kes sageli helistasid.</span><span class="sxs-lookup"><span data-stu-id="c4259-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="c4259-147">Segmendi salvestamiseks valige nupp **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="c4259-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="c4259-148">Segment salvestatakse ja töödeldakse, kui kõik nõuded on kinnitatud.</span><span class="sxs-lookup"><span data-stu-id="c4259-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="c4259-149">Vastasel juhul salvestatakse see mustandina.</span><span class="sxs-lookup"><span data-stu-id="c4259-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="c4259-150">Valige **Tagasi segmentidesse**, et naasta lehele **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="c4259-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="c4259-151">Olemasolevate segmentide haldamine</span><span class="sxs-lookup"><span data-stu-id="c4259-151">Manage existing segments</span></span>

<span data-ttu-id="c4259-152">Lehel **Segmendid** näete kõiki salvestatud segmente ja saate neid hallata.</span><span class="sxs-lookup"><span data-stu-id="c4259-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="c4259-153">Igat segmenti esindab rida, mis sisaldab segmendi kohta täiendavat teavet.</span><span class="sxs-lookup"><span data-stu-id="c4259-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="c4259-154">Saate veeru segmente sorteerida, valides veerupäise.</span><span class="sxs-lookup"><span data-stu-id="c4259-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="c4259-155">Kasutage segmentide filtreerimiseks paremas ülanurgas asuvat välja **Otsing**.</span><span class="sxs-lookup"><span data-stu-id="c4259-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4259-156">![Olemasoleva segmendi haldamise võimalused](media/segments-selected-segment.png "Olemasoleva segmendi haldamise võimalused")</span><span class="sxs-lookup"><span data-stu-id="c4259-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="c4259-157">Segmendi valimisel on saadaval järgmised tegevused.</span><span class="sxs-lookup"><span data-stu-id="c4259-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="c4259-158">Segmendi üksikasjade **Vaatamine**, sealhulgas liikmete arvu suundumist, segmendi liikmete ülevaadet.</span><span class="sxs-lookup"><span data-stu-id="c4259-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="c4259-159">Segmendi **Redigeerimine** atribuutide muutmiseks.</span><span class="sxs-lookup"><span data-stu-id="c4259-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="c4259-160">Segmendi **Duplikaadi loomine**.</span><span class="sxs-lookup"><span data-stu-id="c4259-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="c4259-161">Saate selle atribuute kohe redigeerida või lihtsalt duplikaadi salvestada.</span><span class="sxs-lookup"><span data-stu-id="c4259-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="c4259-162">Segmendi **Värskendamine** viimaste andmete kaasamiseks.</span><span class="sxs-lookup"><span data-stu-id="c4259-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="c4259-163">Segmendi **Aktiveerimine** või **Desaktiveerimine**.</span><span class="sxs-lookup"><span data-stu-id="c4259-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="c4259-164">Segmentidel on kaks võimalikku olekut – aktiivne või passiivne.</span><span class="sxs-lookup"><span data-stu-id="c4259-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="c4259-165">Nendest olekutest on kasu segmendi redigeerimise ajal.</span><span class="sxs-lookup"><span data-stu-id="c4259-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="c4259-166">Passiivsete segmentide puhul segmendi määratlus on olemus, kuid see ei sisalda ühtegi klienti.</span><span class="sxs-lookup"><span data-stu-id="c4259-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="c4259-167">Kui aktiveerite segmendi, siis selle olekuks muutub valikult passiivne valikule aktiivne ja see hakkab otsima kliente, mis vastavad segmendi määratlusele.</span><span class="sxs-lookup"><span data-stu-id="c4259-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="c4259-168">Kui [plaanitud värskendus](system.md#schedule-tab) on konfigureeritud, on passiivsete segmentide **olekuks** **Vahele jäetud**, mis näitab, et värskendamist isegi ei proovitud.</span><span class="sxs-lookup"><span data-stu-id="c4259-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="c4259-169">Kui passiivne segment aktiveeritakse, värskendatakse seda ja lisatakse plaanitud värskendustesse.</span><span class="sxs-lookup"><span data-stu-id="c4259-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="c4259-170">Teise võimalusena saate kasutada ripploendi **Aktiveeri/desaktiveeri** funktsiooni **Ajasta hiljem**, et määrata kindla segmendi aktiveerimise ja desaktiveerimise tulevane kuupäev ja kellaaeg.</span><span class="sxs-lookup"><span data-stu-id="c4259-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="c4259-171">Segmendi **Ümbernimetamine**.</span><span class="sxs-lookup"><span data-stu-id="c4259-171">**Rename** the segment.</span></span>
- <span data-ttu-id="c4259-172">Liikmete loendi **Allalaadimine** CSV-failina.</span><span class="sxs-lookup"><span data-stu-id="c4259-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="c4259-173">Suvand **Lisa** saadab segmendi kliendi ID-de loendi teises rakenduses töötlemiseks.</span><span class="sxs-lookup"><span data-stu-id="c4259-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="c4259-174">Segmendi **Kustutamine**.</span><span class="sxs-lookup"><span data-stu-id="c4259-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="c4259-175">Segmentide värskendamine</span><span class="sxs-lookup"><span data-stu-id="c4259-175">Refresh segments</span></span>

<span data-ttu-id="c4259-176">Saate kõiki segmente korraga värskendada, valides lehel **Segmendid** suvandi **Värskenda kõik** või saate ühte või mitut segmenti värskendada, kui valite need ja valite suvandite hulgast **Värskenda**.</span><span class="sxs-lookup"><span data-stu-id="c4259-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="c4259-177">Teise võimalusena saate konfigureerida korduva värskendamise, valides **Administraator** > **Süsteem** > **Ajasta**.</span><span class="sxs-lookup"><span data-stu-id="c4259-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="c4259-178">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="c4259-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="c4259-179">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="c4259-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="c4259-180">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="c4259-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="c4259-181">Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="c4259-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="c4259-182">Segmentide allalaadimine ja eksportimine</span><span class="sxs-lookup"><span data-stu-id="c4259-182">Download and export segments</span></span>

<span data-ttu-id="c4259-183">Saate oma segmendid kas CSV-faili alla laadida või eksportida need rakendusse Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c4259-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="c4259-184">Segmentide allalaadimine CSV-faili</span><span class="sxs-lookup"><span data-stu-id="c4259-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="c4259-185">Avage sihtrühmaülevaadetes leht **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="c4259-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c4259-186">Valige konkreetse segmendi paanil kolmikpunkt.</span><span class="sxs-lookup"><span data-stu-id="c4259-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c4259-187">Valige ripploendi toimingutest käsk **Laadi alla CSV-vormingus**.</span><span class="sxs-lookup"><span data-stu-id="c4259-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="c4259-188">Segmentide eksportimine rakendusse Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="c4259-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="c4259-189">Enne segmentide eksportimist rakendusse Dynamics 365 Sales peab administraator [looma ekspordi sihtkoha](export-destinations.md) rakendusele Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="c4259-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="c4259-190">Avage sihtrühmaülevaadetes leht **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="c4259-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="c4259-191">Valige konkreetse segmendi paanil kolmikpunkt.</span><span class="sxs-lookup"><span data-stu-id="c4259-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="c4259-192">Valige toimingute ripploendist **Lisa** ja valige ekspordi sihtkoht, kuhu soovite andmed saata.</span><span class="sxs-lookup"><span data-stu-id="c4259-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="c4259-193">Segmentide mustandi režiim</span><span class="sxs-lookup"><span data-stu-id="c4259-193">Draft mode for segments</span></span>

<span data-ttu-id="c4259-194">Kui kõik segmendi töötlemise nõuded pole täidetud, saate salvestada segmendi mustandina ja pääsete sellele juurde lehelt **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="c4259-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="c4259-195">See salvestatakse passiivse segmendina ja seda ei saa aktiveerida enne, kui see on kehtiv.</span><span class="sxs-lookup"><span data-stu-id="c4259-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="c4259-196">Lisage rühma täiendavaid tingimusi</span><span class="sxs-lookup"><span data-stu-id="c4259-196">Add more conditions to a group</span></span>

<span data-ttu-id="c4259-197">Rühmale täiendavate tingimuste lisamiseks saate kasutada kaht loogikatehet:</span><span class="sxs-lookup"><span data-stu-id="c4259-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="c4259-198">**AND** tehtemärk: mõlemad tingimused tuleb täita segmenteerimise võimaldamiseks.</span><span class="sxs-lookup"><span data-stu-id="c4259-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="c4259-199">See valik on kõige kasulikum juhul, kui määratlete eri olemite tingimusi.</span><span class="sxs-lookup"><span data-stu-id="c4259-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="c4259-200">**VÕI** tehtemärk: üks tingimus tuleb täita segmenteerimise võimaldamiseks.</span><span class="sxs-lookup"><span data-stu-id="c4259-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="c4259-201">See valik on kõige kasulikum juhul, kui määratlete sama olemi mitu tingimusi.</span><span class="sxs-lookup"><span data-stu-id="c4259-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4259-202">![OR tehtemärk, kus tuleb täita üks tingimustest](media/segmentation-either-condition.png "OR tehtemärk, kus tuleb täita üks tingimustest")</span><span class="sxs-lookup"><span data-stu-id="c4259-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="c4259-203">Praegu saab pesastada tehtemärki **OR** tehtemärgi **AND** põhjal, ent mitte vastupidi.</span><span class="sxs-lookup"><span data-stu-id="c4259-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="c4259-204">Mitme rühma kombineerimine</span><span class="sxs-lookup"><span data-stu-id="c4259-204">Combine multiple groups</span></span>

<span data-ttu-id="c4259-205">Iga rühm toodab kindla klientide kogumi.</span><span class="sxs-lookup"><span data-stu-id="c4259-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="c4259-206">Neid rühmi saate kombineerida, et kaasata teie ärimudeli jaoks vajalikud kliendid.</span><span class="sxs-lookup"><span data-stu-id="c4259-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="c4259-207">Minge sihtrühmaülevaadetes lehele **Segmendid** ja valige segment.</span><span class="sxs-lookup"><span data-stu-id="c4259-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="c4259-208">Valige **Lisa rühm**.</span><span class="sxs-lookup"><span data-stu-id="c4259-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4259-209">![Kliendirühma lisamine](media/customer-group-add-group.png "Kliendirühma lisamine")</span><span class="sxs-lookup"><span data-stu-id="c4259-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="c4259-210">Valige üks järgmistest määramistehetest: **Ühend**, **Ühisosa** või **Välja arvatud**.</span><span class="sxs-lookup"><span data-stu-id="c4259-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4259-211">![Kliendirühma ühendi lisamine](media/customer-group-union.png "Kliendirühma ühendi lisamine")</span><span class="sxs-lookup"><span data-stu-id="c4259-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="c4259-212">Valige uue rühma määratlemiseks tehtemärk.</span><span class="sxs-lookup"><span data-stu-id="c4259-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="c4259-213">Salvestage eri rühmad, et teha kindlaks säilitatavad andmed.</span><span class="sxs-lookup"><span data-stu-id="c4259-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="c4259-214">**ühend** ühendab kaks rühma.</span><span class="sxs-lookup"><span data-stu-id="c4259-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="c4259-215">**Ühisosa** kattub kahe rühmaga.</span><span class="sxs-lookup"><span data-stu-id="c4259-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="c4259-216">Koondatud rühma jäetakse alles ainult andmed, mis on mõlemas rühmas *ühised*.</span><span class="sxs-lookup"><span data-stu-id="c4259-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="c4259-217">**Välja arvatud** kombineerib kaks rühma.</span><span class="sxs-lookup"><span data-stu-id="c4259-217">**Except** combines the two groups.</span></span> <span data-ttu-id="c4259-218">Alles jäetakse ainult sellised rühma A andmed, mida *ei leidu* rühmas B.</span><span class="sxs-lookup"><span data-stu-id="c4259-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="c4259-219">Vaadake töötlemise ajalugu ja segmendi liikmeid</span><span class="sxs-lookup"><span data-stu-id="c4259-219">View processing history and segment members</span></span>

<span data-ttu-id="c4259-220">Segmendi koondandmete nägemiseks vaadake üle selle üksikasjad.</span><span class="sxs-lookup"><span data-stu-id="c4259-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="c4259-221">Lehel **Segmendid** valige ülevaadatav segment.</span><span class="sxs-lookup"><span data-stu-id="c4259-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="c4259-222">Lehe ülaosa sisaldab suundumuse trendigraafikut, mis visualiseerib liikmete arvu muudatused.</span><span class="sxs-lookup"><span data-stu-id="c4259-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="c4259-223">Hoidke kursorit andmepunktide kohal, et näha liikmete arvu kindlal kuupäeval.</span><span class="sxs-lookup"><span data-stu-id="c4259-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="c4259-224">Saate uuendada visualiseerimise ajavahemikku.</span><span class="sxs-lookup"><span data-stu-id="c4259-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c4259-225">![Segmendi ajavahemik](media/segment-time-range.png "Segmendi ajavahemik")</span><span class="sxs-lookup"><span data-stu-id="c4259-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="c4259-226">Alaosa sisaldab segmendi liikmete loendit.</span><span class="sxs-lookup"><span data-stu-id="c4259-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="c4259-227">Selle loendi väljad põhinevad segmendi olemite atribuutidel.</span><span class="sxs-lookup"><span data-stu-id="c4259-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="c4259-228">Loend on eelvaade kattuvatest segmendi liikmetest ja näitab segmendi 100 esimest kirjet, et saaksite vajadusel kiiresti seda hinnata ja kontrollida selle määratlusi.</span><span class="sxs-lookup"><span data-stu-id="c4259-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="c4259-229">Kõikide kattuvate kirjete nägemiseks peate [eksportima segmendi](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c4259-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="c4259-230">Kiirsegmendid</span><span class="sxs-lookup"><span data-stu-id="c4259-230">Quick segments</span></span>

<span data-ttu-id="c4259-231">Lisaks segmendikujundajale on veel üks võimalus segmentide loomiseks.</span><span class="sxs-lookup"><span data-stu-id="c4259-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="c4259-232">Kiirsegmendid võimaldavad teil luua lihtsaid segmente (ühe operaatoriga) kiiresti ja koheste ülevaadetega.</span><span class="sxs-lookup"><span data-stu-id="c4259-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="c4259-233">Valige lehel **Segmendid** jaotis **Uus** > **Kiirloomise vorm**.</span><span class="sxs-lookup"><span data-stu-id="c4259-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="c4259-234">Ühendatud kliendiprofiilil põhineva segmendi loomiseks valige valik **Profiilid**.</span><span class="sxs-lookup"><span data-stu-id="c4259-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="c4259-235">Valige valik **Mõõtmed**, et luua varem lehel **Mõõtmed** loodud iga mõõtme kliendiatribuudi tüübi ümber segment.</span><span class="sxs-lookup"><span data-stu-id="c4259-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="c4259-236">Valige suvand **Ärianalüüs**, et luua segment ümber ühe väljundi olemi, mille olete loonud, kasutades kas **Prognooside** või **Kohandatud mudelite** võimalusi.</span><span class="sxs-lookup"><span data-stu-id="c4259-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="c4259-237">Valige dialoogiboksis **Uus kiirsegment** atribuut ripploendist **Väli**.</span><span class="sxs-lookup"><span data-stu-id="c4259-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="c4259-238">Süsteem esitab paar täiendavat ülevaadet, mis aitavad luua klientidest paremad segmendid.</span><span class="sxs-lookup"><span data-stu-id="c4259-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="c4259-239">Kategooria väljade puhul näitame 10 peamist kliendi arvu.</span><span class="sxs-lookup"><span data-stu-id="c4259-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="c4259-240">Valige **Väärtus** ja **Ülevaatamine**.</span><span class="sxs-lookup"><span data-stu-id="c4259-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="c4259-241">Süsteem näitab numbrilise atribuudi puhul, mis atribuudi väärtus langeb iga kliendi protsendiili alla.</span><span class="sxs-lookup"><span data-stu-id="c4259-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="c4259-242">Valige **Tehtemärk**, **Väärtus** ja **Ülevaatamine**.</span><span class="sxs-lookup"><span data-stu-id="c4259-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="c4259-243">Süsteem esitab **hinnangulise segmendi mahu**.</span><span class="sxs-lookup"><span data-stu-id="c4259-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="c4259-244">Saate valida, kas luua määratletud segment või esmalt vaadata seda uuesti, et hankida muus mahus segment.</span><span class="sxs-lookup"><span data-stu-id="c4259-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c4259-245">![Kiirsegmendi nimi ja hinnang](media/quick-segment-name.png "Kiirsegmendi nimi ja hinnang")</span><span class="sxs-lookup"><span data-stu-id="c4259-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="c4259-246">Sisestage segmendi **nimi**.</span><span class="sxs-lookup"><span data-stu-id="c4259-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="c4259-247">Soovi korral sisestage **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="c4259-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="c4259-248">Segmendi loomiseks valige käsk **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="c4259-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="c4259-249">Pärast segmendi töötlust saate seda vaadata nagu kõiki teisi loodud segmente.</span><span class="sxs-lookup"><span data-stu-id="c4259-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="c4259-250">Järgmistes olukordades soovitame kasutada segmendikoosturit, mitte soovitatavat segmentide võimalust:</span><span class="sxs-lookup"><span data-stu-id="c4259-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="c4259-251">Segmentide loomine filtritega kategooriliselt väljadel, kus tehtemärgiks pole **Is**</span><span class="sxs-lookup"><span data-stu-id="c4259-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="c4259-252">Segmentide loomine filtritega numbriliselt väljadel, kus tehtemärkideks pole **Between**, **Greater than** ja **Less than**</span><span class="sxs-lookup"><span data-stu-id="c4259-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="c4259-253">Filtritega segmentide loomine kuupäeva tüüpi väljadel</span><span class="sxs-lookup"><span data-stu-id="c4259-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="c4259-254">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="c4259-254">Next steps</span></span>

<span data-ttu-id="c4259-255">Kliendi taseme ülevaadete hankimiseks [eksportige segment](export-destinations.md) ja tutvuge [kliendikaardiga](customer-card-add-in.md) ning [ühendajatega](export-power-bi.md).</span><span class="sxs-lookup"><span data-stu-id="c4259-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]