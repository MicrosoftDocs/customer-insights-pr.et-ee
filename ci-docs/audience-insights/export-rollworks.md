---
title: Customer Insights andmete eksportimine RollWorksi
description: Lugege, kuidas konfigureerida ühendust ja eksportida RollWorksi.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760513"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="b1f1a-103">Segmendiloendite eksportimine RollWorksi (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="b1f1a-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="b1f1a-104">Saate eksportida ühendatud kliendiprofiilide segmente RollWorksi ja kasutada neid turundustegevuste jaoks.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="b1f1a-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="b1f1a-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="b1f1a-106">Teil on [RollWorks konto](https://www.rollworks.com/) ja vastav administraatori mandaat.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b1f1a-107">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="b1f1a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b1f1a-108">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b1f1a-109">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="b1f1a-109">Known limitations</span></span>

- <span data-ttu-id="b1f1a-110">RollWorksi saate eksportida kuni 250 000 profiili ekspordi kohta.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="b1f1a-111">Vähem kui 100 profiiliga segmente ei saa RollWorksi eksportida.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="b1f1a-112">Eksportimine RollWorksi on piiratud segmentidega.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="b1f1a-113">Kuni 250'000 profiili eksportimine RollWorksi võib võtta kuni 10 minutit lõpuleviimiseks.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="b1f1a-114">RollWorksi eksporditavate profiilide arv sõltub ja on piiratud teie lepinguga RollWorksiga.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="b1f1a-115">Ühenduse loomine RollWorksiga</span><span class="sxs-lookup"><span data-stu-id="b1f1a-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="b1f1a-116">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b1f1a-117">Valige **Lisa ühendus** ja valige **RollWorks** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="b1f1a-118">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b1f1a-119">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b1f1a-120">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b1f1a-121">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-121">Choose who can use this connection.</span></span> <span data-ttu-id="b1f1a-122">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b1f1a-123">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b1f1a-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b1f1a-124">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b1f1a-125">Valige **Ühenda** RollWorks ühenduse lähtestamiseks.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="b1f1a-126">Valige **Autentimine RollWorksiga** ja sisestage oma administraatori mandaadid RollWorksi jaoks.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="b1f1a-127">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b1f1a-128">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b1f1a-129">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="b1f1a-129">Configure an export</span></span>

<span data-ttu-id="b1f1a-130">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b1f1a-131">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b1f1a-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b1f1a-132">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b1f1a-133">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b1f1a-134">Valige **Ekspordiühendus** väljal ühendus RollWorks jaotisest.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="b1f1a-135">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b1f1a-136">Sisestage oma **RollWorks Advertiser ID** [ID RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="b1f1a-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="b1f1a-137">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b1f1a-138">Segmentide eksportimine RollWorksi on vajalik.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="b1f1a-139">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-139">Select the segments you want to export.</span></span> <span data-ttu-id="b1f1a-140">Valige vähemalt 100 liikmega segment.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="b1f1a-141">Väiksemaid segmente ei saa eksportida.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-141">You can't export smaller segments.</span></span> <span data-ttu-id="b1f1a-142">Lisaks on eksporditava segmendi maksimummaht 250 000 liiget ekspordi kohta.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="b1f1a-143">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-143">Select **Save**.</span></span>

<span data-ttu-id="b1f1a-144">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b1f1a-145">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b1f1a-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b1f1a-146">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b1f1a-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b1f1a-147">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="b1f1a-147">Data privacy and compliance</span></span>

<span data-ttu-id="b1f1a-148">Kui lubate, et Dynamics 365 Customer Insights edastab andmeid RollWorksile, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b1f1a-149">Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et RollWorks vastaks teie võimalikele privaatsus- või turvalisuse nõuetele.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b1f1a-150">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b1f1a-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="b1f1a-151">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="b1f1a-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
