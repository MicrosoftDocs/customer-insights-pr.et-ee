---
title: Customer Insightsi andmete eksportimine rakendusse Dynamics 365 Sales
description: Lugege, kuidas konfigureerida ühendust ja eksportida Dynamics 365 Sales'i.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976221"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="de5aa-103">Kasutage segmente rakendusega Dynamics 365 Sales (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="de5aa-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="de5aa-104">Kasutage kliendiandmeid turundusloendite loomiseks, töövoogude järeltegevusteks ja kampaaniate saatmiseks Dynamics 365 Salesi abil.</span><span class="sxs-lookup"><span data-stu-id="de5aa-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="de5aa-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="de5aa-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="de5aa-106">Enne segmendi eksportimist Customer Insightsist Salesi, peavad kontaktikirjed olema olemas rakenduses Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="de5aa-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="de5aa-107">Lugege lisateavet selle kohta, kuidas valmendada kontakte [Dynamics 365 Salesis Common Data Servicesi abil](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="de5aa-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="de5aa-108">Segmentide eksportimine sihtrühmaülevaadetest Salesi ei loo uusi kontaktikirjeid Salesi eksemplaris.</span><span class="sxs-lookup"><span data-stu-id="de5aa-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="de5aa-109">Salesi kontaktikirjed peavad olema valmendatud sihtrühmaülevaadetes ja neid tuleb kasutada andmeallikana.</span><span class="sxs-lookup"><span data-stu-id="de5aa-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="de5aa-110">Need tuleb lisada ka ühendatud kliendi olemisse, et vastendada kliendi ID-d ja kontakti ID-deks, enne kui segmente saab eksportida.</span><span class="sxs-lookup"><span data-stu-id="de5aa-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="de5aa-111">Ühenduse loomine Sales'iga</span><span class="sxs-lookup"><span data-stu-id="de5aa-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="de5aa-112">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="de5aa-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="de5aa-113">Valige **Lisa ühendus** ja valige **Dynamics 365 Sales** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="de5aa-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="de5aa-114">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="de5aa-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="de5aa-115">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="de5aa-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="de5aa-116">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="de5aa-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="de5aa-117">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="de5aa-117">Choose who can use this connection.</span></span> <span data-ttu-id="de5aa-118">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="de5aa-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="de5aa-119">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="de5aa-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="de5aa-120">Sisestage väljale **Serveri aadress** oma organisatsiooni Salesi URL.</span><span class="sxs-lookup"><span data-stu-id="de5aa-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="de5aa-121">Jaotises **Serveri administraatorikonto** valige suvand **Logi sisse** ja valige rakenduse Dynamics 365 Sales konto.</span><span class="sxs-lookup"><span data-stu-id="de5aa-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="de5aa-122">Vastendage kliendi ID väli Dynamics 365 kontakti ID-ga.</span><span class="sxs-lookup"><span data-stu-id="de5aa-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="de5aa-123">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="de5aa-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="de5aa-124">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="de5aa-124">Configure an export</span></span>

<span data-ttu-id="de5aa-125">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="de5aa-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="de5aa-126">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="de5aa-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="de5aa-127">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="de5aa-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="de5aa-128">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="de5aa-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="de5aa-129">Valige **Ekspordiühendus** väljal ühendus Dynamics 365 Sales jaotisest.</span><span class="sxs-lookup"><span data-stu-id="de5aa-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="de5aa-130">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="de5aa-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="de5aa-131">Valige üks või mitu segmenti.</span><span class="sxs-lookup"><span data-stu-id="de5aa-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="de5aa-132">Valige **Salvesta**</span><span class="sxs-lookup"><span data-stu-id="de5aa-132">Select **Save**</span></span>

<span data-ttu-id="de5aa-133">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="de5aa-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="de5aa-134">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="de5aa-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="de5aa-135">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="de5aa-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
