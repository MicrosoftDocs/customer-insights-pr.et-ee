---
title: Customer Insightsi andmete eksportimine SendGridi
description: Vaadake, kuidas konfigureerida ühendust SendGridiga.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597276"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="cc0b3-103">SendGridi konnektor (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="cc0b3-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="cc0b3-104">Saate eksportida ühendatud kliendiprofiilide segmente SendGridi kontaktiloenditesse ja kasutada neid SendGridis kampaaniate ja meiliturunduste jaoks.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="cc0b3-105">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="cc0b3-105">Prerequisites</span></span>

-   <span data-ttu-id="cc0b3-106">Teil on [SendGridi konto](https://sendgrid.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="cc0b3-107">SendGridis on olemas kontaktiloendid ja asjakohased ID-d.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="cc0b3-108">Lisateavet leiate teemast [SendGrid – kontaktide haldamine](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="cc0b3-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="cc0b3-109">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="cc0b3-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="cc0b3-110">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="cc0b3-111">Ühenda SendGrid</span><span class="sxs-lookup"><span data-stu-id="cc0b3-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="cc0b3-112">Avage **Haldus** > **Ekspordi sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cc0b3-113">Tehke jaotises **SendGrid** valik **Seadista**.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="cc0b3-114">Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGridi ekspordi konfiguratsioonipaan.":::

1. <span data-ttu-id="cc0b3-116">Sisestage oma **SendGridi API võti** [SendGridi API võti](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="cc0b3-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="cc0b3-117">Sisestage oma **[SendGridi loendi ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="cc0b3-118">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cc0b3-119">Valige **Ühenda**, et käivitada ühendus SendGridiga.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="cc0b3-120">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="cc0b3-121">Ekspordi konfigureerimiseks valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="cc0b3-122">Konnektori konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="cc0b3-122">Configure the connector</span></span>

1. <span data-ttu-id="cc0b3-123">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="cc0b3-124">Korrake samu juhiseid muude valikuliste väljade puhul, nagu **Eesnimi**, **Perekonnanimi**, **Riik/piirkond**, **Maakond**, **Linn** ja **Sihtnumber**.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="cc0b3-125">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-125">Select the segments you want to export.</span></span> <span data-ttu-id="cc0b3-126">Soovitame **tungivalt mitte eksportida kokku üle 100 000 kliendiprofiili** SendGridi.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="cc0b3-127">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="cc0b3-128">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="cc0b3-128">Export the data</span></span>

<span data-ttu-id="cc0b3-129">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cc0b3-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="cc0b3-130">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cc0b3-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cc0b3-131">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="cc0b3-131">Known limitations</span></span>

- <span data-ttu-id="cc0b3-132">Kokku kuni 100 000 profiili SendGridi.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="cc0b3-133">SendGridi saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="cc0b3-134">Kuni 100 000 profiili eksportimiseks SendGridi võib kuluda paar tundi.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="cc0b3-135">SendGridi eksporditavate profiilide arv sõltub SendGridiga sõlmitud lepingust.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cc0b3-136">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="cc0b3-136">Data privacy and compliance</span></span>

<span data-ttu-id="cc0b3-137">Kui lubate Dynamics 365 Customer Insightsil SendGridi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="cc0b3-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cc0b3-138">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et SendGrid täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="cc0b3-139">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cc0b3-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="cc0b3-140">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="cc0b3-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]