---
title: Customer Insightsi andmete eksportimine Google Adsi
description: Lugege, kuidas konfigureerida ühendust ja eksportida Google Adsi.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c23c8b4e6758df08e04bf1e3ae0cba4dee06fe2b
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305335"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="1c469-103">Segmentide eksportimine Google Adsi (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="1c469-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="1c469-104">Eksportige ühtsete kliendiprofiilide segmendid Google Ads vaatajaskonna loendisse ja kasutage neid Google'i otsingus, Gmailis, YouTube ja Google Display Network'is reklaamimiseks.</span><span class="sxs-lookup"><span data-stu-id="1c469-104">Export segments of unified customer profiles to a Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="1c469-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="1c469-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="1c469-106">Teil on [Google Adsi konto](https://ads.google.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="1c469-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1c469-107">Teil on [kinnitatud Google Ads arendaja token](https://developers.google.com/google-ads/api/docs/first-call/dev-token).</span><span class="sxs-lookup"><span data-stu-id="1c469-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token).</span></span> 
-   <span data-ttu-id="1c469-108">Te täidate [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717) nõuded.</span><span class="sxs-lookup"><span data-stu-id="1c469-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717).</span></span>
-   <span data-ttu-id="1c469-109">Te täidate [uuesti turundamise loendi suurused](https://support.google.com/google-ads/answer/7558048) nõudeid.</span><span class="sxs-lookup"><span data-stu-id="1c469-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048).</span></span>
-   <span data-ttu-id="1c469-110">Google Adsis on olemas vaatajaskonnad ja asjakohased ID-d.</span><span class="sxs-lookup"><span data-stu-id="1c469-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="1c469-111">Lisateavet leiate teemast [Google Adsi vaatajaskonnad](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="1c469-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="1c469-112">Te olete [konfigureerinud segmendid](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1c469-112">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="1c469-113">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välju, mis tähistavad meiliaadressi, eesnime ja perekonnanime.</span><span class="sxs-lookup"><span data-stu-id="1c469-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1c469-114">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="1c469-114">Known limitations</span></span>

- <span data-ttu-id="1c469-115">Google Adsi saab eksportida korraga kuni miljon profiili.</span><span class="sxs-lookup"><span data-stu-id="1c469-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="1c469-116">Google Adsi saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="1c469-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="1c469-117">Miljoni profiiliga segmentide eksportimiseks võib teenusepakkuja tõttu kuluda kuni viis minutit.</span><span class="sxs-lookup"><span data-stu-id="1c469-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="1c469-118">Google Adsis võib vastavusseviimine võtta kuni 48 tundi.</span><span class="sxs-lookup"><span data-stu-id="1c469-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="1c469-119">Ühenduse Google Ads loomine</span><span class="sxs-lookup"><span data-stu-id="1c469-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="1c469-120">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="1c469-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1c469-121">Valige **Lisa ühendus** ja valige **Google Ads** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="1c469-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="1c469-122">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="1c469-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1c469-123">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="1c469-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1c469-124">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="1c469-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1c469-125">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="1c469-125">Choose who can use this connection.</span></span> <span data-ttu-id="1c469-126">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="1c469-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1c469-127">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1c469-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1c469-128">Sisestage oma **[Google Adsi kliendi-ID](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="1c469-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="1c469-129">Sisestage oma **[Google Adsi kinnitatud arendajatunnus](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="1c469-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="1c469-130">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="1c469-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1c469-131">Valige **Autentimine Google Adsiga** ja sisestage oma Google Adsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="1c469-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="1c469-132">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="1c469-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1c469-133">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="1c469-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="1c469-134">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="1c469-134">Configure an export</span></span>

<span data-ttu-id="1c469-135">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="1c469-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1c469-136">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1c469-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1c469-137">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="1c469-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1c469-138">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="1c469-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1c469-139">Valige **Ekspordiühendus** väljal ühendus Google Ads jaotisest.</span><span class="sxs-lookup"><span data-stu-id="1c469-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="1c469-140">Kui te seda jaotise nime ei näe, pole seda tüüpi ühendused teile saadaval.</span><span class="sxs-lookup"><span data-stu-id="1c469-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="1c469-141">Sisestage oma **[Google Adsi vaatajaskonna ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ja valige **Ühenda**, et käivitada ühendus Google Adsiga.</span><span class="sxs-lookup"><span data-stu-id="1c469-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="1c469-142">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="1c469-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1c469-143">Korrake samu samme väljade **Eesnimi** ja **Perekonnanimi** korral.</span><span class="sxs-lookup"><span data-stu-id="1c469-143">Repeat the same steps for **First name** and **Last name** fields.</span></span>

1. <span data-ttu-id="1c469-144">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="1c469-144">Select the segments you want to export.</span></span> <span data-ttu-id="1c469-145">Google Adsi saate eksportida kuni miljon kliendiprofiili.</span><span class="sxs-lookup"><span data-stu-id="1c469-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="1c469-146">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="1c469-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1c469-147">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1c469-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="1c469-148">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1c469-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1c469-149">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="1c469-149">Data privacy and compliance</span></span>

<span data-ttu-id="1c469-150">Kui lubate Dynamics 365 Customer Insightsil Google Adsi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="1c469-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1c469-151">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Google Ads täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="1c469-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="1c469-152">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1c469-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1c469-153">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="1c469-153">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
