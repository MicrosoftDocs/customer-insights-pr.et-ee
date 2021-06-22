---
title: Kliendi eluea väärtuse prognoosi näidisjuhend
description: Selle näidisjuhendi abil saate proovida kliendi eluaja väärtuse prognoosi mudelit.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129940"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="a7896-103">Kliendi eluea väärtuse (CLV) prognoosi näidisjuhend</span><span class="sxs-lookup"><span data-stu-id="a7896-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="a7896-104">Selles juhendis selgitatakse teile lõppnäidet kliendi eluea väärtuse (CLV) prognoosi kohta teenuses Customer Insights näidisandmete abil.</span><span class="sxs-lookup"><span data-stu-id="a7896-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="a7896-105">Stsenaarium</span><span class="sxs-lookup"><span data-stu-id="a7896-105">Scenario</span></span>

<span data-ttu-id="a7896-106">Contoso on ettevõte, mis toodab kvaliteetseid kohvi- ja kohvimasinaid.</span><span class="sxs-lookup"><span data-stu-id="a7896-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="a7896-107">Nad müüvad tooteid oma Contoso Coffee veebisaidil.</span><span class="sxs-lookup"><span data-stu-id="a7896-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="a7896-108">Ettevõte soovib mõista väärtust (tulu), mida nende kliendid saavad järgmise 12 kuu jooksul teenida.</span><span class="sxs-lookup"><span data-stu-id="a7896-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="a7896-109">Teades oma klientide eeldatavat väärtust järgmise 12 kuu jooksul, aitab see neil juhtida oma turundustegevust kõrge väärtusega klientidele.</span><span class="sxs-lookup"><span data-stu-id="a7896-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a7896-110">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="a7896-110">Prerequisites</span></span>

- <span data-ttu-id="a7896-111">Vähemalt [kaasautori õigused](permissions.md) sihtrühma ülevaates.</span><span class="sxs-lookup"><span data-stu-id="a7896-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="a7896-112">Soovitame teil järgmisi samme rakendada [uues keskkonnas](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="a7896-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="a7896-113">Ülesanne 1 – andmete valmendamine</span><span class="sxs-lookup"><span data-stu-id="a7896-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="a7896-114">Vaadake üle artiklid [andmete rakendamise](data-sources.md) ja [andmeallikate importimise kohta Power Query konnektorite](connect-power-query.md) abil.</span><span class="sxs-lookup"><span data-stu-id="a7896-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="a7896-115">Järgmises teabes eeldatakse, et olete andmete valmendamisega üldiselt tuttav.</span><span class="sxs-lookup"><span data-stu-id="a7896-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="a7896-116">E-kaubanduse platvormist pärit kliendiandmete valmendamine</span><span class="sxs-lookup"><span data-stu-id="a7896-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="a7896-117">Looge andmeallikas nimega **eCommerce**, valige importimise suvand ja valige konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a7896-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a7896-118">Sisestage eCommerce kontaktide URL [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="a7896-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="a7896-119">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="a7896-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a7896-120">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="a7896-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="a7896-121">**DateOfBirth**: kuupäev</span><span class="sxs-lookup"><span data-stu-id="a7896-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="a7896-122">**CreatedOn**: kuupäev/kellaaeg/ajatsoon</span><span class="sxs-lookup"><span data-stu-id="a7896-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Sünniaja teisendamine kuupäevaks.":::

