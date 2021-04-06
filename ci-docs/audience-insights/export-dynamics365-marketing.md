---
title: Customer Insightsi andmete eksportimine rakendusse Dynamics 365 Marketing
description: Vaadake, kuidas konfigureerida ühendust rakendusega Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597598"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="c8f24-103">Ühendus rakendusega Dynamics 365 Marketing (eelvaateversioon)</span><span class="sxs-lookup"><span data-stu-id="c8f24-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="c8f24-104">Kasutage lahenduses Dynamics 365 Marketing kampaaniate loomiseks ja konkreetsete kliendirühmadega ühenduse võtmiseks [segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="c8f24-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="c8f24-105">Lisateavet leiate teemast [Dynamics 365 Customer Insightsi segmentide kasutamine Dynamics 365 Marketingiga](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="c8f24-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="c8f24-106">Eeltingimus</span><span class="sxs-lookup"><span data-stu-id="c8f24-106">Prerequisite</span></span>

- <span data-ttu-id="c8f24-107">Enne segmendi eksportimist Customer Insightsist Marketingi, peavad kontaktikirjed olema olemas rakenduses Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="c8f24-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="c8f24-108">Lugege lisateavet selle kohta, kuidas valmendada kontakte [Dynamics 365 Marketingis Common Data Servicesi abil](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="c8f24-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="c8f24-109">Segmentide eksportimine sihtrühmaülevaadetest Marketingi ei loo uusi kontaktikirjeid Marketingi eksemplaris.</span><span class="sxs-lookup"><span data-stu-id="c8f24-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="c8f24-110">Marketingi kontaktikirjed peavad olema valmendatud sihtrühmaülevaadetes ja neid tuleb kasutada andmeallikana.</span><span class="sxs-lookup"><span data-stu-id="c8f24-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="c8f24-111">Need tuleb lisada ka ühendatud kliendi olemisse, et vastendada kliendi ID-d ja kontakti ID-deks, enne kui segmente saab eksportida.</span><span class="sxs-lookup"><span data-stu-id="c8f24-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="c8f24-112">Konnektori konfigureerimine Marketingi jaoks</span><span class="sxs-lookup"><span data-stu-id="c8f24-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="c8f24-113">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="c8f24-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c8f24-114">Jaotises **Dynamics 365 Marketing** valige suvand **Häälestamine**.</span><span class="sxs-lookup"><span data-stu-id="c8f24-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="c8f24-115">Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="c8f24-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c8f24-116">Sisestage väljale **Serveri aadress** oma organisatsiooni Marketingi URL.</span><span class="sxs-lookup"><span data-stu-id="c8f24-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="c8f24-117">Jaotises **Serveri administraatorikonto** valige suvand **Logi sisse** ja valige rakenduse Dynamics 365 Marketing konto.</span><span class="sxs-lookup"><span data-stu-id="c8f24-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="c8f24-118">Vastendage kliendi ID väli Dynamics 365 kontakti ID-ga.</span><span class="sxs-lookup"><span data-stu-id="c8f24-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="c8f24-119">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="c8f24-119">Select **Next**.</span></span>

1. <span data-ttu-id="c8f24-120">Valige üks või mitu segmenti.</span><span class="sxs-lookup"><span data-stu-id="c8f24-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="c8f24-121">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="c8f24-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c8f24-122">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="c8f24-122">Export the data</span></span>

<span data-ttu-id="c8f24-123">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c8f24-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c8f24-124">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c8f24-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]