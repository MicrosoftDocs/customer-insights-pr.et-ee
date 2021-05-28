---
title: Customer Insightsi andmete eksportimine SendGridi
description: Lugege, kuidas konfigureerida ühendust ja eksportida SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976911"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="7c717-103">Segmentide eksportimine SendGrid (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="7c717-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="7c717-104">Saate eksportida ühendatud kliendiprofiilide segmente SendGridi kontaktiloenditesse ja kasutada neid SendGridis kampaaniate ja meiliturunduste jaoks.</span><span class="sxs-lookup"><span data-stu-id="7c717-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="7c717-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="7c717-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="7c717-106">Teil on [SendGridi konto](https://sendgrid.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="7c717-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="7c717-107">SendGridis on olemas kontaktiloendid ja asjakohased ID-d.</span><span class="sxs-lookup"><span data-stu-id="7c717-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="7c717-108">Lisateavet leiate teemast [SendGrid – kontaktide haldamine](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="7c717-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="7c717-109">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="7c717-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="7c717-110">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="7c717-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="7c717-111">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="7c717-111">Known limitations</span></span>

- <span data-ttu-id="7c717-112">Kokku kuni 100 000 profiili SendGridi.</span><span class="sxs-lookup"><span data-stu-id="7c717-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="7c717-113">SendGridi saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="7c717-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="7c717-114">Kuni 100 000 profiili eksportimiseks SendGridi võib kuluda paar tundi.</span><span class="sxs-lookup"><span data-stu-id="7c717-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="7c717-115">SendGridi eksporditavate profiilide arv sõltub SendGridiga sõlmitud lepingust.</span><span class="sxs-lookup"><span data-stu-id="7c717-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="7c717-116">Ühenduse loomine SendGrid</span><span class="sxs-lookup"><span data-stu-id="7c717-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="7c717-117">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="7c717-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="7c717-118">Valige **Lisa ühendus** ja valige **SendGrid** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="7c717-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="7c717-119">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="7c717-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="7c717-120">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="7c717-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="7c717-121">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="7c717-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="7c717-122">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="7c717-122">Choose who can use this connection.</span></span> <span data-ttu-id="7c717-123">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="7c717-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="7c717-124">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7c717-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="7c717-125">Sisestage oma **SendGridi API võti** [SendGridi API võti](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="7c717-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="7c717-126">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="7c717-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="7c717-127">Valige **Ühenda**, et käivitada ühendus SendGridiga.</span><span class="sxs-lookup"><span data-stu-id="7c717-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="7c717-128">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="7c717-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="7c717-129">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="7c717-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="7c717-130">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="7c717-130">Configure an export</span></span>

<span data-ttu-id="7c717-131">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="7c717-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="7c717-132">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="7c717-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="7c717-133">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="7c717-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7c717-134">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="7c717-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="7c717-135">Valige **Ekspordiühendus** väljal ühendus SendGrid jaotisest.</span><span class="sxs-lookup"><span data-stu-id="7c717-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="7c717-136">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="7c717-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="7c717-137">Sisestage oma **[SendGridi loendi ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="7c717-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="7c717-138">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="7c717-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="7c717-139">Korrake samu juhiseid muude valikuliste väljade puhul, nagu **Eesnimi**, **Perekonnanimi**, **Riik/piirkond**, **Maakond**, **Linn** ja **Sihtnumber**.</span><span class="sxs-lookup"><span data-stu-id="7c717-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="7c717-140">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="7c717-140">Select the segments you want to export.</span></span> <span data-ttu-id="7c717-141">Soovitame **tungivalt mitte eksportida kokku üle 100 000 kliendiprofiili** SendGridi.</span><span class="sxs-lookup"><span data-stu-id="7c717-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="7c717-142">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="7c717-142">Select **Save**.</span></span>

<span data-ttu-id="7c717-143">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="7c717-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="7c717-144">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7c717-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7c717-145">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="7c717-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7c717-146">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="7c717-146">Data privacy and compliance</span></span>

<span data-ttu-id="7c717-147">Kui lubate Dynamics 365 Customer Insightsil SendGridi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="7c717-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7c717-148">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et SendGrid täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="7c717-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="7c717-149">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7c717-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7c717-150">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="7c717-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]