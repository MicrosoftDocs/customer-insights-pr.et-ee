---
title: Customer Insightsi andmete eksportimine AdRolli
description: Vaadake, kuidas konfigureerida ühendust AdRolliga.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697069"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="92a6f-103">AdRolli konnektor (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="92a6f-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="92a6f-104">Eksportige kliendi koondprofiili segmendid AdRolli ja kasutage neid reklaamimiseks.</span><span class="sxs-lookup"><span data-stu-id="92a6f-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="92a6f-105">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="92a6f-105">Prerequisites</span></span>

-   <span data-ttu-id="92a6f-106">Teil on [AdRolli konto](https://www.adroll.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="92a6f-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="92a6f-107">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="92a6f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="92a6f-108">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="92a6f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="92a6f-109">Ühenda AdRolliga</span><span class="sxs-lookup"><span data-stu-id="92a6f-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="92a6f-110">Avage **Haldus** > **Ekspordi sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="92a6f-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="92a6f-111">Tehke jaotises **AdRoll** valik **Seadista**.</span><span class="sxs-lookup"><span data-stu-id="92a6f-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="92a6f-112">Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="92a6f-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="AdRolli ühenduse konfiguratsioonipaan.":::

1. <span data-ttu-id="92a6f-114">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="92a6f-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="92a6f-115">Valige **Ühenda**, et käivitada ühendus AdRolliga.</span><span class="sxs-lookup"><span data-stu-id="92a6f-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="92a6f-116">Valige **Autentimine AdRolliga** ja sisestage oma AdRolli administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="92a6f-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="92a6f-117">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="92a6f-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="92a6f-118">Sisestage **AdRolli reklaamija ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="92a6f-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="92a6f-119">Ekspordi konfigureerimiseks valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="92a6f-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="92a6f-120">Konnektori konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="92a6f-120">Configure the connector</span></span>

1. <span data-ttu-id="92a6f-121">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="92a6f-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="92a6f-122">See on vajalik segmentide eksportimiseks AdRolli.</span><span class="sxs-lookup"><span data-stu-id="92a6f-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="92a6f-123">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="92a6f-123">Select the segments you want to export.</span></span> <span data-ttu-id="92a6f-124">Valige vähemalt 100 liikmega segment.</span><span class="sxs-lookup"><span data-stu-id="92a6f-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="92a6f-125">Väiksemaid segmente ei saa eksportida.</span><span class="sxs-lookup"><span data-stu-id="92a6f-125">You can't export smaller segments.</span></span> <span data-ttu-id="92a6f-126">Lisaks on eksporditava segmendi maksimummaht 250 000 liiget ekspordi kohta.</span><span class="sxs-lookup"><span data-stu-id="92a6f-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="92a6f-127">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="92a6f-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="92a6f-128">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="92a6f-128">Export the data</span></span>

<span data-ttu-id="92a6f-129">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="92a6f-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="92a6f-130">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="92a6f-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="92a6f-131">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="92a6f-131">Known limitations</span></span>

- <span data-ttu-id="92a6f-132">AdRolli saate ühe ekspordi kohta eksportida kuni 250 000 profiili.</span><span class="sxs-lookup"><span data-stu-id="92a6f-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="92a6f-133">Vähem kui 100 profiiliga segmente ei saa AdRolli eksportida.</span><span class="sxs-lookup"><span data-stu-id="92a6f-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="92a6f-134">AdRolli saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="92a6f-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="92a6f-135">Kuni 250 000 profiili eksportimiseks AdRolli võib kuluda kuni 10 minutit.</span><span class="sxs-lookup"><span data-stu-id="92a6f-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="92a6f-136">AdRolli eksporditavate profiilide arv sõltub AdRollga sõlmitud lepingust ja on sellega piiratud.</span><span class="sxs-lookup"><span data-stu-id="92a6f-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="92a6f-137">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="92a6f-137">Data privacy and compliance</span></span>

<span data-ttu-id="92a6f-138">Kui lubate Dynamics 365 Customer Insightsil AdRolli andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="92a6f-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="92a6f-139">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et AdRoll täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="92a6f-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="92a6f-140">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="92a6f-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="92a6f-141">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="92a6f-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
