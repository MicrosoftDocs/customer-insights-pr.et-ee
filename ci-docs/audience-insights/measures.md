---
title: Näitajate loomine ja muutmine
description: Määratlege kliendiga seotud meetmed, et analüüsida ja kajastada teatud ärialade tootlikkust.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405565"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="6169a-103">Meetmete määratlemine ja haldamine</span><span class="sxs-lookup"><span data-stu-id="6169a-103">Define and manage measures</span></span>

<span data-ttu-id="6169a-104">**Meetmed** tähendavad juhtimismõõdikuid (KPI-d), mis kajastavad teatud ärialade tootlikkust ja seisu.</span><span class="sxs-lookup"><span data-stu-id="6169a-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="6169a-105">Sihtrühmaülevaated pakuvad intuitiivset kogemust eri tüüpi näitajate loomiseks, kasutades päringukujundajat, milles pole vaja koodi kirjutada ega näitajaid manuaalselt kontrollida.</span><span class="sxs-lookup"><span data-stu-id="6169a-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="6169a-106">Saate lehel **Avaleht** jälgida ettevõtte meetmeid, vaadata **kliendikaardi** klientide meetmeid ja määratleda meetmetega kliendisegmente lehel **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="6169a-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="6169a-107">Meetme loomine</span><span class="sxs-lookup"><span data-stu-id="6169a-107">Create a measure</span></span>

<span data-ttu-id="6169a-108">See jaotis juhendab teid uue meetme loomisel.</span><span class="sxs-lookup"><span data-stu-id="6169a-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="6169a-109">Saate luua meetmeid mitme kliendi olemi kaudu ühendatud andmeallika andmete alusel.</span><span class="sxs-lookup"><span data-stu-id="6169a-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="6169a-110">Kehtivad [teenusepiirangud](service-limits.md).</span><span class="sxs-lookup"><span data-stu-id="6169a-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="6169a-111">Avage sihtrühmaülevaadetes jaotis **Näitajad**.</span><span class="sxs-lookup"><span data-stu-id="6169a-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="6169a-112">Valige **Uus meede**.</span><span class="sxs-lookup"><span data-stu-id="6169a-112">Select **New measure**.</span></span>

3. <span data-ttu-id="6169a-113">Valige meede **Tüüp**.</span><span class="sxs-lookup"><span data-stu-id="6169a-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="6169a-114">**Kliendi atribuut**: üks väli kliendi kohta, kus on kliendi skoor, väärtus või olek.</span><span class="sxs-lookup"><span data-stu-id="6169a-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="6169a-115">Kliendiatribuudid luuakse uue süsteemi loodud olemi atribuutidena, mida nimetatakse **kliendi meetmeks**.</span><span class="sxs-lookup"><span data-stu-id="6169a-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="6169a-116">**Kliendi meede**: kliendikäitumise ülevaated struktuuriga, mis põhineb valitud mõõtmetel.</span><span class="sxs-lookup"><span data-stu-id="6169a-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="6169a-117">Iga meetme jaoks luuakse uus olem, potentsiaalselt mitme kirjega kliendi kohta.</span><span class="sxs-lookup"><span data-stu-id="6169a-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="6169a-118">**Ärimeede**: jälgib äri tootlikkust ja seisu.</span><span class="sxs-lookup"><span data-stu-id="6169a-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="6169a-119">Ärimeetmetel võib olla kaks eri väljundit: lehel **Avaleht** asuv numbriline väljund või uus olem, mille leiate lehelt **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="6169a-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="6169a-120">Sisestage **Nimi** ja valikuline **Kuvatav nimi**, seejärel valige **Järgmine**.</span><span class="sxs-lookup"><span data-stu-id="6169a-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="6169a-121">Jaotises **Olemid** valige ripploendist esimene olem.</span><span class="sxs-lookup"><span data-stu-id="6169a-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="6169a-122">Sellel hetkel peaksite otsustama, kas mõõdu määratlusel läheb vaja täiendavaid olemeid.</span><span class="sxs-lookup"><span data-stu-id="6169a-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6169a-123">![Mõõdu määratlus](media/measure-definition.png "Mõõdu määratlus")</span><span class="sxs-lookup"><span data-stu-id="6169a-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="6169a-124">Täiendavate olemite lisamiseks valige **Lisa olem** ja valige meetmetes kasutatavad olemid.</span><span class="sxs-lookup"><span data-stu-id="6169a-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6169a-125">Võite valida ainult olemeid, millel on alustamise olemiga seosed.</span><span class="sxs-lookup"><span data-stu-id="6169a-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="6169a-126">Lisateavet suhete määratlemise kohta leiate jaotisest [Suhted](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="6169a-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="6169a-127">Soovi korral saate seadistada muutujaid.</span><span class="sxs-lookup"><span data-stu-id="6169a-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="6169a-128">Tehke jaotises **Muutujad** valik **Uus muutuja**.</span><span class="sxs-lookup"><span data-stu-id="6169a-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="6169a-129">Muutujad on arvutused, mis luuakse iga valitud kirje puhul.</span><span class="sxs-lookup"><span data-stu-id="6169a-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="6169a-130">Näiteks iga kliendi kirje puhul kokkuvõtlik müügipunkt (POS) ja võrgumüügid.</span><span class="sxs-lookup"><span data-stu-id="6169a-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="6169a-131">Sisestage muutuja **nimi**.</span><span class="sxs-lookup"><span data-stu-id="6169a-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="6169a-132">Jaotises **Avaldis** valige välju, millega algav arvutus.</span><span class="sxs-lookup"><span data-stu-id="6169a-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="6169a-133">Sisestage avaldis jaotisesse **Avaldis**, samas valige veel välju, mida lisada arvutusse.</span><span class="sxs-lookup"><span data-stu-id="6169a-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6169a-134">Praegu toetatakse ainult aritmeetilisi avaldisi.</span><span class="sxs-lookup"><span data-stu-id="6169a-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="6169a-135">Lisaks ei toetata eri [olemi teede](relationships.md) muutuja arvutust.</span><span class="sxs-lookup"><span data-stu-id="6169a-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="6169a-136">Valige nupp **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="6169a-136">Select **Done**.</span></span>

