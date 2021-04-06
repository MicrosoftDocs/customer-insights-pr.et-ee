---
title: Tehinguvoolavuse prognoos
description: Prognoosige, kas on oht, et klient ei osta enam teie ettevõtte tooteid või teenuseid.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f120e9e3cf8d40d913c7fa6a81fbf9facd045e3c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597184"
---
# <a name="transactional-churn-prediction-preview"></a><span data-ttu-id="48ea9-103">Tehinguvoolavuse prognoos (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="48ea9-103">Transactional churn prediction (preview)</span></span>

<span data-ttu-id="48ea9-104">Tehinguvoolavuse prognoos aitab ennustada, kas klient on lõpetanud kindlal perioodil teie toodete või teenuste ostmise.</span><span class="sxs-lookup"><span data-stu-id="48ea9-104">Transactional churn prediction helps predict if a customer will no longer purchase your products or services in a given time window.</span></span> <span data-ttu-id="48ea9-105">Saate luua uusi voolavusprognoose, liikudes **Ärianalüüs** > **Prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-105">You can create new churn predictions on **Intelligence** > **Predictions**.</span></span> <span data-ttu-id="48ea9-106">Muude loodud prognooside kuvamiseks valige **Minu prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-106">Select **My predictions** to see other predictions that you've created.</span></span>

