---
title: Customer Insightsi andmete eksportimine Mailchimpi
description: Vaadake, kuidas konfigureerida ühendust Mailchimpiga.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267168"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="68fb3-103">Mailchimpi konnektor (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="68fb3-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="68fb3-104">Eksportige koondatud kliendiprofiilide segmendid MailChimpi, et luua teabelehti ja meilikampaaniad.</span><span class="sxs-lookup"><span data-stu-id="68fb3-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="68fb3-105">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="68fb3-105">Prerequisites</span></span>

-   <span data-ttu-id="68fb3-106">Teil on [Mailchimpi konto](https://mailchimp.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="68fb3-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="68fb3-107">Mailchimpis on olemas sihtrühmad ja asjakohased ID-d.</span><span class="sxs-lookup"><span data-stu-id="68fb3-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="68fb3-108">Lisateavet leiate teemast [Mailchimpi sihtrühmad](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="68fb3-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="68fb3-109">Te olete [konfigureerinud segmendid](segments.md)</span><span class="sxs-lookup"><span data-stu-id="68fb3-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="68fb3-110">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="68fb3-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="68fb3-111">Loo ühendus Mailchimpiga</span><span class="sxs-lookup"><span data-stu-id="68fb3-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="68fb3-112">Avage **Haldus** > **Ekspordi sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="68fb3-113">Tehke jaotises **Mailchimp** valik **Seadista**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="68fb3-114">Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="68fb3-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="68fb3-115">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="68fb3-116">Sisestage oma **[Mailchimpi sihtrühma ID](https://mailchimp.com/help/find-audience-id/)** ja valige **Ühenda**, et käivitada ühendus Mailchimpiga.</span><span class="sxs-lookup"><span data-stu-id="68fb3-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="68fb3-117">Valige **Autentimine Mailchimpiga** ja sisestage oma Mailchimpi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="68fb3-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="68fb3-118">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="68fb3-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Mailchimpi ühenduse ekspordi kuvatõmmis":::

1. <span data-ttu-id="68fb3-120">Ekspordi konfigureerimiseks valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="68fb3-121">Konnektori konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="68fb3-121">Configure the connector</span></span>

1. <span data-ttu-id="68fb3-122">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="68fb3-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="68fb3-123">Soovi korral saate isikupärastatud meilide loomiseks täiendavalt eksportida väljad **Eesnimi** ja **Perekonnanimi**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="68fb3-124">Nende väljade vastendamiseks valige **Lisa atribuut**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="68fb3-125">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="68fb3-125">Select the segments you want to export.</span></span> <span data-ttu-id="68fb3-126">Mailchimpi saate eksportida kuni miljon kliendiprofiili.</span><span class="sxs-lookup"><span data-stu-id="68fb3-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Väljade ja segmentide valimine Mailchimpi eksportimiseks":::

1. <span data-ttu-id="68fb3-128">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="68fb3-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="68fb3-129">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="68fb3-129">Export the data</span></span>

<span data-ttu-id="68fb3-130">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="68fb3-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="68fb3-131">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="68fb3-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="68fb3-132">Mailchimpis leiate nüüd oma segmendid jaotisest [Mailchimpi sihtrühmad](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="68fb3-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="68fb3-133">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="68fb3-133">Known limitations</span></span>

- <span data-ttu-id="68fb3-134">Mailchimpi saab eksportida korraga kuni miljon profiili.</span><span class="sxs-lookup"><span data-stu-id="68fb3-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="68fb3-135">Mailchimpi saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="68fb3-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="68fb3-136">Miljoni profiiliga segmentide eksportimiseks võib teenusepakkuja tõttu kuluda kuni kolm tundi.</span><span class="sxs-lookup"><span data-stu-id="68fb3-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="68fb3-137">Mailchimpi eksporditavate profiilide arv sõltub Mailchimpiga sõlmitud lepingust.</span><span class="sxs-lookup"><span data-stu-id="68fb3-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="68fb3-138">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="68fb3-138">Data privacy and compliance</span></span>

<span data-ttu-id="68fb3-139">Kui lubate Dynamics 365 Customer Insightsil Mailchimpi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="68fb3-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="68fb3-140">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Mailchimp täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="68fb3-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="68fb3-141">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="68fb3-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="68fb3-142">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="68fb3-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]