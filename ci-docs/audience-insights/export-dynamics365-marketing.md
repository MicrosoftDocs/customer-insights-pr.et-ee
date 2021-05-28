---
title: Customer Insightsi andmete eksportimine rakendusse Dynamics 365 Marketing
description: Lugege, kuidas konfigureerida ühendust ja eksportida Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976795"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="721e9-103">Kasutage segmente rakendusega Dynamics 365 Marketing (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="721e9-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="721e9-104">Kasutage lahenduses Dynamics 365 Marketing kampaaniate loomiseks ja konkreetsete kliendirühmadega ühenduse võtmiseks [segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="721e9-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="721e9-105">Lisateavet leiate teemast [Dynamics 365 Customer Insightsi segmentide kasutamine Dynamics 365 Marketingiga](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="721e9-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="721e9-106">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="721e9-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="721e9-107">Enne segmendi eksportimist Customer Insightsist Marketingi, peavad kontaktikirjed olema olemas rakenduses Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="721e9-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="721e9-108">Lugege lisateavet selle kohta, kuidas valmendada kontakte [Dynamics 365 Marketingis Common Data Servicesi abil](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="721e9-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="721e9-109">Segmentide eksportimine sihtrühmaülevaadetest Marketingi ei loo uusi kontaktikirjeid Marketingi eksemplaris.</span><span class="sxs-lookup"><span data-stu-id="721e9-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="721e9-110">Marketingi kontaktikirjed peavad olema valmendatud sihtrühmaülevaadetes ja neid tuleb kasutada andmeallikana.</span><span class="sxs-lookup"><span data-stu-id="721e9-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="721e9-111">Need tuleb lisada ka ühendatud kliendi olemisse, et vastendada kliendi ID-d ja kontakti ID-deks, enne kui segmente saab eksportida.</span><span class="sxs-lookup"><span data-stu-id="721e9-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="721e9-112">Ühenduse loomine Marketingiga</span><span class="sxs-lookup"><span data-stu-id="721e9-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="721e9-113">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="721e9-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="721e9-114">Valige **Lisa ühendus** ja valige **Dynamics 365 Marketing** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="721e9-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="721e9-115">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="721e9-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="721e9-116">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="721e9-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="721e9-117">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="721e9-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="721e9-118">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="721e9-118">Choose who can use this connection.</span></span> <span data-ttu-id="721e9-119">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="721e9-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="721e9-120">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="721e9-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="721e9-121">Sisestage väljale **Serveri aadress** oma organisatsiooni Marketingi URL.</span><span class="sxs-lookup"><span data-stu-id="721e9-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="721e9-122">Jaotises **Serveri administraatorikonto** valige suvand **Logi sisse** ja valige rakenduse Dynamics 365 Marketing konto.</span><span class="sxs-lookup"><span data-stu-id="721e9-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="721e9-123">Vastendage kliendi ID väli Dynamics 365 kontakti ID-ga.</span><span class="sxs-lookup"><span data-stu-id="721e9-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="721e9-124">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="721e9-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="721e9-125">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="721e9-125">Configure an export</span></span>

<span data-ttu-id="721e9-126">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="721e9-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="721e9-127">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="721e9-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="721e9-128">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="721e9-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="721e9-129">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="721e9-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="721e9-130">Valige **Ekspordiühendus** väljal ühendus Dynamics 365 Marketing jaotisest.</span><span class="sxs-lookup"><span data-stu-id="721e9-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="721e9-131">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="721e9-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="721e9-132">Valige üks või mitu segmenti.</span><span class="sxs-lookup"><span data-stu-id="721e9-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="721e9-133">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="721e9-133">Select **Save**.</span></span>

<span data-ttu-id="721e9-134">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="721e9-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="721e9-135">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="721e9-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="721e9-136">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="721e9-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