11. <span data-ttu-id="6169a-137">Jaotises **Mõõdu määratlus** saate määratleda, kuidas teie valitud olemid ja arvutatud muutujad liidetakse uue mõõdu olemile või atribuudile.</span><span class="sxs-lookup"><span data-stu-id="6169a-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="6169a-138">Valige **Uus dimensioon**.</span><span class="sxs-lookup"><span data-stu-id="6169a-138">Select **New dimension**.</span></span> <span data-ttu-id="6169a-139">Dimensiooni võib ette kujutada ka funktsioonina *rühmitamisalus*.</span><span class="sxs-lookup"><span data-stu-id="6169a-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="6169a-140">Meetme olemi või atribuudi andmete väljund rühmitatakse kõikide määratletud dimensioonide alusel.</span><span class="sxs-lookup"><span data-stu-id="6169a-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6169a-141">![Koondtsükli valimine](media/measures-businessreport-measure-definition2.png "Koondtsükli valimine")</span><span class="sxs-lookup"><span data-stu-id="6169a-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="6169a-142">Valige või sisestage järgmine teave dimensiooni määratluse osana:</span><span class="sxs-lookup"><span data-stu-id="6169a-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="6169a-143">**Olem**: kui määratlete meetme olemi, peaks see sisaldama vähemalt üht atribuuti.</span><span class="sxs-lookup"><span data-stu-id="6169a-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="6169a-144">Kui määratlete meetme atribuudi, sisaldab see tavaliselt vaid üht atribuuti.</span><span class="sxs-lookup"><span data-stu-id="6169a-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="6169a-145">See valik käib atribuudiga olemi valimise kohta.</span><span class="sxs-lookup"><span data-stu-id="6169a-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="6169a-146">**Väli**: valige kindel atribuut, mis lisatakse meetme olemisse või atribuuti.</span><span class="sxs-lookup"><span data-stu-id="6169a-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="6169a-147">**Salv**: valige, kas soovite koondada andmed iga päev, iga kuu või iga aasta.</span><span class="sxs-lookup"><span data-stu-id="6169a-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="6169a-148">See on kohustuslik valik ainult juhul, kui olete valinud atribuudi tüübi Kuupäev.</span><span class="sxs-lookup"><span data-stu-id="6169a-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="6169a-149">**Kui**: määratleb uue välja nime.</span><span class="sxs-lookup"><span data-stu-id="6169a-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="6169a-150">**Kuvatav nimi**: määratleb välja kuvatava nime.</span><span class="sxs-lookup"><span data-stu-id="6169a-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6169a-151">Ettevõtte meede salvestatakse ühe numbrilise olemina ja ilmub lehel **Avaleht**, kui te ei lisa meetmesse täiendavaid dimensioone.</span><span class="sxs-lookup"><span data-stu-id="6169a-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="6169a-152">Pärast täiendavate dimensioonide lisamist *ei* ilmu meede lehel **Avaleht**.</span><span class="sxs-lookup"><span data-stu-id="6169a-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="6169a-153">Soovi korral lisage liitmisfunktsioonid.</span><span class="sxs-lookup"><span data-stu-id="6169a-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="6169a-154">Kõikide liitmiste summadeks on uus väärtus, mis jääb mõõtude olemi või atribuudi raamesse.</span><span class="sxs-lookup"><span data-stu-id="6169a-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="6169a-155">Toetatud liitmisfunktsioonid on: **min**, **max**, **keskmine**, **mediaan**, **Sum**, **kordumatu arv**, **esimene** (kasutab dimensiooni väärtuse esimest kirjet) ja **viimane** (kasutab dimensiooni väärtusele lisatud viimast kirjet).</span><span class="sxs-lookup"><span data-stu-id="6169a-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="6169a-156">Mõõtmele tehtud muudatuste kasutamiseks klõpsake käsku **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="6169a-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="6169a-157">Meetmete haldamine</span><span class="sxs-lookup"><span data-stu-id="6169a-157">Manage your measures</span></span>

