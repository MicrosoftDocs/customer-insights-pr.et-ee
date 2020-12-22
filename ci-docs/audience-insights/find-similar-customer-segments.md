---
title: Sarnaste klientide leidmine tehisintellekti abil
description: Leidke tehisintellekti abil sarnaseid kliendi segmente.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405554"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="fc968-103">Sarnased kliendid (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="fc968-103">Similar Customers (preview)</span></span>

<span data-ttu-id="fc968-104">See funktsioon võimaldab tehisintellekti kasutades leida teie kliendibaasist sarnaseid kliente.</span><span class="sxs-lookup"><span data-stu-id="fc968-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="fc968-105">Selle funktsiooni kasutamiseks peab teil olema loodud vähemalt üks segment.</span><span class="sxs-lookup"><span data-stu-id="fc968-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="fc968-106">Olemasoleva segmendi kriteeriumide laiendamine aitab leida sellele segmendile sarnaseid kliente.</span><span class="sxs-lookup"><span data-stu-id="fc968-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="fc968-107">*Sarnaste klientide leidmine* kasutab automatiseeritud vahendeid andmete hindamiseks ja andmete põhjal prognooside tegemiseks ning seega saab seda kasutada ka profiilimismeetodina, nagu see mõiste on isikuandmete kaitse üldmääruses (GDPR) määratletud.</span><span class="sxs-lookup"><span data-stu-id="fc968-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="fc968-108">Kui klient seda funktsiooni andmete töötlemiseks kasutab, võivad kohalduda GDPR või muud seadused ja määrused.</span><span class="sxs-lookup"><span data-stu-id="fc968-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="fc968-109">Teie vastutate selle eest, et Dynamics 365 Customer Insightsi kasutades (sh prognoose kasutades) järgite te kõiki kohaldatavaid seadusi ja määrusi, sh eraelu puutumatuse, isikuandmete, biomeetriliste andmete, andmekaitse ja suhtluse konfidentsiaalsusega seotud seadusi.</span><span class="sxs-lookup"><span data-stu-id="fc968-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="fc968-110">Sarnaste klientide leidmine</span><span class="sxs-lookup"><span data-stu-id="fc968-110">Finding similar customers</span></span>

1. <span data-ttu-id="fc968-111">Minge sihtrühmaülevaadetes jaotisse **Segmendid** ja valige segment, mille põhjal soovite uue segmendi luua.</span><span class="sxs-lookup"><span data-stu-id="fc968-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="fc968-112">See on teie *lähtesegment*.</span><span class="sxs-lookup"><span data-stu-id="fc968-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="fc968-113">Valige tegevusribal **Leia sarnased kliendid**.</span><span class="sxs-lookup"><span data-stu-id="fc968-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="fc968-114">Vaadake uue segmendi jaoks soovitatud nimi üle ja muutke vajaduse korral seda.</span><span class="sxs-lookup"><span data-stu-id="fc968-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="fc968-115">Vaadake üle väljad, mis teie uue segmendi määratlevad.</span><span class="sxs-lookup"><span data-stu-id="fc968-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="fc968-116">Need väljad määratlevad aluse, mille põhjal süsteem proovib leida teie lähtesegmendile sarnaseid kliente.</span><span class="sxs-lookup"><span data-stu-id="fc968-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="fc968-117">Süsteem valib vaikimisi soovitatavad väljad.</span><span class="sxs-lookup"><span data-stu-id="fc968-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="fc968-118">Väljad, mis võivad mudeli jõudlust oluliselt vähendada, jäetakse automaatselt kõrvale.</span><span class="sxs-lookup"><span data-stu-id="fc968-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="fc968-119">Järgmiste andmetüüpidega väljad: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="fc968-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="fc968-120">Väljad, mille kardinaalsus (välja elementide arv) on alla 2 või üle 30</span><span class="sxs-lookup"><span data-stu-id="fc968-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="fc968-121">Valige, kas soovite kaasata uude segmenti **kõik kliendid** või ainult **kindlas olemasolevas segmendis** olevad kliendid.</span><span class="sxs-lookup"><span data-stu-id="fc968-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="fc968-122">Välistage lähtesegmendis olevad kliendid, valides märkeruudu **Välista kõik lähtesegmendis olijad**.</span><span class="sxs-lookup"><span data-stu-id="fc968-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="fc968-123">Vaikimisi soovitab süsteem väljundisse kaasata vaid 20% sihtrühma suurusest.</span><span class="sxs-lookup"><span data-stu-id="fc968-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="fc968-124">Redigeerige seda lävendit vastavalt vajadusele.</span><span class="sxs-lookup"><span data-stu-id="fc968-124">Edit this threshold as needed.</span></span> <span data-ttu-id="fc968-125">Lävendi suurendamine vähendab täpsust.</span><span class="sxs-lookup"><span data-stu-id="fc968-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="fc968-126">Valige lehe allosas käsk **Käivita**, et käivitada kahendliigituse ülesanne (masinõppe meetod), mis analüüsib andmekomplekti.</span><span class="sxs-lookup"><span data-stu-id="fc968-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="fc968-127">Sarnase segmendi vaatamine</span><span class="sxs-lookup"><span data-stu-id="fc968-127">View the similar segment</span></span>

