---
title: Customer Insightsi andmete eksportimine Mailchimpi
description: Lugege, kuidas konfigureerida ühendust ja eksportida Mailchimpi.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976150"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="202b1-103">Segmendiloendite eksportimine Mailchimpi (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="202b1-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="202b1-104">Eksportige koondatud kliendiprofiilide segmendid MailChimpi, et luua teabelehti ja meilikampaaniad.</span><span class="sxs-lookup"><span data-stu-id="202b1-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="202b1-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="202b1-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="202b1-106">Teil on [Mailchimpi konto](https://mailchimp.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="202b1-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="202b1-107">Mailchimpis on olemas sihtrühmad ja asjakohased ID-d.</span><span class="sxs-lookup"><span data-stu-id="202b1-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="202b1-108">Lisateavet leiate teemast [Mailchimpi sihtrühmad](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="202b1-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="202b1-109">Te olete [konfigureerinud segmendid](segments.md)</span><span class="sxs-lookup"><span data-stu-id="202b1-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="202b1-110">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="202b1-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="202b1-111">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="202b1-111">Known limitations</span></span>

- <span data-ttu-id="202b1-112">Mailchimpi saab eksportida korraga kuni miljon profiili.</span><span class="sxs-lookup"><span data-stu-id="202b1-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="202b1-113">Mailchimpi saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="202b1-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="202b1-114">1 miljoni profiiliga segmentide eksportimiseks võib aega minna kuni kolm tundi.</span><span class="sxs-lookup"><span data-stu-id="202b1-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="202b1-115">Mailchimpi eksporditavate profiilide arv sõltub Mailchimpiga sõlmitud lepingust.</span><span class="sxs-lookup"><span data-stu-id="202b1-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="202b1-116">Ühenduse loomine Mailchimpiga</span><span class="sxs-lookup"><span data-stu-id="202b1-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="202b1-117">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="202b1-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="202b1-118">Valige **Lisa ühendus** ja valige **Autopilot** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="202b1-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="202b1-119">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="202b1-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="202b1-120">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="202b1-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="202b1-121">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="202b1-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="202b1-122">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="202b1-122">Choose who can use this connection.</span></span> <span data-ttu-id="202b1-123">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="202b1-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="202b1-124">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="202b1-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="202b1-125">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="202b1-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="202b1-126">Valige **Ühenda** Mailchimp ühenduse lähtestamiseks.</span><span class="sxs-lookup"><span data-stu-id="202b1-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="202b1-127">Valige **Autentimine Mailchimpiga** ja sisestage oma Mailchimpi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="202b1-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="202b1-128">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="202b1-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="202b1-129">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="202b1-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="202b1-130">Konnektori konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="202b1-130">Configure the connector</span></span>

<span data-ttu-id="202b1-131">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="202b1-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="202b1-132">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="202b1-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="202b1-133">Minge **Andmed**> **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="202b1-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="202b1-134">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="202b1-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="202b1-135">Valige **Ekspordiühendus** väljal ühendus Mailchimp jaotisest.</span><span class="sxs-lookup"><span data-stu-id="202b1-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="202b1-136">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="202b1-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="202b1-137">Sisestage oma **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="202b1-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="202b1-138">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="202b1-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="202b1-139">Soovi korral saate eksportida **Eesnimi** ja **Perekonnanimi** isikupärastatud meilide loomiseks.</span><span class="sxs-lookup"><span data-stu-id="202b1-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="202b1-140">Nende väljade vastendamiseks valige **Lisa atribuut**.</span><span class="sxs-lookup"><span data-stu-id="202b1-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="202b1-141">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="202b1-141">Select the segments you want to export.</span></span> <span data-ttu-id="202b1-142">Mailchimpi saate eksportida kuni miljon kliendiprofiili.</span><span class="sxs-lookup"><span data-stu-id="202b1-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="202b1-143">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="202b1-143">Select **Save**.</span></span>

<span data-ttu-id="202b1-144">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="202b1-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="202b1-145">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="202b1-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="202b1-146">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="202b1-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="202b1-147">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="202b1-147">Data privacy and compliance</span></span>

<span data-ttu-id="202b1-148">Kui lubate Dynamics 365 Customer Insightsil Mailchimpi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="202b1-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="202b1-149">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Mailchimp täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="202b1-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="202b1-150">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="202b1-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="202b1-151">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="202b1-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
