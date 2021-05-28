---
title: Aadressi täiustamise rikastamine
description: Rikastage ja normaliseerige kliendiprofiilide aadressiteavet Microsofti mudelitega.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 07271d491460764f2c738e760e41c3492f2b6de9
ms.sourcegitcommit: 27f9dd837304ef9fc00f055a6e900fbf6fce1429
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/30/2021
ms.locfileid: "5965573"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="079a2-103">Kliendiprofiilide rikastamine täiustatud aadressidega</span><span class="sxs-lookup"><span data-stu-id="079a2-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="079a2-104">Teie andmetes kuvatud aadressid võivad olla struktureerimata, mittetäielikud või valed.</span><span class="sxs-lookup"><span data-stu-id="079a2-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="079a2-105">Kasutage Microsofti mudeleid aadresside normaliseerimiseks ja rikastamiseks [Common Data Model vormingusse,](/common-data-model/schema/core/applicationcommon/address) et saada paremat täpsust ja ülevaadet.</span><span class="sxs-lookup"><span data-stu-id="079a2-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="079a2-106">Kuidas me aadresse täiustame</span><span class="sxs-lookup"><span data-stu-id="079a2-106">How we enhance addresses</span></span>

<span data-ttu-id="079a2-107">Meie mudel läbib aadressi täiustamiseks kaheastmelise protsessi.</span><span class="sxs-lookup"><span data-stu-id="079a2-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="079a2-108">Esiteks sõelub see aadressi oma komponentide tuvastamiseks ja paneb need struktureeritud vormingusse.</span><span class="sxs-lookup"><span data-stu-id="079a2-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="079a2-109">Seejärel kasutame tehisintellekti aadressi väärtuste parandamiseks, täiendamiseks ja standardimiseks.</span><span class="sxs-lookup"><span data-stu-id="079a2-109">Then, we use artificial intelligence to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="079a2-110">Näide</span><span class="sxs-lookup"><span data-stu-id="079a2-110">Example</span></span>

<span data-ttu-id="079a2-111">Aadressiteave võib olla mittestandardses vormingus ja sisaldada õigekirjavigu.</span><span class="sxs-lookup"><span data-stu-id="079a2-111">Address information might be in a non-standard format and contain spelling errors.</span></span> <span data-ttu-id="079a2-112">Mudel saab need probleemid lahendada ja luua ühtsetes kliendiprofiilides järjepidevaid aadresse.</span><span class="sxs-lookup"><span data-stu-id="079a2-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="079a2-113">Piirangud</span><span class="sxs-lookup"><span data-stu-id="079a2-113">Limitations</span></span>

<span data-ttu-id="079a2-114">Täiustatud aadressid töötavad ainult väärtustega, mis on teie sissetoodud aadressiandmetes juba olemas.</span><span class="sxs-lookup"><span data-stu-id="079a2-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="079a2-115">Mudel ei ole:</span><span class="sxs-lookup"><span data-stu-id="079a2-115">The model doesn't:</span></span> 

1. <span data-ttu-id="079a2-116">Kontrollige, kas aadress on kehtiv aadress.</span><span class="sxs-lookup"><span data-stu-id="079a2-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="079a2-117">Kontrollige, kas mõni väärtustest (nt sihtnumbrid või tänavanimed) on kehtiv.</span><span class="sxs-lookup"><span data-stu-id="079a2-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="079a2-118">Muutke väärtusi, mida ta ei tunne.</span><span class="sxs-lookup"><span data-stu-id="079a2-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="079a2-119">Mudel kasutab aadresside täiustamiseks masinõppel põhinevaid tehnikaid.</span><span class="sxs-lookup"><span data-stu-id="079a2-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="079a2-120">Kuigi me rakendame kõrget usaldusläve, kui mudel muudab sisendväärtust, nagu iga ML-põhise mudeli puhul, ei ole 100% täpsus tagatud.</span><span class="sxs-lookup"><span data-stu-id="079a2-120">While we apply a high confidence threshold for when the model changes an input value, as with any ML-based model, 100% accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="079a2-121">Toetatud riikides või regioonides</span><span class="sxs-lookup"><span data-stu-id="079a2-121">Supported countries or regions</span></span>