1. <span data-ttu-id="a7896-124">Muutke parempoolsel paanil väljal „Nimi“ oma andmeallika praegune nimi **Päring** nimeks **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="a7896-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="a7896-125">**Salvestage** andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="a7896-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="a7896-126">Internetiostude andmete valmendamine</span><span class="sxs-lookup"><span data-stu-id="a7896-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="a7896-127">Lisage samasse andmeallikasse **eCommerce** veel üks andmekogum.</span><span class="sxs-lookup"><span data-stu-id="a7896-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="a7896-128">Valige uuesti konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a7896-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="a7896-129">Sisestage **internetiostude** andmete URL https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="a7896-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="a7896-130">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="a7896-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a7896-131">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="a7896-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="a7896-132">**PurchasedOn**: kuupäev/kellaaeg</span><span class="sxs-lookup"><span data-stu-id="a7896-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="a7896-133">**TotalPrice**: valuuta</span><span class="sxs-lookup"><span data-stu-id="a7896-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="a7896-134">Muutke küljepaanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="a7896-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="a7896-135">**Salvestage** andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="a7896-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="a7896-136">Kliendiandmete valmendamine lojaalsusskeemi kaudu</span><span class="sxs-lookup"><span data-stu-id="a7896-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="a7896-137">Looge andmeallikas nimega **LoyaltyScheme**, valige importimise suvand ja valige konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a7896-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a7896-138">Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="a7896-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="a7896-139">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="a7896-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a7896-140">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="a7896-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="a7896-141">**DateOfBirth**: kuupäev</span><span class="sxs-lookup"><span data-stu-id="a7896-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="a7896-142">**RewardsPoints**: täisarv</span><span class="sxs-lookup"><span data-stu-id="a7896-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="a7896-143">**CreatedOn**: kuupäev/kellaaeg</span><span class="sxs-lookup"><span data-stu-id="a7896-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="a7896-144">Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a7896-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="a7896-145">**Salvestage** andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="a7896-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="a7896-146">Kliendiandmete valmendamine veebisaidiarvustustest</span><span class="sxs-lookup"><span data-stu-id="a7896-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="a7896-147">Looge andmeallikas nimega **Veebisait**, valige importimise suvand ja valige konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a7896-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a7896-148">Sisestage e-kaubanduse kontaktide URL https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="a7896-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="a7896-149">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="a7896-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a7896-150">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="a7896-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="a7896-151">**ReviewRating**: kümnendarv</span><span class="sxs-lookup"><span data-stu-id="a7896-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="a7896-152">**ReviewDate**: kuupäev</span><span class="sxs-lookup"><span data-stu-id="a7896-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="a7896-153">Nimetage parempoolse paani väljal 'Nimi' oma andmeallikas ümber **päringust** **arvustusteks**.</span><span class="sxs-lookup"><span data-stu-id="a7896-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="a7896-154">**Salvestage** andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="a7896-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="a7896-155">Ülesanne 2 – andmete koondamine</span><span class="sxs-lookup"><span data-stu-id="a7896-155">Task 2 - Data unification</span></span>

<span data-ttu-id="a7896-156">Pärast andmete sisestamist alustame andmete ühendamise protsessi, et luua ühtne kliendiprofiil.</span><span class="sxs-lookup"><span data-stu-id="a7896-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="a7896-157">Lisateavet leiate teemast [Andmete koondamine](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="a7896-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="a7896-158">Vastendus</span><span class="sxs-lookup"><span data-stu-id="a7896-158">Map</span></span>

