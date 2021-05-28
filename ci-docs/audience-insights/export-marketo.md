---
title: Customer Insightsi andmete eksportimine Marketosse
description: Lugege, kuidas konfigureerida ühendust ja eksportida platvormile Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059311"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="0693c-103">Segmentide eksportimine platvormile Marketo (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="0693c-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="0693c-104">Eksportige Marketo abil koondatud kliendiprofiilide segmente kampaaniate loomiseks, meiliturunduse pakkumiseks ja konkreetsete kliendirühmade kasutamiseks.</span><span class="sxs-lookup"><span data-stu-id="0693c-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0693c-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="0693c-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="0693c-106">Teil on [Marketo konto](https://login.marketo.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="0693c-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0693c-107">Marketos on olemas loendid ja asjakohased ID-d.</span><span class="sxs-lookup"><span data-stu-id="0693c-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="0693c-108">Lisateavet leiate artiklist [Marketo loendid](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="0693c-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="0693c-109">Te olete [konfigureerinud segmendid](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0693c-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="0693c-110">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="0693c-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0693c-111">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="0693c-111">Known limitations</span></span>

- <span data-ttu-id="0693c-112">Marketosse saab eksportida korraga kuni miljon profiili.</span><span class="sxs-lookup"><span data-stu-id="0693c-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="0693c-113">Marketosse saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="0693c-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="0693c-114">Miljoni profiiliga segmentide eksportimine võib kesta kuni kolm tundi.</span><span class="sxs-lookup"><span data-stu-id="0693c-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="0693c-115">Marketosse eksporditavate profiilide arv sõltub Marketoga sõlmitud lepingust.</span><span class="sxs-lookup"><span data-stu-id="0693c-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="0693c-116">Ühenduse loomine platvormiga Marketo</span><span class="sxs-lookup"><span data-stu-id="0693c-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="0693c-117">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="0693c-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0693c-118">Valige **Lisa ühendus** ja valige **Marketo** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="0693c-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="0693c-119">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="0693c-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0693c-120">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="0693c-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0693c-121">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="0693c-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0693c-122">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="0693c-122">Choose who can use this connection.</span></span> <span data-ttu-id="0693c-123">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="0693c-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0693c-124">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0693c-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0693c-125">Sisestage oma **[Marketo kliendi-ID, Client secret ja REST Endpoint hostinimi](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="0693c-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="0693c-126">REST lõpp-punkti hostinimi on ainult hostinimi ilma `https://`.</span><span class="sxs-lookup"><span data-stu-id="0693c-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="0693c-127">Näide: `xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="0693c-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="0693c-128">Valige **Nõustun**, et nõustuda jaotise **Andmete privaatsus ja nõuetele vastavus** tingimustega ja valige **Ühenda**, et Marketoga ühenduda.</span><span class="sxs-lookup"><span data-stu-id="0693c-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="0693c-129">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="0693c-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0693c-130">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="0693c-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0693c-131">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="0693c-131">Configure an export</span></span>

<span data-ttu-id="0693c-132">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="0693c-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0693c-133">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0693c-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0693c-134">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="0693c-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0693c-135">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="0693c-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0693c-136">Valige **Ekspordiühendus** väljal ühendus Marketo jaotisest.</span><span class="sxs-lookup"><span data-stu-id="0693c-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="0693c-137">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="0693c-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0693c-138">Sisestage oma **[Marketo loendi ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="0693c-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="0693c-139">Loendi ID on lihtsalt arvväärtus.</span><span class="sxs-lookup"><span data-stu-id="0693c-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="0693c-140">Kui teie Marketo loendi ID on näiteks ST12345A7, eemaldage märk enne ja pärast numbreid ning sisestage `12345`.</span><span class="sxs-lookup"><span data-stu-id="0693c-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="0693c-141">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="0693c-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0693c-142">Soovi korral saate eksportida **Eesnimi**, **Perekonnanimi**, **Linn**, **Osariik** ja **Riik/regioon**  isikupärastatud meilide loomiseks.</span><span class="sxs-lookup"><span data-stu-id="0693c-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="0693c-143">Nende väljade vastendamiseks valige **Lisa atribuut**.</span><span class="sxs-lookup"><span data-stu-id="0693c-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0693c-144">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="0693c-144">Select the segments you want to export.</span></span> <span data-ttu-id="0693c-145">Marketosse saate eksportida kuni miljon kliendiprofiili.</span><span class="sxs-lookup"><span data-stu-id="0693c-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="0693c-146">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="0693c-146">Select **Save**.</span></span>

<span data-ttu-id="0693c-147">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="0693c-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0693c-148">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0693c-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0693c-149">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0693c-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="0693c-150">Marketos leiate nüüd oma segmendid jaotisest [Marketo loendid](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="0693c-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0693c-151">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="0693c-151">Data privacy and compliance</span></span>

<span data-ttu-id="0693c-152">Kui lubate Dynamics 365 Customer Insightsil Marketosse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="0693c-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0693c-153">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Marketo täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="0693c-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0693c-154">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0693c-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0693c-155">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="0693c-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
