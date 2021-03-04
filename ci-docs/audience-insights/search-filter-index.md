---
title: Kliendiprofiilide otsimine ja filtreerimine
description: Leidke kiiresti teavet ühtsete klientide profiilide kohta ja filtreerige määratud atribuute.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270061"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="c9ef8-103">Kliendiprofiilid: otsing ja filtri register</span><span class="sxs-lookup"><span data-stu-id="c9ef8-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="c9ef8-104">Kliendiandmete ühtlustamise tulemusena tekib kliendiprofiili olem, mis pakub kogu kliendibaasi ühtset vaadet.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="c9ef8-105">[Kindla kliendi või klientide rühma teabe](customer-profiles.md) kiireks leidmiseks saate seadistada lehe **Kliendid** võimalused **Otsi** ja **Filtreeri**.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="c9ef8-106">Lugege edasi, et õppida, kuidas administraatorid saavad muuta lehe **Otsing ja filtri register** atribuute, millega kasutajad saavad otsida ja filtreerida.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c9ef8-107">![Otsingufilter](media/search-filter.png "Otsingufilter")</span><span class="sxs-lookup"><span data-stu-id="c9ef8-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="c9ef8-108">Lisage välju ja määrake atribuute</span><span class="sxs-lookup"><span data-stu-id="c9ef8-108">Add fields and specify attributes</span></span>

<span data-ttu-id="c9ef8-109">Kui määratlete otsitavaid atribuute administraatorina esimest korda, peate esmalt määratlema indekseeritud välju.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="c9ef8-110">Soovitame valida kõik atribuudid, millega kasutajad saavad kliente otsida ja filtreerida lehel **Kliendid**.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="c9ef8-111">Saate määrata vaid kliendiprofiili olemi atribuute, mida lõite andmete ühendamisel.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="c9ef8-112">Avage leht **Kliendid** ja valige **Otsingu ja filtri register**.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="c9ef8-113">Valige **+ Lisa** indekseeritud väljade määramiseks.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="c9ef8-114">Valige loendist indekseeritud väljadena lisatavad atribuudid.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="c9ef8-115">Saate alati lisada rohkem atribuute, valides **Lisa**.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="c9ef8-116">Saate eemaldada kõiki valitud atribuute, kui valite sümboli **Eemalda**.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="c9ef8-117">Uudistage indekseeritud kliendiväljade tabelit</span><span class="sxs-lookup"><span data-stu-id="c9ef8-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="c9ef8-118">Järgmine teave asub tabelis.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="c9ef8-119">**Nimi**: tähistab atribuudi nime kliendiprofiili olemis.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="c9ef8-120">**Andmetüüp**: määrab, kas andmetüüp on string, arv või kuupäev.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="c9ef8-121">**Kaasatud otsingusse**: määrab, kas selle atribuudiga saab otsida kliente lehel **Kliendid** välja **Otsing** abil.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="c9ef8-122">**Lisa filter** juhtelement, millega määratletakse atribuudi kasutamist lehel **Kliendid** filtreerimiseks.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="c9ef8-123">Kindla atribuudi filtreerimisvalikute muutmine</span><span class="sxs-lookup"><span data-stu-id="c9ef8-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="c9ef8-124">Lehel **Kliendid** asuva **Filter** menüü võib sisaldada erinevas koguses atribuutide tasemeid (nt erinevate vanuserühmade puhul filtreeritakse kliente järgmiselt).</span><span class="sxs-lookup"><span data-stu-id="c9ef8-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="c9ef8-125">Valige lehel **Otsing ja registri filtreerimine** kindla atribuudi puhul **Lisa filter**.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="c9ef8-126">Saate määratleda tulemuste arvu ja nende järjestust.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="c9ef8-127">Olenevalt atribuudi andmetüübist ilmub üks järgmistest paanidest.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="c9ef8-128">Stringi tüüpi atribuudid: täpsustage paanil **Stringi filtreerimissuvandid** soovitud tulemuste arvu ja nende järjestusreegleid.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="c9ef8-129">Numbrilist tüüpi atribuudid: täpsustage paanil **Numbrilised filtreerimissuvandid** hõlmatud intervallid ja nende järjestusreegleid.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="c9ef8-130">Kuupäeva tüüpi atribuudid: täpsustage paanil **Kuupäevafiltri suvandid** hõlmatud intervallid ja nende järjestusreegleid.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="c9ef8-131">Vajutage nuppu **Salvesta**, et muudatused rakendada.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="c9ef8-132">Valige **Käivita**, kui olete valmis seadete rakendamiseks.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c9ef8-133">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="c9ef8-133">Next steps</span></span>

<span data-ttu-id="c9ef8-134">Kliendiprofiilide otsimiseks või indekseeritud väljade kasutamiseks minge lehele **Kliendid**, et näha kõigi kliendiprofiilide alamhulka.</span><span class="sxs-lookup"><span data-stu-id="c9ef8-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]