---
title: Kliendiprofiilide rikastamine Microsoft Graphiga
description: Microsoft Graphi konfidentsiaalsete andmete kasutamine, et rikastada kliendi andmeid brändi ja huvide ligitõmbavusega.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: aa46dac4f9c0d27881371877b14a92a6725710da
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596448"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="16764-103">Kliendiprofiilide rikastamine brändi ja huvide ligitõmbavusega (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="16764-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="16764-104">Microsoft Graphi konfidentsiaalsete andmete kasutamine, et rikastada kliendi andmeid brändi ja huvide ligitõmbavusega.</span><span class="sxs-lookup"><span data-stu-id="16764-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="16764-105">Need ühtivused määratakse teie klientidega sarnaste demograafiliste näitajatega inimeste andmete põhjal.</span><span class="sxs-lookup"><span data-stu-id="16764-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="16764-106">See teave aitab teil paremini mõista ja segmentida oma kliente, lähtudes nende ligitõmbavusest konkreetsetele tootemarkidele ja huvidele.</span><span class="sxs-lookup"><span data-stu-id="16764-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="16764-107">Liikuge sihtrühmaülevaadetes jaotisse **Andmed** > **Rikastamine**, et [seadistada ja vaadata rikastamisi](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="16764-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="16764-108">Tootemargi külgetõmbe rikastamise konfigureerimiseks minge vahekaardile **Avastamine** ja valige paanil **Tootemargid** suvand **Rikasta minu andmed**.</span><span class="sxs-lookup"><span data-stu-id="16764-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="16764-109">Huvide külgetõmbe rikastamise konfigureerimiseks minge vahekaardile **Avastamine** ja valige paanil **Huvid** suvand **Rikasta minu andmed**.</span><span class="sxs-lookup"><span data-stu-id="16764-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="16764-110">![Tootemarkide ja huvide paanid](media/BrandsInterest-tile-Hub.png "Tootemarkide ja huvide paanid")</span><span class="sxs-lookup"><span data-stu-id="16764-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="16764-111">Microsoft Graphi teave</span><span class="sxs-lookup"><span data-stu-id="16764-111">About Microsoft Graph</span></span>

