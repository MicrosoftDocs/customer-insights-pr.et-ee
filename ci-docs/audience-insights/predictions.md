---
title: Osaliste andmete täiendamine prognooside abil
description: Kasutage prognoose, et täiendada mittetäielikke kliendiandmeid.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 66f0b16b5d05741ab98ca5ce2157da8c46b6d9e0
ms.sourcegitcommit: 5379c2b77d613d071a177f509e6417ebf3c47516
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/26/2020
ms.locfileid: "4648706"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="9d895-103">Osaliste andmete lõpetamine prognooside abil</span><span class="sxs-lookup"><span data-stu-id="9d895-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9d895-104">Prognooside abil saate hõlpsalt luua ennustatud väärtusi, mis aitavad suurendada teie arusaamist kliendist.</span><span class="sxs-lookup"><span data-stu-id="9d895-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="9d895-105">Saate valida lehel **Ärianalüüs** > **Prognoosid** suvandi **Minu prognoosid**, et näha prognoose, mille olete konfigureerinud sihtrühmaülevaadetes muudes kohtades, ning neid veelgi kohandada.</span><span class="sxs-lookup"><span data-stu-id="9d895-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="9d895-106">Seda funktsiooni ei saa kasutada, kui teie keskkond kasutab Azure Data Lake Gen 2 mäluruumi.</span><span class="sxs-lookup"><span data-stu-id="9d895-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="9d895-107">Prognooside funktsioon kasutab andmete hindamiseks ja andmete põhjal prognooside tegemiseks automatiseeritud vahendeid. Seetõttu on seda võimalik kasutada profileerimisviisina, selle termini isikuandmete kaitse üldmääruses (edaspidi „GDPR”) toodud definitsiooni kohaselt.</span><span class="sxs-lookup"><span data-stu-id="9d895-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="9d895-108">Kui klient seda funktsiooni andmete töötlemiseks kasutab, võivad kohalduda GDPR või muud seadused ja määrused.</span><span class="sxs-lookup"><span data-stu-id="9d895-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="9d895-109">Teie vastutate selle eest, et Dynamics 365 Customer Insightsi kasutades (sh prognoose kasutades) järgite te kõiki kohaldatavaid seadusi ja määrusi, sh eraelu puutumatuse, isikuandmete, biomeetriliste andmete, andmekaitse ja suhtluse konfidentsiaalsusega seotud seadusi.</span><span class="sxs-lookup"><span data-stu-id="9d895-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d895-110">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="9d895-110">Prerequisites</span></span>

