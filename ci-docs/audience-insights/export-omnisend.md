---
title: Customer Insights andmete eksportimine Omnisendi
description: Lugege, kuidas konfigureerida ühendust ja eksportida Omnisendi.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124478"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="959cd-103">Segmentide eksportimine Omnisendi (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="959cd-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="959cd-104">Saate eksportida ühendatud kliendiprofiilide segmente Omnisendi ja kasutada neid turundustegevuste jaoks.</span><span class="sxs-lookup"><span data-stu-id="959cd-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="959cd-105">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="959cd-105">Prerequisites</span></span>

-   <span data-ttu-id="959cd-106">Teil on [Omnisend konto](https://www.omnisend.com/) ja vastav administraatori mandaat.</span><span class="sxs-lookup"><span data-stu-id="959cd-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="959cd-107">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="959cd-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="959cd-108">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="959cd-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="959cd-109">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="959cd-109">Known limitations</span></span>

- <span data-ttu-id="959cd-110">Omnisendi saate eksportida kuni 1 miljon profiili ekspordi kohta ja selle lõpuleviimiseks võib kuluda kuni 4 tundi.</span><span class="sxs-lookup"><span data-stu-id="959cd-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="959cd-111">Eksportimine Omnisendi on piiratud segmentidega.</span><span class="sxs-lookup"><span data-stu-id="959cd-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="959cd-112">Omnisendi eksporditavate profiilide arv sõltub teie lepingust Omnisendiga.</span><span class="sxs-lookup"><span data-stu-id="959cd-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="959cd-113">Ühenduse loomine Omnisendiga</span><span class="sxs-lookup"><span data-stu-id="959cd-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="959cd-114">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="959cd-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="959cd-115">Valige **Lisa ühendus** ja valige **Omnisend** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="959cd-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="959cd-116">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="959cd-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="959cd-117">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="959cd-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="959cd-118">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="959cd-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="959cd-119">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="959cd-119">Choose who can use this connection.</span></span> <span data-ttu-id="959cd-120">Vaikimisi on see ainult Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="959cd-120">By default it's only administrators.</span></span> <span data-ttu-id="959cd-121">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="959cd-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="959cd-122">Sisestage oma [Omnisend API võti](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="959cd-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="959cd-123">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="959cd-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="959cd-124">Valige **Ühenda** Omnisend ühenduse lähtestamiseks.</span><span class="sxs-lookup"><span data-stu-id="959cd-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="959cd-125">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="959cd-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="959cd-126">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="959cd-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="959cd-127">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="959cd-127">Configure an export</span></span>

<span data-ttu-id="959cd-128">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="959cd-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="959cd-129">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="959cd-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="959cd-130">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="959cd-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="959cd-131">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="959cd-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="959cd-132">Valige **Ekspordiühendus** väljal ühendus Omnisend jaotisest.</span><span class="sxs-lookup"><span data-stu-id="959cd-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="959cd-133">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="959cd-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="959cd-134">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="959cd-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="959cd-135">Segmentide eksportimine Omnisendi on vajalik.</span><span class="sxs-lookup"><span data-stu-id="959cd-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="959cd-136">Soovi korral saate eksportida Eesnimi, Perekonnanimi, Aadress, Riik/regioon, Osariik, Linn ja Postiindeks isikupärastatud meilide loomiseks.</span><span class="sxs-lookup"><span data-stu-id="959cd-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="959cd-137">Nende väljade vastendamiseks valige **Lisa atribuut**.</span><span class="sxs-lookup"><span data-stu-id="959cd-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="959cd-138">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="959cd-138">Select **Save**.</span></span>

<span data-ttu-id="959cd-139">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="959cd-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="959cd-140">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="959cd-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="959cd-141">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="959cd-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="959cd-142">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="959cd-142">Data privacy and compliance</span></span>

<span data-ttu-id="959cd-143">Kui lubate, et Dynamics 365 Customer Insights edastab andmeid Omnisendile, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed.</span><span class="sxs-lookup"><span data-stu-id="959cd-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="959cd-144">Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et Omnisend vastaks teie võimalikele privaatsus- või turvalisuse nõuetele.</span><span class="sxs-lookup"><span data-stu-id="959cd-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="959cd-145">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="959cd-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="959cd-146">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="959cd-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
