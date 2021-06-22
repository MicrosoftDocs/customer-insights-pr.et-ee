---
title: Customer Insights andmete eksportimine Microsoft Advertisingusse
description: Lugege, kuidas konfigureerida ühendust ja eksportida Microsoft Advertisingusse.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124477"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="064bd-103">Segmentide eksportimine Microsoft Advertisingusse (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="064bd-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="064bd-104">Customer Insights segmentide eksportimine Microsoft Advertisingusse, et luua kliendisobivuse sihtrühmad.</span><span class="sxs-lookup"><span data-stu-id="064bd-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="064bd-105">Kasutage neid vaatajaskondi oma reklaamikampaaniate jaoks.</span><span class="sxs-lookup"><span data-stu-id="064bd-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="064bd-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="064bd-106">Prerequisites</span></span>

-   <span data-ttu-id="064bd-107">[Microsoft Advertising konto](https://ads.microsoft.com/) ja vastav administraatori mandaat.</span><span class="sxs-lookup"><span data-stu-id="064bd-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="064bd-108">Olete aktsepteerinud kliendi sobitamise kasutustingimused.</span><span class="sxs-lookup"><span data-stu-id="064bd-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="064bd-109">[Konfigureeritud segmendid](segments.md) vaatajaskonna ülevaates.</span><span class="sxs-lookup"><span data-stu-id="064bd-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="064bd-110">Eksporditud segmentide ühildatud kliendiprofiilid sisaldavad meiliaadressiga välja.</span><span class="sxs-lookup"><span data-stu-id="064bd-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="064bd-111">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="064bd-111">Known limitations</span></span>

- <span data-ttu-id="064bd-112">Microsoft Advertisingusse saate eksportida kuni 500 000 profiili ekspordi kohta.</span><span class="sxs-lookup"><span data-stu-id="064bd-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="064bd-113">Eksportimine Microsoft Advertisingusse on piiratud segmentidega.</span><span class="sxs-lookup"><span data-stu-id="064bd-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="064bd-114">Kuni 500 000 profiili eksportimine Microsoft Advertisingusse võib võtta kuni 10 minutit lõpuleviimiseks.</span><span class="sxs-lookup"><span data-stu-id="064bd-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="064bd-115">Ühenduse loomine Microsoft Advertisinguga</span><span class="sxs-lookup"><span data-stu-id="064bd-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="064bd-116">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="064bd-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="064bd-117">Valige **Lisa ühendus** ja valige **Microsoft Advertising** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="064bd-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="064bd-118">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="064bd-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="064bd-119">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="064bd-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="064bd-120">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="064bd-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="064bd-121">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="064bd-121">Choose who can use this connection.</span></span> <span data-ttu-id="064bd-122">Vaikimisi on Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="064bd-122">The default is administrators.</span></span> <span data-ttu-id="064bd-123">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="064bd-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="064bd-124">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="064bd-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="064bd-125">Valige **Ühenda** Microsoft Advertisinguga ühenduse lähtestamiseks.</span><span class="sxs-lookup"><span data-stu-id="064bd-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="064bd-126">Valige **Autentimine Microsoft Advertisinguga** ja sisestage oma administraatori mandaadid Microsoft Advertisingu jaoks.</span><span class="sxs-lookup"><span data-stu-id="064bd-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="064bd-127">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="064bd-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="064bd-128">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="064bd-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="064bd-129">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="064bd-129">Configure an export</span></span>

<span data-ttu-id="064bd-130">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="064bd-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="064bd-131">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="064bd-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="064bd-132">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="064bd-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="064bd-133">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="064bd-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="064bd-134">Valige **Ekspordiühendus** väljal ühendus Microsoft Advertisingu jaotisest.</span><span class="sxs-lookup"><span data-stu-id="064bd-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="064bd-135">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="064bd-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="064bd-136">Valige eksportimiseks segmendid.</span><span class="sxs-lookup"><span data-stu-id="064bd-136">Select the segments to export.</span></span> <span data-ttu-id="064bd-137">Microsoft Advertisingi kliendisobituse sihtrühmad luuakse automaatselt ekspordiks valitud segmentide nimega.</span><span class="sxs-lookup"><span data-stu-id="064bd-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="064bd-138">Iga segmendi tulemuseks on eraldi kliendisobitatud sihtrühm.</span><span class="sxs-lookup"><span data-stu-id="064bd-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="064bd-139">Sisestage oma **Microsofti Advertising Customer ID ja Account ID**.</span><span class="sxs-lookup"><span data-stu-id="064bd-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="064bd-140">Microsoft Advertisingi sisselogimise korral leiate URL-i parameetritest kliendi ID (`cid`) ja konto ID (`aid`).</span><span class="sxs-lookup"><span data-stu-id="064bd-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="064bd-141">Valige jaotises **Andmete sobitamine** väljas **Email** oma ühtse kliendiprofiili väli kliendi meiliaadressiga.</span><span class="sxs-lookup"><span data-stu-id="064bd-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="064bd-142">Segmentide eksportimine Microsoft Advertisingusse on vajalik.</span><span class="sxs-lookup"><span data-stu-id="064bd-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="064bd-143">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="064bd-143">Select **Save**.</span></span>

<span data-ttu-id="064bd-144">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="064bd-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="064bd-145">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="064bd-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="064bd-146">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="064bd-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="064bd-147">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="064bd-147">Data privacy and compliance</span></span>

<span data-ttu-id="064bd-148">Kui lubate, et Dynamics 365 Customer Insights edastab andmeid Microsoft Advertisingusse, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed.</span><span class="sxs-lookup"><span data-stu-id="064bd-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="064bd-149">Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et Microsoft Advertising vastaks teie võimalikele privaatsus- või turvalisuse nõuetele.</span><span class="sxs-lookup"><span data-stu-id="064bd-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="064bd-150">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="064bd-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="064bd-151">Teie Dynamics 365 Customer Insights administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="064bd-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
