---
title: Power Automate konnektor | Microsoft Docs
description: Looge Microsoft Power Automate’i vooge Dynamics 365 Customer Insightsi kaudu.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405522"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="6b1bd-103">Power Automate’i konnektor (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="6b1bd-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="6b1bd-104">Käivitage konkreetsed sündmused, mis ilmnevad automaatselt andmete muutmisel ja hallake keerulisemaid vooge otse [Power Automate](https://flow.microsoft.com/)'is.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="6b1bd-105">Power Automate'i päästikud</span><span class="sxs-lookup"><span data-stu-id="6b1bd-105">Power Automate triggers</span></span>

<span data-ttu-id="6b1bd-106">Saate kasutada erinevaid päästikuid, mis võimaldavad teil luua voogusid korduvate tööülesannete automatiseerimiseks (nt teatised või täpsemaid toiminguid).</span><span class="sxs-lookup"><span data-stu-id="6b1bd-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="6b1bd-107">Käivitub, kui andmeallika värskendamine nurjub.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="6b1bd-108">Käivitub, kui andmeallika värskendamine õnnestub.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="6b1bd-109">Käivitub, kui segmendi lävi ületatakse.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="6b1bd-110">Päästiku piiranguks on läve ületamine.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="6b1bd-111">Käivitub, kui ärimeetme lävi ületatakse.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="6b1bd-112">Päästiku piiranguks on läve ületamine.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="6b1bd-113">Käivitub, kui lõpule on viidud (andmeallikate, segmentide, näitajate, ...) täielik värskendamine.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="6b1bd-114">Käivitub, kui ühendamisprotsess (kaardistamine, vastendamine, liitmine) on lõpule viidud.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="6b1bd-115">[Päästikute konfigureerimine Power Automate'is](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="6b1bd-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="6b1bd-116">Power Automate'i toimingud</span><span class="sxs-lookup"><span data-stu-id="6b1bd-116">Power Automate actions</span></span>
<span data-ttu-id="6b1bd-117">Power Automate'i konnektor pakub saadaolevatest päästikutest erinevaid toiminguid.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="6b1bd-118">Lisateavet leiate juhendist [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="6b1bd-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="6b1bd-119">Power Automate'i voo loomine sihtrühmaülevaadetes</span><span class="sxs-lookup"><span data-stu-id="6b1bd-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="6b1bd-120">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Süsteem**.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="6b1bd-121">Valige lehel **Süsteem** vahekaart **Olek**.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="6b1bd-122">Valige jaotises **Andmeallikad** suvand **Vood** ja valige ripploendist **Voo loomine**.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6b1bd-123">![Power Automate’i konnektor, mis näitab voo loomise toimingut](media/power-automate-connector-create-flow.png "Voo loomise toimingut näitav rakenduse Power Automate konnektor")</span><span class="sxs-lookup"><span data-stu-id="6b1bd-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="6b1bd-124">Valige Power Automate'is eelistatud voo loomiseks üks saadaolevatest päästikutest.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="6b1bd-125">Esimest korda voogu luues peate end esmalt rakenduse Power Automate konnektori jaoks autentima.</span><span class="sxs-lookup"><span data-stu-id="6b1bd-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
