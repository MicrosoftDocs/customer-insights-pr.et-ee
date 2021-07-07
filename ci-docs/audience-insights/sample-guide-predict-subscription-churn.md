---
title: Tellimusevoolavuse prognoosi näidisjuhend
description: Kasutage seda näidisjuhendit, et proovida kasutamiseks valmis tellimusevoolavuse prognoosi mudelit.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: fa460fa5c79bc8a356ec5e90050ec85e05c55be8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306298"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="14c0e-103">Tellimusevoolavuse prognoosi (eelversioon) näidisjuhend</span><span class="sxs-lookup"><span data-stu-id="14c0e-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="14c0e-104">Selles juhendis näidatakse teile otsast lõpuni, kuidas kasutada tellimusevoolavuse prognoosi funktsiooni koos alltoodud näidisandmetega.</span><span class="sxs-lookup"><span data-stu-id="14c0e-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="14c0e-105">Stsenaarium</span><span class="sxs-lookup"><span data-stu-id="14c0e-105">Scenario</span></span>

<span data-ttu-id="14c0e-106">Contoso on ettevõte, mis toodab kvaliteetseid kohvi- ja kohvimasinaid, mida nad müüvad oma Contoso Coffee veebisaidi kaudu.</span><span class="sxs-lookup"><span data-stu-id="14c0e-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="14c0e-107">Hiljuti hakkasid nad pakkuma kordustellimusi, et kliendid saaksid kohvi regulaarselt.</span><span class="sxs-lookup"><span data-stu-id="14c0e-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="14c0e-108">Nende eesmärk on mõista, millised tellimusega liitunud kliendid võivad järgmise paari kuu jooksul tellimuse tühistada.</span><span class="sxs-lookup"><span data-stu-id="14c0e-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="14c0e-109">Teades, millised nende kliendid **tõenäoliselt loobuvad**, aitab ettevõttel nende säilitamisele keskendudes turundusvõtteid säästa.</span><span class="sxs-lookup"><span data-stu-id="14c0e-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="14c0e-110">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="14c0e-110">Prerequisites</span></span>

- <span data-ttu-id="14c0e-111">Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.</span><span class="sxs-lookup"><span data-stu-id="14c0e-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="14c0e-112">Soovitame teil järgmisi samme rakendada [uues keskkonnas](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="14c0e-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="14c0e-113">Ülesanne 1 – andmete valmendamine</span><span class="sxs-lookup"><span data-stu-id="14c0e-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="14c0e-114">Vaadake üle artiklid [andmete valmendamise](data-sources.md) ja [Power Query konnektorite abil andmete importimise](connect-power-query.md) kohta.</span><span class="sxs-lookup"><span data-stu-id="14c0e-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="14c0e-115">Järgmises teabes eeldatakse, et olete andmete valmendamisega üldiselt tuttav.</span><span class="sxs-lookup"><span data-stu-id="14c0e-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="14c0e-116">E-kaubanduse platvormist pärit kliendiandmete valmendamine</span><span class="sxs-lookup"><span data-stu-id="14c0e-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="14c0e-117">Looge andmeallikas nimega **eCommerce**, valige importimise suvand ja valige konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="14c0e-118">Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="14c0e-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="14c0e-119">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="14c0e-120">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="14c0e-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="14c0e-121">**DateOfBirth**: kuupäev</span><span class="sxs-lookup"><span data-stu-id="14c0e-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="14c0e-122">**CreatedOn**: kuupäev/kellaaeg/ajatsoon</span><span class="sxs-lookup"><span data-stu-id="14c0e-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Sünniaja teisendamine kuupäevaks.":::

1. <span data-ttu-id="14c0e-124">Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="14c0e-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="14c0e-125">Salvestage andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="14c0e-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="14c0e-126">Kliendiandmete valmendamine lojaalsusskeemi kaudu</span><span class="sxs-lookup"><span data-stu-id="14c0e-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="14c0e-127">Looge andmeallikas nimega **LoyaltyScheme**, valige importimise suvand ja valige konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="14c0e-128">Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="14c0e-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="14c0e-129">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="14c0e-130">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="14c0e-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="14c0e-131">**DateOfBirth**: kuupäev</span><span class="sxs-lookup"><span data-stu-id="14c0e-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="14c0e-132">**RewardsPoints**: täisarv</span><span class="sxs-lookup"><span data-stu-id="14c0e-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="14c0e-133">**CreatedOn**: kuupäev/kellaaeg</span><span class="sxs-lookup"><span data-stu-id="14c0e-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="14c0e-134">Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="14c0e-135">Salvestage andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="14c0e-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="14c0e-136">Tellimuste teabe valmendamine</span><span class="sxs-lookup"><span data-stu-id="14c0e-136">Ingest subscription information</span></span>