<span data-ttu-id="16764-112">Kasutame Microsoft Graphi veebiotsingu andmeid, et leida erinevate demograafiliste segmentide (mis on määratletud vanuse, soo või asukoha järgi) brändide ja huvide ligitõmbavusi.</span><span class="sxs-lookup"><span data-stu-id="16764-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="16764-113">Brändi või huvi veebiotsingu maht määratleb, kui palju ligitõmbavust on demograafilisel segmendil selle brändi või huvi suhtes võrreldes teiste segmentidega.</span><span class="sxs-lookup"><span data-stu-id="16764-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="16764-114">[Lisateave Microsoft Graphi kohta](/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="16764-114">[Learn more about Microsoft Graph](/graph/overview).</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="16764-115">Ühtivuse tase ja skoor</span><span class="sxs-lookup"><span data-stu-id="16764-115">Affinity level and score</span></span>

<span data-ttu-id="16764-116">Igal rikastatud kliendiprofiilil pakume kahte seotud väärtust – ühtivuse tase ja skoor.</span><span class="sxs-lookup"><span data-stu-id="16764-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="16764-117">Need väärtused aitavad teil määratleda, kui suur ühtivus on selle profiili demograafilisel segmendil teatud tootemargi või huvi jaoks, võrreldes muude demograafiliste segmentidega.</span><span class="sxs-lookup"><span data-stu-id="16764-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="16764-118">*Ühtivustase* koosneb neljast tasemest ja *ühtivuse skoor* arvutatakse 100 punkti skaalal, mis vastendatakse ühtivustasemetega.</span><span class="sxs-lookup"><span data-stu-id="16764-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="16764-119">Ühtivustase</span><span class="sxs-lookup"><span data-stu-id="16764-119">Affinity level</span></span> |<span data-ttu-id="16764-120">Ühtivuse skoor</span><span class="sxs-lookup"><span data-stu-id="16764-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="16764-121">Väga palju</span><span class="sxs-lookup"><span data-stu-id="16764-121">Very high</span></span>     | <span data-ttu-id="16764-122">85–100</span><span class="sxs-lookup"><span data-stu-id="16764-122">85-100</span></span>       |
|<span data-ttu-id="16764-123">Suur</span><span class="sxs-lookup"><span data-stu-id="16764-123">High</span></span>     | <span data-ttu-id="16764-124">70–84</span><span class="sxs-lookup"><span data-stu-id="16764-124">70-84</span></span>        |
|<span data-ttu-id="16764-125">Keskmine</span><span class="sxs-lookup"><span data-stu-id="16764-125">Medium</span></span>     | <span data-ttu-id="16764-126">35–69</span><span class="sxs-lookup"><span data-stu-id="16764-126">35-69</span></span>        |
|<span data-ttu-id="16764-127">Väike</span><span class="sxs-lookup"><span data-stu-id="16764-127">Low</span></span>     | <span data-ttu-id="16764-128">1–34</span><span class="sxs-lookup"><span data-stu-id="16764-128">1-34</span></span>        |

<span data-ttu-id="16764-129">Sõltuvalt granulaarsusest, mida soovite ühtivuse mõõtmisel, saate kasutada ühtivuse taset või skoori.</span><span class="sxs-lookup"><span data-stu-id="16764-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="16764-130">Ühtivuse skoor annab teile täpsema kontrolli.</span><span class="sxs-lookup"><span data-stu-id="16764-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="16764-131">Toetatud riigid/piirkonnad</span><span class="sxs-lookup"><span data-stu-id="16764-131">Supported countries/regions</span></span>

<span data-ttu-id="16764-132">Toetame praegu järgmisi riigi/regiooni suvandeid: Austraalia, Kanada (inglise), Prantsusmaa, Saksamaa, Ühendkuningriik või Ameerika Ühendriigid (inglise).</span><span class="sxs-lookup"><span data-stu-id="16764-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="16764-133">Riigi valimiseks avage **Tootemarkide rikastamine** või **Huvide rikastamine** ning valige suvand **Muuda** valiku **Riik/piirkond** kõrval.</span><span class="sxs-lookup"><span data-stu-id="16764-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="16764-134">Paanil **Riigi/piirkonna sätted** valige suvand ja valige **Rakenda**.</span><span class="sxs-lookup"><span data-stu-id="16764-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="16764-135">Riigi valikuga seotud mõjud</span><span class="sxs-lookup"><span data-stu-id="16764-135">Implications related to country selection</span></span>

- <span data-ttu-id="16764-136">Kui [valite oma tootemarke](#define-your-brands-or-interests), pakub süsteem valitud riigil või piirkonnal põhinevaid soovitusi.</span><span class="sxs-lookup"><span data-stu-id="16764-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="16764-137">Kui [valite valdkonna](#define-your-brands-or-interests), saate olulisemaid tootemarke või huvisid valitud riigi või piirkonna põhjal.</span><span class="sxs-lookup"><span data-stu-id="16764-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="16764-138">Kui [rikastate profiile](#refresh-enrichment), rikastame kõiki kliendiprofiile, mille jaoks saame valitud tootemarkide ja huvide andmeid.</span><span class="sxs-lookup"><span data-stu-id="16764-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="16764-139">Sealhulgas profiilid, mis pole valitud riigis või piirkonnas.</span><span class="sxs-lookup"><span data-stu-id="16764-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="16764-140">Näiteks kui valisite Saksamaa, rikastame Ameerika Ühendriikides asuvaid profiile, kui meil on Microsoft Graph'i andmed saadaval valitud kaubamärkide ja huvide kohta USAs.</span><span class="sxs-lookup"><span data-stu-id="16764-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="16764-141">Rikastamise konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="16764-141">Configure Enrichment</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="16764-142">Määratlege oma tootemargid või huvid</span><span class="sxs-lookup"><span data-stu-id="16764-142">Define your brands or interests</span></span>

<span data-ttu-id="16764-143">Valige üks järgmistest suvanditest.</span><span class="sxs-lookup"><span data-stu-id="16764-143">Select one of the following options:</span></span>

- <span data-ttu-id="16764-144">**Tööstus** : süsteem tuvastab peamised teie tööstuse jaoks asjakohased tootemargid või huvid ning rikastab nendega teie kliendiandmeid.</span><span class="sxs-lookup"><span data-stu-id="16764-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="16764-145">**Valige enda oma**: valige tootemarkide või huvide loendist viis üksust, mis on teie organisatsiooni jaoks kõige asjakohasemad.</span><span class="sxs-lookup"><span data-stu-id="16764-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="16764-146">Brändi või huvi lisamiseks sisestage see sisendi alasse, et saada sobivate terminite soovitusi.</span><span class="sxs-lookup"><span data-stu-id="16764-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="16764-147">Kui me ei loetle otsitavaid brände või huvisid, saatke meile tagasisidet, kasutades linki **Soovita**.</span><span class="sxs-lookup"><span data-stu-id="16764-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="16764-148">Rikastamise eelistuste ülevaatamine</span><span class="sxs-lookup"><span data-stu-id="16764-148">Review enrichment preferences</span></span>

<span data-ttu-id="16764-149">Vaadake üle oma rikastamise vaike-eelistused ja värskendage neid vastavalt vajadusele.</span><span class="sxs-lookup"><span data-stu-id="16764-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Rikastamise eelistuste akna kuvatõmmis.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="16764-151">Valige rikastamiseks olem</span><span class="sxs-lookup"><span data-stu-id="16764-151">Select entity to enrich</span></span>

<span data-ttu-id="16764-152">Valige **Vastendatud olem** ja valige andmete kogum, mida soovite Microsoft Graphi ettevõtte andmetega rikastada.</span><span class="sxs-lookup"><span data-stu-id="16764-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft Graph.</span></span> <span data-ttu-id="16764-153">Saate valida olemi Klient, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.</span><span class="sxs-lookup"><span data-stu-id="16764-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="16764-154">Väljade vastendamine</span><span class="sxs-lookup"><span data-stu-id="16764-154">Map your fields</span></span>

<span data-ttu-id="16764-155">Vastendage oma ühendatud kliendiolemi väljad demograafilise segmendi määratlemiseks, mida süsteem kasutab teie kliendiandmete rikastamiseks.</span><span class="sxs-lookup"><span data-stu-id="16764-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="16764-156">Vastendage riigi/piirkonna ja vähemalt sünniaja või soo atribuudid.</span><span class="sxs-lookup"><span data-stu-id="16764-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="16764-157">Lisaks peate näitama kaardil vähemalt ühte linna (ja osariiki/maakonda) või sihtnumbrit.</span><span class="sxs-lookup"><span data-stu-id="16764-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="16764-158">Valige suvand **Redigeeri**, et määratleda väljade vastendamine, ja valige suvand **Rakenda**, kui olete lõpetanud.</span><span class="sxs-lookup"><span data-stu-id="16764-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="16764-159">Väljavastenduse lõpule viimiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="16764-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="16764-160">Toetatakse järgmisi vorminguid ja väärtusi, kuid väärtused pole tõstutundlikud.</span><span class="sxs-lookup"><span data-stu-id="16764-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="16764-161">**Sünniaeg**: soovitame, et sünniaeg oleks andmete valmendamisel teisendatud DateTime tüüpi.</span><span class="sxs-lookup"><span data-stu-id="16764-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="16764-162">Alternatiivina võib see olla string [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) vormingus "aaaa–KK–pp" või "aaaa–KK–PPTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="16764-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="16764-163">**Sugu**: mees, naine, teadmata</span><span class="sxs-lookup"><span data-stu-id="16764-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="16764-164">**Sihtnumber**: viiekohaline sihtnumber USAs, standardne sihtnumber kõikjal mujal</span><span class="sxs-lookup"><span data-stu-id="16764-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="16764-165">**Linn**: linna nimi inglise keeles</span><span class="sxs-lookup"><span data-stu-id="16764-165">**City**: City name in English</span></span>
- <span data-ttu-id="16764-166">**Osariik/maakond**: kahetäheline lühend USA ja Kanada jaoks.</span><span class="sxs-lookup"><span data-stu-id="16764-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="16764-167">Kahe- või kolmetäheline lühend Austraalia jaoks.</span><span class="sxs-lookup"><span data-stu-id="16764-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="16764-168">Ei kohaldata Prantsusmaa, Saksamaa ega Ühendkuningriigi korral.</span><span class="sxs-lookup"><span data-stu-id="16764-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="16764-169">**Riik/piirkond**:</span><span class="sxs-lookup"><span data-stu-id="16764-169">**Country/Region**:</span></span>

  - <span data-ttu-id="16764-170">US: Ameerika Ühendriigid, Ühendriigid, USA, US, Ameerika</span><span class="sxs-lookup"><span data-stu-id="16764-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="16764-171">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="16764-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="16764-172">GB: Ühendkuningriik, UK, Suurbritannia, GB, Suurbritannia ja Põhja-Iiri Ühendkuningriik, Suurbritannia Ühendkuningriik</span><span class="sxs-lookup"><span data-stu-id="16764-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="16764-173">AU: Austraalia, AU, Austraalia Commonwealth</span><span class="sxs-lookup"><span data-stu-id="16764-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="16764-174">FR: Prantsusmaa, FR, Prantsuse Vabariik</span><span class="sxs-lookup"><span data-stu-id="16764-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="16764-175">DE: Saksamaa, Saksa, Deutschland, Allemagne, DE, Saksamaa Liitvabariik, Saksamaa Vabariik</span><span class="sxs-lookup"><span data-stu-id="16764-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="16764-176">Rikastamise värskendamine</span><span class="sxs-lookup"><span data-stu-id="16764-176">Refresh enrichment</span></span>

<span data-ttu-id="16764-177">Pärast brändide, huvide ja demograafilise väljavastenduse konfigureerimist käivitage rikastamine.</span><span class="sxs-lookup"><span data-stu-id="16764-177">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="16764-178">Protsessi käivitamiseks valige tootemargi või huvide lehel käsk **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="16764-178">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="16764-179">Lisaks saate lasta süsteemil käitada rikastamist automaatselt ajastatud värskendamise osana.</span><span class="sxs-lookup"><span data-stu-id="16764-179">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="16764-180">Sõltuvalt kliendiandmete mahust võib rikastamise käitamise lõpuleviimiseks kuluda mitu minutit.</span><span class="sxs-lookup"><span data-stu-id="16764-180">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="16764-181">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="16764-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="16764-182">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="16764-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="16764-183">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="16764-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="16764-184">Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="16764-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="16764-185">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="16764-185">Enrichment results</span></span>

<span data-ttu-id="16764-186">Pärast rikastamise protsessi käitamist, avage jaotis **Minu rikastamised**, et vaadata üle rikastatud klientide koguarv ja kaubamärkide või huvide jagunemine rikastatud kliendiprofiilides.</span><span class="sxs-lookup"><span data-stu-id="16764-186">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Tulemuste eelvaade pärast rikastamise protsessi käitamist":::

<span data-ttu-id="16764-188">Rikastatud andmete ülevaatamiseks valige diagrammilt **Rikastatud andmete vaatamine**.</span><span class="sxs-lookup"><span data-stu-id="16764-188">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="16764-189">Brändide rikastatud andmed lähevad olemisse **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="16764-189">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="16764-190">Huvide andmed on olemis **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="16764-190">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="16764-191">Samuti leiate need olemis loetletuna rühmas **Rikastamine** suvandis **Andmed** > **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="16764-191">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="16764-192">Kliendi kaardi rikastamise andmete vaatamine</span><span class="sxs-lookup"><span data-stu-id="16764-192">See enrichment data on the customer card</span></span>

<span data-ttu-id="16764-193">Kaubamärgi ja huvide ühtivust saate vaadata ka eraldi kliendi kaartidel.</span><span class="sxs-lookup"><span data-stu-id="16764-193">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="16764-194">Avage **Kliendid** ja valige kliendiprofiil.</span><span class="sxs-lookup"><span data-stu-id="16764-194">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="16764-195">Kliendi kaardilt leiate diagrammid tootemarkide või huvide kohta, mille suhtes on külgetõmme selle kliendi demograafilise profiili inimestel.</span><span class="sxs-lookup"><span data-stu-id="16764-195">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kliendi kaart rikastatud andmetega":::

## <a name="next-steps"></a><span data-ttu-id="16764-197">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="16764-197">Next steps</span></span>

<span data-ttu-id="16764-198">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="16764-198">Build on top of your enriched customer data.</span></span> <span data-ttu-id="16764-199">Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [andmete eksport](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="16764-199">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]