<span data-ttu-id="6169a-158">Pärast vähemalt ühe näitaja loomist näete lehel **Näitajad** näitajate loendit.</span><span class="sxs-lookup"><span data-stu-id="6169a-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="6169a-159">Leiate teavet mõõtme tüübi, looja, loomise kuupäeva ja kellaaja, viimase muutmise kuupäeva ja kellaaja, oleku (kas mõõde on aktiivne, passiivne või nurjunud) ning viimase värskendamise kuupäeva ja kellaaja kohta.</span><span class="sxs-lookup"><span data-stu-id="6169a-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="6169a-160">Kui valite loendist mõõdu, näete selle väljundi eelvaadet.</span><span class="sxs-lookup"><span data-stu-id="6169a-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="6169a-161">Kõigi oma meetmete korraga värskendamiseks valige **Värskenda kõik** ilma kindlat meedet valimata.</span><span class="sxs-lookup"><span data-stu-id="6169a-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6169a-162">![Toimingud üksikute meetmete haldamiseks](media/measure-actions.png "Toimingud üksikute meetmete haldamiseks")</span><span class="sxs-lookup"><span data-stu-id="6169a-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="6169a-163">Teise võimalusena valige loendist meede ja tehke üks järgmistest toimingutest.</span><span class="sxs-lookup"><span data-stu-id="6169a-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="6169a-164">Valige meetme nimi, et näha selle üksikasju.</span><span class="sxs-lookup"><span data-stu-id="6169a-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="6169a-165">Meetme konfiguratsiooni **Redigeerimine**.</span><span class="sxs-lookup"><span data-stu-id="6169a-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="6169a-166">Meetme **Ümbernimetamine**.</span><span class="sxs-lookup"><span data-stu-id="6169a-166">**Rename** the measure.</span></span>
- <span data-ttu-id="6169a-167">Meetme **Kustutamine**.</span><span class="sxs-lookup"><span data-stu-id="6169a-167">**Delete** the measure.</span></span>
- <span data-ttu-id="6169a-168">Valige kolmikpunkt (...) ja seejärel **Värskenda**, et käivitada meetme värskendamisprotsess.</span><span class="sxs-lookup"><span data-stu-id="6169a-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="6169a-169">Valige kolmikpunkt (...) ja seejärel **Laadi alla**, et saada meetme .CSV-fail.</span><span class="sxs-lookup"><span data-stu-id="6169a-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="6169a-170">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="6169a-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="6169a-171">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="6169a-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="6169a-172">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="6169a-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="6169a-173">Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="6169a-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="6169a-174">Järgmine etapp</span><span class="sxs-lookup"><span data-stu-id="6169a-174">Next step</span></span>

<span data-ttu-id="6169a-175">Esimese kliendisegmendi loomiseks lehel **Segmendid** saate kasutada olemasolevaid mõõte.</span><span class="sxs-lookup"><span data-stu-id="6169a-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="6169a-176">Lisateavet vt [Segmendid](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6169a-176">For more information, see [Segments](segments.md).</span></span>
