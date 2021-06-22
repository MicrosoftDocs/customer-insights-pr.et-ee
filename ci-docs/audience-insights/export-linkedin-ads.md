---
title: Customer Insights andmete eksportimine LinkedIn Adsi
description: Lugege, kuidas konfigureerida ühendust ja eksportida LinkedIn Adsi.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124479"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="ac51d-103">Segmentide eksportimine LinkedIn Adsi (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="ac51d-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="ac51d-104">Eksportige ühtsete kliendiprofiilide segmendid LinkedIn Adsi, et luua sobivaid vaatajaskondi.</span><span class="sxs-lookup"><span data-stu-id="ac51d-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="ac51d-105">Kasutage sobitatud sihtrühmi ettevõtte sihtimiseks ja kontaktide sihtimiseks.</span><span class="sxs-lookup"><span data-stu-id="ac51d-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac51d-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="ac51d-106">Prerequisites</span></span>

-   <span data-ttu-id="ac51d-107">Teil on [LinkedIn Campaign Manager konto](https://business.linkedin.com/marketing-solutions/ads) ja vastav administraatori sisselogimisandmed.</span><span class="sxs-lookup"><span data-stu-id="ac51d-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ac51d-108">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ac51d-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ac51d-109">Eksporditud segmentide kliendiprofiilid sisaldavad meiliaadressiga välja.</span><span class="sxs-lookup"><span data-stu-id="ac51d-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ac51d-110">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="ac51d-110">Known limitations</span></span>

- <span data-ttu-id="ac51d-111">LinkedIn Adsi saate eksportida kuni 100 000 profiili ekspordi kohta.</span><span class="sxs-lookup"><span data-stu-id="ac51d-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="ac51d-112">Eksportimine LinkedIn Adsi on piiratud segmentidega.</span><span class="sxs-lookup"><span data-stu-id="ac51d-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="ac51d-113">Kuni 100 000 profiili eksportimine LinkedIn Adsi võib võtta kuni 10 minutit lõpuleviimiseks.</span><span class="sxs-lookup"><span data-stu-id="ac51d-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="ac51d-114">Loo LinkedIn Adsi ühendus</span><span class="sxs-lookup"><span data-stu-id="ac51d-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="ac51d-115">Avage sihtrühma ülevaadetes **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="ac51d-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ac51d-116">Valige **Lisa ühendus** ja valige **LinkedIn Ads** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="ac51d-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="ac51d-117">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="ac51d-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ac51d-118">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="ac51d-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ac51d-119">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="ac51d-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ac51d-120">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="ac51d-120">Choose who can use this connection.</span></span> <span data-ttu-id="ac51d-121">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="ac51d-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="ac51d-122">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ac51d-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ac51d-123">Sisestage oma [LinkedIn Campaign Manager konto ID](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="ac51d-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="ac51d-124">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="ac51d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ac51d-125">Valige **Ühenda** Campaign Monitoriga ühenduse lähtestamiseks.</span><span class="sxs-lookup"><span data-stu-id="ac51d-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="ac51d-126">Valige **Autentimine LinkedIn** ja sisestage oma administraatori mandaadid LinkedIn Campaign Manager jaoks.</span><span class="sxs-lookup"><span data-stu-id="ac51d-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="ac51d-127">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="ac51d-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ac51d-128">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="ac51d-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ac51d-129">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="ac51d-129">Configure an export</span></span>

<span data-ttu-id="ac51d-130">Kui teil on juurdepääs sellist tüüpi ühendusele, saate ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="ac51d-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="ac51d-131">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ac51d-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ac51d-132">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="ac51d-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ac51d-133">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="ac51d-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ac51d-134">Valige **Ekspordiühendus** väljal ühendus LinkedIn Ads jaotisest.</span><span class="sxs-lookup"><span data-stu-id="ac51d-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="ac51d-135">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="ac51d-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ac51d-136">Valige, kas soovite eksportida andmeid, et teha [kontaktide sihtimist](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) või [ettevõtte sihtimist](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) LinkedInis.</span><span class="sxs-lookup"><span data-stu-id="ac51d-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="ac51d-137">Valige jaotises **Andmete sobitamine** oma ühtse kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="ac51d-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ac51d-138">Segmentide eksportimine LinkedIn Adsi on vajalik.</span><span class="sxs-lookup"><span data-stu-id="ac51d-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="ac51d-139">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="ac51d-139">Select the segments you want to export.</span></span> <span data-ttu-id="ac51d-140">LinkedIn Campaign Manager sobitatud sihtrühmad luuakse automaatselt ekspordiks valitud segmentide nimega.</span><span class="sxs-lookup"><span data-stu-id="ac51d-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="ac51d-141">Iga segmendi tulemuseks on eraldi sobitatud sihtrühm.</span><span class="sxs-lookup"><span data-stu-id="ac51d-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="ac51d-142">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="ac51d-142">Select **Save**.</span></span>

<span data-ttu-id="ac51d-143">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="ac51d-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ac51d-144">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ac51d-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ac51d-145">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ac51d-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ac51d-146">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="ac51d-146">Data privacy and compliance</span></span>

<span data-ttu-id="ac51d-147">Kui lubate, et Dynamics 365 Customer Insights edastab andmeid LinkedIn Adsi, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed.</span><span class="sxs-lookup"><span data-stu-id="ac51d-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ac51d-148">Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et LinkedIn Ads vastaks teie võimalikele privaatsus- või turvalisuse nõuetele.</span><span class="sxs-lookup"><span data-stu-id="ac51d-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ac51d-149">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ac51d-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ac51d-150">Teie Dynamics 365 Customer Insights administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="ac51d-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
