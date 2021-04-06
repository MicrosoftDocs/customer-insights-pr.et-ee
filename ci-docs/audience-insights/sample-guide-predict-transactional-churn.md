---
title: Tehinguvoolavuse prognoosi näidisjuhend
description: Kasutage seda näidisjuhendit, et proovida kasutamiseks valmis tehinguvoolavuse prognoosi mudelit.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 251bc26246cee16952e8e4cb08e2ed7aa4d18488
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595421"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="24286-103">Tehinguvoolavuse prognoosi (eelversioon) näidisjuhend</span><span class="sxs-lookup"><span data-stu-id="24286-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="24286-104">Selles juhendis näidatakse teile otsast lõpuni, kuidas kasutada Customer Insightsis tehinguvoolavuse prognoosi funktsiooni koos alltoodud andmetega.</span><span class="sxs-lookup"><span data-stu-id="24286-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="24286-105">Kõik selles juhendis kasutatud andmed ei ole tegelikud kliendiandmed ja need kuuluvad Contoso andmekogumi hulka, mis asub teie Customer Insightsi tellimuse keskkonnas *Demo*.</span><span class="sxs-lookup"><span data-stu-id="24286-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="24286-106">Stsenaarium</span><span class="sxs-lookup"><span data-stu-id="24286-106">Scenario</span></span>

<span data-ttu-id="24286-107">Contoso on ettevõte, mis toodab kvaliteetset kohvi ja kohvimasinaid, mida müüakse veebisaidi Contoso Coffee kaudu.</span><span class="sxs-lookup"><span data-stu-id="24286-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="24286-108">Nende eesmärk on teada saada, millised kliendid, kes tavaliselt nende tooteid regulaarselt ostavad, pole enam järgmise 60 päeva jooksul aktiivsed.</span><span class="sxs-lookup"><span data-stu-id="24286-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="24286-109">Teades, millised nende kliendid **tõenäoliselt loobuvad**, aitab ettevõttel nende säilitamisele keskendudes turundusvõtteid säästa.</span><span class="sxs-lookup"><span data-stu-id="24286-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="24286-110">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="24286-110">Prerequisites</span></span>

- <span data-ttu-id="24286-111">Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.</span><span class="sxs-lookup"><span data-stu-id="24286-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="24286-112">Soovitame teil järgmisi samme rakendada [uues keskkonnas](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="24286-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="24286-113">Ülesanne 1 – andmete valmendamine</span><span class="sxs-lookup"><span data-stu-id="24286-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="24286-114">Vaadake üle artiklid [andmete valmendamise](data-sources.md) ja [Power Query konnektorite abil andmete importimise](connect-power-query.md) kohta.</span><span class="sxs-lookup"><span data-stu-id="24286-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="24286-115">Järgmises teabes eeldatakse, et olete andmete valmendamisega üldiselt tuttav.</span><span class="sxs-lookup"><span data-stu-id="24286-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="24286-116">E-kaubanduse platvormist pärit kliendiandmete valmendamine</span><span class="sxs-lookup"><span data-stu-id="24286-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="24286-117">Looge andmeallikas nimega **eCommerce**, valige importimise suvand ja valige konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="24286-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="24286-118">Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="24286-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="24286-119">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="24286-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="24286-120">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="24286-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="24286-121">**DateOfBirth**: kuupäev</span><span class="sxs-lookup"><span data-stu-id="24286-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="24286-122">**CreatedOn**: kuupäev/kellaaeg/ajatsoon</span><span class="sxs-lookup"><span data-stu-id="24286-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="24286-123">![Sünniaja teisendamine kuupäevaks](media/ecommerce-dob-date.PNG "sünniaja teisendamine kuupäevaks")</span><span class="sxs-lookup"><span data-stu-id="24286-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="24286-124">Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="24286-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="24286-125">Salvestage andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="24286-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="24286-126">Internetiostude andmete valmendamine</span><span class="sxs-lookup"><span data-stu-id="24286-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="24286-127">Lisage samasse andmeallikasse **eCommerce** veel üks andmekogum.</span><span class="sxs-lookup"><span data-stu-id="24286-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="24286-128">Valige uuesti konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="24286-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="24286-129">Sisestage **internetiostude** andmete URL https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="24286-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="24286-130">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="24286-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="24286-131">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="24286-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="24286-132">**PurchasedOn**: kuupäev/kellaaeg</span><span class="sxs-lookup"><span data-stu-id="24286-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="24286-133">**TotalPrice**: valuuta</span><span class="sxs-lookup"><span data-stu-id="24286-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="24286-134">Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="24286-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="24286-135">Salvestage andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="24286-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="24286-136">Kliendiandmete valmendamine lojaalsusskeemi kaudu</span><span class="sxs-lookup"><span data-stu-id="24286-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="24286-137">Looge andmeallikas nimega **LoyaltyScheme**, valige importimise suvand ja valige konnektor **Tekst/CSV**.</span><span class="sxs-lookup"><span data-stu-id="24286-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="24286-138">Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="24286-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="24286-139">Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.</span><span class="sxs-lookup"><span data-stu-id="24286-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="24286-140">Värskendage allpool loetletud veergude andmetüüp.</span><span class="sxs-lookup"><span data-stu-id="24286-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="24286-141">**DateOfBirth**: kuupäev</span><span class="sxs-lookup"><span data-stu-id="24286-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="24286-142">**RewardsPoints**: täisarv</span><span class="sxs-lookup"><span data-stu-id="24286-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="24286-143">**CreatedOn**: kuupäev/kellaaeg</span><span class="sxs-lookup"><span data-stu-id="24286-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="24286-144">Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="24286-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="24286-145">Salvestage andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="24286-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="24286-146">Ülesanne 2 – andmete koondamine</span><span class="sxs-lookup"><span data-stu-id="24286-146">Task 2 - Data unification</span></span>

