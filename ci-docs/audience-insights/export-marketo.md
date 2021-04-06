---
title: Customer Insightsi andmete eksportimine Marketosse
description: Vaadake, kuidas konfigureerida ühendust Marketoga.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 74d19a0448123904210c26f7b8760d00296c9cfd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597966"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="7a807-103">Marketo konnektor (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="7a807-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="7a807-104">Eksportige Marketo abil koondatud kliendiprofiilide segmente kampaaniate loomiseks, meiliturunduse pakkumiseks ja konkreetsete kliendirühmade kasutamiseks.</span><span class="sxs-lookup"><span data-stu-id="7a807-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7a807-105">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="7a807-105">Prerequisites</span></span>

-   <span data-ttu-id="7a807-106">Teil on [Marketo konto](https://login.marketo.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="7a807-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7a807-107">Marketos on olemas loendid ja asjakohased ID-d.</span><span class="sxs-lookup"><span data-stu-id="7a807-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="7a807-108">Lisateavet leiate artiklist [Marketo loendid](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="7a807-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="7a807-109">Te olete [konfigureerinud segmendid](segments.md).</span><span class="sxs-lookup"><span data-stu-id="7a807-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="7a807-110">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="7a807-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="7a807-111">Marketoga ühendumine</span><span class="sxs-lookup"><span data-stu-id="7a807-111">Connect to Marketo</span></span>

1. <span data-ttu-id="7a807-112">Avage **Haldus** > **Ekspordi sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="7a807-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7a807-113">Tehke jaotises **Marketo** valik **Seadista**.</span><span class="sxs-lookup"><span data-stu-id="7a807-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="7a807-114">Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="7a807-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7a807-115">Sisestage oma **[Marketo kliendi-ID, klientrakenduse salatus ja REST-i lõpp-punkti hostinimi](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="7a807-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="7a807-116">Sisestage oma **[Marketo loendi ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="7a807-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="7a807-117">Valige **Nõustun**, et nõustuda jaotise **Andmete privaatsus ja nõuetele vastavus** tingimustega ja valige **Ühenda**, et Marketoga ühenduda.</span><span class="sxs-lookup"><span data-stu-id="7a807-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="7a807-118">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="7a807-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Marketo ühenduse ekspordi kuvatõmmis":::

1. <span data-ttu-id="7a807-120">Ekspordi konfigureerimiseks valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="7a807-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="7a807-121">Konnektori konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="7a807-121">Configure the connector</span></span>

1. <span data-ttu-id="7a807-122">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="7a807-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="7a807-123">Soovi korral saate isikupärastatud meilide loomiseks täiendavalt eksportida väljad **Eesnimi**, **Perekonnanimi**, **Linn**, **Maakond** ja **Riik/regioon**.</span><span class="sxs-lookup"><span data-stu-id="7a807-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="7a807-124">Nende väljade vastendamiseks valige **Lisa atribuut**.</span><span class="sxs-lookup"><span data-stu-id="7a807-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="7a807-125">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="7a807-125">Select the segments you want to export.</span></span> <span data-ttu-id="7a807-126">Marketosse saate eksportida kuni miljon kliendiprofiili.</span><span class="sxs-lookup"><span data-stu-id="7a807-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Väljade ja segmentide valimine Marketosse eksportimiseks":::

1. <span data-ttu-id="7a807-128">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="7a807-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7a807-129">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="7a807-129">Export the data</span></span>

<span data-ttu-id="7a807-130">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="7a807-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="7a807-131">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7a807-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7a807-132">Marketos leiate nüüd oma segmendid jaotisest [Marketo loendid](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="7a807-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7a807-133">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="7a807-133">Known limitations</span></span>

- <span data-ttu-id="7a807-134">Marketosse saab eksportida korraga kuni miljon profiili.</span><span class="sxs-lookup"><span data-stu-id="7a807-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="7a807-135">Marketosse saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="7a807-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="7a807-136">Miljoni profiiliga segmentide eksportimine võib kesta kuni kolm tundi.</span><span class="sxs-lookup"><span data-stu-id="7a807-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="7a807-137">Marketosse eksporditavate profiilide arv sõltub Marketoga sõlmitud lepingust.</span><span class="sxs-lookup"><span data-stu-id="7a807-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7a807-138">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="7a807-138">Data privacy and compliance</span></span>

<span data-ttu-id="7a807-139">Kui lubate Dynamics 365 Customer Insightsil Marketosse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="7a807-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7a807-140">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Marketo täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="7a807-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7a807-141">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7a807-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7a807-142">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="7a807-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]