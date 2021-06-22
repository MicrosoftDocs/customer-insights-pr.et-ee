---
title: Customer Insights andmete eksportimine Campaign Monitori
description: Lugege, kuidas konfigureerida ühendust ja eksportida Campaign Monitori.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124176"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="8af82-103">Segmentide eksportimine Campaign Monitori (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="8af82-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="8af82-104">Saate eksportida ühendatud kliendiprofiilide segmente Campaign Monitori ja kasutada neid turundustegevuste jaoks.</span><span class="sxs-lookup"><span data-stu-id="8af82-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8af82-105">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="8af82-105">Prerequisites</span></span>

-   <span data-ttu-id="8af82-106">Teil on [Campaign Monitori konto](https://www.campaignmonitor.com/) ja vastav administraatori volikiri.</span><span class="sxs-lookup"><span data-stu-id="8af82-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8af82-107">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8af82-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="8af82-108">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="8af82-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8af82-109">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="8af82-109">Known limitations</span></span>

- <span data-ttu-id="8af82-110">Campaign Monitori saate eksportida kuni 1 miljoni profiili ekspordi kohta.</span><span class="sxs-lookup"><span data-stu-id="8af82-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="8af82-111">Eksportimine Campaign Monitori on piiratud segmentidega.</span><span class="sxs-lookup"><span data-stu-id="8af82-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="8af82-112">Kuni 1 miljoni profiili eksportimine Campaign Monitori võib võtta kuni 20 minutit lõpuleviimiseks.</span><span class="sxs-lookup"><span data-stu-id="8af82-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="8af82-113">Campaign Monitori eksporditavate profiilide arv sõltub ja on piiratud teie lepinguga Campaign Monitoriga.</span><span class="sxs-lookup"><span data-stu-id="8af82-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="8af82-114">Campaign Monitoriga ühenduse loomine</span><span class="sxs-lookup"><span data-stu-id="8af82-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="8af82-115">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="8af82-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="8af82-116">Valige **Lisa ühendus** ja valige **Campaign Monitor** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="8af82-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="8af82-117">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="8af82-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="8af82-118">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="8af82-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="8af82-119">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="8af82-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="8af82-120">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="8af82-120">Choose who can use this connection.</span></span> <span data-ttu-id="8af82-121">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="8af82-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="8af82-122">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="8af82-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="8af82-123">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="8af82-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8af82-124">Valige **Ühenda** Campaign Monitoriga ühenduse lähtestamiseks.</span><span class="sxs-lookup"><span data-stu-id="8af82-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="8af82-125">Valige **Autentimine Campaign Monitoriga** ja sisestage oma administraatori mandaadid Campaign Monitori jaoks.</span><span class="sxs-lookup"><span data-stu-id="8af82-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="8af82-126">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="8af82-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="8af82-127">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="8af82-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="8af82-128">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="8af82-128">Configure an export</span></span>

<span data-ttu-id="8af82-129">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="8af82-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="8af82-130">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="8af82-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="8af82-131">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="8af82-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="8af82-132">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="8af82-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="8af82-133">Valige **Ekspordiühendus** väljal ühendus Campaign Monitori jaotisest.</span><span class="sxs-lookup"><span data-stu-id="8af82-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="8af82-134">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="8af82-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="8af82-135">Sisestage [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="8af82-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="8af82-136">[Looge API-võti](https://www.campaignmonitor.com/api/getting-started/) esmalt Campaign Monitori **Konto sätted** sätetest, et vaadata API-loendi ID-d.</span><span class="sxs-lookup"><span data-stu-id="8af82-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="8af82-137">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="8af82-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="8af82-138">Segmentide eksportimine Campaign Monitori on vajalik.</span><span class="sxs-lookup"><span data-stu-id="8af82-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="8af82-139">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="8af82-139">Select **Save**.</span></span>

<span data-ttu-id="8af82-140">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="8af82-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="8af82-141">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8af82-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8af82-142">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8af82-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8af82-143">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="8af82-143">Data privacy and compliance</span></span>

<span data-ttu-id="8af82-144">Kui lubate, et Dynamics 365 Customer Insights edastab andmeid Campaign Monitorile, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed.</span><span class="sxs-lookup"><span data-stu-id="8af82-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8af82-145">Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et Campaign Monitor vastaks teie võimalikele privaatsus- või turvalisuse nõuetele.</span><span class="sxs-lookup"><span data-stu-id="8af82-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8af82-146">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8af82-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="8af82-147">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="8af82-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
