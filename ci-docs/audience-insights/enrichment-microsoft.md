---
title: Kliendiprofiilide rikastamine Microsofti andmetega
description: Kasutage Microsofti omandiandmeid kliendiandmete rikastamiseks kaubamärgi ja omandiõigusega seotud andmetega.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 1b11c325649b91ebb47cde924227eacedae64b7a
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305151"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="078ec-103">Kliendiprofiilide rikastamine brändi ja huvide ligitõmbavusega (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="078ec-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="078ec-104">Kasutage Microsofti omandiandmeid kliendiandmete rikastamiseks kaubamärgi ja omandiõigusega seotud andmetega.</span><span class="sxs-lookup"><span data-stu-id="078ec-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="078ec-105">Need sarnasused põhinevad teie klientidele sarnase demograafilise demograafiaga inimeste andmetel.</span><span class="sxs-lookup"><span data-stu-id="078ec-105">These affinities are based on data from people with demographics similar to your customers.</span></span> <span data-ttu-id="078ec-106">See teave aitab teil paremini mõista ja segmentida oma kliente, lähtudes nende ligitõmbavusest konkreetsetele tootemarkidele ja huvidele.</span><span class="sxs-lookup"><span data-stu-id="078ec-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="078ec-107">Liikuge sihtrühmaülevaadetes jaotisse **Andmed** > **Rikastamine**, et [seadistada ja vaadata rikastamisi](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="078ec-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="078ec-108">Tootemargi külgetõmbe rikastamise konfigureerimiseks minge vahekaardile **Avastamine** ja valige paanil **Tootemargid** suvand **Rikasta minu andmed**.</span><span class="sxs-lookup"><span data-stu-id="078ec-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="078ec-109">Huvide külgetõmbe rikastamise konfigureerimiseks minge vahekaardile **Avastamine** ja valige paanil **Huvid** suvand **Rikasta minu andmed**.</span><span class="sxs-lookup"><span data-stu-id="078ec-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="078ec-110">![Tootemarkide ja huvide paanid](media/BrandsInterest-tile-Hub.png "Tootemarkide ja huvide paanid")</span><span class="sxs-lookup"><span data-stu-id="078ec-110">![Brands and Interests tiles](media/BrandsInterest-tile-Hub.png "Brands and Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="078ec-111">Kuidas määratleme ärisuhteid</span><span class="sxs-lookup"><span data-stu-id="078ec-111">How we determine affinities</span></span>

<span data-ttu-id="078ec-112">Microsoft kasutab veebipõhised otsinguandmed, et leida kaubamärkide ja omandiõiguste vahelisi sidemeid erinevates demograafilistes segmentides (määratletud vanuse, soo või asukoha järgi).</span><span class="sxs-lookup"><span data-stu-id="078ec-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="078ec-113">Brändi või huvi veebiotsingu maht määratleb, kui palju ligitõmbavust on demograafilisel segmendil selle brändi või huvi suhtes võrreldes teiste segmentidega.</span><span class="sxs-lookup"><span data-stu-id="078ec-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="078ec-114">Ühtivuse tase ja skoor</span><span class="sxs-lookup"><span data-stu-id="078ec-114">Affinity level and score</span></span>

<span data-ttu-id="078ec-115">Igal rikastatud kliendiprofiilil pakume kahte seotud väärtust: afiinsuse tase ja afiinsuse skoor.</span><span class="sxs-lookup"><span data-stu-id="078ec-115">On every enriched customer profile, we provide two related values: affinity level and affinity score.</span></span> <span data-ttu-id="078ec-116">Need väärtused aitavad teil määratleda, kui suur ühtivus on selle profiili demograafilisel segmendil teatud tootemargi või huvi jaoks, võrreldes muude demograafiliste segmentidega.</span><span class="sxs-lookup"><span data-stu-id="078ec-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="078ec-117">*Ühtivustase* koosneb neljast tasemest ja *ühtivuse skoor* arvutatakse 100 punkti skaalal, mis vastendatakse ühtivustasemetega.</span><span class="sxs-lookup"><span data-stu-id="078ec-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="078ec-118">Ühtivustase</span><span class="sxs-lookup"><span data-stu-id="078ec-118">Affinity level</span></span> |<span data-ttu-id="078ec-119">Ühtivuse skoor</span><span class="sxs-lookup"><span data-stu-id="078ec-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="078ec-120">Väga palju</span><span class="sxs-lookup"><span data-stu-id="078ec-120">Very high</span></span>     | <span data-ttu-id="078ec-121">85–100</span><span class="sxs-lookup"><span data-stu-id="078ec-121">85-100</span></span>       |
|<span data-ttu-id="078ec-122">Suur</span><span class="sxs-lookup"><span data-stu-id="078ec-122">High</span></span>     | <span data-ttu-id="078ec-123">70–84</span><span class="sxs-lookup"><span data-stu-id="078ec-123">70-84</span></span>        |
|<span data-ttu-id="078ec-124">Keskmine</span><span class="sxs-lookup"><span data-stu-id="078ec-124">Medium</span></span>     | <span data-ttu-id="078ec-125">35–69</span><span class="sxs-lookup"><span data-stu-id="078ec-125">35-69</span></span>        |
|<span data-ttu-id="078ec-126">Väike</span><span class="sxs-lookup"><span data-stu-id="078ec-126">Low</span></span>     | <span data-ttu-id="078ec-127">1–34</span><span class="sxs-lookup"><span data-stu-id="078ec-127">1-34</span></span>        |

<span data-ttu-id="078ec-128">Sõltuvalt granulaarsusest, mida soovite ühtivuse mõõtmisel, saate kasutada ühtivuse taset või skoori.</span><span class="sxs-lookup"><span data-stu-id="078ec-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="078ec-129">Ühtivuse skoor annab teile täpsema kontrolli.</span><span class="sxs-lookup"><span data-stu-id="078ec-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="078ec-130">Toetatud riigid/piirkonnad</span><span class="sxs-lookup"><span data-stu-id="078ec-130">Supported countries/regions</span></span>

<span data-ttu-id="078ec-131">Toetame praegu järgmisi riigi/regiooni suvandeid: Austraalia, Kanada (inglise), Prantsusmaa, Saksamaa, Ühendkuningriik või Ameerika Ühendriigid (inglise).</span><span class="sxs-lookup"><span data-stu-id="078ec-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="078ec-132">Et valida riik või piirkond, avage **Tootemarkide rikastamine** või **Huvide rikastamine** ja valige **Muuda** **Riik/regioon** kõrval.</span><span class="sxs-lookup"><span data-stu-id="078ec-132">To select a country or region, open **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="078ec-133">Paanil **Riigi/piirkonna sätted** valige suvand ja valige **Rakenda**.</span><span class="sxs-lookup"><span data-stu-id="078ec-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="078ec-134">Riigi valikuga seotud mõjud</span><span class="sxs-lookup"><span data-stu-id="078ec-134">Implications related to country selection</span></span>

- <span data-ttu-id="078ec-135">Kui [valite oma tootemarke](#define-your-brands-or-interests), pakub süsteem valitud riigil või piirkonnal põhinevaid soovitusi.</span><span class="sxs-lookup"><span data-stu-id="078ec-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="078ec-136">Kui [valite valdkonna](#define-your-brands-or-interests), saate olulisemaid tootemarke või huvisid valitud riigi või piirkonna põhjal.</span><span class="sxs-lookup"><span data-stu-id="078ec-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="078ec-137">Kui [rikastame profiile](#refresh-enrichment), rikastame kõiki kliendiprofiile, mille jaoks me saame andmeid valitud tootemarkide ja huvide jaoks, kaasaarvatud profiilid, mis ei ole valitud riigis või piirkonnas.</span><span class="sxs-lookup"><span data-stu-id="078ec-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests, including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="078ec-138">Näiteks kui valisite Saksamaa, rikastame Ameerika Ühendriikides asuvad profiilid, kui meil on Ameerika Ühendriikides valitud kaubamärkide ja omandiõiguse andmeid.</span><span class="sxs-lookup"><span data-stu-id="078ec-138">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="078ec-139">Rikastamise konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="078ec-139">Configure enrichment</span></span>

<span data-ttu-id="078ec-140">Juhendatud kogemus aitab teid läbi rikastamise konfiguratsiooni.</span><span class="sxs-lookup"><span data-stu-id="078ec-140">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="078ec-141">Määratlege oma tootemargid või huvid</span><span class="sxs-lookup"><span data-stu-id="078ec-141">Define your brands or interests</span></span>

<span data-ttu-id="078ec-142">Valige kuni viis kaubamärki või huvi, kasutades ühte või mõlemat järgmist valikut.</span><span class="sxs-lookup"><span data-stu-id="078ec-142">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="078ec-143">**Tööstus**: Valige ripploendist oma valdkond ja valige siis selle valdkonna jaoks kõige populaarsem kaubamärk või huvid.</span><span class="sxs-lookup"><span data-stu-id="078ec-143">**Industry**: Select your industry from the dropdown list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="078ec-144">**Valige oma nimi**. Sisestage oma ettevõtte jaoks oluline kaubamärk või huvi ja valige siis valite vastavate soovituste vahel.</span><span class="sxs-lookup"><span data-stu-id="078ec-144">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="078ec-145">Kui me ei loetle otsitavaid brände või huvisid, saatke meile tagasisidet, kasutades linki **Soovita**.</span><span class="sxs-lookup"><span data-stu-id="078ec-145">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="078ec-146">Rikastamise eelistuste ülevaatamine</span><span class="sxs-lookup"><span data-stu-id="078ec-146">Review enrichment preferences</span></span>

<span data-ttu-id="078ec-147">Vaadake üle oma rikastamise vaike-eelistused ja värskendage neid vastavalt vajadusele.</span><span class="sxs-lookup"><span data-stu-id="078ec-147">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Rikastamise eelistuste akna kuvatõmmis.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="078ec-149">Valige rikastamiseks olem</span><span class="sxs-lookup"><span data-stu-id="078ec-149">Select entity to enrich</span></span>

<span data-ttu-id="078ec-150">Valige **Rikastatud olem** ja valige andmekomplekt, mida soovite rikastada ettevõtte andmetega Microsoftilt.</span><span class="sxs-lookup"><span data-stu-id="078ec-150">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="078ec-151">Saate valida olemi Klient, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.</span><span class="sxs-lookup"><span data-stu-id="078ec-151">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="078ec-152">Väljade vastendamine</span><span class="sxs-lookup"><span data-stu-id="078ec-152">Map your fields</span></span>

<span data-ttu-id="078ec-153">Vastendage oma ühendatud kliendiolemi väljad demograafilise segmendi määratlemiseks, mida süsteem kasutab teie kliendiandmete rikastamiseks.</span><span class="sxs-lookup"><span data-stu-id="078ec-153">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="078ec-154">Vastendage riigi/piirkonna ja vähemalt sünniaja või soo atribuudid.</span><span class="sxs-lookup"><span data-stu-id="078ec-154">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="078ec-155">Lisaks peate näitama kaardil vähemalt ühte linna (ja osariiki/maakonda) või sihtnumbrit.</span><span class="sxs-lookup"><span data-stu-id="078ec-155">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="078ec-156">Valige suvand **Redigeeri**, et määratleda väljade vastendamine, ja valige suvand **Rakenda**, kui olete lõpetanud.</span><span class="sxs-lookup"><span data-stu-id="078ec-156">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="078ec-157">Väljavastenduse lõpule viimiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="078ec-157">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="078ec-158">Toetatakse järgmisi vorminguid ja väärtusi (väärtused pole tõstutundlikud):</span><span class="sxs-lookup"><span data-stu-id="078ec-158">The following formats and values are supported (values are not case-sensitive):</span></span>

- <span data-ttu-id="078ec-159">**Sünniaeg**: soovitame, et sünniaeg oleks andmete valmendamisel teisendatud DateTime tüüpi.</span><span class="sxs-lookup"><span data-stu-id="078ec-159">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="078ec-160">Teise võimalusena võib see olla string [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) formaadis "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span><span class="sxs-lookup"><span data-stu-id="078ec-160">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ss".</span></span>
- <span data-ttu-id="078ec-161">**Sugu**: mees, naine, teadmata.</span><span class="sxs-lookup"><span data-stu-id="078ec-161">**Gender**: Male, Female, Unknown.</span></span>
- <span data-ttu-id="078ec-162">**Sihtnumber**: Ameerika Ühendriikide viiekohaline sihtnumber, standardne sihtnumber mujal.</span><span class="sxs-lookup"><span data-stu-id="078ec-162">**Postal code**: Five-digit ZIP codes for United States, standard postal code everywhere else.</span></span>
- <span data-ttu-id="078ec-163">**Linn**: linna nimi inglise keeles.</span><span class="sxs-lookup"><span data-stu-id="078ec-163">**City**: City name in English.</span></span>
- <span data-ttu-id="078ec-164">**Osariik/maakond**: kahetäheline lühend USA ja Kanada jaoks.</span><span class="sxs-lookup"><span data-stu-id="078ec-164">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="078ec-165">Kahe- või kolmetäheline lühend Austraalia jaoks.</span><span class="sxs-lookup"><span data-stu-id="078ec-165">Two- or three-letter abbreviation for Australia.</span></span> <span data-ttu-id="078ec-166">Ei kohaldata Prantsusmaa, Saksamaa ega Ühendkuningriigi korral.</span><span class="sxs-lookup"><span data-stu-id="078ec-166">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="078ec-167">**Riik/piirkond**:</span><span class="sxs-lookup"><span data-stu-id="078ec-167">**Country/Region**:</span></span>

  - <span data-ttu-id="078ec-168">US: Ameerika Ühendriigid, Ühendriigid, USA, US, Ameerika</span><span class="sxs-lookup"><span data-stu-id="078ec-168">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="078ec-169">CA: Kanada, CA</span><span class="sxs-lookup"><span data-stu-id="078ec-169">CA: Canada, CA</span></span>
  - <span data-ttu-id="078ec-170">GB: Ühendkuningriik, UK, Suurbritannia, GB, Suurbritannia ja Põhja-Iiri Ühendkuningriik, Suurbritannia Ühendkuningriik</span><span class="sxs-lookup"><span data-stu-id="078ec-170">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="078ec-171">AU: Austraalia, AU, Austraalia Liit</span><span class="sxs-lookup"><span data-stu-id="078ec-171">AU: Australia, AU, Commonwealth of Australia</span></span>
  - <span data-ttu-id="078ec-172">FR: Prantsusmaa, FR, Prantsuse Vabariik</span><span class="sxs-lookup"><span data-stu-id="078ec-172">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="078ec-173">DE: Saksamaa, Saksa, Deutschland, Allemagne, DE, Saksamaa Liitvabariik, Saksamaa Vabariik</span><span class="sxs-lookup"><span data-stu-id="078ec-173">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="078ec-174">Rikastamise läbivaatamine ja rikastamisele nime andmine</span><span class="sxs-lookup"><span data-stu-id="078ec-174">Review and name the enrichment</span></span>

<span data-ttu-id="078ec-175">Lõpuks saate eelvaadata teavet ja anda rikastamisele nimi.</span><span class="sxs-lookup"><span data-stu-id="078ec-175">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Omandiõiguste eelversioon ja nime leht.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="078ec-177">Rikastamise värskendamine</span><span class="sxs-lookup"><span data-stu-id="078ec-177">Refresh enrichment</span></span>

<span data-ttu-id="078ec-178">Pärast brändide, huvide ja demograafilise väljavastenduse konfigureerimist käivitage rikastamine.</span><span class="sxs-lookup"><span data-stu-id="078ec-178">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="078ec-179">Protsessi käivitamiseks valige tootemargi või huvide lehel käsk **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="078ec-179">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="078ec-180">Lisaks saate lasta süsteemil käitada rikastamist automaatselt ajastatud värskendamise osana.</span><span class="sxs-lookup"><span data-stu-id="078ec-180">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>

<span data-ttu-id="078ec-181">Sõltuvalt kliendiandmete mahust võib rikastamise käitamise lõpuleviimiseks kuluda mitu minutit.</span><span class="sxs-lookup"><span data-stu-id="078ec-181">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="078ec-182">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="078ec-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="078ec-183">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="078ec-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="078ec-184">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="078ec-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="078ec-185">Kui olete valinud **Vaata detaile** ühe tööülesande kohta, leiate lisateavet: töötlemise aeg, viimane töötlemise kuupäev ning kõik ülesandega seotud vead ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="078ec-185">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="078ec-186">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="078ec-186">Enrichment results</span></span>

<span data-ttu-id="078ec-187">Pärast rikastamise protsessi käitamist, avage jaotis **Minu rikastamised**, et vaadata üle rikastatud klientide koguarv ja kaubamärkide või huvide jagunemine rikastatud kliendiprofiilides.</span><span class="sxs-lookup"><span data-stu-id="078ec-187">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Tulemuste eelvaade pärast rikastamise protsessi käitamist":::

<span data-ttu-id="078ec-189">Rikastatud andmete ülevaatamiseks valige diagrammilt **Rikastatud andmete vaatamine**.</span><span class="sxs-lookup"><span data-stu-id="078ec-189">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="078ec-190">Brändide rikastatud andmed lähevad olemisse **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="078ec-190">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="078ec-191">Huvide andmed on olemis **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="078ec-191">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="078ec-192">Samuti leiate need olemis loetletuna rühmas **Rikastamine** suvandis **Andmed** > **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="078ec-192">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="078ec-193">Kliendi kaardi rikastamise andmete vaatamine</span><span class="sxs-lookup"><span data-stu-id="078ec-193">See enrichment data on the customer card</span></span>

<span data-ttu-id="078ec-194">Kaubamärgi ja huvide ühtivust saate vaadata ka eraldi kliendi kaartidel.</span><span class="sxs-lookup"><span data-stu-id="078ec-194">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="078ec-195">Avage **Kliendid** ja valige kliendiprofiil.</span><span class="sxs-lookup"><span data-stu-id="078ec-195">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="078ec-196">Kliendi kaardilt leiate diagrammid tootemarkide või huvide kohta, mille suhtes on külgetõmme selle kliendi demograafilise profiili inimestel.</span><span class="sxs-lookup"><span data-stu-id="078ec-196">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Kliendi kaart rikastatud andmetega":::

## <a name="next-steps"></a><span data-ttu-id="078ec-198">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="078ec-198">Next steps</span></span>

<span data-ttu-id="078ec-199">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="078ec-199">Build on top of your enriched customer data.</span></span> <span data-ttu-id="078ec-200">Looge [Segmendid](segments.md) ja [Näitajaid](measures.md) ning isegi [eksportige andmed](export-destinations.md), et pakkuda oma klientidele isikupärastatud kogemust.</span><span class="sxs-lookup"><span data-stu-id="078ec-200">Create [Segments](segments.md) and [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