<span data-ttu-id="24286-147">Pärast andmete valmendamist alustame protsessi **Vastenda, vii vastavusse, ühenda**, et luua koondatud kliendiprofiil.</span><span class="sxs-lookup"><span data-stu-id="24286-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="24286-148">Lisateavet leiate teemast [Andmete koondamine](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="24286-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="24286-149">Vastendus</span><span class="sxs-lookup"><span data-stu-id="24286-149">Map</span></span>

1. <span data-ttu-id="24286-150">Pärast andmete valmendamist vastendage e-kaubanduse ja lojaalsusandmete kontaktid harilike andmetüüpidega.</span><span class="sxs-lookup"><span data-stu-id="24286-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="24286-151">Liikuge **Andmed** > **Koondamine** > **Vastendamine**.</span><span class="sxs-lookup"><span data-stu-id="24286-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="24286-152">Valige olemid, mis esindavad kliendiprofiili: **eCommerceContacts** ja **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="24286-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="E-kaubanduse ja lojaalsuse andmeallikad vahekaardil „Koondamine“.":::

1. <span data-ttu-id="24286-154">Valige andmeallika **eCommerceContacts** peamiseks võtmeks **ContactId** ja andmeallika **loyCustomers** peamiseks võtmeks **LoyaltyID**.</span><span class="sxs-lookup"><span data-stu-id="24286-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId peamise võtmena vahekaardil „Koondamine“.":::

### <a name="match"></a><span data-ttu-id="24286-156">Vastenda</span><span class="sxs-lookup"><span data-stu-id="24286-156">Match</span></span>

1. <span data-ttu-id="24286-157">Liikuge vahekaardile **Vastavusseviimine** ja valige **Määra järjekord**.</span><span class="sxs-lookup"><span data-stu-id="24286-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="24286-158">Valige ripploendis **Peamine** peamiseks andmeallikaks **eCommerceContacts: eCommerce** ja kaasake kõik kirjed.</span><span class="sxs-lookup"><span data-stu-id="24286-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="24286-159">Valige ripploendist **Olem 2** **loyCustomers: LoyaltyScheme** ja kaasake kõik kirjed.</span><span class="sxs-lookup"><span data-stu-id="24286-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="E-kaubanduse ja lojaalsuse vastavusseviimine vahekaardil „Koondamine“.":::

