---
title: Segmendiülevaated olemasolevate segmentide kohta
description: Vaadake ülevaadet olemasolevate segmentide kohta, et näha erinevusi ja sarnasusi.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2856888d6ac64d5daabcc5a234f13bc6f88bb3df
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306069"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="f0b7e-103">Segmendi ülevaated (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="f0b7e-103">Segment insights (preview)</span></span>

<span data-ttu-id="f0b7e-104">Tutvuge lisateabega ja ülevaadetega olemasolevate segmentide kohta.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="f0b7e-105">Saage teada, mis on kahe segmendi puhul erinev või mis on neil ühist.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="f0b7e-106">Segmendi kattumine</span><span class="sxs-lookup"><span data-stu-id="f0b7e-106">Segment overlap</span></span>

<span data-ttu-id="f0b7e-107">Segmendi kattumise analüüs näitab, kui paljudel ja millistel klientidel on kaks või rohkem ühist segmenti.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="f0b7e-108">Näiteks kuidas sagedaste klientide segment kattub segmendiga, mis sisaldab kliente, kes on teie teenuse või tootega rahul.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="f0b7e-109">Lisaks saate analüüsida, kuidas kattumine teatud atribuute muudab.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="f0b7e-110">Kattumise analüüsi käitamine</span><span class="sxs-lookup"><span data-stu-id="f0b7e-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="f0b7e-111">Avage **Segmendid** ja valige vahekaart **Ülevaated (eelversioon)**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="f0b7e-112">Valige **Uus** ja valige suvand **Kattumine** paanil **Ülevaate tüübi valimine**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="f0b7e-113">Valige huvipakkuvad segmendid ja valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="f0b7e-114">Soovi korral võite valida ühe või mitu huvipakkuvat välja, et analüüsida iga võimaliku välja väärtuse kattumist, ja valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="f0b7e-115">Sisestage kattumise analüüsi nimi, valikuline kuvatav nimi ja kirjeldus.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="f0b7e-116">Analüüsi käivitamiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="f0b7e-117">Kattumise analüüs on valmis, kui olek muutub valikust Värskendab valikule Õnnestus.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="f0b7e-118">Kattumise analüüsi vaatamine ja optimeerimine</span><span class="sxs-lookup"><span data-stu-id="f0b7e-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="f0b7e-119">Pärast analüüsi lõpetamist näete selle ülevaate kohta üksikasju suvandis **Segmendid** > **Ülevaated (eelversioon)**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Segmendi kattumise ülevaate üksikasjad":::

<span data-ttu-id="f0b7e-121">Analüüsi tulemuste nägemiseks valige ülevaade.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="f0b7e-122">Liikmete arv, kelle segmendid valitud analüüsis kattuvad.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="f0b7e-123">Liikmete arv, mis sisaldub ühes segmendis, kuid mitte teistes segmentides.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="f0b7e-124">Kui valisite kattuva analüüsi konfigureerimisel väljad, leiate need vastavatelt vahekaartidelt.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="f0b7e-125">Filtri ripploendi abil saate valida mis tahes atribuudi huvitaseme ja allservas olevas tabelis kuvatakse vastavad andmed.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-125">You can use the filter dropdown to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="f0b7e-126">Segmendidiferentseerijad</span><span class="sxs-lookup"><span data-stu-id="f0b7e-126">Segment differentiators</span></span>

<span data-ttu-id="f0b7e-127">Segmentide eristajad aitavad teil selgitada välja, mis eristab segmenti teistest klientidest või teisest segmendist.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="f0b7e-128">Te peate valima segmendi ja süsteem tuvastab profiili atribuudid ja meetmed, mis valitud segmente eristab.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="f0b7e-129">Eristajate analüüsi käitamine</span><span class="sxs-lookup"><span data-stu-id="f0b7e-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="f0b7e-130">Avage **Segmendid** ja valige vahekaart **Ülevaated (eelversioon)**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="f0b7e-131">Valige **Uus** ja valige suvand **Kattumine** paanil **Ülevaate tüübi valimine**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="f0b7e-132">Valige segment, mida soovite analüüsida, kui **Primaarne segment** ja valige nupp **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="f0b7e-133">Valige **Kõik kliendid** või **Teisene segment**, et oma primaarset segmenti sellega võrrelda, ja valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="f0b7e-134">Soovi korral võite valida ühe või mitu huvivälja, et keskenduda konkreetsete atribuutide analüüsile, ja valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="f0b7e-135">Sisestage kattumise analüüsi nimi, valikuline kuvatav nimi ja kirjeldus.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="f0b7e-136">Analüüsi käivitamiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="f0b7e-137">Kattumise analüüs on valmis, kui olek muutub valikust Värskendab valikule Õnnestus.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="f0b7e-138">Eristajate analüüsi vaatamine ja otimeerimine</span><span class="sxs-lookup"><span data-stu-id="f0b7e-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="f0b7e-139">Pärast analüüsi lõpetamist näete selle ülevaate kohta üksikasju suvandis **Segmendid** > **Ülevaated (eelversioon)**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Segmendi eristaja ülevaate üksikasjad":::

<span data-ttu-id="f0b7e-141">Analüüsi tulemuste nägemiseks valige ülevaade.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="f0b7e-142">Eristaja analüüs hõlmab kahte vahekaarti.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="f0b7e-143">Vahekaart **Atribuudid** loetleb profiili atribuudid, mida loetakse eristajateks.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="f0b7e-144">Vahekaart **Meetmed** loetleb eristajad.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="f0b7e-145">Iga vahekaart sisaldab järgmisi üksikasju.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="f0b7e-146">Eristajate järjestatud loendit, mis on erinevuse skoori alusel sorditud.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="f0b7e-147">Iga eristaja **Erinevuse skoor**.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="f0b7e-148">Erinevuse skoor tähistab atribuudi erinevust kahe segmendi vahel.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="f0b7e-149">Mida suurem on erinevuse skoor, seda suurem on kahe segmendi vaheline atribuutide erinevus.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="f0b7e-150">Valige skoor, et avada paan **Erinevuse skoor** selle atribuudi eristaja väärtustega.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="f0b7e-151">Segmendi ülevaadete haldus</span><span class="sxs-lookup"><span data-stu-id="f0b7e-151">Manage segment insights</span></span>

<span data-ttu-id="f0b7e-152">Saate ülevaadetega kasutada kärusiba järgmisi valikuid.</span><span class="sxs-lookup"><span data-stu-id="f0b7e-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="f0b7e-153">**Tagasi** ülevaadete loendisse naasmiseks</span><span class="sxs-lookup"><span data-stu-id="f0b7e-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="f0b7e-154">**Värskenda** analüüsi uuesti käivitamiseks</span><span class="sxs-lookup"><span data-stu-id="f0b7e-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="f0b7e-155">**Kustuta** selle ülevaate eemaldamiseks</span><span class="sxs-lookup"><span data-stu-id="f0b7e-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]