> [!TIP]
> <span data-ttu-id="48ea9-107">Proovige järgmist näidisandmetega tehinguvoolavuse prognoosi õppetükki: [Tehinguvoolavuse prognoosi (eelversioon) näidisjuhend](sample-guide-predict-transactional-churn.md).</span><span class="sxs-lookup"><span data-stu-id="48ea9-107">Try the tutorial for a translactional churn prediction using sample data: [Transactional churn prediction (preview) sample guide](sample-guide-predict-transactional-churn.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="48ea9-108">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="48ea9-108">Prerequisites</span></span>

- <span data-ttu-id="48ea9-109">Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.</span><span class="sxs-lookup"><span data-stu-id="48ea9-109">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="48ea9-110">Äriteadmised voolavuse tähendusest teie ettevõttes.</span><span class="sxs-lookup"><span data-stu-id="48ea9-110">Business knowledge to understand what churn means for your business.</span></span> <span data-ttu-id="48ea9-111">Toetame ajapõhiseid voolavuse määratlusi, mis tähendab, et klient loetakse loobunuks, kui ta pole mingi perioodi jooksul oste teinud.</span><span class="sxs-lookup"><span data-stu-id="48ea9-111">We support time-based churn definitions, meaning a customer is considered to have churned after a period of no purchases.</span></span>
- <span data-ttu-id="48ea9-112">Andmed teie tehingute/ostude ja nende ajaloo kohta.</span><span class="sxs-lookup"><span data-stu-id="48ea9-112">Data about your transactions/purchases and their history:</span></span>
    - <span data-ttu-id="48ea9-113">Tehinguidentifikaatorid, et eristada oste/tehinguid.</span><span class="sxs-lookup"><span data-stu-id="48ea9-113">Transaction identifiers to distinguish purchases/transactions.</span></span>
    - <span data-ttu-id="48ea9-114">Kliendiidentifikaatorid, et ühitada tehingud teie klientidega.</span><span class="sxs-lookup"><span data-stu-id="48ea9-114">Customer identifiers to match transactions to your customers.</span></span>
    - <span data-ttu-id="48ea9-115">Tehingusündmuse kuupäevad, mis määratlevad tehingu toimumise kuupäevad.</span><span class="sxs-lookup"><span data-stu-id="48ea9-115">Transaction event dates, which define the dates the transaction occurred on.</span></span>
    - <span data-ttu-id="48ea9-116">Ostude/tehingute semantilise andmeskeemi jaoks on vajalik järgmine teave.</span><span class="sxs-lookup"><span data-stu-id="48ea9-116">The semantic data schema for purchases/transactions requires the following information:</span></span>
        - <span data-ttu-id="48ea9-117">**Tehingu ID:** ostu või tehingu ainuidentifikaator.</span><span class="sxs-lookup"><span data-stu-id="48ea9-117">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="48ea9-118">**Tehingu kuupäev:** ostu või tehingu kuupäev.</span><span class="sxs-lookup"><span data-stu-id="48ea9-118">**Transaction Date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="48ea9-119">**Tehingu väärtus:** tehingu/kauba rahalise/numbrilise väärtuse summa.</span><span class="sxs-lookup"><span data-stu-id="48ea9-119">**Value of the transaction:** The currency/numerical value amount of the transaction/item.</span></span>
        - <span data-ttu-id="48ea9-120">(Valikuline) **Kordumatu toote ID:** ostetud toote või teenuse ID, kui teie andmed on reakauba tasemel.</span><span class="sxs-lookup"><span data-stu-id="48ea9-120">(Optional) **Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="48ea9-121">(Valikuline) **Kas see tehing oli tagastamine:** tõene/väär väli, mis määrab, kas tehingu puhul oli tegemist tagastamisega või mitte.</span><span class="sxs-lookup"><span data-stu-id="48ea9-121">(Optional) **Whether this transaction was a return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="48ea9-122">Kui **Tehingu väärtus** on negatiivne, kasutame seda teavet samuti tagastamise järeldamiseks.</span><span class="sxs-lookup"><span data-stu-id="48ea9-122">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="48ea9-123">(Valikuline) Andmed klienditegevuste kohta.</span><span class="sxs-lookup"><span data-stu-id="48ea9-123">(Optional) Data about customer activities:</span></span>
    - <span data-ttu-id="48ea9-124">Tegevuse identifikaatorid, mis eristavad sama tüüpi tegevusi.</span><span class="sxs-lookup"><span data-stu-id="48ea9-124">Activity identifiers to distinguish activities of the same type.</span></span>
    - <span data-ttu-id="48ea9-125">Kliendi identifikaatorid, mis vastendavad teie klientide tegevusi.</span><span class="sxs-lookup"><span data-stu-id="48ea9-125">Customer identifiers to map activities to your customers.</span></span>
    - <span data-ttu-id="48ea9-126">Tegevuse teave, mis sisaldab tegevuse nime ja kuupäeva.</span><span class="sxs-lookup"><span data-stu-id="48ea9-126">Activity information containing the name and date of the activity.</span></span>
    - <span data-ttu-id="48ea9-127">Kliendi tegevuste semantiline andmete skeem sisaldab järgmist.</span><span class="sxs-lookup"><span data-stu-id="48ea9-127">The semantic data schema for customer activities includes:</span></span>
        - <span data-ttu-id="48ea9-128">**Primaarvõti:** tegevuse ainuidentifikaator.</span><span class="sxs-lookup"><span data-stu-id="48ea9-128">**Primary key:** A unique identifier for an activity.</span></span> <span data-ttu-id="48ea9-129">Näiteks veebisaidikülastus või kasutuskirje, mis näitab, et klient proovis teie toote näidist.</span><span class="sxs-lookup"><span data-stu-id="48ea9-129">For example, a website visit or a usage record showing the customer tried a sample of your product.</span></span>
        - <span data-ttu-id="48ea9-130">**Ajatempel:** primaarvõtmega tuvastatud sündmuse kuupäev ja kellaaeg.</span><span class="sxs-lookup"><span data-stu-id="48ea9-130">**Timestamp:** The date and time of the event identified by the primary key.</span></span>
        - <span data-ttu-id="48ea9-131">**Sündmus:** sündmuse nimi, mida soovite kasutada.</span><span class="sxs-lookup"><span data-stu-id="48ea9-131">**Event:** The name of the event you want to use.</span></span> <span data-ttu-id="48ea9-132">Näiteks väli nimega „UserAction“ võid toidupoe korral märkida, et klient kasutas kupongi.</span><span class="sxs-lookup"><span data-stu-id="48ea9-132">For example, a field called "UserAction" in a grocery store might be a coupon use by the customer.</span></span>
        - <span data-ttu-id="48ea9-133">**Üksikasjad:** sündmuse üksikasjalik teave.</span><span class="sxs-lookup"><span data-stu-id="48ea9-133">**Details:** Detailed information about the event.</span></span> <span data-ttu-id="48ea9-134">Näiteks väli nimega „CouponValue“ võib olla toidupoes kupongi rahaline väärtus.</span><span class="sxs-lookup"><span data-stu-id="48ea9-134">For example, a field called "CouponValue" in a grocery store might be the currency value of the coupon.</span></span>

## <a name="create-a-transactional-churn-prediction"></a><span data-ttu-id="48ea9-135">Tehinguvoolavuse prognoosi loomine</span><span class="sxs-lookup"><span data-stu-id="48ea9-135">Create a transactional churn prediction</span></span>

1. <span data-ttu-id="48ea9-136">Avage teenuses Customer Insights jaotised **Ärianalüüs** > **Prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-136">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="48ea9-137">Valige paan **Kliendivoolavuse mudel (eelversioon)** ja seejärel suvand **Kasuta seda mudelit**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-137">Select the **Customer churn model (preview)** tile and select **Use this model**.</span></span>
   
1. <span data-ttu-id="48ea9-138">Valige paanil **Kliendivoolavuse mudel** suvand **Tehingupõhine** ja seejärel **Alusta**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-138">In the **Customer churn model** pane, choose **Transactional** and select **Get started**.</span></span>

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Kuvatõmmis paanil „Kliendivoolavuse mudel“ valitud tehingupõhisest suvandist.":::

### <a name="name-model"></a><span data-ttu-id="48ea9-140">Mudelile nime panemine</span><span class="sxs-lookup"><span data-stu-id="48ea9-140">Name model</span></span>

1. <span data-ttu-id="48ea9-141">Sisestage mudelile nimi, et eristada seda teistest mudelitest.</span><span class="sxs-lookup"><span data-stu-id="48ea9-141">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="48ea9-142">Sisestage väljundolemi nimi, kasutades ainult tähti ja numbreid, ilma tühikuteta.</span><span class="sxs-lookup"><span data-stu-id="48ea9-142">Provide a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="48ea9-143">Seda nime kasutab mudeli olem.</span><span class="sxs-lookup"><span data-stu-id="48ea9-143">That's the name that the model entity will use.</span></span> 

1. <span data-ttu-id="48ea9-144">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-144">Select **Next**.</span></span>

### <a name="define-customer-churn"></a><span data-ttu-id="48ea9-145">Määratlege kliendi teenusest loobumine</span><span class="sxs-lookup"><span data-stu-id="48ea9-145">Define customer churn</span></span>

1. <span data-ttu-id="48ea9-146">Sisestage loobumise ennustamiseks kasutatav päevade arv väljale **Tuvasta kliendid, kes võivad loobuda ajavahemikus**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-146">Set a window of days to predict churn for in the **Identify customers who may churn in the next** field.</span></span> <span data-ttu-id="48ea9-147">Näiteks ennustage oma klientide voolavusriski järgmise 90 päeva jooksul, et kohandada oma klientide säilitamise jõupingutusi.</span><span class="sxs-lookup"><span data-stu-id="48ea9-147">For example, predict the risk of churn for your customers over the next 90 days to align to your marketing retention efforts.</span></span> <span data-ttu-id="48ea9-148">Voolavusriski ennustamine pikema või lühema ajavahemiku jooksul võib raskendada voolavusriski tekitavate tegurite käsitlemist, kuid see sõltub teie ettevõtte vajadustest.</span><span class="sxs-lookup"><span data-stu-id="48ea9-148">Predicting churn risk for a longer or shorter period of time can make it more difficult to address the factors in your churn risk profile, but it depends on your specific business requirements.</span></span> 
   >[!TIP]
   > <span data-ttu-id="48ea9-149">Saate igal hetkel valida **Salvesta ja sule**, et salvestada prognoos mustandina.</span><span class="sxs-lookup"><span data-stu-id="48ea9-149">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="48ea9-150">Prognoosi mustandi leiate vahekaardilt **Minu prognoosid** selle jätkamiseks.</span><span class="sxs-lookup"><span data-stu-id="48ea9-150">You'll find the draft prediction in the **My predictions** tab to continue.</span></span>

1. <span data-ttu-id="48ea9-151">Sisestage voolavuse määratlemiseks päevade arv väljale **Klient on loobunud, kui ta pole teinud ühtegi ostu ajavahemikus**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-151">Enter the number of days to define churn in the **A customer has churned if they've made no purchases in:** field.</span></span> <span data-ttu-id="48ea9-152">Näiteks kui klient pole viimase 30 päeva jooksul oste teinud, võib neid pidada teie ettevõttest loobunuks.</span><span class="sxs-lookup"><span data-stu-id="48ea9-152">For example, if a customer has made no purchases in the last 30 days, they might be considered as churned for your business.</span></span> 

1. <span data-ttu-id="48ea9-153">Jätkamiseks valige **Edasi**</span><span class="sxs-lookup"><span data-stu-id="48ea9-153">Select **Next** to continue</span></span>

### <a name="add-required-data"></a><span data-ttu-id="48ea9-154">Lisage nõutud andmed</span><span class="sxs-lookup"><span data-stu-id="48ea9-154">Add required data</span></span>

1. <span data-ttu-id="48ea9-155">Valige jaotises **Ostuajalugu** suvand **Lisa andmeid** ja valige olem, mis sisaldab tehingu-/ostuajaloo teavet, nagu on kirjeldatud [eeltingimustes](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="48ea9-155">Select **Add data** for **Purchase history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="48ea9-156">Vastendage semantilised väljad oma ostuajaloo olemi atribuutidega ja valige **Järgmine**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="48ea9-157">Väljade kirjelduste kohta vaadake teavet [eeltingimustes](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="48ea9-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Ostuolemi semantiliste väljade vastendamine.":::

1. <span data-ttu-id="48ea9-159">Kui allolevad väljad pole täidetud, konfigureerige oma ostuajaloo olemis seos kliendiolemiga.</span><span class="sxs-lookup"><span data-stu-id="48ea9-159">If the fields below aren't populated, configure the relationship from your purchase history entity to the Customer entity.</span></span>
    1. <span data-ttu-id="48ea9-160">Valige **Ostuajaloo olem**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="48ea9-161">Valige **Väli**, mis tuvastab kliendi ostuajaloo olemis.</span><span class="sxs-lookup"><span data-stu-id="48ea9-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="48ea9-162">See peab olema seostatud teie kliendiolemi esmase kliendi ID-ga.</span><span class="sxs-lookup"><span data-stu-id="48ea9-162">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="48ea9-163">Valige **Kliendi olem**, mis vastab teie peamisele kliendiolemile.</span><span class="sxs-lookup"><span data-stu-id="48ea9-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="48ea9-164">Tippige seost kirjeldav nimi.</span><span class="sxs-lookup"><span data-stu-id="48ea9-164">Enter a name that describes the relationship.</span></span>

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Ostuajaluu leht, millel on näha kliendiga seose loomine.":::
   
1. <span data-ttu-id="48ea9-166">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-166">Select **Next**.</span></span>

1. <span data-ttu-id="48ea9-167">Soovi korral valige jaotises **Klienditegevused** suvand **Lisa andmed**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-167">Optionally, select **Add data** for **Customer activities**.</span></span> <span data-ttu-id="48ea9-168">Valige olem, mis sisaldab klienditegevuse teavet, nagu on kirjeldatud eeltingimustes.</span><span class="sxs-lookup"><span data-stu-id="48ea9-168">Choose the entity that provides the customer activity information as described in the prerequisites.</span></span>

1. <span data-ttu-id="48ea9-169">Vastendage semantilised väljad oma klienditegevuse olemi atribuutidega ja valige **Järgmine**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-169">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span> <span data-ttu-id="48ea9-170">Väljade kirjelduste kohta vaadake teavet [eeltingimustes](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="48ea9-170">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Kliendiväljade vastendamine tehinguandmete saamiseks.":::

1. <span data-ttu-id="48ea9-172">Valige tegevuse tüüp, mis vastab konfigureeritavale kliendi tegevuse tüübile.</span><span class="sxs-lookup"><span data-stu-id="48ea9-172">Select an activity type that matches to the type of customer activity you're configuring.</span></span> <span data-ttu-id="48ea9-173">Valige **Loo uus** ja valige saadaolev tegevusetüüp või looge uus tüüp.</span><span class="sxs-lookup"><span data-stu-id="48ea9-173">Select **Create new** and choose an available activity type or create a new type.</span></span>

1. <span data-ttu-id="48ea9-174">Peate konfigureerima kliendiolemile seose kliendi tegevuse olemist.</span><span class="sxs-lookup"><span data-stu-id="48ea9-174">You'll need to configure the relationship from your customer activity entity to the Customer entity.</span></span>
    1. <span data-ttu-id="48ea9-175">Valige väli, mis tuvastab kliendi klienditegevuse tabelis.</span><span class="sxs-lookup"><span data-stu-id="48ea9-175">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="48ea9-176">See võib olla otse kliendiolemi peamise kliendi-ID-ga.</span><span class="sxs-lookup"><span data-stu-id="48ea9-176">It can be directly related to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="48ea9-177">Valige kliendi olem, mis vastab teie peamisele kliendi olemile</span><span class="sxs-lookup"><span data-stu-id="48ea9-177">Select the Customer entity that matches your primary Customer entity</span></span>
    1. <span data-ttu-id="48ea9-178">Tippige seost kirjeldav nimi.</span><span class="sxs-lookup"><span data-stu-id="48ea9-178">Enter a name that describes the relationship.</span></span>

1. <span data-ttu-id="48ea9-179">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-179">Select **Save**.</span></span>

1. <span data-ttu-id="48ea9-180">Kui teil on mõni muu klienditegevus, mida soovite kaasata, korrake ülaltoodud samme.</span><span class="sxs-lookup"><span data-stu-id="48ea9-180">If you have any other customer activities you would like to include, repeat the steps above.</span></span>

1. <span data-ttu-id="48ea9-181">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-181">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="48ea9-182">Ajakava seadistamine ja konfiguratsiooni ülevaatamine</span><span class="sxs-lookup"><span data-stu-id="48ea9-182">Set schedule and review configuration</span></span>

1. <span data-ttu-id="48ea9-183">Määrake oma mudeli ümberõppe sagedus.</span><span class="sxs-lookup"><span data-stu-id="48ea9-183">Set a frequency to retrain your model.</span></span> <span data-ttu-id="48ea9-184">See säte on oluline, et värskendada prognooside täpsust uute andmete valmendamisel.</span><span class="sxs-lookup"><span data-stu-id="48ea9-184">This setting is important to update the accuracy of predictions as new data is ingested.</span></span> <span data-ttu-id="48ea9-185">Suur osa ettevõtteid saavad teha ümberõpet kord kuus ja saavutavad täpsed prognoosid.</span><span class="sxs-lookup"><span data-stu-id="48ea9-185">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="48ea9-186">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-186">Select **Next**.</span></span>

1. <span data-ttu-id="48ea9-187">Vaadake prognoosi konfiguratsiooni üle.</span><span class="sxs-lookup"><span data-stu-id="48ea9-187">Review the configuration of the prediction.</span></span> <span data-ttu-id="48ea9-188">Saate tagasi minna eelmiste etappide juurde, valides kuvatud väärtuse all **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-188">You can go back to prior steps by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="48ea9-189">Saate ka valida edenemise näidikust konfiguratsiooni etapi.</span><span class="sxs-lookup"><span data-stu-id="48ea9-189">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="48ea9-190">Kui kõik väärtused on õigesti konfigureeritud, valige pognoosimisprotsessi alustamiseks suvand **Salvesta ja käivita**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-190">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="48ea9-191">Vahekaardil **Minu prognoosid** kuvatakse teie prognooside olekut.</span><span class="sxs-lookup"><span data-stu-id="48ea9-191">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="48ea9-192">Selle protsessi lõpule viimiseks võib kuluda mitu tundi, olenevalt prognoosis kasutatud andmete hulgast.</span><span class="sxs-lookup"><span data-stu-id="48ea9-192">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="48ea9-193">Prognoosi oleku ja tulemuste läbivaatamine</span><span class="sxs-lookup"><span data-stu-id="48ea9-193">Review a prediction status and results</span></span>

1. <span data-ttu-id="48ea9-194">Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-194">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="48ea9-195">Valige prognoos, mille soovite üle vaadata.</span><span class="sxs-lookup"><span data-stu-id="48ea9-195">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="48ea9-196">**Prognoosi nimi:** prognoosi loomisel sellele pandud nimi.</span><span class="sxs-lookup"><span data-stu-id="48ea9-196">**Prediction name:** Name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="48ea9-197">**Prognoosi tüüp:** prognoosi jaoks kasutatud mudeli tüüp</span><span class="sxs-lookup"><span data-stu-id="48ea9-197">**Prediction type:** Type of model used for the prediction</span></span>
   - <span data-ttu-id="48ea9-198">**Väljundolem:** olemi nimi, kuhu talletatakse prognoosi väljund.</span><span class="sxs-lookup"><span data-stu-id="48ea9-198">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="48ea9-199">Selle nimega olemi leiate jaotisest **Andmed** > **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-199">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="48ea9-200">**Prognoositav väli:** see väli täidetakse ainult kindlat tüüpi prognooside korral ja seda ei kasutata voolavuse prognoosimisel.</span><span class="sxs-lookup"><span data-stu-id="48ea9-200">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="48ea9-201">**Olek:** prognoosi käitamise olek.</span><span class="sxs-lookup"><span data-stu-id="48ea9-201">**Status:** Status of the prediction run.</span></span>
        - <span data-ttu-id="48ea9-202">**Järjekorras:** prognoos ootab muude protsesside käivitamist.</span><span class="sxs-lookup"><span data-stu-id="48ea9-202">**Queued:** Prediction is waiting for other processes to run.</span></span>
        - <span data-ttu-id="48ea9-203">**Värskendamine:** prognoos töötab praegu, et luua tulemusi, mis sisestatakse väljundolemisse.</span><span class="sxs-lookup"><span data-stu-id="48ea9-203">**Refreshing:** Prediction is currently running to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="48ea9-204">**Nurjunud:** prognoosi käitamine nurjus.</span><span class="sxs-lookup"><span data-stu-id="48ea9-204">**Failed:** Prediction run has failed.</span></span> <span data-ttu-id="48ea9-205">Lisateabe saamiseks [vaadake üle logid](#troubleshoot-a-failed-prediction).</span><span class="sxs-lookup"><span data-stu-id="48ea9-205">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
        - <span data-ttu-id="48ea9-206">**Õnnestus:** prognoos on õnnestunud.</span><span class="sxs-lookup"><span data-stu-id="48ea9-206">**Succeeded:** Prediction has succeeded.</span></span> <span data-ttu-id="48ea9-207">Valige prognoosi läbivaatamiseks **Vaade** vertikaalse kolmikpunkti juures</span><span class="sxs-lookup"><span data-stu-id="48ea9-207">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="48ea9-208">**Redigeeritud:** prognoosi konfiguratsiooni muutmise kuupäev.</span><span class="sxs-lookup"><span data-stu-id="48ea9-208">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="48ea9-209">**Viimati värskendatud:** kuupäev, mil prognoos värskendas tulemusi väljundolemis.</span><span class="sxs-lookup"><span data-stu-id="48ea9-209">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="48ea9-210">Valige vertikaalne kolmikpunkt prognoosi kõrval, mille tulemusi soovite läbivaadata ja valige **Vaade**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-210">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Juhtelement „Kuva“ prognoosi tulemuste vaatamiseks.":::   

1. <span data-ttu-id="48ea9-212">Tulemuste lehel on kolm peamist andmete jaotist.</span><span class="sxs-lookup"><span data-stu-id="48ea9-212">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="48ea9-213">**Koolituse mudeli jõudlus:** võimalikud punktisummad on A, B või C.</span><span class="sxs-lookup"><span data-stu-id="48ea9-213">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="48ea9-214">See skoor näitab prognoosi jõudlust ja aitab teil otsustada, kas kasutada väljundolemis talletatud tulemusi.</span><span class="sxs-lookup"><span data-stu-id="48ea9-214">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="48ea9-215">Skoorid määratletakse järgmiste reeglite alusel.</span><span class="sxs-lookup"><span data-stu-id="48ea9-215">Scores are determined based on the following rules:</span></span>
         
         - <span data-ttu-id="48ea9-216">**A**, kui vähemalt 50% kõikidest prognoosidest olid täpsed ja kui täpsete loobunud klientide prognooside protsent on alusmäärast vähemalt 10% suurem.</span><span class="sxs-lookup"><span data-stu-id="48ea9-216">**A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is greater than the baseline rate by at least 10%.</span></span>
            
         - <span data-ttu-id="48ea9-217">**B**, kui vähemalt 50% kõikidest prognoosidest olid täpsed ja kui täpsete loobunud klientide prognooside protsent on alusmäärast kuni 10% suurem.</span><span class="sxs-lookup"><span data-stu-id="48ea9-217">**B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is up to 10% greater than the baseline.</span></span>
            
         - <span data-ttu-id="48ea9-218">**C**, kui vähem kui 50% kõikidest prognoosidest olid täpsed või kui täpsete loobunud klientide prognooside protsent on alusmäärast väiksem.</span><span class="sxs-lookup"><span data-stu-id="48ea9-218">**C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for customers who churned is less than the baseline.</span></span>
               
         - <span data-ttu-id="48ea9-219">**Aluse** jaoks võetakse mudeli prognoosiajavahemiku sisend (näiteks üks aasta) ja luuakse eri ajalõigud, jagades ajavahemikku kahega, kuni see on üks kuu või väiksem.</span><span class="sxs-lookup"><span data-stu-id="48ea9-219">**Baseline** takes the prediction time window input for the model (for example, one year) and the model creates different fractions of time by dividing it by 2 until it reaches one month or less.</span></span> <span data-ttu-id="48ea9-220">Mudel kasutab neid ajalõike, et luua ärireegel klientidele, kes pole selles ajavahemikus oste teinud.</span><span class="sxs-lookup"><span data-stu-id="48ea9-220">It uses these fractions to create a business rule for customers who have not purchased in this time frame.</span></span> <span data-ttu-id="48ea9-221">Need kliendid loetakse loobunuks.</span><span class="sxs-lookup"><span data-stu-id="48ea9-221">These customers are considered as churned.</span></span> <span data-ttu-id="48ea9-222">Alusmudeliks valitakse ajapõhine ärireegel, mis ennustab kõige täpsemini, kes võib loobuda.</span><span class="sxs-lookup"><span data-stu-id="48ea9-222">The time-based business rule with the highest ability to predict who is likely to churn is chosen as baseline model.</span></span>
            
    1. <span data-ttu-id="48ea9-223">**Voolavuse tõenäosus (klientide arv):** kliendirühmad nende prognoositud voolavuse riski põhjal.</span><span class="sxs-lookup"><span data-stu-id="48ea9-223">**Likelihood to churn (number of customers):** Groups of customers based on their predicted risk of churn.</span></span> <span data-ttu-id="48ea9-224">Need andmed aitavad teil hiljem soovi korral luua kõrge voolavuse riskiga klientide segmendi.</span><span class="sxs-lookup"><span data-stu-id="48ea9-224">This data can help you later if you want to create a segment of customers with high churn risk.</span></span> <span data-ttu-id="48ea9-225">Sellised segmendid aitavad mõista, kus segmendi liikmelisuse sulgemiskuupäev peaks olema.</span><span class="sxs-lookup"><span data-stu-id="48ea9-225">Such segments help to understand where your cutoff should be for segment membership.</span></span>
       
    1. <span data-ttu-id="48ea9-226">**Kõige mõjukamad tegurid:** prognoosi loomisel võetakse arvesse paljusid tegureid.</span><span class="sxs-lookup"><span data-stu-id="48ea9-226">**Most influential factors:** There are many factors that are taken into account when creating your prediction.</span></span> <span data-ttu-id="48ea9-227">Mudeli loodavate koondprognooside jaoks arvutatakse iga teguri olulisus.</span><span class="sxs-lookup"><span data-stu-id="48ea9-227">Each of the factors has its importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="48ea9-228">Nende tegurite abil saate oma prognoosi tulemusi kinnitada.</span><span class="sxs-lookup"><span data-stu-id="48ea9-228">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="48ea9-229">Samuti saate seda teavet hiljem kasutada [segmentide loomiseks](segments.md), mis võiksid aidata mõjutada kliendivoolavuse ohtu.</span><span class="sxs-lookup"><span data-stu-id="48ea9-229">Or you can use this information later to [create segments](segments.md) that could help influence churn risk for customers.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="48ea9-230">Nurjunud prognoosi tõrkeotsing</span><span class="sxs-lookup"><span data-stu-id="48ea9-230">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="48ea9-231">Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-231">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="48ea9-232">Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mille tõrkelogisid soovite vaadata.</span><span class="sxs-lookup"><span data-stu-id="48ea9-232">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="48ea9-233">Valige **Logid**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-233">Select **Logs**.</span></span>

1. <span data-ttu-id="48ea9-234">Kõikide tõrgete läbivaatamine.</span><span class="sxs-lookup"><span data-stu-id="48ea9-234">Review all the errors.</span></span> <span data-ttu-id="48ea9-235">Esineda võib mitmesuguseid tüüpe tõrkeid ja need kirjeldavad, mis olukord selle tõrke tekitad.</span><span class="sxs-lookup"><span data-stu-id="48ea9-235">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="48ea9-236">Näiteks tõrge, et täpse prognoosi tegemiseks pole piisavalt andmeid, lahendatakse tavaliselt täiendavate andmete laadimisel Customer Insightsis.</span><span class="sxs-lookup"><span data-stu-id="48ea9-236">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="48ea9-237">Prognoosi värskendamine</span><span class="sxs-lookup"><span data-stu-id="48ea9-237">Refresh a prediction</span></span>

<span data-ttu-id="48ea9-238">Prognoose värskendatakse automaatselt [teie andmete värskendamiste ajakava](system.md#schedule-tab) järgi, mis on sätetes konfigureeritud.</span><span class="sxs-lookup"><span data-stu-id="48ea9-238">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="48ea9-239">Neid saab värskendada ka käsitsi.</span><span class="sxs-lookup"><span data-stu-id="48ea9-239">You can refresh them manually too.</span></span>

1. <span data-ttu-id="48ea9-240">Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-240">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="48ea9-241">Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mida soovite värskendada.</span><span class="sxs-lookup"><span data-stu-id="48ea9-241">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="48ea9-242">Valige **Värskenda**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-242">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="48ea9-243">Prognoosi kustutamine</span><span class="sxs-lookup"><span data-stu-id="48ea9-243">Delete a prediction</span></span>

<span data-ttu-id="48ea9-244">Prognoosi kustutamisel eemaldatakse ka selle väljundolem.</span><span class="sxs-lookup"><span data-stu-id="48ea9-244">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="48ea9-245">Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-245">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="48ea9-246">Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mida soovite kustutada.</span><span class="sxs-lookup"><span data-stu-id="48ea9-246">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="48ea9-247">Valige **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="48ea9-247">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]