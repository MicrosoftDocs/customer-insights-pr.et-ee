---
title: Customer Insightsi andmete eksportimine rakendusse Dynamics 365 Sales
description: Vaadake, kuidas konfigureerida ühendust rakendusega Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269003"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="ae907-103">Ühendus rakendusega Dynamics 365 for Sales (eelvaateversioon)</span><span class="sxs-lookup"><span data-stu-id="ae907-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ae907-104">Kasutage kliendiandmeid turundusloendite loomiseks, töövoogude järeltegevusteks ja kampaaniate saatmiseks Dynamics 365 Salesi abil.</span><span class="sxs-lookup"><span data-stu-id="ae907-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="ae907-105">Eeltingimus</span><span class="sxs-lookup"><span data-stu-id="ae907-105">Prerequisite</span></span>

1. <span data-ttu-id="ae907-106">Enne segmendi eksportimist Customer Insightsist Salesi, peavad kontaktikirjed olema olemas rakenduses Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ae907-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="ae907-107">Lugege lisateavet selle kohta, kuidas valmendada kontakte [Dynamics 365 Salesis Common Data Servicesi abil](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ae907-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="ae907-108">Segmentide eksportimine sihtrühmaülevaadetest Salesi ei loo uusi kontaktikirjeid Salesi eksemplaris.</span><span class="sxs-lookup"><span data-stu-id="ae907-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="ae907-109">Salesi kontaktikirjed peavad olema valmendatud sihtrühmaülevaadetes ja neid tuleb kasutada andmeallikana.</span><span class="sxs-lookup"><span data-stu-id="ae907-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="ae907-110">Need tuleb lisada ka ühendatud kliendi olemisse, et vastendada kliendi ID-d ja kontakti ID-deks, enne kui segmente saab eksportida.</span><span class="sxs-lookup"><span data-stu-id="ae907-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="ae907-111">Konnektori konfigureerimine Salesi jaoks</span><span class="sxs-lookup"><span data-stu-id="ae907-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="ae907-112">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="ae907-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="ae907-113">Jaotises **Dynamics 365 Sales** valige suvand **Häälestamine**.</span><span class="sxs-lookup"><span data-stu-id="ae907-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="ae907-114">Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="ae907-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ae907-115">Sisestage väljale **Serveri aadress** oma organisatsiooni Salesi URL.</span><span class="sxs-lookup"><span data-stu-id="ae907-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="ae907-116">Jaotises **Serveri administraatorikonto** valige suvand **Logi sisse** ja valige rakenduse Dynamics 365 Sales konto.</span><span class="sxs-lookup"><span data-stu-id="ae907-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="ae907-117">Vastendage kliendi ID väli Dynamics 365 kontakti ID-ga.</span><span class="sxs-lookup"><span data-stu-id="ae907-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="ae907-118">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="ae907-118">Select **Next**.</span></span>

1. <span data-ttu-id="ae907-119">Valige üks või mitu segmenti.</span><span class="sxs-lookup"><span data-stu-id="ae907-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="ae907-120">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="ae907-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="ae907-121">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="ae907-121">Export the data</span></span>

<span data-ttu-id="ae907-122">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="ae907-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="ae907-123">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ae907-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]