1. <span data-ttu-id="a7896-159">Pärast andmete valmendamist vastendage e-kaubanduse ja lojaalsusandmete kontaktid harilike andmetüüpidega.</span><span class="sxs-lookup"><span data-stu-id="a7896-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="a7896-160">Liikuge **Andmed** > **Koondamine** > **Vastendamine**.</span><span class="sxs-lookup"><span data-stu-id="a7896-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="a7896-161">Valige olemid, mis esindavad kliendiprofiili: **eCommerceContacts** ja **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a7896-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="a7896-162">Seejärel valige **Rakenda**.</span><span class="sxs-lookup"><span data-stu-id="a7896-162">Then, select **Apply**.</span></span>

   ![E-kaubanduse ja lojaalsuse andmeallikad vahekaardil „Koondamine“.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="a7896-164">Valige andmeallika **eCommerceContacts** peamiseks võtmeks **ContactId** ja andmeallika **loyCustomers** peamiseks võtmeks **LoyaltyID**.</span><span class="sxs-lookup"><span data-stu-id="a7896-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![LoyaltyId peamise võtmena vahekaardil „Koondamine“.](media/unify-loyaltyid.png)

1. <span data-ttu-id="a7896-166">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="a7896-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="a7896-167">Vastenda</span><span class="sxs-lookup"><span data-stu-id="a7896-167">Match</span></span>

1. <span data-ttu-id="a7896-168">Liikuge vahekaardile **Vastavusseviimine** ja valige **Määra järjekord**.</span><span class="sxs-lookup"><span data-stu-id="a7896-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="a7896-169">Valige ripploendis **Peamine** peamiseks andmeallikaks **eCommerceContacts: eCommerce** ja kaasake kõik kirjed.</span><span class="sxs-lookup"><span data-stu-id="a7896-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="a7896-170">Valige ripploendist **Olem 2** **loyCustomers: LoyaltyScheme** ja kaasake kõik kirjed.</span><span class="sxs-lookup"><span data-stu-id="a7896-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![E-kaubanduse ja lojaalsuse vastavusseviimine vahekaardil „Koondamine“.](media/unify-match-order.png)

1. <span data-ttu-id="a7896-172">Valige **Lisa reegel**</span><span class="sxs-lookup"><span data-stu-id="a7896-172">Select **Add rule**</span></span>

1. <span data-ttu-id="a7896-173">Lisage esimene tingimus suvandi FullName abil.</span><span class="sxs-lookup"><span data-stu-id="a7896-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="a7896-174">Valige andmeallika eCommerceContacts jaoks ripploendist **FullName**.</span><span class="sxs-lookup"><span data-stu-id="a7896-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="a7896-175">Valige andmeallika loyCustomers jaoks ripploendist **FullName**.</span><span class="sxs-lookup"><span data-stu-id="a7896-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="a7896-176">Valige ripploend **Normaliseerimine** ja valige **Tüüp (telefon, nimi, aadress, ...)**.</span><span class="sxs-lookup"><span data-stu-id="a7896-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="a7896-177">Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.</span><span class="sxs-lookup"><span data-stu-id="a7896-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="a7896-178">Sisestage uuele reeglile nimi **FullName, Email**.</span><span class="sxs-lookup"><span data-stu-id="a7896-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="a7896-179">Lisage meiliaadressi jaoks teine tingimus, valides suvandi **Lisa tingimus**</span><span class="sxs-lookup"><span data-stu-id="a7896-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="a7896-180">Valige olemi eCommerceContacts jaoks ripploendist **Meil**.</span><span class="sxs-lookup"><span data-stu-id="a7896-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="a7896-181">Valige olemi loyCustomers jaoks ripploendist **Meil**.</span><span class="sxs-lookup"><span data-stu-id="a7896-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="a7896-182">Jätke suvand „Normaliseerimine“ tühjaks.</span><span class="sxs-lookup"><span data-stu-id="a7896-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="a7896-183">Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.</span><span class="sxs-lookup"><span data-stu-id="a7896-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Reegli vastavusseviimine nime ja meili korral vahekaardil „Koondamine“.](media/unify-match-rule.png)

1. <span data-ttu-id="a7896-185">Valige nupp **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="a7896-185">Select **Done**.</span></span>

1. <span data-ttu-id="a7896-186">Valige **Salvesta** ja **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="a7896-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="a7896-187">Ühendamine</span><span class="sxs-lookup"><span data-stu-id="a7896-187">Merge</span></span>

1. <span data-ttu-id="a7896-188">Avage vahekaart **Ühendamine**.</span><span class="sxs-lookup"><span data-stu-id="a7896-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="a7896-189">Määrake olemi **loyCustomers** üksuse **ContactId** kuvatavaks nimeks **ContactIdLOYALTY**, et eristada seda muudest valmendatud ID-dest.</span><span class="sxs-lookup"><span data-stu-id="a7896-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![contactid nime vahetamine lojaalsuse ID-s.](media/unify-merge-contactid.png)

1. <span data-ttu-id="a7896-191">Valige **Salvesta** ja **Käivita liitmine ja allavooluprotsessid**.</span><span class="sxs-lookup"><span data-stu-id="a7896-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="a7896-192">3. ülesanne – kliendi eluea prognoosi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="a7896-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="a7896-193">Kui ühendatud kliendiprofiilid on paigas, saame nüüd käivitada kliendi eluea väärtuse prognoosi.</span><span class="sxs-lookup"><span data-stu-id="a7896-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="a7896-194">Üksikasjalikud juhised leiate teemast [Kliendi eluea väärtuse prognoos (eelvaade)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="a7896-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="a7896-195">Minge loendisse **Intelligents**  > **Prognoosid** ja valige **Kliendi eluea väärtuse mudel**.</span><span class="sxs-lookup"><span data-stu-id="a7896-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="a7896-196">Avage külgpaanil soovitud teave ja valige **Alustamine**.</span><span class="sxs-lookup"><span data-stu-id="a7896-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="a7896-197">Pange mudeli nimeks **OOB eCommerce CLV prognoos** ja väljundolemi nimeks **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="a7896-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="a7896-198">Määratlege CLV mudeli eelistused.</span><span class="sxs-lookup"><span data-stu-id="a7896-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="a7896-199">**Prognoosi ajavahemik**: **12 kuud või 1 aasta**.</span><span class="sxs-lookup"><span data-stu-id="a7896-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="a7896-200">Selle sättega määratletakse, kui palju tulevikku prognoositakse kliendi eluea väärtus.</span><span class="sxs-lookup"><span data-stu-id="a7896-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="a7896-201">**Aktiivsed kliendid**: määrake, mida aktiivsed kliendid teie ettevõtte jaoks tähendab.</span><span class="sxs-lookup"><span data-stu-id="a7896-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="a7896-202">Saate määrata ajaloolise ajaraami, mille jooksul peab kliendil olema olnud vähemalt üks tehing, mida tuleb aktiivseks lugeda.</span><span class="sxs-lookup"><span data-stu-id="a7896-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="a7896-203">Mudel prognoosib, ainult aktiivsete klientide CLV-d.</span><span class="sxs-lookup"><span data-stu-id="a7896-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="a7896-204">Valige kuupäevade vahemik, kas mudel arvutab ajaperioodi varasemate kannete andmete põhjal või tagab kindla ajavahemiku.</span><span class="sxs-lookup"><span data-stu-id="a7896-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="a7896-205">Selles näidisjuhendis **lubame mudelil arvutada ostuintervalli**, mis on vaikesuvand.</span><span class="sxs-lookup"><span data-stu-id="a7896-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="a7896-206">**Kõrge väärtusega kliendid**: määratlege kõrge väärtusega kliendid protsentuaalselt kõige paremini tasuvatest klientidest.</span><span class="sxs-lookup"><span data-stu-id="a7896-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="a7896-207">Mudelis kasutatakse seda sisendit, et pakkuda tulemusi, mis vastaksid teie kõrge väärtusega klientide ärimääratlusele.</span><span class="sxs-lookup"><span data-stu-id="a7896-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="a7896-208">Võite lasta mudelil määratleda kõrge väärtusega kliente.</span><span class="sxs-lookup"><span data-stu-id="a7896-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="a7896-209">See kasutab heuristilist reeglit, mis tuletab protsentiili.</span><span class="sxs-lookup"><span data-stu-id="a7896-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="a7896-210">Saate määratleda ka kõrge väärtusega kliendid tulevaste maksvate klientide protsentiilina.</span><span class="sxs-lookup"><span data-stu-id="a7896-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="a7896-211">Selles näidisjuhendis määratleme kõrge väärtusega kliendid käsitsi **30% aktiivseimaks ostuklientideks** ja valime suvandi **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="a7896-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Eelistused, etapp CLV mudeli juhendatud kogemuses.":::

1. <span data-ttu-id="a7896-213">Tehinguajaloo andmete lisamiseks valige **nõutavate andmete** sammus **Lisa andmed**.</span><span class="sxs-lookup"><span data-stu-id="a7896-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="a7896-214">Lisage olem **eCommercePurkirjeses: eCommerce** ja vastendage mudeli puhul nõutavad atribuudid.</span><span class="sxs-lookup"><span data-stu-id="a7896-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="a7896-215">Tehingu ID: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="a7896-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="a7896-216">Tehingu kuupäev: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="a7896-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="a7896-217">Tehingu summa: eCommerce.eCommercePursseses.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="a7896-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="a7896-218">Toote ID: eCommerce.eCommercePurtooteses.ProductId</span><span class="sxs-lookup"><span data-stu-id="a7896-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="a7896-219">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="a7896-219">Select **Next**.</span></span>

1. <span data-ttu-id="a7896-220">Saate seadistada seose olemi **eCommercePursseses: eCommerce** ja **eCommerceContacts: eCommerce** vahel.</span><span class="sxs-lookup"><span data-stu-id="a7896-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="a7896-221">**Täiendavate andmete (valikuline)** sammuga saate lisada rohkem klienditegevuse andmeid.</span><span class="sxs-lookup"><span data-stu-id="a7896-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="a7896-222">Need andmed võivad aidata saada rohkem ülevaateid kliendi ja teie ettevõtte vahelisest suhtlusest, mis võib aidata kaasa CLV-le.</span><span class="sxs-lookup"><span data-stu-id="a7896-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="a7896-223">Klientide peamiste suhtluste, nt veebilogide, klienditeenindus logide või autasude programmiajaloo lisamine võib parandada prognooside täpsust.</span><span class="sxs-lookup"><span data-stu-id="a7896-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="a7896-224">Kui soovite kaasata rohkem klienditegevuseandmeid, valige **Lisa andmed**.</span><span class="sxs-lookup"><span data-stu-id="a7896-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="a7896-225">Lisage klienditegevuse olem ja vastendage selle väljade nimed mudelis nõutavatele väljadele.</span><span class="sxs-lookup"><span data-stu-id="a7896-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="a7896-226">Klienditegevuse olem: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="a7896-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="a7896-227">Esmane võti: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="a7896-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="a7896-228">Ajatempel: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="a7896-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="a7896-229">Sündmus (tegevuse nimi): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="a7896-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="a7896-230">Üksikasjad (summa või väärtus): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="a7896-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="a7896-231">Valige **Edasi** ja konfigureerige tegevus ning kannete ja kliendiandmete vaheline seos.</span><span class="sxs-lookup"><span data-stu-id="a7896-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="a7896-232">Tegevuse tüüp: valige olemasolev</span><span class="sxs-lookup"><span data-stu-id="a7896-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="a7896-233">Tegevuse silt: ülevaade</span><span class="sxs-lookup"><span data-stu-id="a7896-233">Activity label: Review</span></span>
   - <span data-ttu-id="a7896-234">Vastav silt: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="a7896-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="a7896-235">Kliendi olem: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="a7896-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="a7896-236">Seos: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="a7896-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="a7896-237">Valige **Järgmine**, et määratleda mudeli ajakava.</span><span class="sxs-lookup"><span data-stu-id="a7896-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="a7896-238">Mudel peab uute mustrite õppimiseks regulaarselt treenima, kui uusi andmeid sisestatakse.</span><span class="sxs-lookup"><span data-stu-id="a7896-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="a7896-239">Selle näite puhul valige **Igakuine**.</span><span class="sxs-lookup"><span data-stu-id="a7896-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="a7896-240">Pärast kõigi üksikasjade läbivaatamist valige **Salvesta ja käivita**.</span><span class="sxs-lookup"><span data-stu-id="a7896-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="a7896-241">Ülesanne 4 – mudeli tulemuste ja selgituste läbivaatamine</span><span class="sxs-lookup"><span data-stu-id="a7896-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="a7896-242">Laske mudelil treenimine ja andmete hindamine lõpule viia.</span><span class="sxs-lookup"><span data-stu-id="a7896-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="a7896-243">Järgmiseks saate vaadata CLV mudeli tulemusi ja selgitusi.</span><span class="sxs-lookup"><span data-stu-id="a7896-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="a7896-244">Lisateavet leiate teemast [Prognoos oleku ja tulemuste läbivaatamine](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="a7896-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="a7896-245">5. ülesanne – suure väärtusega klientide segmendi loomine</span><span class="sxs-lookup"><span data-stu-id="a7896-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="a7896-246">Mudeli käivitamine loob uue olemi, mis on loetletud asukohas **Andmed** > **Olemid** loendis.</span><span class="sxs-lookup"><span data-stu-id="a7896-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="a7896-247">Saate luua mudeli loodud olemi põhjal uue kliendisegmendi.</span><span class="sxs-lookup"><span data-stu-id="a7896-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="a7896-248">Liikuge jaotisse **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="a7896-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="a7896-249">Valige **Uus** ja seejärel **Loo üksusest** > **Ärianalüüs**.</span><span class="sxs-lookup"><span data-stu-id="a7896-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Segmendi loomine mudeli väljundiga.](media/segment-intelligence.png)

1. <span data-ttu-id="a7896-251">Valige olem **OOBeCommerceCLVPrediction** ja määratlege segment.</span><span class="sxs-lookup"><span data-stu-id="a7896-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="a7896-252">Väli: CLVScore</span><span class="sxs-lookup"><span data-stu-id="a7896-252">Field: CLVScore</span></span>
  - <span data-ttu-id="a7896-253">Tehtemärk: suurem kui</span><span class="sxs-lookup"><span data-stu-id="a7896-253">Operator: greater than</span></span>
  - <span data-ttu-id="a7896-254">Väärtus: 1500</span><span class="sxs-lookup"><span data-stu-id="a7896-254">Value: 1500</span></span>

1. <span data-ttu-id="a7896-255">Valige **Ülevaade** ja **salvestage** segment.</span><span class="sxs-lookup"><span data-stu-id="a7896-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="a7896-256">Teil on nüüd segment, mis tuvastab kliendid, kes prognooside kohaselt teenivad järgmise 12 kuu jooksul rohkem kui 1500 dollarit tulu.</span><span class="sxs-lookup"><span data-stu-id="a7896-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="a7896-257">Kui kasutatakse rohkem andmeid, värskendatakse see segment dünaamiliselt.</span><span class="sxs-lookup"><span data-stu-id="a7896-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="a7896-258">Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a7896-258">For more information, see [Create and manage segments](segments.md).</span></span>
