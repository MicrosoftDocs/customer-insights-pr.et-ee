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
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895908"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="04abe-103">Ettevõtte profiilide rikastamine Leadspace'iga (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="04abe-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="04abe-104">Leadspace on andmeteaduse ettevõte, mis pakub kliendi hulgiandmete platvormi.</span><span class="sxs-lookup"><span data-stu-id="04abe-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="04abe-105">See võimaldab ettevõtetel kliendi koondprofiilidega klientide andmeid rikastada.</span><span class="sxs-lookup"><span data-stu-id="04abe-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="04abe-106">Rikastused sisaldavad rohkem atribuute, nagu ettevõtte suurus, asukoht, tegevusala ja palju muud.</span><span class="sxs-lookup"><span data-stu-id="04abe-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="04abe-107">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="04abe-107">Prerequisites</span></span>

<span data-ttu-id="04abe-108">Leadspace'i seadistamiseks peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="04abe-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="04abe-109">Teil on aktiivne Leadspace litsents.</span><span class="sxs-lookup"><span data-stu-id="04abe-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="04abe-110">Teil on ettevõtete [kliendi koondprofiilid](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="04abe-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="04abe-111">Administraator on juba konfigureerinud Leadspace'i ühenduse või teil on [administraatoriõigused](permissions.md#administrator) ja "alaline võti (nimetatakse **Leadspace tokeniks**).</span><span class="sxs-lookup"><span data-stu-id="04abe-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="04abe-112">Võtke [Leadspaceiga](https://www.leadspace.com/products/leadspace-on-demand/) otse ühendust toodete üksikasjade teabe saamiseks.</span><span class="sxs-lookup"><span data-stu-id="04abe-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="04abe-113">Rikastamise konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="04abe-113">Configure the enrichment</span></span>

1. <span data-ttu-id="04abe-114">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Rikastamine**.</span><span class="sxs-lookup"><span data-stu-id="04abe-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="04abe-115">Valige **Mu andmete rikastamine** Leadspace paanil ja valige **Alustamine**.</span><span class="sxs-lookup"><span data-stu-id="04abe-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace'i paani kuvatõmmis.":::

1. <span data-ttu-id="04abe-117">Valige ripploendist [ühendus](connections.md).</span><span class="sxs-lookup"><span data-stu-id="04abe-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="04abe-118">Kui ühendusi pole saadaval, pöörduge administraatori poole.</span><span class="sxs-lookup"><span data-stu-id="04abe-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="04abe-119">Kui olete administraator, saate ühenduse luua, kui valite suvandi **Lisa ühendus** ja valides **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="04abe-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="04abe-120">Valige **Ühenda Leadspace**, et kinnitada ühendus.</span><span class="sxs-lookup"><span data-stu-id="04abe-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="04abe-121">Valige **Edasi** ja valige **Kliendi andmekomplekt**, mida soovite rikastada ettevõtte andmetega Leadspace'ilt..</span><span class="sxs-lookup"><span data-stu-id="04abe-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="04abe-122">Saate valida olemi **Klient**, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.</span><span class="sxs-lookup"><span data-stu-id="04abe-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendiandmete kogumi valimisel.":::

1. <span data-ttu-id="04abe-124">Valige **Edasi** ja määratlege, millist tüüpi välju teie ühendatud profiilidest tuleks kasutada Leadspace ettevõtete andmete vastavuse otsimiseks.</span><span class="sxs-lookup"><span data-stu-id="04abe-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="04abe-125">Nõutav on väli **Ettevõtte nimi**.</span><span class="sxs-lookup"><span data-stu-id="04abe-125">The **Name of company** field is required.</span></span> <span data-ttu-id="04abe-126">Selleks et vasted oleksid täpsemad, saab lisada kuni kaks muud välja (**Ettevõtte veebisait** ja **Ettevõtte asukoht**).</span><span class="sxs-lookup"><span data-stu-id="04abe-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace'i väljade vastendamise paan.":::

1. <span data-ttu-id="04abe-128">Valige **Edasi**, et lõpetada väljade kaardistamine.</span><span class="sxs-lookup"><span data-stu-id="04abe-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="04abe-129">Sisestage rikastamiseks nimi ja valige **Salvesta rikastamine** pärast valikute läbivaatamist.</span><span class="sxs-lookup"><span data-stu-id="04abe-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="04abe-130">Konfigureerige ühendus Leadspace'iga</span><span class="sxs-lookup"><span data-stu-id="04abe-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="04abe-131">Ühenduste konfigureerimiseks peate olema administraator.</span><span class="sxs-lookup"><span data-stu-id="04abe-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="04abe-132">Valige **Lisa ühendus** rikastamise konfigureerimisel *või* minge **Administraator** > **Ühendused** ja valige **Seadista** Leadspace paanil.</span><span class="sxs-lookup"><span data-stu-id="04abe-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="04abe-133">Valige suvand **Alustamine**</span><span class="sxs-lookup"><span data-stu-id="04abe-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="04abe-134">Sisestage ühenduse nimi **Kuvatav nimi** väljale.</span><span class="sxs-lookup"><span data-stu-id="04abe-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="04abe-135">Sisestage kehtiv Leadspace token.</span><span class="sxs-lookup"><span data-stu-id="04abe-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="04abe-136">Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides **Nõustun** märkeruudu</span><span class="sxs-lookup"><span data-stu-id="04abe-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="04abe-137">Valige **Kontrolli** konfiguratsiooni valideerimiseks.</span><span class="sxs-lookup"><span data-stu-id="04abe-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="04abe-138">Pärast kontrollimise lõpuleviimist valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="04abe-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace ühenduse konfiguratsiooni leht.":::

## <a name="enrichment-results"></a><span data-ttu-id="04abe-140">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="04abe-140">Enrichment results</span></span>

<span data-ttu-id="04abe-141">Pärast rikastamise värskendamist saate värskelt rikastatud ettevõtte andmed üle vaadata jaotises [Minu rikastamised](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="04abe-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="04abe-142">Kuvatakse viimase värskendamise aeg ja rikastatud profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="04abe-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="04abe-143">Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.</span><span class="sxs-lookup"><span data-stu-id="04abe-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="04abe-144">Lisateavet leiate teemast [Leadspace'i API-d](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="04abe-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="04abe-145">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="04abe-145">Next steps</span></span>

<span data-ttu-id="04abe-146">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="04abe-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="04abe-147">Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [Ekspordi andmed](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="04abe-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="04abe-148">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="04abe-148">Data privacy and compliance</span></span>

<span data-ttu-id="04abe-149">Kui lubate Dynamics 365 Customer Insightsil Leadspace'i andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="04abe-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="04abe-150">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Leadspace täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="04abe-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="04abe-151">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="04abe-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="04abe-152">Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="04abe-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
