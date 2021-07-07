---
title: Ettevõtteprofiilide rikastamine kolmanda osapoole rikastamisteenusega Leadspace'ilt
description: Üldine teave Leadspace'i kolmanda osapoole rikastamise kohta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305197"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="24c0c-103">Ettevõtte profiilide rikastamine Leadspace'iga (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="24c0c-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="24c0c-104">Leadspace on andmeteaduse ettevõte, mis pakub kliendi hulgiandmete platvormi.</span><span class="sxs-lookup"><span data-stu-id="24c0c-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="24c0c-105">See võimaldab ettevõtetel kliendi koondprofiilidega klientide andmeid rikastada.</span><span class="sxs-lookup"><span data-stu-id="24c0c-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="24c0c-106">Rikastused sisaldavad rohkem atribuute, nagu ettevõtte suurus, asukoht, tegevusala ja palju muud.</span><span class="sxs-lookup"><span data-stu-id="24c0c-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="24c0c-107">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="24c0c-107">Prerequisites</span></span>

<span data-ttu-id="24c0c-108">Leadspace'i seadistamiseks peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="24c0c-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="24c0c-109">Teil on aktiivne Leadspace litsents.</span><span class="sxs-lookup"><span data-stu-id="24c0c-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="24c0c-110">Teil on ettevõtete [kliendi koondprofiilid](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="24c0c-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="24c0c-111">Administraator on juba konfigureerinud Leadspace'i ühenduse või teil on [administraatoriõigused](permissions.md#administrator) ja "alaline võti (nimetatakse **Leadspace tokeniks**).</span><span class="sxs-lookup"><span data-stu-id="24c0c-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="24c0c-112">Võtke [Leadspaceiga](https://www.leadspace.com/products/leadspace-on-demand/) otse ühendust toodete üksikasjade teabe saamiseks.</span><span class="sxs-lookup"><span data-stu-id="24c0c-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="24c0c-113">Rikastamise konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="24c0c-113">Configure the enrichment</span></span>

1. <span data-ttu-id="24c0c-114">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Rikastamine**.</span><span class="sxs-lookup"><span data-stu-id="24c0c-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="24c0c-115">Valige **Mu andmete rikastamine** Leadspace paanil ja valige **Alustamine**.</span><span class="sxs-lookup"><span data-stu-id="24c0c-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace'i paani kuvatõmmis.":::

1. <span data-ttu-id="24c0c-117">Valige [ühendus](connections.md) ripploendist.</span><span class="sxs-lookup"><span data-stu-id="24c0c-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="24c0c-118">Kui ühendusi pole saadaval, pöörduge administraatori poole.</span><span class="sxs-lookup"><span data-stu-id="24c0c-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="24c0c-119">Kui olete administraator, saate ühenduse luua, kui valite suvandi **Lisa ühendus** ja valides **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="24c0c-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="24c0c-120">Valige **Ühenda Leadspace**, et kinnitada ühendus.</span><span class="sxs-lookup"><span data-stu-id="24c0c-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="24c0c-121">Valige **Edasi** ja valige **Kliendi andmekomplekt**, mida soovite rikastada ettevõtte andmetega Leadspace'ilt..</span><span class="sxs-lookup"><span data-stu-id="24c0c-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="24c0c-122">Saate valida olemi **Klient**, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.</span><span class="sxs-lookup"><span data-stu-id="24c0c-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendiandmete kogumi valimisel.":::

1. <span data-ttu-id="24c0c-124">Valige **Edasi** ja määratlege, millist tüüpi välju teie ühendatud profiilidest tuleks kasutada Leadspace ettevõtete andmete vastavuse otsimiseks.</span><span class="sxs-lookup"><span data-stu-id="24c0c-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="24c0c-125">Nõutav on väli **Ettevõtte nimi**.</span><span class="sxs-lookup"><span data-stu-id="24c0c-125">The **Name of company** field is required.</span></span> <span data-ttu-id="24c0c-126">Selleks et vasted oleksid täpsemad, saab lisada kuni kaks muud välja (**Ettevõtte veebisait** ja **Ettevõtte asukoht**).</span><span class="sxs-lookup"><span data-stu-id="24c0c-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace'i väljade vastendamise paan.":::

1. <span data-ttu-id="24c0c-128">Valige **Edasi**, et lõpetada väljade kaardistamine.</span><span class="sxs-lookup"><span data-stu-id="24c0c-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="24c0c-129">Sisestage rikastamiseks nimi ja valige **Salvesta rikastamine** pärast valikute läbivaatamist.</span><span class="sxs-lookup"><span data-stu-id="24c0c-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="24c0c-130">Konfigureerige ühendus Leadspace'iga</span><span class="sxs-lookup"><span data-stu-id="24c0c-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="24c0c-131">Ühenduste konfigureerimiseks peate olema administraator.</span><span class="sxs-lookup"><span data-stu-id="24c0c-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="24c0c-132">Valige **Lisa ühendus** rikastamise konfigureerimisel *või* minge **Administraator** > **Ühendused** ja valige **Seadista** Leadspace paanil.</span><span class="sxs-lookup"><span data-stu-id="24c0c-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="24c0c-133">Seejärel valige suvand **Alustamine**.</span><span class="sxs-lookup"><span data-stu-id="24c0c-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="24c0c-134">Sisestage ühenduse nimi **Kuvatav nimi** väljale.</span><span class="sxs-lookup"><span data-stu-id="24c0c-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="24c0c-135">Sisestage kehtiv Leadspace token.</span><span class="sxs-lookup"><span data-stu-id="24c0c-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="24c0c-136">Vaadake üle ja esitage oma nõusolek **Andmete privaatsuse ja nõuetele vastavus** kohta, valides suvandi **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="24c0c-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="24c0c-137">Valige **Kontrolli** konfiguratsiooni valideerimiseks.</span><span class="sxs-lookup"><span data-stu-id="24c0c-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="24c0c-138">Pärast kontrollimise lõpuleviimist valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="24c0c-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace ühenduse konfiguratsiooni leht.":::

## <a name="enrichment-results"></a><span data-ttu-id="24c0c-140">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="24c0c-140">Enrichment results</span></span>

<span data-ttu-id="24c0c-141">Pärast rikastamise värskendamist saate värskelt rikastatud ettevõtte andmed üle vaadata jaotises [Minu rikastamised](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="24c0c-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="24c0c-142">Kuvatakse viimase värskendamise aeg ja rikastatud profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="24c0c-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="24c0c-143">Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.</span><span class="sxs-lookup"><span data-stu-id="24c0c-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="24c0c-144">Lisateavet leiate teemast [Leadspace'i API-d](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="24c0c-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="24c0c-145">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="24c0c-145">Next steps</span></span>

<span data-ttu-id="24c0c-146">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="24c0c-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="24c0c-147">Looge [segmente](segments.md) ja [näitajaid](measures.md) ning isegi [eksportige andmed](export-destinations.md), et pakkuda oma klientidele isikupärastatud kogemust.</span><span class="sxs-lookup"><span data-stu-id="24c0c-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="24c0c-148">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="24c0c-148">Data privacy and compliance</span></span>

<span data-ttu-id="24c0c-149">Kui lubate Dynamics 365 Customer Insightsil Leadspace'i andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="24c0c-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="24c0c-150">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Leadspace täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="24c0c-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="24c0c-151">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="24c0c-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="24c0c-152">Teie Dynamics 365 Customer Insights administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="24c0c-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