<span data-ttu-id="9d895-111">Enne kui teie organisatsioon saab prognooside funktsiooni kasutada, peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="9d895-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="9d895-112">Teie ettevõttel on eksemplar [Common Data Service'is seadistatud](https://docs.microsoft.com/ai-builder/build-model#prerequisites) ja see on samas organisatsioonis kui Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9d895-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="9d895-113">Teie keskkond on ühendatud teie Common Data Service'i eksemplariga.</span><span class="sxs-lookup"><span data-stu-id="9d895-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="9d895-114">Kui [loote uue keskkonna](manage-environments.md), konfigureerige see dialoogis **Loo keskkond** ja valige suvand **Täpsem**.</span><span class="sxs-lookup"><span data-stu-id="9d895-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="9d895-115">Kui olete keskkonna juba loonud, minge selle sätetesse ja valige suvand **Täpsem**.</span><span class="sxs-lookup"><span data-stu-id="9d895-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="9d895-116">Mõlemal juhul sisestage jaotises **Prognooside kasutamine** Common Data Service'i eksemplari URL, millele soovite oma keskkonna lisada.</span><span class="sxs-lookup"><span data-stu-id="9d895-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="9d895-117">Prognoosi loomine kliendiolemis</span><span class="sxs-lookup"><span data-stu-id="9d895-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="9d895-118">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="9d895-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="9d895-119">Valige olem **Klient**.</span><span class="sxs-lookup"><span data-stu-id="9d895-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="9d895-120">Olemis **Klient: CustomerInsights** valige vahekaart **Väljad**.</span><span class="sxs-lookup"><span data-stu-id="9d895-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="9d895-121">Leidke atribuudi nimi, mille jaoks soovite väärtusi prognoosida, ja seejärel valige ikoon **Ülevaade** veerus **Kokkuvõte**.</span><span class="sxs-lookup"><span data-stu-id="9d895-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9d895-122">![Ülevaateikoon](media/intelligence-overviewicon.png "Ülevaateikoon")</span><span class="sxs-lookup"><span data-stu-id="9d895-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="9d895-123">Kui teie atribuudil on palju puuduvaid väärtusi, valige prognoosiga jätkamiseks suvand **Prognoosi puuduvad väärtused**.</span><span class="sxs-lookup"><span data-stu-id="9d895-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9d895-124">![Ülevaate olek koos puuduvate väärtuste prognoosimise nupuga](media/intelligence-overviewpredictmissingvalues.png "Ülevaate olek koos puuduvate väärtuste prognoosimise nupuga")</span><span class="sxs-lookup"><span data-stu-id="9d895-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="9d895-125">Esitage prognooside tulemuste jaoks **Kuvanimi** ja **Väljundi olemi nimi**.</span><span class="sxs-lookup"><span data-stu-id="9d895-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="9d895-126">Eeltäidetud suvandite loend näitab, missugused väärtused saate prognoositud kategooriatesse vastendada.</span><span class="sxs-lookup"><span data-stu-id="9d895-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="9d895-127">Sel juhul on teie ainsad kategooriavalikud 0 või 1, kuna need on vastendatavad õige/vale prognoosi või prognoosi binaarse iseloomuga.</span><span class="sxs-lookup"><span data-stu-id="9d895-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="9d895-128">Veerus Kategooria vastendage väljaväärtused, mida soovite veeru Kategooria lõplikus prognoosis kuni 0 klassifitseerida 0-na, ja üksused, mida soovite lõplikus prognoosis kuni 1 klassifitseerida 1-na.</span><span class="sxs-lookup"><span data-stu-id="9d895-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9d895-129">![Kategooriatega vastendatud väljade väärtuste näide](media/intelligence-categorymapping.png "Kategooriatega vastendatud väljade väärtuste näide")</span><span class="sxs-lookup"><span data-stu-id="9d895-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="9d895-130">Valige **Valmis** ja prognoosi hakatakse töötlema.</span><span class="sxs-lookup"><span data-stu-id="9d895-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="9d895-131">Andmete töötlemise mahust ja keerukusest olenevalt võib töötlemine aega võtta.</span><span class="sxs-lookup"><span data-stu-id="9d895-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="9d895-132">Tulemused on saadaval uues olemis, mis põhineb teie loodud prognoosi suvandil **Väljundi olemi nimi**.</span><span class="sxs-lookup"><span data-stu-id="9d895-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="9d895-133">Prognoosi loomine segmendi loomisel</span><span class="sxs-lookup"><span data-stu-id="9d895-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="9d895-134">Mõne kindla atribuudi valimisel puuduvate väärtuste prognoosimine on võimalik ka segmendi loomisel.</span><span class="sxs-lookup"><span data-stu-id="9d895-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="9d895-135">Täpsemalt siis, kui loote kiiresti segmendi, mis põhineb kas teie ühtlustatud kliendiolemil või kliendi mõõtmise olemil.</span><span class="sxs-lookup"><span data-stu-id="9d895-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="9d895-136">Selle voo osana saate valida kindla atribuudi, mis põhineb teie segmendil (nt kliendi rahulolu või ostusumma).</span><span class="sxs-lookup"><span data-stu-id="9d895-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="9d895-137">Segmendi loomisel soovitab süsteem meetodit selle atribuudi mis tahes puuduvate väärtuste prognoosimiseks.</span><span class="sxs-lookup"><span data-stu-id="9d895-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="9d895-138">Minge sihtrühmaülevaadetes lehele **Segmendid** ja valige paan **Profiilid**.</span><span class="sxs-lookup"><span data-stu-id="9d895-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="9d895-139">Valige **Väli**, mille alusel soovite segmendi luua, ja seejärel **Tehtemärk** ja käsk **Vaata üle**.</span><span class="sxs-lookup"><span data-stu-id="9d895-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="9d895-140">Sisestage segmendi jaoks väärtused **Nimi** ja **Kuvanimi**.</span><span class="sxs-lookup"><span data-stu-id="9d895-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="9d895-141">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="9d895-141">Select **Save**.</span></span>