1. <span data-ttu-id="24286-161">Valige **Loo uus reegel**</span><span class="sxs-lookup"><span data-stu-id="24286-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="24286-162">Lisage esimene tingimus suvandi FullName abil.</span><span class="sxs-lookup"><span data-stu-id="24286-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="24286-163">Valige andmeallika eCommerceContacts jaoks ripploendist **FullName**.</span><span class="sxs-lookup"><span data-stu-id="24286-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="24286-164">Valige andmeallika loyCustomers jaoks ripploendist **FullName**.</span><span class="sxs-lookup"><span data-stu-id="24286-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="24286-165">Valige ripploend **Normaliseerimine** ja valige **Tüüp (telefon, nimi, aadress, ...)**.</span><span class="sxs-lookup"><span data-stu-id="24286-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="24286-166">Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.</span><span class="sxs-lookup"><span data-stu-id="24286-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="24286-167">Sisestage uuele reeglile nimi **FullName, Email**.</span><span class="sxs-lookup"><span data-stu-id="24286-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="24286-168">Lisage meiliaadressi jaoks teine tingimus, valides suvandi **Lisa tingimus**</span><span class="sxs-lookup"><span data-stu-id="24286-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="24286-169">Valige olemi eCommerceContacts jaoks ripploendist **Meil**.</span><span class="sxs-lookup"><span data-stu-id="24286-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="24286-170">Valige olemi loyCustomers jaoks ripploendist **Meil**.</span><span class="sxs-lookup"><span data-stu-id="24286-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="24286-171">Jätke suvand „Normaliseerimine“ tühjaks.</span><span class="sxs-lookup"><span data-stu-id="24286-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="24286-172">Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.</span><span class="sxs-lookup"><span data-stu-id="24286-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Reegli vastavusseviimine nime ja meili korral vahekaardil „Koondamine“.":::

7. <span data-ttu-id="24286-174">Valige **Salvesta** ja **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="24286-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="24286-175">Ühendamine</span><span class="sxs-lookup"><span data-stu-id="24286-175">Merge</span></span>

1. <span data-ttu-id="24286-176">Avage vahekaart **Ühendamine**.</span><span class="sxs-lookup"><span data-stu-id="24286-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="24286-177">Määrake olemi **loyCustomers** üksuse **ContactId** kuvatavaks nimeks **ContactIdLOYALTY**, et eristada seda muudest valmendatud ID-dest.</span><span class="sxs-lookup"><span data-stu-id="24286-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="contactid nime vahetamine lojaalsuse ID-s.":::

1. <span data-ttu-id="24286-179">Valige **Salvesta** ja **Käivita**, et käivitada ühendamisprotsess.</span><span class="sxs-lookup"><span data-stu-id="24286-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="24286-180">Ülesanne 3 – tehinguvoolavuse prognoosi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="24286-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="24286-181">Kui kliendiprofiilid on koondatud, saame käivitada tellimusevoolavuse prognoosi.</span><span class="sxs-lookup"><span data-stu-id="24286-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="24286-182">Üksikasjalikud juhised leiate artiklist [Tellimusevoolavuse prognoos (eelversioon)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="24286-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="24286-183">Minge jaotisse **Ärianalüüs** > **Avastamine** ja valige kasutamiseks **Kliendivoolavuse mudel**.</span><span class="sxs-lookup"><span data-stu-id="24286-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="24286-184">Valige suvand **Tehingupõhine** ja valige **Alusta**.</span><span class="sxs-lookup"><span data-stu-id="24286-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="24286-185">Pange mudelile nimi **OOB e-kaubanduse tehinguvoolavuse prognoos** ja väljundolemile nimi **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="24286-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="24286-186">Määratlege voolavuse mudeli jaoks kaks tingimust.</span><span class="sxs-lookup"><span data-stu-id="24286-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="24286-187">**Prognoosiajavahemik**: **vähemalt 60** päeva.</span><span class="sxs-lookup"><span data-stu-id="24286-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="24286-188">See säte määratleb, kui kaugel tulevikus tahame kliendivoolavust ennustada.</span><span class="sxs-lookup"><span data-stu-id="24286-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="24286-189">**Voolavuse määratlus**: **vähemalt 60** päeva.</span><span class="sxs-lookup"><span data-stu-id="24286-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="24286-190">Ostudeta aeg, pärast mida loetakse klient loobunuks.</span><span class="sxs-lookup"><span data-stu-id="24286-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Mudeli suvandite „Prognoosiajavahemik“ ja „Voolavuse määratlus“ valimine.":::

