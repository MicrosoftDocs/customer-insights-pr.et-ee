---
title: Kliendiprofiilide vaatamine
description: Saate ühendatud ülevaate oma koondatud kliendiandmetest.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 433e6ceda0ec7827bd672cff40f895d7719561df
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896322"
---
# <a name="customer-profiles"></a><span data-ttu-id="36146-103">Kliendiprofiilid</span><span class="sxs-lookup"><span data-stu-id="36146-103">Customer profiles</span></span>

<span data-ttu-id="36146-104">Lehel **Kliendid** kuvatakse teie klientide kombineeritud vaade, mis põhineb [kõigist andmeallikatest](data-sources.md) kogutud profiiliandmetel.</span><span class="sxs-lookup"><span data-stu-id="36146-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="36146-105">Kliendiprofiilid on saadaval, kui [loote ühendatud kliendiolemi](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="36146-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="36146-106">Klientide põhjalikemate vaadete hankimiseks viige andmete ühendamine lõpuni.</span><span class="sxs-lookup"><span data-stu-id="36146-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="36146-107">Leht võimaldab otsida ka kliente.</span><span class="sxs-lookup"><span data-stu-id="36146-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="36146-108">Klientideks võivad olla eraisikud või ettevõtted (eelvaade).</span><span class="sxs-lookup"><span data-stu-id="36146-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="36146-109">Igat kliendi või ettevõtte profiili esindab pealkiri.</span><span class="sxs-lookup"><span data-stu-id="36146-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="36146-110">Kindla kliendi või ettevõtte täiendava teabe nägemiseks valige paan.</span><span class="sxs-lookup"><span data-stu-id="36146-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="36146-111">Täiendavate kirjete nägemiseks kasutage lehe allservas olevaid lehejaotuse juhtelemente.</span><span class="sxs-lookup"><span data-stu-id="36146-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="36146-112">![Jaekliendi profiilid](media/profiles-customers.png "Jaekliendi profiilid")</span><span class="sxs-lookup"><span data-stu-id="36146-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="36146-113">Ettevõtted (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="36146-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="36146-114">![Jaekliendi profiilid](media/profile-customers-b2b.png "B2B kliendi profiilid")</span><span class="sxs-lookup"><span data-stu-id="36146-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="36146-115">Kui te ei näe paane, kui valite navigeerimisel **Kliendid**, peab teie administraator [määratleda vähemalt ühe otsitava atribuudi](search-filter-index.md) jaotises **Otsing ja filtri register**.</span><span class="sxs-lookup"><span data-stu-id="36146-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="36146-116">Otsige kliente</span><span class="sxs-lookup"><span data-stu-id="36146-116">Search for customers</span></span>

<span data-ttu-id="36146-117">Klientide otsimiseks sisestage otsingukasti nimi või mingi muu atribuut.</span><span class="sxs-lookup"><span data-stu-id="36146-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="36146-118">Otsida saab vaid kliendiprofiili olemist, mille lõite andmete ühendamisel.</span><span class="sxs-lookup"><span data-stu-id="36146-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="36146-119">Administraatorina saate seadistada otsitavaid atribuute lehel **Otsing ja filtri register**.</span><span class="sxs-lookup"><span data-stu-id="36146-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="36146-120">Lisateavet leiate teemast [Otsingu ja filtri registri haldamine](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="36146-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="36146-121">Filtreerige kliente</span><span class="sxs-lookup"><span data-stu-id="36146-121">Filter customers</span></span>

