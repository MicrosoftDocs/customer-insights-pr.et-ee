---
title: Customer Insightsi andmete eksportimine rakendusse Dynamics 365 Marketing
description: Vaadake, kuidas konfigureerida ühendust rakendusega Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643768"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="a027c-103">Ühendus rakendusega Dynamics 365 Marketing (eelvaateversioon)</span><span class="sxs-lookup"><span data-stu-id="a027c-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a027c-104">Kasutage lahenduses Dynamics 365 Marketing kampaaniate loomiseks ja konkreetsete kliendirühmadega ühenduse võtmiseks [segmente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a027c-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="a027c-105">Lisateavet leiate teemast [Dynamics 365 Customer Insightsi segmentide kasutamine Dynamics 365 Marketingiga](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="a027c-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a027c-106">Eeltingimus</span><span class="sxs-lookup"><span data-stu-id="a027c-106">Prerequisite</span></span>

<span data-ttu-id="a027c-107">Kontaktikirjed [rakendusest Dynamics 365 Marketing on valmendatud Common Data Service'is](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a027c-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="a027c-108">Konnektori konfigureerimine Marketingi jaoks</span><span class="sxs-lookup"><span data-stu-id="a027c-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="a027c-109">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="a027c-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a027c-110">Jaotises **Dynamics 365 Marketing** valige suvand **Häälestamine**.</span><span class="sxs-lookup"><span data-stu-id="a027c-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="a027c-111">Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="a027c-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a027c-112">Sisestage väljale **Serveri aadress** oma organisatsiooni Marketingi URL.</span><span class="sxs-lookup"><span data-stu-id="a027c-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a027c-113">Jaotises **Serveri administraatorikonto** valige suvand **Logi sisse** ja valige rakenduse Dynamics 365 Marketing konto.</span><span class="sxs-lookup"><span data-stu-id="a027c-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="a027c-114">Vastendage kliendi ID väli Dynamics 365 kontakti ID-ga.</span><span class="sxs-lookup"><span data-stu-id="a027c-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a027c-115">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="a027c-115">Select **Next**.</span></span>

1. <span data-ttu-id="a027c-116">Valige üks või mitu segmenti.</span><span class="sxs-lookup"><span data-stu-id="a027c-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="a027c-117">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="a027c-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a027c-118">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="a027c-118">Export the data</span></span>

<span data-ttu-id="a027c-119">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a027c-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a027c-120">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a027c-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
