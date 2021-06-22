---
title: Tootesoovituste prognoosimise näidisjuhend
description: Kasutage seda näidisjuhendit, et proovida kasutamiseks valmis tootesoovituste prognoosi mudelit.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b136084316da5ae17a8428236381f69e5c21f9ea
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129894"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="07263-103">Toote soovituste prognoosimise (eelvaate) näidisjuhend</span><span class="sxs-lookup"><span data-stu-id="07263-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="07263-104">Selles juhendis näidatakse teile otsast lõpuni, kuidas kasutada tootesoovituste prognoosi funktsiooni koos alltoodud näidisandmetega.</span><span class="sxs-lookup"><span data-stu-id="07263-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="07263-105">Stsenaarium</span><span class="sxs-lookup"><span data-stu-id="07263-105">Scenario</span></span>

<span data-ttu-id="07263-106">Contoso on ettevõte, mis toodab kvaliteetseid kohvi- ja kohvimasinaid, mida nad müüvad oma Contoso Coffee veebisaidi kaudu.</span><span class="sxs-lookup"><span data-stu-id="07263-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="07263-107">Nende eesmärk on mõista, milliseid tooteid nad peaksid püsiklientidele soovitama.</span><span class="sxs-lookup"><span data-stu-id="07263-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="07263-108">Teades, millised kliendid **tõenäoliselt ostavad**, aitab ettevõttel nendele toodetele keskendudes turundusvõtteid säästa.</span><span class="sxs-lookup"><span data-stu-id="07263-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="07263-109">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="07263-109">Prerequisites</span></span>

- <span data-ttu-id="07263-110">Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.</span><span class="sxs-lookup"><span data-stu-id="07263-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="07263-111">Soovitame teil järgmisi samme rakendada [uues keskkonnas](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="07263-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="07263-112">Ülesanne 1 – andmete valmendamine</span><span class="sxs-lookup"><span data-stu-id="07263-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="07263-113">Vaadake üle artiklid [andmete valmendamise](data-sources.md) ja [Power Query konnektorite abil andmete importimise](connect-power-query.md) kohta.</span><span class="sxs-lookup"><span data-stu-id="07263-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="07263-114">Järgmises teabes eeldatakse, et olete andmete valmendamisega üldiselt tuttav.</span><span class="sxs-lookup"><span data-stu-id="07263-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="07263-115">E-kaubanduse platvormist pärit kliendiandmete valmendamine</span><span class="sxs-lookup"><span data-stu-id="07263-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="07263-116">Looge andmeallikas nimega **eCommerce**, valige importimise suvand ja valige konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="07263-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="07263-117">Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="07263-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="07263-118">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="07263-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="07263-119">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="07263-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="07263-120">**DateOfBirth**: kuupäev</span><span class="sxs-lookup"><span data-stu-id="07263-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="07263-121">**CreatedOn**: kuupäev/kellaaeg/ajatsoon</span><span class="sxs-lookup"><span data-stu-id="07263-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Sünniaja teisendamine kuupäevaks.":::

