---
title: Customer Insights andmete eksportimine Constant Contacti
description: Lugege, kuidas konfigureerida ühendust ja eksportida Constant Contacti.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124268"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="597db-103">Segmentide eksportimine Constant Contacti (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="597db-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="597db-104">Saate eksportida ühendatud kliendiprofiilide segmente Constant Contacti ja kasutada neid turundustegevuste jaoks.</span><span class="sxs-lookup"><span data-stu-id="597db-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="597db-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="597db-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="597db-106">Teil on [Constant Contact konto](https://www.constantcontact.com/account-home) ja vastav administraatori mandaat.</span><span class="sxs-lookup"><span data-stu-id="597db-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="597db-107">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="597db-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="597db-108">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="597db-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="597db-109">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="597db-109">Known limitations</span></span>

- <span data-ttu-id="597db-110">Constant Contacti saate eksportida kuni 1 miljoni profiili ekspordi kohta.</span><span class="sxs-lookup"><span data-stu-id="597db-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="597db-111">Eksportimine Constant Contacti on piiratud segmentidega.</span><span class="sxs-lookup"><span data-stu-id="597db-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="597db-112">Kuni 1 miljoni profiili eksportimine Constant Contacti võib võtta kuni 1 tunni lõpuleviimiseks.</span><span class="sxs-lookup"><span data-stu-id="597db-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="597db-113">Constant Contacti eksporditavate profiilide arv sõltub ja on piiratud teie lepinguga Constant Contactiga.</span><span class="sxs-lookup"><span data-stu-id="597db-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="597db-114">Ühenduse loomine Constant Contactiga</span><span class="sxs-lookup"><span data-stu-id="597db-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="597db-115">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="597db-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="597db-116">Valige **Lisa ühendus** ja valige **Constant Contact** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="597db-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="597db-117">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="597db-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="597db-118">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="597db-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="597db-119">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="597db-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="597db-120">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="597db-120">Choose who can use this connection.</span></span> <span data-ttu-id="597db-121">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="597db-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="597db-122">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="597db-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="597db-123">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="597db-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="597db-124">Valige **Ühenda** Constant Contactiga ühenduse lähtestamiseks.</span><span class="sxs-lookup"><span data-stu-id="597db-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="597db-125">Valige **Autentimine Constant Contactiga** ja sisestage oma administraatori mandaadid Constant Contacti jaoks.</span><span class="sxs-lookup"><span data-stu-id="597db-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="597db-126">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="597db-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="597db-127">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="597db-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="597db-128">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="597db-128">Configure an export</span></span>

<span data-ttu-id="597db-129">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="597db-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="597db-130">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="597db-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="597db-131">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="597db-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="597db-132">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="597db-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="597db-133">Valige **Ekspordiühendus** väljal ühendus Constant Contacti jaotisest.</span><span class="sxs-lookup"><span data-stu-id="597db-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="597db-134">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="597db-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="597db-135">Sisestage oma [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="597db-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="597db-136">Et leida URL-ist loendi ID, avage loend Constant Contactis.</span><span class="sxs-lookup"><span data-stu-id="597db-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="597db-137">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="597db-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="597db-138">Segmentide eksportimine Constant Contacti on vajalik.</span><span class="sxs-lookup"><span data-stu-id="597db-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="597db-139">Soovi korral saate isikupärastatud meilide loomiseks täiendavalt eksportida väljad Eesnimi ja Perekonnanimi.</span><span class="sxs-lookup"><span data-stu-id="597db-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="597db-140">Nende väljade vastendamiseks valige **Lisa atribuut**.</span><span class="sxs-lookup"><span data-stu-id="597db-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="597db-141">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="597db-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="597db-142">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="597db-142">Select **Save**.</span></span>

<span data-ttu-id="597db-143">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="597db-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="597db-144">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="597db-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="597db-145">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="597db-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="597db-146">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="597db-146">Data privacy and compliance</span></span>

<span data-ttu-id="597db-147">Kui lubate, et Dynamics 365 Customer Insights edastab andmeid Constant Contactile, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed.</span><span class="sxs-lookup"><span data-stu-id="597db-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="597db-148">Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et Constant Contact vastaks teie võimalikele privaatsus- või turvalisuse nõuetele.</span><span class="sxs-lookup"><span data-stu-id="597db-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="597db-149">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="597db-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="597db-150">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="597db-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