5. <span data-ttu-id="9d895-142">Kui äsja loodud segmendil allikavälja andmed on puudulikud, saate valida puuduvate väärtuste prognoosimise.</span><span class="sxs-lookup"><span data-stu-id="9d895-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9d895-143">![Nupp Prognoos](media/segments-predictoption.png "Nupp Prognoos")</span><span class="sxs-lookup"><span data-stu-id="9d895-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="9d895-144">Esitage prognooside tulemuste jaoks **Kuvanimi** ja **Väljundi olemi nimi**.</span><span class="sxs-lookup"><span data-stu-id="9d895-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="9d895-145">Valige nupp **Valmis**.</span><span class="sxs-lookup"><span data-stu-id="9d895-145">Select **Done**.</span></span> <span data-ttu-id="9d895-146">Teie prognoos luuakse peatselt uues olemis nimega, mille sisestasite suvandi **Väljundi olemi nimi** jaoks.</span><span class="sxs-lookup"><span data-stu-id="9d895-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="9d895-147">Prognoosi kuvamine</span><span class="sxs-lookup"><span data-stu-id="9d895-147">View a prediction</span></span>

1. <span data-ttu-id="9d895-148">Avage sihtrühmaülevaadetes jaotis **Ärianalüüs** > **Prognoosid** > **Minu prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="9d895-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9d895-149">Valige prognoos, mille soovite üle vaadata.</span><span class="sxs-lookup"><span data-stu-id="9d895-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="9d895-150">Valige kolmikpunkt veerus **Toimingud** ja seejärel **Vaade**.</span><span class="sxs-lookup"><span data-stu-id="9d895-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="9d895-151">Näete prognoosi vaates andmepunktide arvu.</span><span class="sxs-lookup"><span data-stu-id="9d895-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9d895-152">![Prognooside leht](media/intelligence-predictionsviewpage.png "Prognooside leht")</span><span class="sxs-lookup"><span data-stu-id="9d895-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="9d895-153">**Prognoositud väärtused** näitavad vastendust, mille lõite väljaväärtuse ja kategooria vastendamisel.</span><span class="sxs-lookup"><span data-stu-id="9d895-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="9d895-154">Need on teie andmekomplektis olevad väärtused, mis on vastendatud kindla kategooriaga.</span><span class="sxs-lookup"><span data-stu-id="9d895-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="9d895-155">-**Peamised mõjutajad** on teie andmekomplekti tegurid, mis mõjutavad kõige tõenäolisemalt prognoosi usaldusväärsust teie väljaväärtuse vastendamisel kindla kategooriaga.</span><span class="sxs-lookup"><span data-stu-id="9d895-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="9d895-156">**Jõudlus** näitab prognooside edenemist.</span><span class="sxs-lookup"><span data-stu-id="9d895-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="9d895-157">Lisateabe saamiseks valige soovitud link.</span><span class="sxs-lookup"><span data-stu-id="9d895-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="9d895-158">**Eelvaade** kuvab teie prognooside ja tõenäosuste väljundi andmekogumi näited, või meie usalduse väärtused eeldatava väärtusega, kus 0 on ebakindel ja 1 on kindel.</span><span class="sxs-lookup"><span data-stu-id="9d895-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="9d895-159">Prognoosi värskendamine</span><span class="sxs-lookup"><span data-stu-id="9d895-159">Update a prediction</span></span>

1. <span data-ttu-id="9d895-160">Avage sihtrühmaülevaadetes jaotis **Ärianalüüs** > **Prognoosid** > **Minu prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="9d895-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9d895-161">Valige prognoos, mida soovite värskendada, ja seejärel ikoon **Värskenda**.</span><span class="sxs-lookup"><span data-stu-id="9d895-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="9d895-162">Prognoos kavandatakse töötlemiseks.</span><span class="sxs-lookup"><span data-stu-id="9d895-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="9d895-163">Lehe **Prognoosid** veerus **Värskendatud** saate vaadata, millal seda viimati värskendati.</span><span class="sxs-lookup"><span data-stu-id="9d895-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="9d895-164">Prognoosi redigeerimine</span><span class="sxs-lookup"><span data-stu-id="9d895-164">Edit a prediction</span></span>

