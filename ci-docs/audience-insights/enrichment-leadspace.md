---
title: Ettevõtteprofiilide rikastamine kolmanda osapoole rikastamisteenusega Leadspace'ilt
description: Üldine teave Leadspace'i kolmanda osapoole rikastamise kohta.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269417"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="330a4-103">Ettevõtte profiilide rikastamine Leadspace'iga (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="330a4-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="330a4-104">Leadspace on andmeteaduse ettevõte, mis pakub kliendi hulgiandmete platvormi.</span><span class="sxs-lookup"><span data-stu-id="330a4-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="330a4-105">See võimaldab ettevõtetel kliendi koondprofiilidega klientide andmeid rikastada.</span><span class="sxs-lookup"><span data-stu-id="330a4-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="330a4-106">Rikastamised hõlmavad lisaatribuute, nt ettevõtte suurus, asukoht, valdkond jne.</span><span class="sxs-lookup"><span data-stu-id="330a4-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="330a4-107">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="330a4-107">Prerequisites</span></span>

<span data-ttu-id="330a4-108">Leadspace'i seadistamiseks peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="330a4-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="330a4-109">Teil on aktiivne Leadspace'i litsents ja „igavene võti“ (edaspidi **Leadspace'i tõend**).</span><span class="sxs-lookup"><span data-stu-id="330a4-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="330a4-110">Nende toote kohta üksikasjade saamiseks võtke otse [Leadspace’iga](https://www.leadspace.com/products/leadspace-on-demand/) ühendust.</span><span class="sxs-lookup"><span data-stu-id="330a4-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="330a4-111">Teil on [administraatori](permissions.md#administrator) õigused.</span><span class="sxs-lookup"><span data-stu-id="330a4-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="330a4-112">Teil on ettevõtete [kliendi koondprofiilid](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="330a4-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="330a4-113">Konfiguratsioon</span><span class="sxs-lookup"><span data-stu-id="330a4-113">Configuration</span></span>

1. <span data-ttu-id="330a4-114">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Rikastamine**.</span><span class="sxs-lookup"><span data-stu-id="330a4-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="330a4-115">Valige Leadspace’i paanil suvand **Rikasta minu andmeid**.</span><span class="sxs-lookup"><span data-stu-id="330a4-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace'i paani kuvatõmmis.":::

1. <span data-ttu-id="330a4-117">Valige **Alusta** ja seejärel sisestage aktiivne **Leadspace'i tõend** (igavene võti).</span><span class="sxs-lookup"><span data-stu-id="330a4-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="330a4-118">Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="330a4-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="330a4-119">Kinnitage mõlemad sisendid, valides **Loo ühendus Leadspace'iga**.</span><span class="sxs-lookup"><span data-stu-id="330a4-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="330a4-120">Valige **Vastenda andmed** ja valige andmete kogum, mida soovite Leadspace'i ettevõtte andmetega rikastada.</span><span class="sxs-lookup"><span data-stu-id="330a4-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="330a4-121">Saate valida olemi *Klient*, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.</span><span class="sxs-lookup"><span data-stu-id="330a4-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Valige kliendiprofiili ja segmendi rikastamise vahel.":::

1. <span data-ttu-id="330a4-123">Klõpsake suvandit **Edasi** ja määratlege, milliseid teie koondatud profiilide välju tuleks kasutada, et otsida ühtivad andmeid Leadspace'ist.</span><span class="sxs-lookup"><span data-stu-id="330a4-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="330a4-124">Nõutav on väli **Ettevõtte nimi**.</span><span class="sxs-lookup"><span data-stu-id="330a4-124">The **Name of company** field is required.</span></span> <span data-ttu-id="330a4-125">Selleks et vasted oleksid täpsemad, saab lisada kuni kaks muud välja (**Ettevõtte veebisait** ja **Ettevõtte asukoht**).</span><span class="sxs-lookup"><span data-stu-id="330a4-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace'i väljade vastendamise paan.":::
   
1. <span data-ttu-id="330a4-127">Valige **Rakenda**, et lõpetada väljade vastendamine.</span><span class="sxs-lookup"><span data-stu-id="330a4-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="330a4-128">Valige ettevõtte profiilide rikastamiseks **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="330a4-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="330a4-129">Rikastamise kestus sõltub koondatud kliendiprofiilide arvust.</span><span class="sxs-lookup"><span data-stu-id="330a4-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="330a4-130">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="330a4-130">Enrichment results</span></span>

<span data-ttu-id="330a4-131">Pärast rikastamise värskendamist saate värskelt rikastatud ettevõtte andmed üle vaadata jaotises [Minu rikastamised](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="330a4-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="330a4-132">Kuvatakse viimase värskendamise aeg ja rikastatud profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="330a4-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="330a4-133">Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.</span><span class="sxs-lookup"><span data-stu-id="330a4-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="330a4-134">Lisateavet leiate teemast [Leadspace'i API-d](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="330a4-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="330a4-135">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="330a4-135">Next steps</span></span>

<span data-ttu-id="330a4-136">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="330a4-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="330a4-137">Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [Ekspordi andmed](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="330a4-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="330a4-138">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="330a4-138">Data privacy and compliance</span></span>

<span data-ttu-id="330a4-139">Kui lubate Dynamics 365 Customer Insightsil Leadspace'i andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="330a4-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="330a4-140">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Leadspace täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="330a4-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="330a4-141">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="330a4-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="330a4-142">Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="330a4-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]