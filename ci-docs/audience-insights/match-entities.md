---
title: Olemite vastavusseviimine andmete koondamiseks
description: Viige olemid vastavusse, et luua koondatud kliendiprofiile.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405563"
---
# <a name="match-entities"></a><span data-ttu-id="64830-103">Olemite vastavusseviimine</span><span class="sxs-lookup"><span data-stu-id="64830-103">Match entities</span></span>

<span data-ttu-id="64830-104">Pärast vastendamise etappi olete valmis olemite vastavusse viimiseks.</span><span class="sxs-lookup"><span data-stu-id="64830-104">After completing the map phase, you're ready to match your entities.</span></span> <span data-ttu-id="64830-105">Vastavusse viimise etapp täpsustab, kuidas kombineerida andmekogusid koondatud kliendiprofiilide andmekogusse.</span><span class="sxs-lookup"><span data-stu-id="64830-105">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="64830-106">Vastendamisetapp vajab vähemalt [kahte kaardistatud olemit](map-entities.md).</span><span class="sxs-lookup"><span data-stu-id="64830-106">The match phase requires at least [two mapped entities](map-entities.md).</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="64830-107">Vastendamisjärjestuse määramine</span><span class="sxs-lookup"><span data-stu-id="64830-107">Specify the match order</span></span>

<span data-ttu-id="64830-108">Vastendamisetapi käivitamiseks minge **Ühendamine** > **Vastendamine** ja valige **Järjestuse määramine**.</span><span class="sxs-lookup"><span data-stu-id="64830-108">Go to **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="64830-109">Iga vaste ühendab vähemalt kaks olemit üheks olemiks, samas säilitades iga kordumatu kliendi kirjega.</span><span class="sxs-lookup"><span data-stu-id="64830-109">Each match unifies two or more entities into a single entity, while persisting each unique customer record.</span></span> <span data-ttu-id="64830-110">Järgmises näited valisime kolm olemit: **ContactCSV: TestData** **primaarse** olemina, **WebAccountCSV: TestData** **2. olemina** ja **CallRecordSmall: TestData** **3. olemina**.</span><span class="sxs-lookup"><span data-stu-id="64830-110">In the following example, we selected three entities: **ContactCSV: TestData** as the **Primary** entity, **WebAccountCSV: TestData** as **Entity 2**, and **CallRecordSmall: TestData** as **Entity 3**.</span></span> <span data-ttu-id="64830-111">Valikute kohal olev diagramm kirjeldab vastendamisjärjestuse toimimist.</span><span class="sxs-lookup"><span data-stu-id="64830-111">The diagram above the selections illustrates how the match order will be executed.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="64830-112">![Andmete vastendamisjärjestuse muutmine](media/configure-data-match-order-edit-page.png "Andmete vastendamisjärjestuse muutmine")</span><span class="sxs-lookup"><span data-stu-id="64830-112">![Edit the data match order](media/configure-data-match-order-edit-page.png "Edit the data match order")</span></span>
  
<span data-ttu-id="64830-113">**Primaarne** olem vastendataks **2. olemiga**.</span><span class="sxs-lookup"><span data-stu-id="64830-113">The **Primary** entity is matched with **Entity 2**.</span></span> <span data-ttu-id="64830-114">Esimesest vastest tulenev andmekogum vastab **3. olemile**.</span><span class="sxs-lookup"><span data-stu-id="64830-114">The dataset that results from the first match is matched with **Entity 3**.</span></span>
<span data-ttu-id="64830-115">Selles näites valisime vaid kaks vastet, ent süsteem võimaldab rohkem.</span><span class="sxs-lookup"><span data-stu-id="64830-115">In this example, we only selected two matches, but the system can support more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64830-116">Olemil, mille valite **primaarseks** olemiks, hakkab põhinema koondpõhiandmekogumil.</span><span class="sxs-lookup"><span data-stu-id="64830-116">The entity that you choose as your **Primary** entity will serve as the basis for your unified master dataset.</span></span> <span data-ttu-id="64830-117">Sellele olemile lisatakse täiendavad olemid, mis on valitud vastendamisetapis.</span><span class="sxs-lookup"><span data-stu-id="64830-117">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="64830-118">Samas ei tähenda see, et ühendatud olem hõlmab *kõiki* sellesse olemisse kaasatud andmeid.</span><span class="sxs-lookup"><span data-stu-id="64830-118">At the same time, this doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="64830-119">Kaks mõtet, mis võivad aidata valida olemite järjestust:</span><span class="sxs-lookup"><span data-stu-id="64830-119">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="64830-120">Milline olem on kõige põhjalikum ja mille kliendiandmed on kõige usaldusväärsemad?</span><span class="sxs-lookup"><span data-stu-id="64830-120">What entity do you consider having the most complete and reliable data about your customers?</span></span>
> - <span data-ttu-id="64830-121">Kas äsja tuvastatud olemil on atribuudid, mida jagavad ka teised olemid (näiteks nimi, telefoninumber või e-posti aadress)?</span><span class="sxs-lookup"><span data-stu-id="64830-121">Does the entity that you just identified have attributes that are also shared by other entities (for example, name, phone number, or email address)?</span></span> <span data-ttu-id="64830-122">Kui ei, siis valige järgmine kõige usaldusväärsem olem.</span><span class="sxs-lookup"><span data-stu-id="64830-122">If not, choose your second most reliable entity.</span></span>

<span data-ttu-id="64830-123">Valige **valmis**, et salvestada vaste tellimus.</span><span class="sxs-lookup"><span data-stu-id="64830-123">Select **Done** to save your match order.</span></span>