<span data-ttu-id="36146-122">Filtreerige kliente kliendiprofiili olemi väljade alusel.</span><span class="sxs-lookup"><span data-stu-id="36146-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="36146-123">Sarnaselt otsingule peab administraator esmalt määrama väljad filtreeritavaks lehel **Otsing ja filtri register**.</span><span class="sxs-lookup"><span data-stu-id="36146-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="36146-124">Valige lehel **Kliendid** suvand **Filtreeri**.</span><span class="sxs-lookup"><span data-stu-id="36146-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="36146-125">Märkige atribuutide, mille alusel tahate filtreerida kliente, kõrval asuvad ruudud.</span><span class="sxs-lookup"><span data-stu-id="36146-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="36146-126">![Kliendi profiilid](media/profiles-customers3.png "Kliendi profiilid")</span><span class="sxs-lookup"><span data-stu-id="36146-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="36146-127">Eemaldage filtrid, valides lehel **Kliendid** suvand **Eemalda filtrid**.</span><span class="sxs-lookup"><span data-stu-id="36146-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="36146-128">Kliendi üksikasjade leht</span><span class="sxs-lookup"><span data-stu-id="36146-128">Customer details page</span></span>

<span data-ttu-id="36146-129">Valige mis tahes kliendipaan, et avada **Kliendi üksikasjade leht**.</span><span class="sxs-lookup"><span data-stu-id="36146-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="36146-130">See vaade sisaldab valitud kliendi koondatud teavet.</span><span class="sxs-lookup"><span data-stu-id="36146-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="36146-131">Kliendi üksikasjade hulka kuuluvad järgmised.</span><span class="sxs-lookup"><span data-stu-id="36146-131">Customer details include:</span></span>

-   <span data-ttu-id="36146-132">**Kliendiprofiili paan:** sellel paanil kuvatakse eri väärtused koondatud kliendiprofiili olemist.</span><span class="sxs-lookup"><span data-stu-id="36146-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="36146-133">Need üksikasjad võivad hõlmata meiliaadressi, nime, linna ja nii edasi.</span><span class="sxs-lookup"><span data-stu-id="36146-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="36146-134">**Potentsiaalsed huvid, potentsiaalsed kaubamärgid:** näitab, kui olete konfigureerinud esimese osapoole rikastumise.</span><span class="sxs-lookup"><span data-stu-id="36146-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="36146-135">See esindab sellise kliendi potentsiaalseid huve ja lemmikbrände, kellel on praeguse kliendi omaga sarnanev profiil.</span><span class="sxs-lookup"><span data-stu-id="36146-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="36146-136">Lisateavet vaadake teemast [Kliendiprofiilide rikastamine kaubamärgi ja huvide ühtivusega](enrichment-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="36146-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft.md).</span></span>

-   <span data-ttu-id="36146-137">**Näitajad:** kuvatakse, kui olete konfigureerinud ühe või mitu näitajat, mis on kindlat tüüpi: kliendiatribuudi näitajad.</span><span class="sxs-lookup"><span data-stu-id="36146-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="36146-138">Nende hulka kuuluvad teie klientide arvutatud KPI-sid iga kliendi tasemel.</span><span class="sxs-lookup"><span data-stu-id="36146-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="36146-139">Lisateavet leiate teemast [Näitajate määratlemine ja haldamine](measures.md).</span><span class="sxs-lookup"><span data-stu-id="36146-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="36146-140">**Tegevuse ajaskaala:** kuvatakse, kui teil on konfigureeritud tegevused.</span><span class="sxs-lookup"><span data-stu-id="36146-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="36146-141">Ajaskaala vaade sisaldab selle kliendi kronoloogiliselt sorditud tegevusi, alustades kõige hiljutisest tegevusest.</span><span class="sxs-lookup"><span data-stu-id="36146-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="36146-142">Lisateavet vt teemast [Klienditegevused](activities.md).</span><span class="sxs-lookup"><span data-stu-id="36146-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="36146-143">Valige **Tagasi klientide lehele**, et naasta kliendiotsingu lehele.</span><span class="sxs-lookup"><span data-stu-id="36146-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="36146-144">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="36146-144">Next steps</span></span>

<span data-ttu-id="36146-145">[Täiendavate andmeallikate lisamine](data-sources.md) või [kliendisegmentide loomine](segments.md).</span><span class="sxs-lookup"><span data-stu-id="36146-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]