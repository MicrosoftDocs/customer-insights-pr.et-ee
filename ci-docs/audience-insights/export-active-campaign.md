---
title: Customer Insights andmete eksportimine ActiveCampaigni
description: Vaadake, kuidas konfigureerida ühendust ja eksportida ActiveCampaigni.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314602"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="9070d-103">Segmentide eksportimine ActiveCampaigni (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="9070d-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="9070d-104">Eksportige ühtsete kliendiprofiilide segmendid ActiveCampaigni ja kasutage neid turundustegevusteks.</span><span class="sxs-lookup"><span data-stu-id="9070d-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9070d-105">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="9070d-105">Prerequisites</span></span>

-   <span data-ttu-id="9070d-106">Teil on [ActiveCampaign konto](https://www.activecampaign.com/) ja vastav administraatori mandaat.</span><span class="sxs-lookup"><span data-stu-id="9070d-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9070d-107">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9070d-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="9070d-108">Eksporditud segmentide ühildatud kliendiprofiilid sisaldavad meiliaadressiga välja.</span><span class="sxs-lookup"><span data-stu-id="9070d-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9070d-109">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="9070d-109">Known limitations</span></span>

- <span data-ttu-id="9070d-110">ActiveCampaigni saate eksportida kuni 1 miljon profiili ekspordi kohta ja selle lõpuleviimiseks võib kuluda kuni 90 minutit.</span><span class="sxs-lookup"><span data-stu-id="9070d-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="9070d-111">ActiveCampaign eksportimine on piiratud segmentidega.</span><span class="sxs-lookup"><span data-stu-id="9070d-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="9070d-112">ActiveCampaign eksporditavate profiilide arv sõltub teie ActiveCampaign lepingust.</span><span class="sxs-lookup"><span data-stu-id="9070d-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="9070d-113">Saate häälestada ActiveCampaign ühendust</span><span class="sxs-lookup"><span data-stu-id="9070d-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="9070d-114">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="9070d-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9070d-115">Valige **Lisa ühendus** ja valige **ActiveCampaign** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="9070d-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="9070d-116">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="9070d-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9070d-117">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="9070d-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9070d-118">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="9070d-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9070d-119">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="9070d-119">Choose who can use this connection.</span></span> <span data-ttu-id="9070d-120">Vaikimisi on see ainult Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="9070d-120">By default, it's only administrators.</span></span> <span data-ttu-id="9070d-121">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9070d-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9070d-122">Sisestage oma [ActiveCampaign API võti ja REST lõpp-punkti hostinimi](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="9070d-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="9070d-123">REST lõpp-punkti hostinimi on ainult hostinimi ilma https://.</span><span class="sxs-lookup"><span data-stu-id="9070d-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="9070d-124">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="9070d-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9070d-125">**Ühenda** ActiveCampaign ühenduse lähtestamiseks.</span><span class="sxs-lookup"><span data-stu-id="9070d-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="9070d-126">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="9070d-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9070d-127">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="9070d-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9070d-128">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="9070d-128">Configure an export</span></span>

<span data-ttu-id="9070d-129">Kui teil on juurdepääs sellist tüüpi ühendusele, saate ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="9070d-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="9070d-130">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9070d-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9070d-131">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="9070d-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9070d-132">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="9070d-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9070d-133">Valige **Ühendus ekspordiks** väljal soovitud ühendus ActiveCampaign jaotisest.</span><span class="sxs-lookup"><span data-stu-id="9070d-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="9070d-134">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="9070d-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9070d-135">Sisestage oma [**ActiveCampaigni loendi ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="9070d-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="9070d-136">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="9070d-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="9070d-137">Segmentide ActiveCampaign eksportimine on vajalik.</span><span class="sxs-lookup"><span data-stu-id="9070d-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="9070d-138">Soovi korral saate isikupärastatud meilide loomiseks eksportida eesnime, perekonnanime ja telefoni.</span><span class="sxs-lookup"><span data-stu-id="9070d-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="9070d-139">Nende väljade vastendamiseks valige Lisa atribuut.</span><span class="sxs-lookup"><span data-stu-id="9070d-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="9070d-140">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="9070d-140">Select **Save**.</span></span>

<span data-ttu-id="9070d-141">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="9070d-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9070d-142">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9070d-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9070d-143">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9070d-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9070d-144">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="9070d-144">Data privacy and compliance</span></span>

<span data-ttu-id="9070d-145">Kui lubate Dynamics 365 Customer Insights edastada andmeid ActiveCampaign'i, lubate andmete edastamist väljapoole vastavuse piiri Dynamics 365 Customer Insights jaoks, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid.</span><span class="sxs-lookup"><span data-stu-id="9070d-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9070d-146">Microsoft edastab sellised andmed teie juhiste alusel, kuid teie vastutate selle eest, et ActiveCampaign täidaks kõiki privaatsus- või turvakohustusi, mis teil võivad olla.</span><span class="sxs-lookup"><span data-stu-id="9070d-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9070d-147">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9070d-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="9070d-148">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="9070d-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