## <a name="define-rules-for-your-first-match-pair"></a><span data-ttu-id="64830-124">Määratlege esimese vastenduse paari reeglid</span><span class="sxs-lookup"><span data-stu-id="64830-124">Define rules for your first match pair</span></span>

<span data-ttu-id="64830-125">Pärast vastendamisjärjestuse määramist näete määratletud vasteid lehel **Vastendamine**.</span><span class="sxs-lookup"><span data-stu-id="64830-125">After specifying the match order, you'll see the defined matches on the **Match** page.</span></span> <span data-ttu-id="64830-126">Ekraani ülaosas olevad paanid jäävad tühjaks kuni käivitate vastendamisjärjestuse.</span><span class="sxs-lookup"><span data-stu-id="64830-126">The tiles at the top of the screen will be empty until you run your match order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="64830-127">![Reeglite määratlemine](media/configure-data-match-need-rules.png "Reeglite määratlemine")</span><span class="sxs-lookup"><span data-stu-id="64830-127">![Define rules](media/configure-data-match-need-rules.png "Define rules")</span></span>

<span data-ttu-id="64830-128">Hoiatus **Vajab reegleid** hoiatus viitab sellele, et vastenduse paari jaoks pole määratletud ühtegi vastendusreeglit.</span><span class="sxs-lookup"><span data-stu-id="64830-128">The **Needs Rules** warning suggests that no match rule is defined for a match pair.</span></span> <span data-ttu-id="64830-129">Vastendamisreeglid määratlevad loogika, mille alusel vastendatakse kindlat olemite paari.</span><span class="sxs-lookup"><span data-stu-id="64830-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

1. <span data-ttu-id="64830-130">Esimese reegli määratlemiseks avage paan **Reeglimääratlus**, valides vastenduste tabelis (1) vastava vasterea ja seejärel valides **Loo uus reegel** (2).</span><span class="sxs-lookup"><span data-stu-id="64830-130">To define your first rule, open the **Rule Definition** pane by selecting the corresponding match row in the matches table (1) and then selecting **Create new rule** (2).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64830-131">![Loo uus reegel](media/configure-data-match-new-rule2.png "Loo uus reegel")</span><span class="sxs-lookup"><span data-stu-id="64830-131">![Create new rule](media/configure-data-match-new-rule2.png "Create new rule")</span></span>

2. <span data-ttu-id="64830-132">Seadistage paanis **Reegli muutmine** selle reegli tingimused.</span><span class="sxs-lookup"><span data-stu-id="64830-132">In the **Edit Rule** pane, configure the conditions for that rule.</span></span> <span data-ttu-id="64830-133">Tingimusi väljendatakse kohustuslike valikutega kahe reaga.</span><span class="sxs-lookup"><span data-stu-id="64830-133">Each condition is represented by two rows that include mandatory selections.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64830-134">![Uue reegli paan](media/configure-data-match-new-rule-condition.png "Uue reegli paan")</span><span class="sxs-lookup"><span data-stu-id="64830-134">![New rule pane](media/configure-data-match-new-rule-condition.png "New rule pane")</span></span>

   <span data-ttu-id="64830-135">Olem/väli (esimene) – esimese vastendamise paari olemi vastendamiseks kasutatav atribuut.</span><span class="sxs-lookup"><span data-stu-id="64830-135">Entity/Field (first) - An attribute that will be used for matching from the first match pair entity.</span></span> <span data-ttu-id="64830-136">Näidete hulgas võib olla telefoninumber või e-postiaadress.</span><span class="sxs-lookup"><span data-stu-id="64830-136">Examples could include a phone number or email address.</span></span> <span data-ttu-id="64830-137">Valige atribuut, mis tõenäoliselt on kliendile ainulaadne.</span><span class="sxs-lookup"><span data-stu-id="64830-137">Choose an attribute that is likely to be unique to the customer.</span></span>

   > [!TIP]
   > <span data-ttu-id="64830-138">Vältige toimingu tüüpi atribuutidel põhinevat vastendamist.</span><span class="sxs-lookup"><span data-stu-id="64830-138">Avoid matching on the basis of activity-type attributes.</span></span> <span data-ttu-id="64830-139">Teisisõnu, kui atribuut tundub olevat tegevus, võib see olla vastendamiseks halb kriteerium.</span><span class="sxs-lookup"><span data-stu-id="64830-139">In other words, if an attribute seems to be an activity, then it might be a poor criteria to match by.</span></span>  

   <span data-ttu-id="64830-140">Olem/väli (teine) – teise vastendamise paari olemi vastendamiseks kasutatav atribuut.</span><span class="sxs-lookup"><span data-stu-id="64830-140">Entity/Field (Second) - An attribute that will be used for matching from the second match pair entity.</span></span>

   <span data-ttu-id="64830-141">Normaliseerimine – **Normaliseerimismeetod**: valitud atribuutide jaoks on saadaval erinevad normaliseerimisvalikud.</span><span class="sxs-lookup"><span data-stu-id="64830-141">Normalize - **Normalization method**: Various normalization options are available for the selected attributes.</span></span> <span data-ttu-id="64830-142">Näiteks kirjavahemärkide või tühikute eemaldamine</span><span class="sxs-lookup"><span data-stu-id="64830-142">For example, removing punctuation or removing spaces</span></span>

   <span data-ttu-id="64830-143">Ettevõtte nime normaliseerimise (eelvaade) puhul saate valida ka **Tüüp (telefon, nimi, ettevõte)**</span><span class="sxs-lookup"><span data-stu-id="64830-143">For Organization name normalization (Preview), you can also select **Type (Phone, Name, Organization)**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64830-144">![Normaliseerimine – B2B](media/match-normalization-b2b.png "Normaliseerimine – B2B")</span><span class="sxs-lookup"><span data-stu-id="64830-144">![Normalization-B2B](media/match-normalization-b2b.png "Normalization-B2B")</span></span>

   <span data-ttu-id="64830-145">Täpsuse tase – selle tingimuse puhul kasutatav täpsuse tase.</span><span class="sxs-lookup"><span data-stu-id="64830-145">Precision level - The level of precision that will be used for this condition.</span></span> <span data-ttu-id="64830-146">Vaste tingimuse täpsuse taset on kaht tüüpi: **põhiline** ja **Kohandatud**.</span><span class="sxs-lookup"><span data-stu-id="64830-146">Setting a precision level for a match condition can have two types: **Basic** and **Custom**.</span></span>  
   - <span data-ttu-id="64830-147">Põhiline: võimaldab valida nelja valikut: madal, keskmine, kõrge ja täpne.</span><span class="sxs-lookup"><span data-stu-id="64830-147">Basic: Provides you with four options to select from: Low, Medium, High, and Exact.</span></span> <span data-ttu-id="64830-148">Vaid 100 protsendiliste kirjete vastendamiseks valige **Täpne**.</span><span class="sxs-lookup"><span data-stu-id="64830-148">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="64830-149">Alla 100 protsendiliste kirjete vastendamiseks valige üks neljast tasemest.</span><span class="sxs-lookup"><span data-stu-id="64830-149">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
   - <span data-ttu-id="64830-150">Kohandatud: liuguriga määratlete kohandatud protsenti, mida kirjed peavad vastendama või sisestage väärtus välja **Kohandatud**.</span><span class="sxs-lookup"><span data-stu-id="64830-150">Custom: Use the slider to define the custom percentage that records need to match or enter a value in the **Custom** field.</span></span> <span data-ttu-id="64830-151">Süsteem vastendab vaid kirjeid, mis ületavad seda läve ühendatud vastenduse paaridena.</span><span class="sxs-lookup"><span data-stu-id="64830-151">The system will only match records passing this threshold as conflated match pairs.</span></span> <span data-ttu-id="64830-152">Liuguri väärtused on vahemikus 0-1.</span><span class="sxs-lookup"><span data-stu-id="64830-152">Values on the slider are between 0 and 1.</span></span> <span data-ttu-id="64830-153">Seega 0,64 tähendab 64 protsenti.</span><span class="sxs-lookup"><span data-stu-id="64830-153">So 0.64 represents 64 percent.</span></span>