5. <span data-ttu-id="07263-123">Muutke parempoolsel paanil väljal „Nimi“ oma andmeallika praegune nimi **Päring** nimeks **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="07263-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="07263-124">**Salvestage** andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="07263-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="07263-125">Internetiostude andmete valmendamine</span><span class="sxs-lookup"><span data-stu-id="07263-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="07263-126">Lisage samasse andmeallikasse **eCommerce** veel üks andmekogum.</span><span class="sxs-lookup"><span data-stu-id="07263-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="07263-127">Valige uuesti konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="07263-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="07263-128">Sisestage **internetiostude** andmete URL https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="07263-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="07263-129">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="07263-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="07263-130">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="07263-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="07263-131">**PurchasedOn**: kuupäev/kellaaeg</span><span class="sxs-lookup"><span data-stu-id="07263-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="07263-132">**TotalPrice**: valuuta</span><span class="sxs-lookup"><span data-stu-id="07263-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="07263-133">Muutke küljepaanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="07263-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="07263-134">**Salvestage** andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="07263-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="07263-135">Kliendiandmete valmendamine lojaalsusskeemi kaudu</span><span class="sxs-lookup"><span data-stu-id="07263-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="07263-136">Looge andmeallikas nimega **LoyaltyScheme**, valige importimise suvand ja valige konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="07263-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="07263-137">Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="07263-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="07263-138">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="07263-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="07263-139">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="07263-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="07263-140">**DateOfBirth**: kuupäev</span><span class="sxs-lookup"><span data-stu-id="07263-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="07263-141">**RewardsPoints**: täisarv</span><span class="sxs-lookup"><span data-stu-id="07263-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="07263-142">**CreatedOn**: kuupäev/kellaaeg</span><span class="sxs-lookup"><span data-stu-id="07263-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="07263-143">Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="07263-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="07263-144">**Salvestage** andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="07263-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="07263-145">Ülesanne 2 – andmete koondamine</span><span class="sxs-lookup"><span data-stu-id="07263-145">Task 2 - Data unification</span></span>

<span data-ttu-id="07263-146">Pärast andmete sisestamist alustame andmete ühendamise protsessi, et luua ühtne kliendiprofiil.</span><span class="sxs-lookup"><span data-stu-id="07263-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="07263-147">Lisateavet leiate teemast [Andmete koondamine](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="07263-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="07263-148">Vastendus</span><span class="sxs-lookup"><span data-stu-id="07263-148">Map</span></span>

1. <span data-ttu-id="07263-149">Pärast andmete valmendamist vastendage e-kaubanduse ja lojaalsusandmete kontaktid harilike andmetüüpidega.</span><span class="sxs-lookup"><span data-stu-id="07263-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="07263-150">Liikuge **Andmed** > **Koondamine** > **Vastendamine**.</span><span class="sxs-lookup"><span data-stu-id="07263-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="07263-151">Valige olemid, mis esindavad kliendiprofiili: **eCommerceContacts** ja **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="07263-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![E-kaubanduse ja lojaalsuse andmeallikad vahekaardil „Koondamine“.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="07263-153">Valige andmeallika **eCommerceContacts** peamiseks võtmeks **ContactId** ja andmeallika **loyCustomers** peamiseks võtmeks **LoyaltyID**.</span><span class="sxs-lookup"><span data-stu-id="07263-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![LoyaltyId peamise võtmena vahekaardil „Koondamine“.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="07263-155">Vastenda</span><span class="sxs-lookup"><span data-stu-id="07263-155">Match</span></span>

1. <span data-ttu-id="07263-156">Liikuge vahekaardile **Vastavusseviimine** ja valige **Määra järjekord**.</span><span class="sxs-lookup"><span data-stu-id="07263-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="07263-157">Valige ripploendis **Peamine** peamiseks andmeallikaks **eCommerceContacts: eCommerce** ja kaasake kõik kirjed.</span><span class="sxs-lookup"><span data-stu-id="07263-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="07263-158">Valige ripploendist **Olem 2** **loyCustomers: LoyaltyScheme** ja kaasake kõik kirjed.</span><span class="sxs-lookup"><span data-stu-id="07263-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![E-kaubanduse ja lojaalsuse vastavusseviimine vahekaardil „Koondamine“.](media/unify-match-order.png)

4. <span data-ttu-id="07263-160">Valige **Loo uus reegel**</span><span class="sxs-lookup"><span data-stu-id="07263-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="07263-161">Lisage esimene tingimus suvandi FullName abil.</span><span class="sxs-lookup"><span data-stu-id="07263-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="07263-162">Valige andmeallika eCommerceContacts jaoks ripploendist **FullName**.</span><span class="sxs-lookup"><span data-stu-id="07263-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="07263-163">Valige andmeallika loyCustomers jaoks ripploendist **FullName**.</span><span class="sxs-lookup"><span data-stu-id="07263-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="07263-164">Valige ripploend **Normaliseerimine** ja valige **Tüüp (telefon, nimi, aadress, ...)**.</span><span class="sxs-lookup"><span data-stu-id="07263-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="07263-165">Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.</span><span class="sxs-lookup"><span data-stu-id="07263-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="07263-166">Sisestage uuele reeglile nimi **FullName, Email**.</span><span class="sxs-lookup"><span data-stu-id="07263-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="07263-167">Lisage meiliaadressi jaoks teine tingimus, valides suvandi **Lisa tingimus**</span><span class="sxs-lookup"><span data-stu-id="07263-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="07263-168">Valige olemi eCommerceContacts jaoks ripploendist **Meil**.</span><span class="sxs-lookup"><span data-stu-id="07263-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="07263-169">Valige olemi loyCustomers jaoks ripploendist **Meil**.</span><span class="sxs-lookup"><span data-stu-id="07263-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="07263-170">Jätke suvand „Normaliseerimine“ tühjaks.</span><span class="sxs-lookup"><span data-stu-id="07263-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="07263-171">Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.</span><span class="sxs-lookup"><span data-stu-id="07263-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Reegli vastavusseviimine nime ja meili korral vahekaardil „Koondamine“.](media/unify-match-rule.png)

