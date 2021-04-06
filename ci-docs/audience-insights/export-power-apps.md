---
title: Power Apps konnektor
description: Ühendumine Power Appsi ja Power Automate'iga.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598150"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="6f657-103">Microsoft Power Apps’i konnektor (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="6f657-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="6f657-104">Ühendatud kliendiprofiilide toomine oma isikupärastatud rakendustesse Power Appsi abil.</span><span class="sxs-lookup"><span data-stu-id="6f657-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="6f657-105">Power Appsi ja Dynamics 365 Customer Insightsi ühendamine</span><span class="sxs-lookup"><span data-stu-id="6f657-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="6f657-106">Customer Insights on üks paljudest [Power Appsis saadaolevatest andmeallikatest](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="6f657-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="6f657-107">Vaadake Power Appsi  dokumentatsiooni, et saada teada, kuidas [lisada rakendusele andmeühendust](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="6f657-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="6f657-108">Soovitame teil ka vaadata üle ka teema [Kuidas Power Apps kasutab delegeerimist lõuendirakendustes suurte andmekogumite käsitlemiseks](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="6f657-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="6f657-109">Saadaolevad olemid</span><span class="sxs-lookup"><span data-stu-id="6f657-109">Available entities</span></span>

<span data-ttu-id="6f657-110">Pärast Customer Insightsi andmeühendusena lisamist saate Power Appsis valida järgmised olemid.</span><span class="sxs-lookup"><span data-stu-id="6f657-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="6f657-111">Klient: [ühendatud kliendiprofiili](customer-profiles.md) andmete kasutamine.</span><span class="sxs-lookup"><span data-stu-id="6f657-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="6f657-112">UnifiedActivity: rakenduses [tegevuse ajajoone](activities.md) kuvamiseks.</span><span class="sxs-lookup"><span data-stu-id="6f657-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="6f657-113">Piirangud</span><span class="sxs-lookup"><span data-stu-id="6f657-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="6f657-114">Toodavad olemid</span><span class="sxs-lookup"><span data-stu-id="6f657-114">Retrievable entities</span></span>

<span data-ttu-id="6f657-115">Saate tuua ainult olemid **Klient**, **UnifiedActivity** ja **Segmendid** Power Appsi konnektori kaudu.</span><span class="sxs-lookup"><span data-stu-id="6f657-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="6f657-116">Teised olemid on näidatud, kuna aluseks olevad konnektorid toetavad neid läbi Power Automate’i päästikute.</span><span class="sxs-lookup"><span data-stu-id="6f657-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="6f657-117">Delegeerimine</span><span class="sxs-lookup"><span data-stu-id="6f657-117">Delegation</span></span>

<span data-ttu-id="6f657-118">Delegeerimine töötab ainult olemi Klient ja olemi UnifiedActivity jaoks.</span><span class="sxs-lookup"><span data-stu-id="6f657-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="6f657-119">Olemi **Klient** delegatsioon: selle olemi korral delegatsiooni kasutamiseks peavad väljad olema indekseeritud [Otsingu- ja filtriregistris](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="6f657-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="6f657-120">Olemi **UnifiedActivity** delegeerimine: selle olemi delegeerimine töötab ainult väljade **ActivityId** ja **CustomerId** jaoks.</span><span class="sxs-lookup"><span data-stu-id="6f657-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="6f657-121">Lisateavet delegeerimise kohta leiate teemast [Power Appsi delegeeritavad funktsioonid ja toimingud](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="6f657-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="6f657-122">Galerii juhtelemendi näide</span><span class="sxs-lookup"><span data-stu-id="6f657-122">Example gallery control</span></span>

<span data-ttu-id="6f657-123">Näiteks lisate kliendiprofiilid [galerii juhtelementi](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="6f657-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="6f657-124">Lisage loodavale rakendusele **Galerii** juhtelement.</span><span class="sxs-lookup"><span data-stu-id="6f657-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6f657-125">![Galerii elemendi lisamine](media/connector-powerapps9.png "Galerii elemendi lisamine")</span><span class="sxs-lookup"><span data-stu-id="6f657-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="6f657-126">Valige üksuste andmeallikaks **Klient**.</span><span class="sxs-lookup"><span data-stu-id="6f657-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="6f657-127">![Andmeallika valimine](media/choose-datasource-powerapps.png "Andmeallika valimine")</span><span class="sxs-lookup"><span data-stu-id="6f657-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="6f657-128">Kliendi olemi galerii välja valimiseks saate muuta paremal asuvat andmete paneeli.</span><span class="sxs-lookup"><span data-stu-id="6f657-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="6f657-129">Kui tahate näidata galeriis valitud kliendi mistahes välja, täitke sildi teksti atribuut:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="6f657-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="6f657-130">Näide: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="6f657-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="6f657-131">Kliendi ühtse ajajoone näitamiseks lisage galerii element ja üksuste atribuut: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="6f657-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="6f657-132">Näide: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="6f657-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]