<span data-ttu-id="079a2-122">Praegu toetame aadresside rikastamist nendes riikides või piirkondades:</span><span class="sxs-lookup"><span data-stu-id="079a2-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="079a2-123">Austraalia</span><span class="sxs-lookup"><span data-stu-id="079a2-123">Australia</span></span>
- <span data-ttu-id="079a2-124">Kanada</span><span class="sxs-lookup"><span data-stu-id="079a2-124">Canada</span></span>
- <span data-ttu-id="079a2-125">Suurbritannia</span><span class="sxs-lookup"><span data-stu-id="079a2-125">United Kingdom</span></span>
- <span data-ttu-id="079a2-126">Ameerika Ühendriigid</span><span class="sxs-lookup"><span data-stu-id="079a2-126">United States</span></span>

<span data-ttu-id="079a2-127">Aadressid peavad sisaldama riigi/regiooni väärtust.</span><span class="sxs-lookup"><span data-stu-id="079a2-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="079a2-128">Me ei töötle nende riikide või piirkondade aadresse, mida ei toetata, ja aadresse, millel pole riiki ega regiooni.</span><span class="sxs-lookup"><span data-stu-id="079a2-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="079a2-129">Rikastamise konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="079a2-129">Configure the enrichment</span></span>

1. <span data-ttu-id="079a2-130">Avage **Andmed** > **Rikastamine**.</span><span class="sxs-lookup"><span data-stu-id="079a2-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="079a2-131">Valige **Rikasta minu andmeid** paanil **Täiustatud aadressid** .</span><span class="sxs-lookup"><span data-stu-id="079a2-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Paani Täiustatud aadressid kuvatõmmis.":::

1. <span data-ttu-id="079a2-133">Valige **Kliendi andmekogum** ja klõpsake olemit, mis sisaldab aadresse, mida soovite rikastada.</span><span class="sxs-lookup"><span data-stu-id="079a2-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="079a2-134">Saate valida olemi *Klient*, et rikastada aadresse kõigis oma kliendiprofiilides, või valida segmendi olemi aadresside rikastamiseks ainult selles segmendis sisalduvates kliendiprofiilides.</span><span class="sxs-lookup"><span data-stu-id="079a2-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="079a2-135">Valige, kuidas aadresse teie andmekogumis vormindatakse.</span><span class="sxs-lookup"><span data-stu-id="079a2-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="079a2-136">Valige **Ühe atribuudi aadress** kui teie andmetes kasutatavad aadressid kasutavad ühte välja.</span><span class="sxs-lookup"><span data-stu-id="079a2-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="079a2-137">Valige **Mitme atribuudi aadress** kui teie andmetes kasutatavad aadressid rohkem kui ühte andmevälja.</span><span class="sxs-lookup"><span data-stu-id="079a2-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="079a2-138">Riik/Regioon on kohustuslik nii ühe- kui ka mitme atribuudi aadressis.</span><span class="sxs-lookup"><span data-stu-id="079a2-138">Country/Region is mandatory in both single-attribute and multiple-attribute address.</span></span> <span data-ttu-id="079a2-139">Aadresse, mis ei sisalda kehtivaid või toetatud riigi/regiooni väärtusi, ei rikastata</span><span class="sxs-lookup"><span data-stu-id="079a2-139">Addresses that don't contain valid or supported country/region values won't be enriched</span></span>

1.  <span data-ttu-id="079a2-140">Kaardistage ühendatud kliendiolemi aadressiväljad.</span><span class="sxs-lookup"><span data-stu-id="079a2-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Täiustatud aadressivälja vastendamise leht.":::

1. <span data-ttu-id="079a2-142">Valige **Edasi**, et lõpetada väljade kaardistamine.</span><span class="sxs-lookup"><span data-stu-id="079a2-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="079a2-143">Sisestage rikastamise nimi ja väljundolemi nimi.</span><span class="sxs-lookup"><span data-stu-id="079a2-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="079a2-144">Valige **Salvesta rikastamine** pärast valikute läbivaatamist.</span><span class="sxs-lookup"><span data-stu-id="079a2-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="079a2-145">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="079a2-145">Enrichment results</span></span>

<span data-ttu-id="079a2-146">Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="079a2-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="079a2-147">Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="079a2-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="079a2-148">Töötlemisaeg sõltub teie kliendiandmete mahust.</span><span class="sxs-lookup"><span data-stu-id="079a2-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="079a2-149">Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt.</span><span class="sxs-lookup"><span data-stu-id="079a2-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="079a2-150">Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="079a2-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="079a2-151">Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.</span><span class="sxs-lookup"><span data-stu-id="079a2-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="079a2-152">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="079a2-152">Next steps</span></span>

<span data-ttu-id="079a2-153">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="079a2-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="079a2-154">Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [Ekspordi andmed](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="079a2-154">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