1. <span data-ttu-id="14c0e-137">Looge andmeallikas nimega **SubscriptionHistory**, valige importimise suvand ja valige konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="14c0e-138">Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="14c0e-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="14c0e-139">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="14c0e-140">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="14c0e-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="14c0e-141">**SubscriptioID**: täisarv</span><span class="sxs-lookup"><span data-stu-id="14c0e-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="14c0e-142">**SubscriptionAmount**: valuuta</span><span class="sxs-lookup"><span data-stu-id="14c0e-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="14c0e-143">**SubscriptionEndDate**: kuupäev/kellaaeg</span><span class="sxs-lookup"><span data-stu-id="14c0e-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="14c0e-144">**SubscriptionStartDate**: kuupäev/kellaaeg</span><span class="sxs-lookup"><span data-stu-id="14c0e-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="14c0e-145">**TransactionDate**: kuupäev/kellaaeg</span><span class="sxs-lookup"><span data-stu-id="14c0e-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="14c0e-146">**IsRecurring**: tõene/väär</span><span class="sxs-lookup"><span data-stu-id="14c0e-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="14c0e-147">**Is_auto_renew**: tõene/väär</span><span class="sxs-lookup"><span data-stu-id="14c0e-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="14c0e-148">**RecurringFrequencyInMonths**: täisarv</span><span class="sxs-lookup"><span data-stu-id="14c0e-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="14c0e-149">Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="14c0e-150">Salvestage andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="14c0e-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="14c0e-151">Kliendiandmete valmendamine veebisaidiarvustustest</span><span class="sxs-lookup"><span data-stu-id="14c0e-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="14c0e-152">Looge andmeallikas nimega **Veebisait**, valige importimise suvand ja valige konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="14c0e-153">Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="14c0e-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="14c0e-154">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="14c0e-155">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="14c0e-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="14c0e-156">**ReviewRating**: täisarv</span><span class="sxs-lookup"><span data-stu-id="14c0e-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="14c0e-157">**ReviewDate**: kuupäev</span><span class="sxs-lookup"><span data-stu-id="14c0e-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="14c0e-158">Muutke parempoolsel paanil väljal „Nimi“ oma andmeallika praegune nimi **Päring** nimeks **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="14c0e-159">Ülesanne 2 – andmete koondamine</span><span class="sxs-lookup"><span data-stu-id="14c0e-159">Task 2 - Data unification</span></span>

<span data-ttu-id="14c0e-160">Pärast andmete valmendamist alustame protsessi **Vastenda, vii vastavusse, ühenda**, et luua koondatud kliendiprofiil.</span><span class="sxs-lookup"><span data-stu-id="14c0e-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="14c0e-161">Lisateavet leiate teemast [Andmete koondamine](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="14c0e-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="14c0e-162">Vastendus</span><span class="sxs-lookup"><span data-stu-id="14c0e-162">Map</span></span>

1. <span data-ttu-id="14c0e-163">Pärast andmete valmendamist vastendage e-kaubanduse ja lojaalsusandmete kontaktid harilike andmetüüpidega.</span><span class="sxs-lookup"><span data-stu-id="14c0e-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="14c0e-164">Liikuge **Andmed** > **Koondamine** > **Vastendamine**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="14c0e-165">Valige olemid, mis esindavad kliendiprofiili: **eCommerceContacts** ja **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="E-kaubanduse ja lojaalsuse andmeallikad vahekaardil „Koondamine“.":::

1. <span data-ttu-id="14c0e-167">Valige andmeallika **eCommerceContacts** peamiseks võtmeks **ContactId** ja andmeallika **loyCustomers** peamiseks võtmeks **LoyaltyID**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId peamise võtmena vahekaardil „Koondamine“.":::

### <a name="match"></a><span data-ttu-id="14c0e-169">Vastenda</span><span class="sxs-lookup"><span data-stu-id="14c0e-169">Match</span></span>

1. <span data-ttu-id="14c0e-170">Liikuge vahekaardile **Vastavusseviimine** ja valige **Määra järjekord**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="14c0e-171">Valige **Esmane** ripploendist **eCommerceContacts: eCommerce** kui esmane allikas ja kaasake kõik kirjed.</span><span class="sxs-lookup"><span data-stu-id="14c0e-171">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="14c0e-172">Valige **Olem 2** ripploendist väärtus **loyCustomers: LoyaltyScheme** ja kaasake kõik kirjed.</span><span class="sxs-lookup"><span data-stu-id="14c0e-172">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="E-kaubanduse ja lojaalsuse vastavusseviimine vahekaardil „Koondamine“.":::