7. <span data-ttu-id="07263-173">Valige **Salvesta** ja **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="07263-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="07263-174">Ühendamine</span><span class="sxs-lookup"><span data-stu-id="07263-174">Merge</span></span>

1. <span data-ttu-id="07263-175">Avage vahekaart **Ühendamine**.</span><span class="sxs-lookup"><span data-stu-id="07263-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="07263-176">Määrake olemi **loyCustomers** üksuse **ContactId** kuvatavaks nimeks **ContactIdLOYALTY**, et eristada seda muudest valmendatud ID-dest.</span><span class="sxs-lookup"><span data-stu-id="07263-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![contactid nime vahetamine lojaalsuse ID-s.](media/unify-merge-contactid.png)

1. <span data-ttu-id="07263-178">Valige **Salvesta** ja **Käivita**, et käivitada ühendamisprotsess.</span><span class="sxs-lookup"><span data-stu-id="07263-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="07263-179">3. toiming – tootesoovituse prognoosi konfiguratsioon</span><span class="sxs-lookup"><span data-stu-id="07263-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="07263-180">Kui kliendiprofiilid on koondatud, saame käivitada tellimusevoolavuse prognoosi.</span><span class="sxs-lookup"><span data-stu-id="07263-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="07263-181">Minge **Intelligents** > **Prognoos** ja valige **Tootesoovitus**.</span><span class="sxs-lookup"><span data-stu-id="07263-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="07263-182">Seejärel valige suvand **Alustamine**.</span><span class="sxs-lookup"><span data-stu-id="07263-182">Select **Get started**.</span></span>

1. <span data-ttu-id="07263-183">Nimetage mudeli **OOB tootesoovituse mudeli prognoos** ja väljundolemi **OOBProductRecommendationPrediction**.</span><span class="sxs-lookup"><span data-stu-id="07263-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="07263-184">Määratlege mudeli jaoks kolm järgmist tingimust.</span><span class="sxs-lookup"><span data-stu-id="07263-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="07263-185">**Toodete arv**: määrake selle väärtuseks **5**.</span><span class="sxs-lookup"><span data-stu-id="07263-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="07263-186">See säte määratleb mitu toodet soovite oma klientidele soovitada.</span><span class="sxs-lookup"><span data-stu-id="07263-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="07263-187">**Eeldatud kordusostud**: valige **Jah** näitamaks, et soovite tooteid kaasata soovitusesse, mille teie kliendid on varem ostnud.</span><span class="sxs-lookup"><span data-stu-id="07263-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="07263-188">**Tagasivaate aken:** valige vähemalt **365 päeva**.</span><span class="sxs-lookup"><span data-stu-id="07263-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="07263-189">See säte määtatleb, kui kaugele mudel vaatab kliendi aktiivsuse ajas tagasi, et seda kasutada oma soovituste sisendina.</span><span class="sxs-lookup"><span data-stu-id="07263-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Toote soovitusmudeli mudeli eelistused.":::

