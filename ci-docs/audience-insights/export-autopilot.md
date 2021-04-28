---
title: Customer Insightsi andmete eksportimine Autopilotisse
description: Lugege, kuidas konfigureerida ühendust ja eksportida Autopilot'isse.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760138"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="96159-103">Segmentide eksportimine Autopilot'isse (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="96159-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="96159-104">Saate eksportida ühendatud kliendiprofiilide segmente Autopiloti kontaktiloenditesse ja kasutada neid Autopilotis kampaaniate ja meiliturunduste jaoks.</span><span class="sxs-lookup"><span data-stu-id="96159-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="96159-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="96159-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="96159-106">Teil on [Autopiloti konto](https://www.autopilothq.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="96159-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="96159-107">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="96159-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="96159-108">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="96159-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="96159-109">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="96159-109">Known limitations</span></span>

- <span data-ttu-id="96159-110">Autopilotisse saate eksportida kuni 100 000 profiili.</span><span class="sxs-lookup"><span data-stu-id="96159-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="96159-111">Autopilotisse saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="96159-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="96159-112">Kuni 100 000 profiili eksportimiseks Autopilotisse võib kuluda paar tundi.</span><span class="sxs-lookup"><span data-stu-id="96159-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="96159-113">Autopilotisse eksporditavate profiilide arv sõltub Autopilotiga sõlmitud lepingust.</span><span class="sxs-lookup"><span data-stu-id="96159-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="96159-114">Ühenduse loomine Autopilot'iga</span><span class="sxs-lookup"><span data-stu-id="96159-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="96159-115">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="96159-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="96159-116">Valige **Lisa ühendus** ja valige **Autopilot** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="96159-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="96159-117">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="96159-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="96159-118">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="96159-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="96159-119">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="96159-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="96159-120">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="96159-120">Choose who can use this connection.</span></span> <span data-ttu-id="96159-121">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="96159-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="96159-122">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="96159-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="96159-123">Sisestage oma [Autopiloti API võti](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="96159-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="96159-124">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="96159-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="96159-125">Valige **Ühenda**, et käivitada ühendus Autopilotiga.</span><span class="sxs-lookup"><span data-stu-id="96159-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="96159-126">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="96159-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="96159-127">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="96159-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="96159-128">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="96159-128">Configure an export</span></span>

<span data-ttu-id="96159-129">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="96159-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="96159-130">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="96159-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="96159-131">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="96159-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="96159-132">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="96159-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="96159-133">Valige **Ekspordiühendus** väljal ühendus Autopilot jaotisest.</span><span class="sxs-lookup"><span data-stu-id="96159-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="96159-134">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="96159-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="96159-135">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="96159-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="96159-136">Korrake samu juhiseid muude valikuliste väljade puhul, nagu **Eesnimi** ja **Perekonnanimi**.</span><span class="sxs-lookup"><span data-stu-id="96159-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="96159-137">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="96159-137">Select the segments you want to export.</span></span> <span data-ttu-id="96159-138">Soovitame **tungivalt mitte eksportida kokku üle 100 000 kliendiprofiili** Autopilotisse.</span><span class="sxs-lookup"><span data-stu-id="96159-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="96159-139">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="96159-139">Select **Save**.</span></span>

<span data-ttu-id="96159-140">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="96159-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="96159-141">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="96159-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="96159-142">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="96159-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="96159-143">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="96159-143">Data privacy and compliance</span></span>

<span data-ttu-id="96159-144">Kui lubate Dynamics 365 Customer Insightsil Autopilotisse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="96159-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="96159-145">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Autopilot täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="96159-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="96159-146">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="96159-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="96159-147">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="96159-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