1. <span data-ttu-id="14c0e-174">Valige **Loo uus reegel**</span><span class="sxs-lookup"><span data-stu-id="14c0e-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="14c0e-175">Lisage esimene tingimus suvandi FullName abil.</span><span class="sxs-lookup"><span data-stu-id="14c0e-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="14c0e-176">eCommerceContacts jaoks valige **Täisnimi** rippmenüüst.</span><span class="sxs-lookup"><span data-stu-id="14c0e-176">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="14c0e-177">loyCustomers jaoks valige **Täisnimi** rippmenüüst.</span><span class="sxs-lookup"><span data-stu-id="14c0e-177">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="14c0e-178">Valige ripploend **Normaliseerimine** ja valige **Tüüp (telefon, nimi, aadress, ...)**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="14c0e-179">Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="14c0e-180">Sisestage uuele reeglile nimi **FullName, Email**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="14c0e-181">Lisage meiliaadressi jaoks teine tingimus, valides suvandi **Lisa tingimus**</span><span class="sxs-lookup"><span data-stu-id="14c0e-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="14c0e-182">Olemi eCommerceContacts jaoks valige **EKiri** rippmenüüst.</span><span class="sxs-lookup"><span data-stu-id="14c0e-182">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="14c0e-183">Olemi loyCustomers jaoks valige **EKiri** rippmenüüst.</span><span class="sxs-lookup"><span data-stu-id="14c0e-183">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="14c0e-184">Jätke suvand „Normaliseerimine“ tühjaks.</span><span class="sxs-lookup"><span data-stu-id="14c0e-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="14c0e-185">Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Reegli vastavusseviimine nime ja meili korral vahekaardil „Koondamine“.":::

7. <span data-ttu-id="14c0e-187">Valige **Salvesta** ja **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="14c0e-188">Ühendamine</span><span class="sxs-lookup"><span data-stu-id="14c0e-188">Merge</span></span>

1. <span data-ttu-id="14c0e-189">Avage vahekaart **Ühendamine**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="14c0e-190">Määrake olemi **loyCustomers** üksuse **ContactId** kuvatavaks nimeks **ContactIdLOYALTY**, et eristada seda muudest valmendatud ID-dest.</span><span class="sxs-lookup"><span data-stu-id="14c0e-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="contactid nime vahetamine lojaalsuse ID-s.":::

1. <span data-ttu-id="14c0e-192">Valige **Salvesta** ja **Käivita**, et käivitada ühendamisprotsess.</span><span class="sxs-lookup"><span data-stu-id="14c0e-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="14c0e-193">Ülesanne 3 – tellimusevoolavuse prognoosi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="14c0e-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="14c0e-194">Kui kliendiprofiilid on koondatud, saame käivitada tellimusevoolavuse prognoosi.</span><span class="sxs-lookup"><span data-stu-id="14c0e-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="14c0e-195">Üksikasjalikud juhised leiate artiklist [Tellimusevoolavuse prognoos (eelversioon)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="14c0e-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="14c0e-196">Minge jaotisse **Ärianalüüs** > **Avastamine** ja valige kasutamiseks **Kliendivoolavuse mudel**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="14c0e-197">Valige suvand **Tellimus** ja valige **Alusta**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="14c0e-198">Pange mudelile nimi **OOB tellimusevoolavuse prognoos** ja väljundolemile nimi **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="14c0e-199">Määratlege voolavuse mudeli jaoks kaks tingimust.</span><span class="sxs-lookup"><span data-stu-id="14c0e-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="14c0e-200">**Päevi pärast tellimuse lõppu**: **vähemalt 60** päeva.</span><span class="sxs-lookup"><span data-stu-id="14c0e-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="14c0e-201">Kui klient ei uuenda tellimust selle perioodi jooksul pärast tellimuse lõppemist, loetakse ta loobunuks.</span><span class="sxs-lookup"><span data-stu-id="14c0e-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="14c0e-202">**Voolavuse määratlus**: **vähemalt 93** päeva.</span><span class="sxs-lookup"><span data-stu-id="14c0e-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="14c0e-203">Aeg, mida mudel kasutab selle prognoosimiseks, millised kliendid võivad loobuda.</span><span class="sxs-lookup"><span data-stu-id="14c0e-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="14c0e-204">Mida suurem on ajavahemik, seda ebatäpsemad on tulemused.</span><span class="sxs-lookup"><span data-stu-id="14c0e-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Mudeli suvandite „Prognoosiajavahemik“ ja „Voolavuse määratlus“ valimine.":::

