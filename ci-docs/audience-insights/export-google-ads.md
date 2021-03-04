---
title: Customer Insightsi andmete eksportimine Google Adsi
description: Vaadake, kuidas konfigureerida ühendust Google Adsiga.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268957"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="e4cbb-103">Google Adsi konnektor (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="e4cbb-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="e4cbb-104">Eksportige koondatud kliendiprofiilide segmendid Google Adsi vaatajaskonna loendisse ning kasutage neid, et näidata reklaame Google'i otsingus, Gmailis, YouTube'is ja Google'i Display-võrgustikus.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e4cbb-105">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="e4cbb-105">Prerequisites</span></span>

-   <span data-ttu-id="e4cbb-106">Teil on [Google Adsi konto](https://ads.google.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e4cbb-107">Google Adsis on olemas vaatajaskonnad ja asjakohased ID-d.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="e4cbb-108">Lisateavet leiate teemast [Google Adsi vaatajaskonnad](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="e4cbb-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="e4cbb-109">Te olete [konfigureerinud segmendid](segments.md)</span><span class="sxs-lookup"><span data-stu-id="e4cbb-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="e4cbb-110">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välju, mis tähistavad meiliaadressi, eesnime ja perekonnanime</span><span class="sxs-lookup"><span data-stu-id="e4cbb-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="e4cbb-111">Google Adsiga ühenduse loomine</span><span class="sxs-lookup"><span data-stu-id="e4cbb-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="e4cbb-112">Avage **Haldus** > **Ekspordi sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e4cbb-113">Valige jaotises **Google Ads** suvand **Seadista**.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="e4cbb-114">Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e4cbb-115">Sisestage oma **[Google Adsi kliendi-ID](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="e4cbb-116">Sisestage oma **[Google Adsi kinnitatud arendajatunnus](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="e4cbb-117">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e4cbb-118">Sisestage oma **[Google Adsi vaatajaskonna ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ja valige **Ühenda**, et käivitada ühendus Google Adsiga.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="e4cbb-119">Valige **Autentimine Google Adsiga** ja sisestage oma Google Adsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="e4cbb-120">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Google Adsi ühenduse ekspordi kuvatõmmis":::

1. <span data-ttu-id="e4cbb-122">Ekspordi konfigureerimiseks valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e4cbb-123">Konnektori konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="e4cbb-123">Configure the connector</span></span>

1. <span data-ttu-id="e4cbb-124">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e4cbb-125">Korrake samu samme väljade **Eesnimi** ja **Perekonnanimi** korral.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="e4cbb-126">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-126">Select the segments you want to export.</span></span> <span data-ttu-id="e4cbb-127">Google Adsi saate eksportida kuni miljon kliendiprofiili.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="e4cbb-128">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e4cbb-129">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="e4cbb-129">Export the data</span></span>

<span data-ttu-id="e4cbb-130">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e4cbb-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e4cbb-131">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e4cbb-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e4cbb-132">Google Adsis leiate nüüd oma segmendid jaotisest [Google Adsi vaatajaskonnad](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="e4cbb-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e4cbb-133">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="e4cbb-133">Known limitations</span></span>

- <span data-ttu-id="e4cbb-134">Google Adsi saab eksportida korraga kuni miljon profiili.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="e4cbb-135">Google Adsi saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="e4cbb-136">Miljoni profiiliga segmentide eksportimiseks võib teenusepakkuja tõttu kuluda kuni viis minutit.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="e4cbb-137">Google Adsis võib vastavusseviimine võtta kuni 48 tundi.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e4cbb-138">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="e4cbb-138">Data privacy and compliance</span></span>

<span data-ttu-id="e4cbb-139">Kui lubate Dynamics 365 Customer Insightsil Google Adsi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="e4cbb-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e4cbb-140">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Google Ads täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e4cbb-141">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e4cbb-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e4cbb-142">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="e4cbb-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]