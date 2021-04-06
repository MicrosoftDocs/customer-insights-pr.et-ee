---
title: Customer Insightsi andmete eksportimine Autopilotisse
description: Vaadake, kuidas konfigureerida ühendust Autopilotiga.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596125"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="647ab-103">Autopiloti konnektor (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="647ab-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="647ab-104">Saate eksportida ühendatud kliendiprofiilide segmente Autopiloti kontaktiloenditesse ja kasutada neid Autopilotis kampaaniate ja meiliturunduste jaoks.</span><span class="sxs-lookup"><span data-stu-id="647ab-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="647ab-105">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="647ab-105">Prerequisites</span></span>

-   <span data-ttu-id="647ab-106">Teil on [Autopiloti konto](https://www.autopilothq.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="647ab-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="647ab-107">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="647ab-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="647ab-108">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="647ab-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="647ab-109">Ühenda Autopilotiga</span><span class="sxs-lookup"><span data-stu-id="647ab-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="647ab-110">Avage **Haldus** > **Ekspordi sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="647ab-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="647ab-111">Tehke jaotises **Autopilot** valik **Seadista**.</span><span class="sxs-lookup"><span data-stu-id="647ab-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="647ab-112">Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="647ab-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Autopiloti ühenduse konfiguratsioonipaan.":::

1. <span data-ttu-id="647ab-114">Sisestage oma **Autopiloti API võti** [Autopiloti API võti](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="647ab-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="647ab-115">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="647ab-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="647ab-116">Valige **Ühenda**, et käivitada ühendus Autopilotiga.</span><span class="sxs-lookup"><span data-stu-id="647ab-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="647ab-117">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="647ab-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="647ab-118">Ekspordi konfigureerimiseks valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="647ab-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="647ab-119">Konnektori konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="647ab-119">Configure the connector</span></span>

1. <span data-ttu-id="647ab-120">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="647ab-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="647ab-121">Korrake samu juhiseid muude valikuliste väljade puhul, nagu **Eesnimi** ja **Perekonnanimi**.</span><span class="sxs-lookup"><span data-stu-id="647ab-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="647ab-122">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="647ab-122">Select the segments you want to export.</span></span> <span data-ttu-id="647ab-123">Soovitame **tungivalt mitte eksportida kokku üle 100 000 kliendiprofiili** Autopilotisse.</span><span class="sxs-lookup"><span data-stu-id="647ab-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="647ab-124">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="647ab-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="647ab-125">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="647ab-125">Export the data</span></span>

<span data-ttu-id="647ab-126">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="647ab-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="647ab-127">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="647ab-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="647ab-128">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="647ab-128">Known limitations</span></span>

- <span data-ttu-id="647ab-129">Autopilotisse saate eksportida kuni 100 000 profiili.</span><span class="sxs-lookup"><span data-stu-id="647ab-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="647ab-130">Autopilotisse saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="647ab-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="647ab-131">Kuni 100 000 profiili eksportimiseks Autopilotisse võib kuluda paar tundi.</span><span class="sxs-lookup"><span data-stu-id="647ab-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="647ab-132">Autopilotisse eksporditavate profiilide arv sõltub Autopilotiga sõlmitud lepingust.</span><span class="sxs-lookup"><span data-stu-id="647ab-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="647ab-133">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="647ab-133">Data privacy and compliance</span></span>

<span data-ttu-id="647ab-134">Kui lubate Dynamics 365 Customer Insightsil Autopilotisse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="647ab-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="647ab-135">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Autopilot täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="647ab-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="647ab-136">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="647ab-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="647ab-137">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="647ab-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]