1. <span data-ttu-id="07263-191">Valige **Nõutavad andmed** ja valige ostuajaloo jaoks **Lisa andmeid**.</span><span class="sxs-lookup"><span data-stu-id="07263-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="07263-192">Lisage olem **eCommercePurchases: eCommerce** ja vastendage e-kaubandusest pärit väljad asjaomaste mudelile vajalike väljadega.</span><span class="sxs-lookup"><span data-stu-id="07263-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="07263-193">Ühendage olem **eCommercePurchases: eCommerce** olemiga **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="07263-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![E-kaubanduse olemite ühendamine.](media/model-purchase-join.png)

1. <span data-ttu-id="07263-195">Valige **Järgmine**, et määratleda mudeli ajakava.</span><span class="sxs-lookup"><span data-stu-id="07263-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="07263-196">Mudelit on vaja regulaarselt treenida, et see õpiks uusi mustreid uute andmete valmendamisel.</span><span class="sxs-lookup"><span data-stu-id="07263-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="07263-197">Selle näite puhul valige **Iga kuu**.</span><span class="sxs-lookup"><span data-stu-id="07263-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="07263-198">Pärast kõigi üksikasjade läbivaatamist valige **Salvesta ja käivita**.</span><span class="sxs-lookup"><span data-stu-id="07263-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="07263-199">Ülesanne 4 – mudeli tulemuste ja selgituste läbivaatamine</span><span class="sxs-lookup"><span data-stu-id="07263-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="07263-200">Laske mudelil treenimine ja andmete hindamine lõpule viia.</span><span class="sxs-lookup"><span data-stu-id="07263-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="07263-201">Nüüd saate üle vaadata tootesoovituste mudeli selgitused.</span><span class="sxs-lookup"><span data-stu-id="07263-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="07263-202">Lisateavet leiate teemast [Prognoos oleku ja tulemuste läbivaatamine](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="07263-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="07263-203">Tööülesanne 5 – rohkelt ostetud toodete segmendi loomine</span><span class="sxs-lookup"><span data-stu-id="07263-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="07263-204">Tootmismudeli käitamisel luuakse uus olem, mida näete, kui liigute **Andmed** > **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="07263-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="07263-205">Saate luua mudeli loodud olemi põhjal uue segmendi.</span><span class="sxs-lookup"><span data-stu-id="07263-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="07263-206">Liikuge jaotisse **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="07263-206">Go to **Segments**.</span></span> <span data-ttu-id="07263-207">Valige **Uus** ja seejärel **Loo üksusest** > **Ärianalüüs**.</span><span class="sxs-lookup"><span data-stu-id="07263-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Segmendi loomine mudeli väljundiga.](media/segment-intelligence.png)

1. <span data-ttu-id="07263-209">Valige lõpp-punkt **OOBProductRecommendationModelPrediction** ja määratlege segment.</span><span class="sxs-lookup"><span data-stu-id="07263-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="07263-210">Väli: ProductID</span><span class="sxs-lookup"><span data-stu-id="07263-210">Field: ProductID</span></span>
   - <span data-ttu-id="07263-211">Tehtemärk: väärtus</span><span class="sxs-lookup"><span data-stu-id="07263-211">Operator: Value</span></span>
   - <span data-ttu-id="07263-212">Väärtus: valige kolm peamist toote ID-d</span><span class="sxs-lookup"><span data-stu-id="07263-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Saate mudelitulemitest luua segmendi.":::

<span data-ttu-id="07263-214">Teil on nüüd dünaamiliselt uuendatud segment, mis tuvastab kliendid, kes on valmis ostma kolme kõige soovitatavamat toodet</span><span class="sxs-lookup"><span data-stu-id="07263-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="07263-215">Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).</span><span class="sxs-lookup"><span data-stu-id="07263-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
