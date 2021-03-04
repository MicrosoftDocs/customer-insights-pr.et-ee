---
title: Olemite vastendamine andmete koondamiseks
description: Vastendage andmed, et luua koondatud kliendiprofiile.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 0088daae0be0cb3e71f87387648430d2353081c9
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267030"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="832f2-103">Olemite ja atribuutide kaardistamine</span><span class="sxs-lookup"><span data-stu-id="832f2-103">Map entities and attributes</span></span>

<span data-ttu-id="832f2-104">**Vastendamine** on sihtrühmaülevaadetes andmete koondamise protsessi esimene etapp.</span><span class="sxs-lookup"><span data-stu-id="832f2-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="832f2-105">Vastendamine koosneb kolmest etapist.</span><span class="sxs-lookup"><span data-stu-id="832f2-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="832f2-106">*Olemi valik*: tuvastage ühendatavad olemid, mis suunavad andmekogumile, mis sisaldab teie klientide kohta täpsemat teavet.</span><span class="sxs-lookup"><span data-stu-id="832f2-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="832f2-107">*Atribuudi valimine*: määrake iga olemi puhul veerud, mida soovite kombineerida ja sobitada etappides *vastendamine* ja *liitmine*.</span><span class="sxs-lookup"><span data-stu-id="832f2-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="832f2-108">Neid veerge nimetatakse *atribuutideks*.</span><span class="sxs-lookup"><span data-stu-id="832f2-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="832f2-109">*Primaarvõtme ja semantilise tüübi valik*: tuvastage iga olemi jaoks atribuut, mille soovite määrata selle olemi jaoks primaarvõtmena, ja iga atribuudi jaoks määratlege semantiline tüüp, mis kirjeldab seda atribuuti kõige paremini.</span><span class="sxs-lookup"><span data-stu-id="832f2-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="832f2-110">Lisateavet andmete ühendamise üldvoo kohta vt [Ühenda](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="832f2-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="832f2-111">Valige esimesed olemid</span><span class="sxs-lookup"><span data-stu-id="832f2-111">Select the first entities</span></span>

1. <span data-ttu-id="832f2-112">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Koondamine** > **Vastendamine**.</span><span class="sxs-lookup"><span data-stu-id="832f2-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="832f2-113">Kaardistamise etapi käivitamiseks valige **Vali olemid**.</span><span class="sxs-lookup"><span data-stu-id="832f2-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="832f2-114">Valige olemid ja atribuudid, mida soovite etappides *vastendamine* ja *ühendamine* kasutada.</span><span class="sxs-lookup"><span data-stu-id="832f2-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="832f2-115">Saate valida vajalikud atribuudid olemis individuaalselt või lisada olemist kõik atribuudid, valides olemi tasandil märkeruudu **Kaasa kõik väljas**.</span><span class="sxs-lookup"><span data-stu-id="832f2-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="832f2-116">Andmete ühendamisest kasu saamiseks soovitame valida vähemalt kaks olemit.</span><span class="sxs-lookup"><span data-stu-id="832f2-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="832f2-117">![Lisa olemite näide](media/data-manager-configure-map-add-entities-example.png "Lisa olemite näide")</span><span class="sxs-lookup"><span data-stu-id="832f2-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="832f2-118">Selles näites lisame olemid **eCommerceContacts** ja **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="832f2-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="832f2-119">Nende olemite valimisel saate tuletada ülevaateid, kus veebikliendid on püsikliendiprogrammi liikmed.</span><span class="sxs-lookup"><span data-stu-id="832f2-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="832f2-120">Saate otsida atribuutide ja olemite üleselt märksõnu, et valida vajalikud atribuudid, mida soovite vastendada.</span><span class="sxs-lookup"><span data-stu-id="832f2-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="832f2-121">![Otsinguväljade näide](media/data-manager-configure-map-search-fields-example.png "Otsinguväljade näide")</span><span class="sxs-lookup"><span data-stu-id="832f2-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="832f2-122">Oma valikute kinnitamiseks valige suvand **Rakenda**.</span><span class="sxs-lookup"><span data-stu-id="832f2-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="832f2-123">Atribuutide primaarvõtme ja semantilise tüübi valimine</span><span class="sxs-lookup"><span data-stu-id="832f2-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="832f2-124">Pärast oma olemite valimist loetleb leht **Kaardistamine** läbivaatamiseks valitud olemid.</span><span class="sxs-lookup"><span data-stu-id="832f2-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="832f2-125">Määratlege olemi primaarvõti ja määratlege olemi atribuudi semantiline tüüp.</span><span class="sxs-lookup"><span data-stu-id="832f2-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="832f2-126">**Primaarvõti**: valige iga olemi primaarvõtmeks üks atribuut.</span><span class="sxs-lookup"><span data-stu-id="832f2-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="832f2-127">Et atribuut saaks olla sobiv primaarvõti, ei tohi see sisaldada topeltväärtusi, puuduvaid väärtusi ega null-väärtusi.</span><span class="sxs-lookup"><span data-stu-id="832f2-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="832f2-128">Stringi, täisarvu ja GUID-i andmetüübi atribuute toetatakse primaarvõtmetena ja need kuvatakse väljal, kust saate need valida.</span><span class="sxs-lookup"><span data-stu-id="832f2-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="832f2-129">**Atribuudi semantiline tüüp**: atribuutide kategooriad (nt e-posti aadress või nimi).</span><span class="sxs-lookup"><span data-stu-id="832f2-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="832f2-130">Selleks et kasutada AI mudeleid semantika nutikaks prognoosiks, säästa aega ja parandada täpsust, määrake suvandi **Intelligentne vastendamine** olekuks **SEES**.</span><span class="sxs-lookup"><span data-stu-id="832f2-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="832f2-131">Intelligentne vastendamine tõstab esile AI-põhise semantika soovituse väljal **Tüüp**.</span><span class="sxs-lookup"><span data-stu-id="832f2-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="832f2-132">Kui määrate selle olekuks **VÄLJAS**, näete meie tavalisi vastendamise soovitusi.</span><span class="sxs-lookup"><span data-stu-id="832f2-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="832f2-133">Saate valida saadaolevate suvandite loendist mis tahes semantilise tüübi ja tühistada soovitatud valiku.</span><span class="sxs-lookup"><span data-stu-id="832f2-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="832f2-134">![Atribuudi tüüp ja semantiline prognoos](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Atribuudi tüüp ja semantiline prognoos")</span><span class="sxs-lookup"><span data-stu-id="832f2-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="832f2-135">Samuti on võimalik lisada enda loodud semantiline tüüp.</span><span class="sxs-lookup"><span data-stu-id="832f2-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="832f2-136">Valige atribuudi tüübi väärtus ja sisestage enda muudetud semantilise tüübi nimi.</span><span class="sxs-lookup"><span data-stu-id="832f2-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="832f2-137">Nii saate muuta ka süsteemi tuvastatud atribuudi tüüpe.</span><span class="sxs-lookup"><span data-stu-id="832f2-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="832f2-138">Kõik atribuudid, mille semantiline tüüp tuvastatakse automaatselt, on rühmitatud jaotises **Vastendatud väljade läbivaatamine**.</span><span class="sxs-lookup"><span data-stu-id="832f2-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="832f2-139">Vaadake need atribuudid ja nende semantilised tüübid läbi, kuna neid kasutatakse teie olemite kombineerimiseks andmete ühendamise ühendamise etapis.</span><span class="sxs-lookup"><span data-stu-id="832f2-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="832f2-140">Atribuudid, mida semantilise tüübiga automaatselt ei vastendata, on rühmitatud jaotises **Vastendamata väljade andmete määratlemine**.</span><span class="sxs-lookup"><span data-stu-id="832f2-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="832f2-141">Valige vastendamata atribuutide jaoks välja semantiline tüüp või sisestage kohandatud atribuudi tüübi nimi.</span><span class="sxs-lookup"><span data-stu-id="832f2-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="832f2-142">![Primaarvõti ja atribuudi tüüp](media/data-manager-configure-map-add-attributes.png "Primaarvõti ja atribuudi tüüp")</span><span class="sxs-lookup"><span data-stu-id="832f2-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="832f2-143">Üks väli peaks olema vastendatud semantilise tüübiga Person.FullName, et lisada kliendi kaardile kliendi nimi.</span><span class="sxs-lookup"><span data-stu-id="832f2-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="832f2-144">Vastasel juhul kuvatakse kliendikaardid ilma nimeta.</span><span class="sxs-lookup"><span data-stu-id="832f2-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="832f2-145">Atribuutide ja olemite lisamine ja eemaldamine</span><span class="sxs-lookup"><span data-stu-id="832f2-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="832f2-146">Suvandis **Ühendamine** > **Kaardistamine** valige **Redigeeri välju**.</span><span class="sxs-lookup"><span data-stu-id="832f2-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="832f2-147">Lisage või eemaldage atribuute ja olemeid paanil **Redigeeri välju**.</span><span class="sxs-lookup"><span data-stu-id="832f2-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="832f2-148">Kasutage otsingut või kerige, et leida ja valida teile huvi pakkuvad atribuudid ja olemid.</span><span class="sxs-lookup"><span data-stu-id="832f2-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="832f2-149">Atribuuti või olemit ei saa eemaldada, kui need on juba vastendatud.</span><span class="sxs-lookup"><span data-stu-id="832f2-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="832f2-150">![Atribuutide lisamine või eemaldamine](media/configure-data-map-edit.png "Atribuutide lisamine või eemaldamine")</span><span class="sxs-lookup"><span data-stu-id="832f2-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="832f2-151">Valige suvand **Rakenda**.</span><span class="sxs-lookup"><span data-stu-id="832f2-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="832f2-152">Profiilidele pildi lisamine</span><span class="sxs-lookup"><span data-stu-id="832f2-152">Add images to profiles</span></span>

<span data-ttu-id="832f2-153">Kui olem sisaldab avalikult saadaolevate profiilipiltidele või logode URL-e, saate need ühendatud kliendiprofiilile lisada.</span><span class="sxs-lookup"><span data-stu-id="832f2-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="832f2-154">Valige olem ja otsige üles väli, mis sisaldab profiilipildi URL-i.</span><span class="sxs-lookup"><span data-stu-id="832f2-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="832f2-155">Sisestage sisendiväljale **Tüüp** käsitsi järgmine väärtus.</span><span class="sxs-lookup"><span data-stu-id="832f2-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="832f2-156">Isiku korral: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="832f2-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="832f2-157">Organisatsiooni korral: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="832f2-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="832f2-158">Jätkake ühendamise sammudega ja veenduge, et pildi URL-i sisaldav atribuut lisatakse samuti etapis [Ühendamine](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="832f2-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="832f2-159">Atribuutide määramine ettevõtetele</span><span class="sxs-lookup"><span data-stu-id="832f2-159">Set attributes for organizations</span></span>

<span data-ttu-id="832f2-160">Organisatsiooni (eelversioon) atribuudi tüüp tuleks vastendada järgmiselt: „organisatsioon.nimi“</span><span class="sxs-lookup"><span data-stu-id="832f2-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="832f2-161">![Primaarvõti ja atribuudi tüüp B2B](media/configure-data-map-edit-b2b.png "Primaarvõti ja atribuudi tüüp B2B")</span><span class="sxs-lookup"><span data-stu-id="832f2-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="832f2-162">Järgmine etapp</span><span class="sxs-lookup"><span data-stu-id="832f2-162">Next step</span></span>

<span data-ttu-id="832f2-163">Andmete ühendamisel minge lehele **Vastenda**.</span><span class="sxs-lookup"><span data-stu-id="832f2-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="832f2-164">Külastage lehte [**Vastendamine**](match-entities.md), et saada rohkem teavet selle etapi kohta.</span><span class="sxs-lookup"><span data-stu-id="832f2-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="832f2-165">Vaadake seda videot: [Alustamine: kliendi koondprofiili loomine](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="832f2-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]