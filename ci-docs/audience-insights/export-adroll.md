---
title: Customer Insightsi andmete eksportimine AdRolli
description: Lugege, kuidas konfigureerida ühendust ja eksportida AdRoll-i.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 67bfa23d56b26ae592efa4d7197713664bb02623
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304809"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="e742b-103">Segmentide eksportimine AdRoll-i (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="e742b-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="e742b-104">Eksportige kliendi koondprofiili segmendid AdRolli ja kasutage neid reklaamimiseks.</span><span class="sxs-lookup"><span data-stu-id="e742b-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e742b-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="e742b-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e742b-106">Teil on [AdRolli konto](https://www.adroll.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="e742b-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e742b-107">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="e742b-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e742b-108">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="e742b-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e742b-109">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="e742b-109">Known limitations</span></span>

- <span data-ttu-id="e742b-110">Korraga saate AdRoll'i eksportida kuni 250 000 profiili.</span><span class="sxs-lookup"><span data-stu-id="e742b-110">You can export up to 250,000 profiles at a time to AdRoll.</span></span>
- <span data-ttu-id="e742b-111">Vähem kui 100 profiiliga segmente ei saa AdRolli eksportida.</span><span class="sxs-lookup"><span data-stu-id="e742b-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="e742b-112">AdRolli saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="e742b-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="e742b-113">Kuni 250 000 profiili eksportimiseks AdRolli võib kuluda kuni 10 minutit.</span><span class="sxs-lookup"><span data-stu-id="e742b-113">Exporting up to 250,000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="e742b-114">AdRoll'i eksporditavate profiilide arv sõltub teie Adroll lepingust.</span><span class="sxs-lookup"><span data-stu-id="e742b-114">The number of profiles that you can export to AdRoll is dependent on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="e742b-115">Ühenduse loomine AdRoll'iga</span><span class="sxs-lookup"><span data-stu-id="e742b-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="e742b-116">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="e742b-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e742b-117">Valige **Lisa ühendus** ja valige **AdRoll** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="e742b-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="e742b-118">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="e742b-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e742b-119">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="e742b-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e742b-120">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="e742b-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e742b-121">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="e742b-121">Choose who can use this connection.</span></span> <span data-ttu-id="e742b-122">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="e742b-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e742b-123">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e742b-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e742b-124">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="e742b-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e742b-125">Valige **Ühenda**, et käivitada ühendus AdRolliga.</span><span class="sxs-lookup"><span data-stu-id="e742b-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="e742b-126">Valige **Autentimine AdRolliga** ja sisestage oma AdRolli administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="e742b-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="e742b-127">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="e742b-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e742b-128">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="e742b-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e742b-129">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="e742b-129">Configure an export</span></span>

<span data-ttu-id="e742b-130">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="e742b-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e742b-131">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e742b-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e742b-132">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="e742b-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e742b-133">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="e742b-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e742b-134">Valige **Ekspordiühendus** väljal ühendus AdRoll jaotisest.</span><span class="sxs-lookup"><span data-stu-id="e742b-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="e742b-135">Kui te seda jaotise nime ei näe, pole seda tüüpi ühendused teile saadaval.</span><span class="sxs-lookup"><span data-stu-id="e742b-135">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="e742b-136">Sisestage oma **AdRoll Advertiser ID**.</span><span class="sxs-lookup"><span data-stu-id="e742b-136">Enter your **AdRoll Advertiser ID**.</span></span> <span data-ttu-id="e742b-137">Lisateavet leiate teemast [AdRoll Advertiser Profiilid](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="e742b-137">For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="e742b-138">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="e742b-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e742b-139">See on vajalik segmentide eksportimiseks AdRolli.</span><span class="sxs-lookup"><span data-stu-id="e742b-139">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="e742b-140">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="e742b-140">Select the segments you want to export.</span></span> <span data-ttu-id="e742b-141">Valige vähemalt 100 liikmega segment.</span><span class="sxs-lookup"><span data-stu-id="e742b-141">Select a segment with a least 100 members.</span></span> <span data-ttu-id="e742b-142">Väiksemaid segmente ei saa eksportida.</span><span class="sxs-lookup"><span data-stu-id="e742b-142">You can't export smaller segments.</span></span> <span data-ttu-id="e742b-143">Lisaks on eksporditava segmendi maksimummaht 250 000 liiget ekspordi kohta.</span><span class="sxs-lookup"><span data-stu-id="e742b-143">Additionally the maximum size of a segment to export is 250,000 members per export.</span></span> 

1. <span data-ttu-id="e742b-144">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="e742b-144">Select **Save**.</span></span>

<span data-ttu-id="e742b-145">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="e742b-145">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e742b-146">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e742b-146">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="e742b-147">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e742b-147">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e742b-148">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="e742b-148">Data privacy and compliance</span></span>

<span data-ttu-id="e742b-149">Kui lubate Dynamics 365 Customer Insightsil AdRolli andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="e742b-149">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e742b-150">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et AdRoll täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="e742b-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e742b-151">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e742b-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e742b-152">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="e742b-152">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
