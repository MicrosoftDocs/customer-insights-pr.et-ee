---
title: Customer Insights andmete eksportimine Snapchati
description: Lugege, kuidas konfigureerida ühendust ja eksportida Snapchati.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760510"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="edf70-103">Segmendiloendite eksportimine Snapchati (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="edf70-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="edf70-104">Saate eksportida ühendatud kliendiprofiilide segmente Snapchati ja kasutada neid turundustegevuste jaoks.</span><span class="sxs-lookup"><span data-stu-id="edf70-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="edf70-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="edf70-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="edf70-106">Teil on [Snapchat Business account](https://business.snapchat.com/), [Snapchat Ads account](https://ads.snapchat.com/) ja vastavad administraatori mandaadid.</span><span class="sxs-lookup"><span data-stu-id="edf70-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="edf70-107">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="edf70-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="edf70-108">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="edf70-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="edf70-109">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="edf70-109">Known limitations</span></span>

- <span data-ttu-id="edf70-110">Eksportimine Snapchati on piiratud segmentidega.</span><span class="sxs-lookup"><span data-stu-id="edf70-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="edf70-111">Kuni 1 miljoni profiili eksportimine Snapchati võib võtta kuni 15 minutit lõpuleviimiseks.</span><span class="sxs-lookup"><span data-stu-id="edf70-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="edf70-112">Ühenduse loomine Snapchatiga</span><span class="sxs-lookup"><span data-stu-id="edf70-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="edf70-113">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="edf70-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="edf70-114">Valige **Lisa ühendus** ja valige **Snapchat** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="edf70-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="edf70-115">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="edf70-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="edf70-116">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="edf70-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="edf70-117">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="edf70-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="edf70-118">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="edf70-118">Choose who can use this connection.</span></span> <span data-ttu-id="edf70-119">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="edf70-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="edf70-120">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="edf70-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="edf70-121">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="edf70-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="edf70-122">Valige **Ühenda** Snapchat ühenduse lähtestamiseks.</span><span class="sxs-lookup"><span data-stu-id="edf70-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="edf70-123">Valige **Autentimine Snapchatiga** ja sisestage oma administraatori mandaadid Snapchati jaoks.</span><span class="sxs-lookup"><span data-stu-id="edf70-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="edf70-124">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="edf70-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="edf70-125">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="edf70-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="edf70-126">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="edf70-126">Configure an export</span></span>

<span data-ttu-id="edf70-127">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="edf70-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="edf70-128">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="edf70-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="edf70-129">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="edf70-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="edf70-130">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="edf70-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="edf70-131">Valige **Ekspordiühendus** väljal ühendus Snapchat jaotisest.</span><span class="sxs-lookup"><span data-stu-id="edf70-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="edf70-132">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="edf70-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="edf70-133">Sisestage [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="edf70-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="edf70-134">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="edf70-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="edf70-135">Segmentide eksportimine Snapchati on vajalik.</span><span class="sxs-lookup"><span data-stu-id="edf70-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="edf70-136">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="edf70-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="edf70-137">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="edf70-137">Select **Save**.</span></span>

<span data-ttu-id="edf70-138">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="edf70-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="edf70-139">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="edf70-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="edf70-140">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="edf70-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="edf70-141">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="edf70-141">Data privacy and compliance</span></span>

<span data-ttu-id="edf70-142">Kui lubate, et Dynamics 365 Customer Insights edastab andmeid Snapchatile, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed.</span><span class="sxs-lookup"><span data-stu-id="edf70-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="edf70-143">Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et Snapchat vastaks teie võimalikele privaatsus- või turvalisuse nõuetele.</span><span class="sxs-lookup"><span data-stu-id="edf70-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="edf70-144">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="edf70-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="edf70-145">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="edf70-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