<span data-ttu-id="9d895-165">Kui olete prognoosi loonud, saate oma mudeli efektiivsuse tõstmiseks kohandada ka AI Builderi mudelit.</span><span class="sxs-lookup"><span data-stu-id="9d895-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="9d895-166">Avage sihtrühmaülevaadetes jaotis **Ärianalüüs** > **Prognoosid** > **Minu prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="9d895-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9d895-167">Valige prognoos, mida soovite redigeerida.</span><span class="sxs-lookup"><span data-stu-id="9d895-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="9d895-168">Valige kolmikpunkt veerus **Toimingud** ja seejärel **Vaade**.</span><span class="sxs-lookup"><span data-stu-id="9d895-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="9d895-169">Valige käsk **Kohanda AI Builderis**.</span><span class="sxs-lookup"><span data-stu-id="9d895-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="9d895-170">Värskendage oma mudelit AI Builderis.</span><span class="sxs-lookup"><span data-stu-id="9d895-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="9d895-171">[Lisateave AI Builderis mudelite haldamise kohta](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="9d895-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="9d895-172">Teie prognoosi järgmiseks käivitamiseks kasutatakse teie loodud värskendatud mudelit.</span><span class="sxs-lookup"><span data-stu-id="9d895-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="9d895-173">AI Builderis loodud uusi mudeleid ei kuvata sihtrühmaülevaadetes, välja arvatud juhul, kui mudel on loodud eespool loetletud kogemuste põhjal.</span><span class="sxs-lookup"><span data-stu-id="9d895-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="9d895-174">Prognoosi eemaldamine</span><span class="sxs-lookup"><span data-stu-id="9d895-174">Remove a prediction</span></span>

1. <span data-ttu-id="9d895-175">Avage sihtrühmaülevaadetes jaotis **Ärianalüüs** > **Prognoosid** > **Minu prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="9d895-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="9d895-176">Valige prognoos, mille soovite kustutada.</span><span class="sxs-lookup"><span data-stu-id="9d895-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="9d895-177">Valige veerus **Toimingud** kolmikpunkt ja seejärel käsk **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="9d895-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="9d895-178">Kinnitage kustutamine.</span><span class="sxs-lookup"><span data-stu-id="9d895-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9d895-179">Tõrkeotsing</span><span class="sxs-lookup"><span data-stu-id="9d895-179">Troubleshooting</span></span>

<span data-ttu-id="9d895-180">Kui te ei saa tõrke tõttu Common Data Service'i manustamise protsessi lõpule viia, võite proovida protsessi käsitsi lõpule viia.</span><span class="sxs-lookup"><span data-stu-id="9d895-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="9d895-181">On kaks teadaolevat probleemi, mis võivad manustamise protsessis esineda.</span><span class="sxs-lookup"><span data-stu-id="9d895-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="9d895-182">Kliendikaardi lisandmooduli lahendus pole installitud.</span><span class="sxs-lookup"><span data-stu-id="9d895-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="9d895-183">Täitke [lahenduse installimise ja konfigureerimise](customer-card-add-in.md) juhised.</span><span class="sxs-lookup"><span data-stu-id="9d895-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="9d895-184">Rakenduse õiguseid pole antud.</span><span class="sxs-lookup"><span data-stu-id="9d895-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="9d895-185">Avage [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="9d895-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="9d895-186">Seejärel valige **Keskkonnad**.</span><span class="sxs-lookup"><span data-stu-id="9d895-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="9d895-187">Valige kolmikpunkt selle keskkonna kõrval, millele soovite õigused lisada, ja valige **Sätted**.</span><span class="sxs-lookup"><span data-stu-id="9d895-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="9d895-188">Laiendage jaotis **Kasutajad + õigused** ja valige **Kasutajad**.</span><span class="sxs-lookup"><span data-stu-id="9d895-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="9d895-189">Valige **+ Uus** ja valige **Kasutaja**.</span><span class="sxs-lookup"><span data-stu-id="9d895-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="9d895-190">Valige **Rakenduse kasutaja**, kui see pole juba valitud, ja sisestage järgmised andmed.</span><span class="sxs-lookup"><span data-stu-id="9d895-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="9d895-191">**Kasutaja nimi:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9d895-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="9d895-192">**Rakenduse ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="9d895-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="9d895-193">**Eesnimi:** Customer</span><span class="sxs-lookup"><span data-stu-id="9d895-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="9d895-194">**Perekonnanimi:** Insights</span><span class="sxs-lookup"><span data-stu-id="9d895-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="9d895-195">**Esmane meiliaadress:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="9d895-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="9d895-196">Valige **Salvesta ja sule**.</span><span class="sxs-lookup"><span data-stu-id="9d895-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="9d895-197">Valige äsja loodud kasutaja.</span><span class="sxs-lookup"><span data-stu-id="9d895-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="9d895-198">Valige ülemiselt menüüribalt suvand **Halda rolle**.</span><span class="sxs-lookup"><span data-stu-id="9d895-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="9d895-199">Valige **Süsteemiadministraator** ja seejärel valige **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d895-199">Select **System Administrator**, then select **OK**.</span></span>