3. <span data-ttu-id="64830-154">Reegli salvestamiseks valige **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="64830-154">Select **Done** to save the rule.</span></span>

### <a name="add-multiple-conditions"></a><span data-ttu-id="64830-155">Mitme tingimuse lisamine</span><span class="sxs-lookup"><span data-stu-id="64830-155">Add multiple conditions</span></span>

<span data-ttu-id="64830-156">Olemite vastendamiseks vaid siis, kui täidetud on mitu tingimust, lisage veel tingimusi, mis on seotud tehtemärgiga AND.</span><span class="sxs-lookup"><span data-stu-id="64830-156">To match your entities only if multiple conditions are met, add more conditions that are linked through an AND operator.</span></span>

1. <span data-ttu-id="64830-157">Valige paanil **Reegli muutmine** valik **Tingimuse lisamine**.</span><span class="sxs-lookup"><span data-stu-id="64830-157">In the **Edit rule** pane, select **Add condition**.</span></span> <span data-ttu-id="64830-158">Soovi korral saate ka kustutada, valides olemasoleva tingimuse kõrval eemaldamisnuppu.</span><span class="sxs-lookup"><span data-stu-id="64830-158">You can also delete conditions by selecting the remove button next to an existing condition.</span></span>

2. <span data-ttu-id="64830-159">Reegli salvestamiseks valige **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="64830-159">Select **Done** so save the rule.</span></span>

## <a name="add-multiple-rules"></a><span data-ttu-id="64830-160">Mitme reegli lisamine</span><span class="sxs-lookup"><span data-stu-id="64830-160">Add multiple rules</span></span>

<span data-ttu-id="64830-161">Kõik tingimused kehtivad ühele atribuutide paarile, kuid reeglid tähendavad tingimuste kogumeid.</span><span class="sxs-lookup"><span data-stu-id="64830-161">Each condition applies to a single pair of attributes, while rules represent sets of conditions.</span></span> <span data-ttu-id="64830-162">Olemite vastendamiseks eri atribuutide komplektiga saate lisada veel reegleid.</span><span class="sxs-lookup"><span data-stu-id="64830-162">To have your entities matched by different sets of attributes, you can add more rules.</span></span>

1. <span data-ttu-id="64830-163">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Koondamine** > **Vastavusseviimine**.</span><span class="sxs-lookup"><span data-stu-id="64830-163">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

2. <span data-ttu-id="64830-164">Valige uuendatav olem ja **Lisa reeglid**.</span><span class="sxs-lookup"><span data-stu-id="64830-164">Select the entity you want to update and select **Add rules**.</span></span>

