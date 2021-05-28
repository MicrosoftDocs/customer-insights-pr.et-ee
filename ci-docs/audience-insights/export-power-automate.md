---
title: Power Automate konnektor | Microsoft Docs
description: Looge voogusid Microsoft Power Automate'is Dynamics 365 Customer Insightsist
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976083"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="c7ceb-103">Power Automate’i konnektor (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="c7ceb-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="c7ceb-104">Käivitage konkreetsed sündmused, mis ilmnevad automaatselt andmete muutmisel ja hallake keerulisemaid vooge otse [Power Automate](https://flow.microsoft.com/)'is.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="c7ceb-105">Power Automate'i päästikud</span><span class="sxs-lookup"><span data-stu-id="c7ceb-105">Power Automate triggers</span></span>

<span data-ttu-id="c7ceb-106">Saate kasutada päästikuid pilvevoogude loomiseks ja korduvate ülesannete (nt teatiste ja keerukamate toimingute) automatiseerimiseks.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="c7ceb-107">Käivitub, kui andmeallika värskendamine nurjub.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="c7ceb-108">Käivitub, kui andmeallika värskendamine õnnestub.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="c7ceb-109">Käivitub, kui segmendi lävi ületatakse.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="c7ceb-110">Päästiku piiranguks on läve ületamine.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="c7ceb-111">Käivitub, kui ärimeetme lävi ületatakse.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="c7ceb-112">Toetatakse ainult ilma dimensioonita ärinäitajad.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="c7ceb-113">Päästiku piiranguks on läve ületamine.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="c7ceb-114">Käivitub, kui lõpule on viidud (andmeallikate, segmentide, näitajate, ...) täielik värskendamine.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="c7ceb-115">Käivitub, kui ühendamisprotsess (kaardistamine, vastendamine, liitmine) on lõpule viidud.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="c7ceb-116">[Päästikute konfigureerimine Power Automate'is](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="c7ceb-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="c7ceb-117">Power Automate'i toimingud</span><span class="sxs-lookup"><span data-stu-id="c7ceb-117">Power Automate actions</span></span>
<span data-ttu-id="c7ceb-118">Power Automate'i konnektor pakub saadaolevatest päästikutest erinevaid toiminguid.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="c7ceb-119">Lisateavet leiate juhendist [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="c7ceb-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="c7ceb-120">Power Automate'i voo loomine</span><span class="sxs-lookup"><span data-stu-id="c7ceb-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="c7ceb-121">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c7ceb-122">Valige **Power Automate'i** paanil suvand **Seadista**.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="c7ceb-123">Avaneb Power Automate'i Customer Insightsi konnektor (eelversioon).</span><span class="sxs-lookup"><span data-stu-id="c7ceb-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="c7ceb-124">**Logige sisse** rakendusse Power Automate.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="c7ceb-125">Valige üks võimalikest päästikutest ja lisage oma uuele voole veel etappe.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="c7ceb-126">Lisateavet leiate teemast [Pilvevoo loomine Power Automate'is](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="c7ceb-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="c7ceb-127">Näited voogude kasutamise kohta.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="c7ceb-128">Sõnumi postitamine Microsoft Teamsi kanalisse juhul, kui andmeallika värskendamine nurjub.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="c7ceb-129">Meili saatmine andmete omanikele segmendi läve ületamisel.</span><span class="sxs-lookup"><span data-stu-id="c7ceb-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