1. <span data-ttu-id="14c0e-206">Valige **Lisa nõutavad andmed** ja valige tellimuseajaloo jaoks **Lisa andmeid**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="14c0e-207">Lisage olem **eSubscription: SubscriptionHistory** ja vastendage e-kaubandusest pärit väljad asjaomaste mudelile vajalike väljadega.</span><span class="sxs-lookup"><span data-stu-id="14c0e-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="14c0e-208">Ühendage olem **Subscription: SubscriptionHistory** olemiga **eCommerceContacts: eCommerce**, pane seosele nimi **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="E-kaubanduse olemite ühendamine.":::

1. <span data-ttu-id="14c0e-210">Lisage klienditegevuste jaotises olem **webReviews: Website** ja vastendage olemist webReviews pärit väljad asjaomaste mudelile vajalike väljadega.</span><span class="sxs-lookup"><span data-stu-id="14c0e-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="14c0e-211">Primaarvõti: ReviewId</span><span class="sxs-lookup"><span data-stu-id="14c0e-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="14c0e-212">Ajatempel: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="14c0e-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="14c0e-213">Sündmus: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="14c0e-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="14c0e-214">Tegevuse konfigureerimine veebisaidiarvustuste jaoks.</span><span class="sxs-lookup"><span data-stu-id="14c0e-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="14c0e-215">Valige tegevus **Ülevaatamine** ja ühendage olem **webReviews: Website** olemiga **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="14c0e-216">Valige **Järgmine**, et määratleda mudeli ajakava.</span><span class="sxs-lookup"><span data-stu-id="14c0e-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="14c0e-217">Mudelit on vaja regulaarselt treenida, et see õpiks uusi mustreid uute andmete valmendamisel.</span><span class="sxs-lookup"><span data-stu-id="14c0e-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="14c0e-218">Selle näite puhul valige **Iga kuu**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="14c0e-219">Pärast kõigi üksikasjade läbivaatamist valige **Salvesta ja käivita**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="14c0e-220">Ülesanne 4 – mudeli tulemuste ja selgituste läbivaatamine</span><span class="sxs-lookup"><span data-stu-id="14c0e-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="14c0e-221">Laske mudelil treenimine ja andmete hindamine lõpule viia.</span><span class="sxs-lookup"><span data-stu-id="14c0e-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="14c0e-222">Nüüd saate üle vaadata tellimusevoolavuse mudeli selgitused.</span><span class="sxs-lookup"><span data-stu-id="14c0e-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="14c0e-223">Lisateavet leiate teemast [Prognoos oleku ja tulemuste läbivaatamine](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="14c0e-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="14c0e-224">Ülesanne 5 – suure voolavusriskiga klientide segmendi loomine</span><span class="sxs-lookup"><span data-stu-id="14c0e-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="14c0e-225">Tootmismudeli käitamisel luuakse uus olem, mida näete, kui liigute **Andmed** > **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="14c0e-226">Saate luua mudeli loodud olemi põhjal uue segmendi.</span><span class="sxs-lookup"><span data-stu-id="14c0e-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="14c0e-227">Liikuge jaotisse **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-227">Go to **Segments**.</span></span> <span data-ttu-id="14c0e-228">Valige **Uus** ja seejärel **Loo üksusest** > **Ärianalüüs**.</span><span class="sxs-lookup"><span data-stu-id="14c0e-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Segmendi loomine mudeli väljundiga.":::

1. <span data-ttu-id="14c0e-230">Valige lõpp-punkt **OOBSubscriptionChurnPrediction** ja määratlege segment.</span><span class="sxs-lookup"><span data-stu-id="14c0e-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="14c0e-231">Väli: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="14c0e-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="14c0e-232">Tehtemärk: suurem kui</span><span class="sxs-lookup"><span data-stu-id="14c0e-232">Operator: greater than</span></span>
   - <span data-ttu-id="14c0e-233">Väärtus: 0,6</span><span class="sxs-lookup"><span data-stu-id="14c0e-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Tellimusevoolavuse segmendi seadistamine.":::

<span data-ttu-id="14c0e-235">Teil on nüüd segment, mida värskendatakse dünaamiliselt ja mis tuvastab selle tellimusäri jaoks suure voolavusriskiga kliente.</span><span class="sxs-lookup"><span data-stu-id="14c0e-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="14c0e-236">Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).</span><span class="sxs-lookup"><span data-stu-id="14c0e-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]