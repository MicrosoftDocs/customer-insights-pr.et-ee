---
title: Customer Insights andmete eksportimine Sendinblue'sse
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314601"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="a1b5c-103">Segmentide eksportimine Sendinblue (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="a1b5c-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="a1b5c-104">Kampaaniate loomiseks, e-posti teel turundamiseks ja konkreetsete klientide rühmade kasutamiseks saate eksportida ühtsete kliendiprofiilide segmente Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="a1b5c-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="a1b5c-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="a1b5c-106">Teil on [Sendinblue konto](https://www.sendinblue.com/) ja vastav administraatori mandaat.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a1b5c-107">Sendinblue's on olemas loendid ja vastavad ID-d.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="a1b5c-108">Te olete [konfigureerinud segmendid](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a1b5c-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="a1b5c-109">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a1b5c-110">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="a1b5c-110">Known limitations</span></span>

- <span data-ttu-id="a1b5c-111">Kuni 1 miljon profiili Sendinblue'sse eksportimise kohta.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="a1b5c-112">Sendinblue eksportimine on piiratud segmentidega.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="a1b5c-113">Kokku 1 miljoni profiiliga segmentide eksportimiseks võib kuluda kuni 90 minutit.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="a1b5c-114">Sendinblue'sse eksporditavate profiilide arv sõltub Sendinblue lepingust ja on piiratud.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="a1b5c-115">Sendinblue ühenduse häälestamine</span><span class="sxs-lookup"><span data-stu-id="a1b5c-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="a1b5c-116">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a1b5c-117">Valige **Lisa ühendus** ja valige **Sendinblue** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="a1b5c-118">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a1b5c-119">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a1b5c-120">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a1b5c-121">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-121">Choose who can use this connection.</span></span> <span data-ttu-id="a1b5c-122">Vaikimisi on see ainult Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-122">By default it's only administrators.</span></span> <span data-ttu-id="a1b5c-123">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a1b5c-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a1b5c-124">Sisestage **[SendinBlue API-võti](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="a1b5c-125">Valige **Nõustun**, et kinnitada **Andmete privaatsus ja nõuetele vastavus** ning valige **Ühenda** Sendinblue ühenduse lähtestamiseks.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="a1b5c-126">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a1b5c-127">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a1b5c-128">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="a1b5c-128">Configure an export</span></span>

<span data-ttu-id="a1b5c-129">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a1b5c-130">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a1b5c-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a1b5c-131">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a1b5c-132">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a1b5c-133">Valige **Ühendus ekspordiks** väljal soovitud ühendus Sendinblue jaotisest.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="a1b5c-134">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a1b5c-135">Sisestage oma **Sendinblue loendi ID**</span><span class="sxs-lookup"><span data-stu-id="a1b5c-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="a1b5c-136">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="a1b5c-137">Soovi korral saate eksportida **Eesnimi**, **Perekonnanimi** ja **Telefon**, et luua rohkem isikupärastatud e-kirju.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="a1b5c-138">Nende väljade vastendamiseks valige **Lisa atribuut**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="a1b5c-139">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="a1b5c-140">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-140">Select **Save**.</span></span>

<span data-ttu-id="a1b5c-141">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a1b5c-142">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a1b5c-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a1b5c-143">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a1b5c-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a1b5c-144">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="a1b5c-144">Data privacy and compliance</span></span>

<span data-ttu-id="a1b5c-145">Kui lubate Dynamics 365 Customer Insights edastada andmeid Sendinlue'le, lubate andmete edastamist väljapoole vastavuse piiri Dynamics 365 Customer Insights jaoks, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a1b5c-146">Microsoft edastab sellised andmed teie juhiste alusel, kuid teie vastutate selle eest, et Sendinblue täidaks kõiki privaatsus- või turvakohustusi, mis teil võivad olla.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a1b5c-147">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a1b5c-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a1b5c-148">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="a1b5c-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