3. <span data-ttu-id="64830-165">Järgige teema [Määratlege esimese vastenduse paari reeglid](#define-rules-for-your-first-match-pair) juhiseid.</span><span class="sxs-lookup"><span data-stu-id="64830-165">Follow the procedure as outlined in [Define rules for your first match pair](#define-rules-for-your-first-match-pair).</span></span>

> [!NOTE]
> <span data-ttu-id="64830-166">Reegli järjekord on oluline.</span><span class="sxs-lookup"><span data-stu-id="64830-166">The rule order matters.</span></span> <span data-ttu-id="64830-167">Vastendamise algoritm proovib vastendada esimese reegli alusel ja jätkab teise reegliga vaid siis, kui esimese reegli korral ei tuvastatud vasteid.</span><span class="sxs-lookup"><span data-stu-id="64830-167">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified under the first rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="64830-168">Vastendatud olemis duplikaadieemalduse määratlemine</span><span class="sxs-lookup"><span data-stu-id="64830-168">Define deduplication on a match entity</span></span>

<span data-ttu-id="64830-169">Lisaks ülaltoodud jaotistes kirjeldatud olemitevahelistele vastavusseviimise reeglite määramisele saate määrata ka duplikaadieemalduse reeglid.</span><span class="sxs-lookup"><span data-stu-id="64830-169">Along with specifying cross entity matching rules as outlined in the above sections, you can also specify deduplications rules.</span></span> <span data-ttu-id="64830-170">*Duplikaadieemaldus* on protsess.</span><span class="sxs-lookup"><span data-stu-id="64830-170">*Deduplication* is a process.</span></span> <span data-ttu-id="64830-171">See tuvastab duplikaatkirjed, ühendab need üheks kirjeks ja lingib kõik lähtekirjed selle ühendatud kirjega koos alternatiivsete ID-dega.</span><span class="sxs-lookup"><span data-stu-id="64830-171">It identifies duplicate records, merges them into one record, and links all the source records to this merged record with alternate IDs to the merged record.</span></span>

<span data-ttu-id="64830-172">Pärast eemaldatud duplikaatidega kirje tuvastamist kasutatakse seda olemitevahelises vastavusseviimise protsessis.</span><span class="sxs-lookup"><span data-stu-id="64830-172">After a deduplicated record is identified, that record will be used in the cross-entity matching process.</span></span> <span data-ttu-id="64830-173">Duplikaadieemaldust rakendatakse olemi tasemel ja seda saab rakendada iga olemi korral, mida kasutatakse vastavusseviimise protsessis.</span><span class="sxs-lookup"><span data-stu-id="64830-173">Deduplication is implemented at the entity level and can be applied to every entity used in the Match process.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="64830-174">Duplikaadieemalduse reeglite lisamine</span><span class="sxs-lookup"><span data-stu-id="64830-174">Add deduplication rules</span></span>

1. <span data-ttu-id="64830-175">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Koondamine** > **Vastavusseviimine**.</span><span class="sxs-lookup"><span data-stu-id="64830-175">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="64830-176">Valige jaotises **Ühendatud duplikaadid** suvand **Sea olemid**.</span><span class="sxs-lookup"><span data-stu-id="64830-176">In the **Merged duplicates** section, select **Set entities**.</span></span>

1. <span data-ttu-id="64830-177">Valige jaotises **Ühendamise eelistused** olemid, mille korral soovite duplikaadieemaldust rakendada.</span><span class="sxs-lookup"><span data-stu-id="64830-177">In the **Merge preferences** section, select the entities you want to apply deduplication to.</span></span>

1. <span data-ttu-id="64830-178">Määrake duplikaatkirjete ühendamise viis ja valige üks kolmest ühendamissuvandist.</span><span class="sxs-lookup"><span data-stu-id="64830-178">Specify how to merge the duplicate records and choose one of three merge options:</span></span>
   - <span data-ttu-id="64830-179">*Enim täidetud*: tuvastab võitjana kirje, millel on kõige rohkem täidetud atribuute.</span><span class="sxs-lookup"><span data-stu-id="64830-179">*Most filled*: Identifies the record with most filled attributes as the winner record.</span></span> <span data-ttu-id="64830-180">See on vaikeühendamissuvand.</span><span class="sxs-lookup"><span data-stu-id="64830-180">This is the default merge option.</span></span>
   - <span data-ttu-id="64830-181">*Kõige hiljutisem*: tuvastab võitjana kirje, millega tegeleti kõige viimasena.</span><span class="sxs-lookup"><span data-stu-id="64830-181">*Most recent*: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="64830-182">Hiljutisuse määratlemiseks on vaja kuupäeva- või numbrilist välja.</span><span class="sxs-lookup"><span data-stu-id="64830-182">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="64830-183">*Kõige vanem*: tuvastab võitjana kirje, millega tegeleti kõige varem.</span><span class="sxs-lookup"><span data-stu-id="64830-183">*Least recent*: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="64830-184">Hiljutisuse määratlemiseks on vaja kuupäeva- või numbrilist välja.</span><span class="sxs-lookup"><span data-stu-id="64830-184">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64830-185">![Duplikaadieemalduse reeglite samm 1](media/match-selfconflation.png "Duplikaadieemalduse reeglite samm 1")</span><span class="sxs-lookup"><span data-stu-id="64830-185">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="64830-186">Kui olemid on valitud ja nende ühendamiseelistus on seatud, valige **Loo uus reegel**, et määratleda duplikaadieemalduse reeglid olemi tasemel.</span><span class="sxs-lookup"><span data-stu-id="64830-186">Once the entities are selected and their merge preference is set, select **Create new rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="64830-187">Suvand **Vali väli** loetleb kõik selle olemi saadaolevad väljad, mille lähteandmetest soovite eemaldada duplikaadid.</span><span class="sxs-lookup"><span data-stu-id="64830-187">**Select field** lists all the available fields from that entity you want to deduplicate source data on.</span></span>
   - <span data-ttu-id="64830-188">Määrake normaliseerimis- ja täpsussätted sarnasel viisil, nagu kirjeldati olemitevahelises vastavusseviimises.</span><span class="sxs-lookup"><span data-stu-id="64830-188">Specify the normalization and precision settings in similar way as specified in the cross entity matching.</span></span>
   - <span data-ttu-id="64830-189">Lisatingimuste määratlemiseks valige **Lisa tingimus**.</span><span class="sxs-lookup"><span data-stu-id="64830-189">You can define additional conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64830-190">![Duplikaadieemalduse reeglite samm 2](media/match-selfconflation-rules.png "Duplikaadieemalduse reeglite samm 2")</span><span class="sxs-lookup"><span data-stu-id="64830-190">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="64830-191">Võite olemi jaoks luua mitu duplikaadieemalduse reeglit.</span><span class="sxs-lookup"><span data-stu-id="64830-191">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="64830-192">Vastavusseviimise protsessi käitamise korral rühmitatakse kirjed nüüd duplikaadieemalduse reeglites määratletud tingimuste alusel.</span><span class="sxs-lookup"><span data-stu-id="64830-192">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="64830-193">Pärast kirjete rühmitamist rakendatakse ühendamispoliitikat, et tuvastada võitjast kirje.</span><span class="sxs-lookup"><span data-stu-id="64830-193">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="64830-194">Seejärel kasutatakse seda võitjast kirjet olemitevahelises vastavusseviimises.</span><span class="sxs-lookup"><span data-stu-id="64830-194">This winner record is then passed on to the cross-entity matching.</span></span>

1. <span data-ttu-id="64830-195">Kõik kohandatud vastavusseviimise reeglid, mis on määratletud „alati vastavusseviimise“ ja „mitte kunagi vastavusseviimise“ jaoks, alistavad duplikaadieemalduse reeglid.</span><span class="sxs-lookup"><span data-stu-id="64830-195">Any custom match rules defined for always match and never match overrule deduplication rules.</span></span> <span data-ttu-id="64830-196">Kui duplikaadieemalduse reegel tuvastab ühtivad kirjed ja kohandatud vastavusseviimise reegel on seatud neid kirjeid mitte kunagi vastavusse viima, siis neid kahte kirjet ei viida vastavusse.</span><span class="sxs-lookup"><span data-stu-id="64830-196">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="64830-197">Pärast vastavusseviimise protsessi käivitamist näete duplikaadieemalduse andmeid.</span><span class="sxs-lookup"><span data-stu-id="64830-197">After running the match process, you will see the deduplication stats.</span></span>
   
> [!NOTE]
> <span data-ttu-id="64830-198">Duplikaadieemalduse reeglite määramine pole kohustuslik.</span><span class="sxs-lookup"><span data-stu-id="64830-198">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="64830-199">Kui selliseid reegleid pole konfigureeritud, rakendatakse süsteemi määratletud reegleid.</span><span class="sxs-lookup"><span data-stu-id="64830-199">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="64830-200">Need ahendavad kõik kirjed, millel on sama primaarvõtme ja vastendusreeglite väljade väärtuskombinatsiooni (täpne vaste) ühte kirjesse, pärast mida edastatakse olemiandmed olemitevaheliseks vastavusseviimiseks, et jõudlus ja süsteem oleksid paremad.</span><span class="sxs-lookup"><span data-stu-id="64830-200">They collapse all records that share the same value combination (exact match) from primary key and the fields in the matching rules into a single record before passing the entity data to cross-entity matching for enhanced performance and system sanity.</span></span>

## <a name="run-your-match-order"></a><span data-ttu-id="64830-201">Käivitage vaste järjestus</span><span class="sxs-lookup"><span data-stu-id="64830-201">Run your match order</span></span>

<span data-ttu-id="64830-202">Pärast vastavusseviimise reeglite (sh olemitevahelise vastavusseviimise ja duplikaadieemalduse reeglite) määratlemist saate käivitada vastavusseviimise korralduse.</span><span class="sxs-lookup"><span data-stu-id="64830-202">After defining the match rules, including cross-entity matching and deduplication rules, you can run the match order.</span></span> <span data-ttu-id="64830-203">Toimingu käivitamiseks valige lehel **Vastendamine** valik **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="64830-203">On the **Match** page, select **Run** to start the process.</span></span> <span data-ttu-id="64830-204">Vastendamisalgoritm võib aega võtta.</span><span class="sxs-lookup"><span data-stu-id="64830-204">The matching algorithm might take some time to complete.</span></span> <span data-ttu-id="64830-205">Lehel **Vastendamine** ei saa muuta atribuute kuni vastendamine on lõppenud.</span><span class="sxs-lookup"><span data-stu-id="64830-205">You can't change properties on the **Match** page until the match process completes.</span></span> <span data-ttu-id="64830-206">Leiate ühendatud kliendiprofiili olemi, mis loodi lehel **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="64830-206">You'll find the unified customer profile entity that was created on the **Entities** page.</span></span> <span data-ttu-id="64830-207">Ühendatud kliendiolemit nimetatakse **ConflationMatchPairs : CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="64830-207">Your unified customer entity is called **ConflationMatchPairs:CustomerInsights**.</span></span>

<span data-ttu-id="64830-208">Täiendavate muudatuste tegemiseks ja etapi uuesti käivitamiseks saate poolelioleva vaste tühistada.</span><span class="sxs-lookup"><span data-stu-id="64830-208">To make additional changes and rerun the step, you can cancel a match in progress.</span></span> <span data-ttu-id="64830-209">Valige tekst **Värskendamine ...** ja valige nähtavale ilmuva külgpaani allosast suvand **Tühista töö**.</span><span class="sxs-lookup"><span data-stu-id="64830-209">Select the **Refreshing ...** text and select **Cancel job** at the bottom of the side pane that appears.</span></span>

<span data-ttu-id="64830-210">Kui vastendamise protsess on lõpule viinud, muutub tekst **Värskendamine ...** tekstiks **Õnnestus**, ja te saate jälle kasutada kõiki lehe funktsioone.</span><span class="sxs-lookup"><span data-stu-id="64830-210">When the match process is complete, the **Refreshing ...** text will change to **Successful** and you can use all functionality of the page again.</span></span>

<span data-ttu-id="64830-211">Esimene vastendamine loob koondpõhiolemit.</span><span class="sxs-lookup"><span data-stu-id="64830-211">The first match process results in the creation of a unified master entity.</span></span> <span data-ttu-id="64830-212">Kõik järgnevad vastendamised laiendavad seda olemit.</span><span class="sxs-lookup"><span data-stu-id="64830-212">All subsequent match runs result in the expansion of that entity.</span></span>

> [!TIP]
> <span data-ttu-id="64830-213">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="64830-213">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="64830-214">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="64830-214">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="64830-215">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="64830-215">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="64830-216">Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="64830-216">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="64830-217">Vastenduste ülevaatamine ja valideerimine</span><span class="sxs-lookup"><span data-stu-id="64830-217">Review and validate your matches</span></span>

<span data-ttu-id="64830-218">Hinnake vastepaaride kvaliteeti ja täiustage seda:</span><span class="sxs-lookup"><span data-stu-id="64830-218">Evaluate the quality of your match pairs and refine it:</span></span>

- <span data-ttu-id="64830-219">Lehel **Vastendamine** leiate kaks paani, kus näidatakse esmaseid ülevaateid teie andmetest.</span><span class="sxs-lookup"><span data-stu-id="64830-219">On the **Match** page, you'll find two tiles showing initial insights about your data.</span></span>

  - <span data-ttu-id="64830-220">**Kordumatud kliendid**: näitab süsteemi tuvastatud kordumatute profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="64830-220">**Unique customers**: shows the number of unique profiles that the system identified.</span></span>
  - <span data-ttu-id="64830-221">**Vastendatud kirjed**: näidatakse vastendamispaaride vastete arvu.</span><span class="sxs-lookup"><span data-stu-id="64830-221">**Matched records**: shows the number of matches across all of your match pairs.</span></span>

- <span data-ttu-id="64830-222">Tabelis **Vaste järjestus** pääsete juurde iga vastendamispaari tulemustele, selleks võrrelge vastepaari olemi kirjete arvu edukalt vastendatud kirjete protsendiga.</span><span class="sxs-lookup"><span data-stu-id="64830-222">In the **Match order** table, you can assess the results of each match pair by comparing the number of records that came from this match-pair entity against the percentage of successfully matched records.</span></span>

- <span data-ttu-id="64830-223">Tabeli **Vaste järjestus** olemi jaotises **Reeglid** leiate edukalt vastendatud kirjete protsendi reegli tasemel.</span><span class="sxs-lookup"><span data-stu-id="64830-223">In the **Rules** section of an entity in the **Match order** table, you'll find the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="64830-224">Reegli kõrval asuva tabeli sümboli valimisel näete kõiki neid kirjeid reegli tasemel.</span><span class="sxs-lookup"><span data-stu-id="64830-224">By selecting the table symbol next to a rule, you can view all these records on the rule level.</span></span> <span data-ttu-id="64830-225">Soovitame üle vaadata kirjete alamhulka, et kinnitada nende õiget vastendamist.</span><span class="sxs-lookup"><span data-stu-id="64830-225">We recommend that you review a subset of the records to validate that they were matched correctly.</span></span>

- <span data-ttu-id="64830-226">Optimaalse väärtuse tuvastamiseks katsetage tingimuste ümber eri täpsusega lävedega.</span><span class="sxs-lookup"><span data-stu-id="64830-226">Experiment with different precision thresholds around your conditions to identify the optimal value.</span></span>

  1. <span data-ttu-id="64830-227">Valige katsetatava vastendamispaari reegli puhul kolme punkti ikooni (...) ja valige **Muuda**.</span><span class="sxs-lookup"><span data-stu-id="64830-227">Select the ellipsis (...) for the match pair rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="64830-228">Valige tingimus, millega soovite katsetada.</span><span class="sxs-lookup"><span data-stu-id="64830-228">Select the condition that you want to experiment with.</span></span> <span data-ttu-id="64830-229">Iga kriteerium asub paanis **Vastendusreegel** ühes reas.</span><span class="sxs-lookup"><span data-stu-id="64830-229">Each criterion is represented by one row in the **Match rule** pane.</span></span>

  3. <span data-ttu-id="64830-230">Lehel **Kriteeriumi eelvaade** nähtu sõltub tingimuse täpsuse taset.</span><span class="sxs-lookup"><span data-stu-id="64830-230">What you'll see on the **Criteria preview** page depends on the precision level you've selected for a condition.</span></span> <span data-ttu-id="64830-231">Leidke valitud tingimuse vastendatud ja vastendamata kirjete arv.</span><span class="sxs-lookup"><span data-stu-id="64830-231">Find the number of matched and unmatched records for the selected condition.</span></span>

     <span data-ttu-id="64830-232">Hankige põhjalikke teadmisi eri läve tasemete mõjudest.</span><span class="sxs-lookup"><span data-stu-id="64830-232">Get a rich understanding of the effects of different threshold levels.</span></span> <span data-ttu-id="64830-233">Saate võrrelda, mitu kirjet vastendataks iga lävetaseme puhul ja vaadake iga valiku kirjeid.</span><span class="sxs-lookup"><span data-stu-id="64830-233">You can compare how many records will be matched under each of the threshold levels, and view the records under each option.</span></span> <span data-ttu-id="64830-234">Valige kõik paanid ja vaadake üle tabeli jaotise andmed.</span><span class="sxs-lookup"><span data-stu-id="64830-234">Select each of the tiles and review the data in the table section.</span></span>

## <a name="optimize-your-matches"></a><span data-ttu-id="64830-235">Vastete optimeerimine</span><span class="sxs-lookup"><span data-stu-id="64830-235">Optimize your matches</span></span>

<span data-ttu-id="64830-236">Parandage kvaliteeti, selleks seadistage uuesti paar vaste näitajat:</span><span class="sxs-lookup"><span data-stu-id="64830-236">Increase the quality by reconfiguring some of your match parameters:</span></span>

- <span data-ttu-id="64830-237">**Muutke vastendamisjärjestust**, selleks valige **Muuda** ja muutke vastendamisjärjekorra välju.</span><span class="sxs-lookup"><span data-stu-id="64830-237">**Change the match order** by selecting **Edit** and change the match order fields.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="64830-238">![Andmete vastendamisjärjestuse muutmine](media/configure-data-match-order-edit.png "Andmete vastendamisjärjestuse muutmine")</span><span class="sxs-lookup"><span data-stu-id="64830-238">![Edit data match order](media/configure-data-match-order-edit.png "Edit data match order")</span></span>

- <span data-ttu-id="64830-239">**Muutke reeglite järjestust**, kui määratlesite mitu reeglit.</span><span class="sxs-lookup"><span data-stu-id="64830-239">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="64830-240">Saate muuta vastendamisreeglite järjestust, selleks valige vastendamisreeglite ruudustikus **Liigu üles** ja **Liigu alla**.</span><span class="sxs-lookup"><span data-stu-id="64830-240">You can reorder the match rules by selecting the **Move Up** and **Move Down** options in the match rules grid.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="64830-241">![Muutke reegli järjestust](media/configure-data-change-rule-order.png "Muutke reegli järjestust")</span><span class="sxs-lookup"><span data-stu-id="64830-241">![Change rule order](media/configure-data-change-rule-order.png "Change rule order")</span></span>

- <span data-ttu-id="64830-242">**Paljundage reegleid**, kui olete määratlenud vastendamisreegli ja soovite luua sarnase, ent muudetud reegli.</span><span class="sxs-lookup"><span data-stu-id="64830-242">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications.</span></span> <span data-ttu-id="64830-243">Selleks valige **Duplikaat**.</span><span class="sxs-lookup"><span data-stu-id="64830-243">Do so by selecting **Duplicate**.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="64830-244">![Reegli paljundaminel](media/configure-data-duplicate-rule.png "Reegli paljundamine")</span><span class="sxs-lookup"><span data-stu-id="64830-244">![Duplicate a rule](media/configure-data-duplicate-rule.png "Duplicate a rule")</span></span>

- <span data-ttu-id="64830-245">**Muutke reegleid**, valides sümboli **Muuda**.</span><span class="sxs-lookup"><span data-stu-id="64830-245">**Edit your rules** by selecting the **Edit** symbol.</span></span> <span data-ttu-id="64830-246">Saate kasutada järgmisi muudatusi.</span><span class="sxs-lookup"><span data-stu-id="64830-246">You can apply the following changes:</span></span>

  - <span data-ttu-id="64830-247">Muutke tingimuse atribuute: valige kindlas tingimuse read uued atribuudid.</span><span class="sxs-lookup"><span data-stu-id="64830-247">Change attributes for a condition: Select new attributes within the specific condition row.</span></span>
  - <span data-ttu-id="64830-248">Muutke tingimuse läve: reguleerige täpsusliugurit.</span><span class="sxs-lookup"><span data-stu-id="64830-248">Change the threshold for a condition: Adjust the precision slider.</span></span>
  - <span data-ttu-id="64830-249">Muutke tingimuse normaliseerimisviisi: uuendage normaliseerimisviisi.</span><span class="sxs-lookup"><span data-stu-id="64830-249">Change the normalization method for a condition: Update the normalization method.</span></span>

## <a name="specify-your-custom-match-records"></a><span data-ttu-id="64830-250">Määrake muudetud vastendamiskirjed.</span><span class="sxs-lookup"><span data-stu-id="64830-250">Specify your custom match records</span></span>

<span data-ttu-id="64830-251">Saate määrata tingimused, et kindlad kirjed peaksid alati vastama või mitte kunagi vastama.</span><span class="sxs-lookup"><span data-stu-id="64830-251">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="64830-252">Neid reegleid saab vastendamisel üles laadida korraga.</span><span class="sxs-lookup"><span data-stu-id="64830-252">These rules can be uploaded in bulk to the match process.</span></span>

1. <span data-ttu-id="64830-253">Valige ekraanil **Vastendamisjärjestus** valikut **Kohandatud vaste**.</span><span class="sxs-lookup"><span data-stu-id="64830-253">Select the **Custom match** option on the **Match order** screen.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64830-254">![Kohandatud vaste loomine](media/custom-match-create.png "Kohandatud vaste loomine")</span><span class="sxs-lookup"><span data-stu-id="64830-254">![Create a custom match](media/custom-match-create.png "Create a custom match")</span></span>

2. <span data-ttu-id="64830-255">Kui olemeid pole üles laaditud, näete uut dialoogikasti **Kohandatud vaste**, mis nõuab teatud andmete sisestamist.</span><span class="sxs-lookup"><span data-stu-id="64830-255">If you have no uploaded entities, you'll see a new **Custom match** dialog box that requires you to fill in some details.</span></span> <span data-ttu-id="64830-256">Kui olete need andmed varem esitanud, jätkake kaheksanda etapiga.</span><span class="sxs-lookup"><span data-stu-id="64830-256">If you've provided these details earlier, skip to step 8.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64830-257">![Uus kohandatud vaste dialoogikast](media/custom-match-new-dialog-box.png "Uus kohandatud vaste dialoogikast")</span><span class="sxs-lookup"><span data-stu-id="64830-257">![New custom match dialog box](media/custom-match-new-dialog-box.png "New custom match dialog box")</span></span>

3. <span data-ttu-id="64830-258">Valige **Täida mall**, et hankida malli fail, mis määratleb, mis olemite kirjed peaksid kattuma alati või mitte kunagi.</span><span class="sxs-lookup"><span data-stu-id="64830-258">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="64830-259">Peate „Vastenda alati“ kirjed ja „Vastenda mitte kunagi“ kirjed sisestama eraldi kahte eri faili.</span><span class="sxs-lookup"><span data-stu-id="64830-259">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

4. <span data-ttu-id="64830-260">Mall sisaldab välju, et täpsustada kohandatud vastendamise olemit ja olemi primaarvõtme väärtusi.</span><span class="sxs-lookup"><span data-stu-id="64830-260">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="64830-261">Näiteks, kui soovite, et olemi Sales primaarvõti 12345 ühtiks alati olemi Contact primaarvõtmega 34567, peate täpsustama järgmiselt.</span><span class="sxs-lookup"><span data-stu-id="64830-261">For example, if you want primary key 12345 from Sales entity to always match with primary key 34567 from Contact entity, you'll need to specify as follows:</span></span>
    - <span data-ttu-id="64830-262">Entity1: Sales</span><span class="sxs-lookup"><span data-stu-id="64830-262">Entity1: Sales</span></span>
    - <span data-ttu-id="64830-263">Entity1Key: 12345</span><span class="sxs-lookup"><span data-stu-id="64830-263">Entity1Key: 12345</span></span>
    - <span data-ttu-id="64830-264">Entity2: Contact</span><span class="sxs-lookup"><span data-stu-id="64830-264">Entity2: Contact</span></span>
    - <span data-ttu-id="64830-265">Entity2Key: 34567</span><span class="sxs-lookup"><span data-stu-id="64830-265">Entity2Key: 34567</span></span>

   <span data-ttu-id="64830-266">Sama malli fail suudab määratleda mitme olemi kohandatud vastendamiskirjeid.</span><span class="sxs-lookup"><span data-stu-id="64830-266">The same template file can specify custom match records from multiple entities.</span></span>

5. <span data-ttu-id="64830-267">Pärast kõikide soovitud asenduste lisamist salvestage malli fail.</span><span class="sxs-lookup"><span data-stu-id="64830-267">After adding all the overrides you want to apply, save the template file.</span></span>

<span data-ttu-id="64830-268">6. Minge jaotisse **Andmed** > **Andmeallikad** ja valmendage mallifailid uute olemitena.</span><span class="sxs-lookup"><span data-stu-id="64830-268">6.Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="64830-269">Pärast sisestamist saate nendega määratleda vastendamisseadistust.</span><span class="sxs-lookup"><span data-stu-id="64830-269">Once ingested, you can use them to specify the Match configuration.</span></span>

7. <span data-ttu-id="64830-270">Pärast failide üleslaadimist ja olemite avalikustamist valige uuesti valik **Kohandatud vaste**.</span><span class="sxs-lookup"><span data-stu-id="64830-270">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="64830-271">Näete valikuid, et täpsustada kaasatavad olemid.</span><span class="sxs-lookup"><span data-stu-id="64830-271">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="64830-272">Valige rippmenüüst vajalikud olemid.</span><span class="sxs-lookup"><span data-stu-id="64830-272">Select the required entities from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="64830-273">![Kohandatud vaste asendused](media/custom-match-overrides.png "Kohandatud vaste asendused")</span><span class="sxs-lookup"><span data-stu-id="64830-273">![Custom match overrides](media/custom-match-overrides.png "Custom match overrides")</span></span>

8. <span data-ttu-id="64830-274">Valige olemid, mida tahate kasutada **Vastenda alati** ja **Vastenda mitte kunagi** puhul, seejärel valige **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="64830-274">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

9. <span data-ttu-id="64830-275">Valige äsja seadistatud kohandatud vaste seadistuse lehel **Vastendamine** valik **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="64830-275">Select **Save** on the **Match** page for the custom match configuration you just set up.</span></span>

10. <span data-ttu-id="64830-276">Vastendamiseks valige lehel **Vastendamine** valik **Käivita** ja kohandatud vaste seadistus läheb kasutusele.</span><span class="sxs-lookup"><span data-stu-id="64830-276">Select **Run** on the **Match** page to start the matching process, and the custom match configuration will be taken into effect.</span></span> <span data-ttu-id="64830-277">Kõik süsteemi vastendatud reeglid asendatakse seadistuskomplektiga.</span><span class="sxs-lookup"><span data-stu-id="64830-277">Any system matched rules are overridden by the configuration set.</span></span>

11. <span data-ttu-id="64830-278">Pärast vastendamist saate kinnitada olemi **ConflationMatchPair**, et kinnitada, kas ühendamisvasted asendati.</span><span class="sxs-lookup"><span data-stu-id="64830-278">Once the matching is complete, you can verify the **ConflationMatchPair** entity to confirm that the overrides are applied in the conflation matches.</span></span>

## <a name="next-step"></a><span data-ttu-id="64830-279">Järgmine etapp</span><span class="sxs-lookup"><span data-stu-id="64830-279">Next step</span></span>

<span data-ttu-id="64830-280">Pärast vähemalt ühe vastendamispaari vastendamist võite lahendada andmete võimalikud vastuolud, selleks lugege teemat [**Liitmine**](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="64830-280">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>
