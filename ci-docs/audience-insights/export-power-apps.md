---
title: Power Apps konnektor
description: Ühendumine Power Appsi ja Power Automate'iga.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405524"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="953da-103">Microsoft Power Apps’i konnektor (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="953da-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="953da-104">Ühendatud kliendiprofiilide toomine oma isikupärastatud rakendustesse Power Appsi abil.</span><span class="sxs-lookup"><span data-stu-id="953da-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="953da-105">Power Appsi ja Dynamics 365 Customer Insightsi ühendamine</span><span class="sxs-lookup"><span data-stu-id="953da-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="953da-106">Customer Insights on üks paljudest [Power Appsis saadaolevatest andmeallikatest](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="953da-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="953da-107">Vaadake Power Appsi  dokumentatsiooni, et saada teada, kuidas [lisada rakendusele andmeühendust](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="953da-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="953da-108">Soovitame teil ka vaadata üle ka teema [Kuidas Power Apps kasutab delegeerimist lõuendirakendustes suurte andmekogumite käsitlemiseks](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="953da-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="953da-109">Saadaolevad olemid</span><span class="sxs-lookup"><span data-stu-id="953da-109">Available entities</span></span>

<span data-ttu-id="953da-110">Pärast Customer Insightsi andmeühendusena lisamist saate Power Appsis valida järgmised olemid.</span><span class="sxs-lookup"><span data-stu-id="953da-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="953da-111">Klient: [ühendatud kliendiprofiili](customer-profiles.md) andmete kasutamine.</span><span class="sxs-lookup"><span data-stu-id="953da-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="953da-112">Ühendatud kliendi tegevus: [tegevuse ajaskaala](activities.md) kuvamine rakenduses.</span><span class="sxs-lookup"><span data-stu-id="953da-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="953da-113">Piirangud</span><span class="sxs-lookup"><span data-stu-id="953da-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="953da-114">Toodavad olemid</span><span class="sxs-lookup"><span data-stu-id="953da-114">Retrievable entities</span></span>

<span data-ttu-id="953da-115">Saate tuua ainult olemid **Klient**, **UnifiedActivity** ja **Segmendid** Power Appsi konnektori kaudu.</span><span class="sxs-lookup"><span data-stu-id="953da-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="953da-116">Teised olemid on näidatud, kuna aluseks olevad konnektorid toetavad neid läbi Power Automate’i päästikute.</span><span class="sxs-lookup"><span data-stu-id="953da-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="953da-117">Delegeerimine</span><span class="sxs-lookup"><span data-stu-id="953da-117">Delegation</span></span>

<span data-ttu-id="953da-118">Delegeerimine töötab ainult olemi Klient ja olemi UnifiedActivity jaoks.</span><span class="sxs-lookup"><span data-stu-id="953da-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="953da-119">Olemi **Klient** delegatsioon: selle olemi korral delegatsiooni kasutamiseks peavad väljad olema indekseeritud [Otsingu- ja filtriregistris](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="953da-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="953da-120">Olemi **UnifiedActivity** delegeerimine: selle olemi delegeerimine töötab ainult väljade **ActivityId** ja **CustomerId** jaoks.</span><span class="sxs-lookup"><span data-stu-id="953da-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="953da-121">Lisateavet delegeerimise kohta leiate teemast [Power Appsi delegeeritavad funktsioonid ja toimingud](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="953da-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="953da-122">Galerii juhtelemendi näide</span><span class="sxs-lookup"><span data-stu-id="953da-122">Example gallery control</span></span>

<span data-ttu-id="953da-123">Näiteks lisate kliendiprofiilid [galerii juhtelementi](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="953da-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="953da-124">Lisage loodavale rakendusele **Galerii** juhtelement.</span><span class="sxs-lookup"><span data-stu-id="953da-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="953da-125">![Galerii elemendi lisamine](media/connector-powerapps9.png "Galerii elemendi lisamine")</span><span class="sxs-lookup"><span data-stu-id="953da-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="953da-126">Valige üksuste andmeallikaks **Klient**.</span><span class="sxs-lookup"><span data-stu-id="953da-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="953da-127">![Andmeallika valimine](media/choose-datasource-powerapps.png "Andmeallika valimine")</span><span class="sxs-lookup"><span data-stu-id="953da-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="953da-128">Kliendi olemi galerii välja valimiseks saate muuta paremal asuvat andmete paneeli.</span><span class="sxs-lookup"><span data-stu-id="953da-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="953da-129">Kui tahate näidata galeriis valitud kliendi mistahes välja, täitke sildi teksti atribuut:  **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="953da-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="953da-130">Näide: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="953da-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="953da-131">Kliendi ühtse ajajoone näitamiseks lisage galerii element ja üksuste atribuut: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="953da-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="953da-132">Näide: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="953da-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