<span data-ttu-id="fc968-128">Pärast sarnase segmendi töötlemist näete uut segmenti loetletuna lehel **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="fc968-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fc968-129">![Sarnaste klientide segmendid](media/expanded-segment.png "Sarnaste klientide segmendid")</span><span class="sxs-lookup"><span data-stu-id="fc968-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="fc968-130">Segmendi üksikasjade avamiseks valige tegevusribal käsk **Vaade**.</span><span class="sxs-lookup"><span data-stu-id="fc968-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="fc968-131">See vaade sisaldab teavet tulemi jaotuse kohta [sarnasuse skooride lõikes](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="fc968-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="fc968-132">Sarnasuse skoori väärtused leiate ka suvandis **Segmendi liikmete eelvaade**.</span><span class="sxs-lookup"><span data-stu-id="fc968-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="fc968-133">Sarnase segmendi väljundi kasutamine</span><span class="sxs-lookup"><span data-stu-id="fc968-133">Use the output of a similar segment</span></span>

<span data-ttu-id="fc968-134">Saate [sarnase segmendi väljundiga töötada](segments.md) samamoodi kui teiste segmentidega.</span><span class="sxs-lookup"><span data-stu-id="fc968-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="fc968-135">Näiteks eksportida segmendi või luua meetme.</span><span class="sxs-lookup"><span data-stu-id="fc968-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="fc968-136">Sarnaste segmentide lähtestamine ja redigeerimine</span><span class="sxs-lookup"><span data-stu-id="fc968-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="fc968-137">Sarnase segmendi värskendamiseks valige see lehel **Segmendid** ja valige tegevusribal nupp **Värskenda**.</span><span class="sxs-lookup"><span data-stu-id="fc968-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="fc968-138">Sarnase segmendi redigeerimine töötleb teie andmeid uuesti.</span><span class="sxs-lookup"><span data-stu-id="fc968-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="fc968-139">Varem loodud segmenti värskendatakse uuendatud andmetega.</span><span class="sxs-lookup"><span data-stu-id="fc968-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="fc968-140">Sarnase segmendi redigeerimiseks valige see lehel **Segmendid** ja valige tegevusribal nupp **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="fc968-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="fc968-141">Rakendage muudatused ja valige töötlemise käivitamiseks käsk **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="fc968-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="fc968-142">Sarnase segmendi kustutamine</span><span class="sxs-lookup"><span data-stu-id="fc968-142">Delete a similar segment</span></span>

<span data-ttu-id="fc968-143">Valige segment lehel **Segmendid** ja valige tegevusribal nupp **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="fc968-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="fc968-144">Seejärel kinnitage oma kustutamine.</span><span class="sxs-lookup"><span data-stu-id="fc968-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="fc968-145">Sarnasuse skoori teave</span><span class="sxs-lookup"><span data-stu-id="fc968-145">About similarity scores</span></span>

<span data-ttu-id="fc968-146">Kahendliigituse masinõppemudel määrav sarnases segmendis olevatele klientidele skoori.</span><span class="sxs-lookup"><span data-stu-id="fc968-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="fc968-147">Skoor põhineb sarnasusel lähtesegmendis olevate klientidega.</span><span class="sxs-lookup"><span data-stu-id="fc968-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="fc968-148">Sarnasuse skoor alla 0,55 on kliendid, kelle süsteem liigitab kui lähtesegmendis olevate klientidega *mitte sarnased*</span><span class="sxs-lookup"><span data-stu-id="fc968-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="fc968-149">Sarnasuse skoorid vahemikus 0,55–0,7 liigitatakse *mõnevõrra sarnaseks*</span><span class="sxs-lookup"><span data-stu-id="fc968-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="fc968-150">Sarnasuse skoorid vahemikus 0,7–0,85 liigitatakse *sarnaseks*</span><span class="sxs-lookup"><span data-stu-id="fc968-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="fc968-151">Sarnasuse skoorid vahemikus 0,85–1 on kliendid, kelle süsteem liigitas kui *väga sarnased*</span><span class="sxs-lookup"><span data-stu-id="fc968-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="fc968-152">Kliente sarnasuse skooriga alla 0,4 ei kaasata mudeli väljundisse.</span><span class="sxs-lookup"><span data-stu-id="fc968-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="fc968-153">Süsteem ei pea neid lähtesegmendiga piisavalt sarnaseks.</span><span class="sxs-lookup"><span data-stu-id="fc968-153">The system doesn't consider them similar enough to the source segment.</span></span>