1. <span data-ttu-id="24286-192">Valige **Ostuajalugu (nõutav)** ja valige ostuajaloo jaoks **Lisa andmeid**.</span><span class="sxs-lookup"><span data-stu-id="24286-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="24286-193">Lisage olem **eCommercePurchases: eCommerce** ja vastendage e-kaubandusest pärit väljad asjaomaste mudelile vajalike väljadega.</span><span class="sxs-lookup"><span data-stu-id="24286-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="24286-194">Ühendage olem **eCommercePurchases: eCommerce** olemiga **eCommerceContacts: eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="24286-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="E-kaubanduse olemite ühendamine.":::

1. <span data-ttu-id="24286-196">Valige **Järgmine**, et määratleda mudeli ajakava.</span><span class="sxs-lookup"><span data-stu-id="24286-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="24286-197">Mudelit on vaja regulaarselt treenida, et see õpiks uusi mustreid uute andmete valmendamisel.</span><span class="sxs-lookup"><span data-stu-id="24286-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="24286-198">Selle näite puhul valige **Iga kuu**.</span><span class="sxs-lookup"><span data-stu-id="24286-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="24286-199">Pärast kõigi üksikasjade läbivaatamist valige **Salvesta ja käivita**.</span><span class="sxs-lookup"><span data-stu-id="24286-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="24286-200">Ülesanne 4 – mudeli tulemuste ja selgituste läbivaatamine</span><span class="sxs-lookup"><span data-stu-id="24286-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="24286-201">Laske mudelil treenimine ja andmete hindamine lõpule viia.</span><span class="sxs-lookup"><span data-stu-id="24286-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="24286-202">Nüüd saate üle vaadata tellimusevoolavuse mudeli selgitused.</span><span class="sxs-lookup"><span data-stu-id="24286-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="24286-203">Lisateavet leiate teemast [Prognoos oleku ja tulemuste läbivaatamine](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="24286-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="24286-204">Ülesanne 5 – suure voolavusriskiga klientide segmendi loomine</span><span class="sxs-lookup"><span data-stu-id="24286-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="24286-205">Tootmismudeli käitamisel luuakse uus olem, mida näete, kui liigute **Andmed** > **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="24286-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="24286-206">Saate luua mudeli loodud olemi põhjal uue segmendi.</span><span class="sxs-lookup"><span data-stu-id="24286-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="24286-207">Liikuge jaotisse **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="24286-207">Go to **Segments**.</span></span> <span data-ttu-id="24286-208">Valige **Uus** ja seejärel **Loo üksusest** > **Ärianalüüs**.</span><span class="sxs-lookup"><span data-stu-id="24286-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Segmendi loomine mudeli väljundiga.":::

1. <span data-ttu-id="24286-210">Valige lõpp-punkt **OOBSubscriptionChurnPrediction** ja määratlege segment.</span><span class="sxs-lookup"><span data-stu-id="24286-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="24286-211">Väli: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="24286-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="24286-212">Tehtemärk: suurem kui</span><span class="sxs-lookup"><span data-stu-id="24286-212">Operator: greater than</span></span>
   - <span data-ttu-id="24286-213">Väärtus: 0,6</span><span class="sxs-lookup"><span data-stu-id="24286-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Tellimusevoolavuse segmendi seadistamine.":::

<span data-ttu-id="24286-215">Teil on nüüd segment, mida värskendatakse dünaamiliselt ja mis tuvastab selle tellimusäri jaoks suure voolavusriskiga kliente.</span><span class="sxs-lookup"><span data-stu-id="24286-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="24286-216">Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).</span><span class="sxs-lookup"><span data-stu-id="24286-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]