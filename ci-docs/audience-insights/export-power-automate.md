---
title: Power Automate konnektor | Microsoft Docs
description: Looge voogusid Microsoft Power Automate'is Dynamics 365 Customer Insightsist
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597920"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="d0980-103">Power Automate’i konnektor (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="d0980-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="d0980-104">Käivitage konkreetsed sündmused, mis ilmnevad automaatselt andmete muutmisel ja hallake keerulisemaid vooge otse [Power Automate](https://flow.microsoft.com/)'is.</span><span class="sxs-lookup"><span data-stu-id="d0980-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="d0980-105">Power Automate'i päästikud</span><span class="sxs-lookup"><span data-stu-id="d0980-105">Power Automate triggers</span></span>

<span data-ttu-id="d0980-106">Saate kasutada päästikuid pilvevoogude loomiseks ja korduvate ülesannete (nt teatiste ja keerukamate toimingute) automatiseerimiseks.</span><span class="sxs-lookup"><span data-stu-id="d0980-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="d0980-107">Käivitub, kui andmeallika värskendamine nurjub.</span><span class="sxs-lookup"><span data-stu-id="d0980-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="d0980-108">Käivitub, kui andmeallika värskendamine õnnestub.</span><span class="sxs-lookup"><span data-stu-id="d0980-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="d0980-109">Käivitub, kui segmendi lävi ületatakse.</span><span class="sxs-lookup"><span data-stu-id="d0980-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="d0980-110">Päästiku piiranguks on läve ületamine.</span><span class="sxs-lookup"><span data-stu-id="d0980-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="d0980-111">Käivitub, kui ärimeetme lävi ületatakse.</span><span class="sxs-lookup"><span data-stu-id="d0980-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="d0980-112">Päästiku piiranguks on läve ületamine.</span><span class="sxs-lookup"><span data-stu-id="d0980-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="d0980-113">Käivitub, kui lõpule on viidud (andmeallikate, segmentide, näitajate, ...) täielik värskendamine.</span><span class="sxs-lookup"><span data-stu-id="d0980-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="d0980-114">Käivitub, kui ühendamisprotsess (kaardistamine, vastendamine, liitmine) on lõpule viidud.</span><span class="sxs-lookup"><span data-stu-id="d0980-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="d0980-115">[Päästikute konfigureerimine Power Automate'is](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="d0980-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="d0980-116">Power Automate'i toimingud</span><span class="sxs-lookup"><span data-stu-id="d0980-116">Power Automate actions</span></span>
<span data-ttu-id="d0980-117">Power Automate'i konnektor pakub saadaolevatest päästikutest erinevaid toiminguid.</span><span class="sxs-lookup"><span data-stu-id="d0980-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="d0980-118">Lisateavet leiate juhendist [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="d0980-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="d0980-119">Power Automate'i voo loomine</span><span class="sxs-lookup"><span data-stu-id="d0980-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="d0980-120">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="d0980-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d0980-121">Valige **Power Automate'i** paanil suvand **Seadista**.</span><span class="sxs-lookup"><span data-stu-id="d0980-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="d0980-122">Avaneb Power Automate'i Customer Insightsi konnektor (eelversioon).</span><span class="sxs-lookup"><span data-stu-id="d0980-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="d0980-123">**Logige sisse** rakendusse Power Automate.</span><span class="sxs-lookup"><span data-stu-id="d0980-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="d0980-124">Valige üks võimalikest päästikutest ja lisage oma uuele voole veel etappe.</span><span class="sxs-lookup"><span data-stu-id="d0980-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="d0980-125">Lisateavet leiate teemast [Pilvevoo loomine Power Automate'is](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="d0980-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="d0980-126">Näited voogude kasutamise kohta.</span><span class="sxs-lookup"><span data-stu-id="d0980-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="d0980-127">Sõnumi postitamine Microsoft Teamsi kanalisse juhul, kui andmeallika värskendamine nurjub.</span><span class="sxs-lookup"><span data-stu-id="d0980-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="d0980-128">Meili saatmine andmete omanikele segmendi läve ületamisel.</span><span class="sxs-lookup"><span data-stu-id="d0980-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]