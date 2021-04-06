---
title: Customer Insightsi andmete eksportimine rakendusse Dynamics 365 Sales
description: Vaadake, kuidas konfigureerida ühendust rakendusega Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598104"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="5a0b5-103">Ühendus rakendusega Dynamics 365 for Sales (eelvaateversioon)</span><span class="sxs-lookup"><span data-stu-id="5a0b5-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="5a0b5-104">Kasutage kliendiandmeid turundusloendite loomiseks, töövoogude järeltegevusteks ja kampaaniate saatmiseks Dynamics 365 Salesi abil.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="5a0b5-105">Eeltingimus</span><span class="sxs-lookup"><span data-stu-id="5a0b5-105">Prerequisite</span></span>

1. <span data-ttu-id="5a0b5-106">Enne segmendi eksportimist Customer Insightsist Salesi, peavad kontaktikirjed olema olemas rakenduses Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="5a0b5-107">Lugege lisateavet selle kohta, kuidas valmendada kontakte [Dynamics 365 Salesis Common Data Servicesi abil](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="5a0b5-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="5a0b5-108">Segmentide eksportimine sihtrühmaülevaadetest Salesi ei loo uusi kontaktikirjeid Salesi eksemplaris.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="5a0b5-109">Salesi kontaktikirjed peavad olema valmendatud sihtrühmaülevaadetes ja neid tuleb kasutada andmeallikana.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="5a0b5-110">Need tuleb lisada ka ühendatud kliendi olemisse, et vastendada kliendi ID-d ja kontakti ID-deks, enne kui segmente saab eksportida.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="5a0b5-111">Konnektori konfigureerimine Salesi jaoks</span><span class="sxs-lookup"><span data-stu-id="5a0b5-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="5a0b5-112">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="5a0b5-113">Jaotises **Dynamics 365 Sales** valige suvand **Häälestamine**.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="5a0b5-114">Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="5a0b5-115">Sisestage väljale **Serveri aadress** oma organisatsiooni Salesi URL.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="5a0b5-116">Jaotises **Serveri administraatorikonto** valige suvand **Logi sisse** ja valige rakenduse Dynamics 365 Sales konto.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="5a0b5-117">Vastendage kliendi ID väli Dynamics 365 kontakti ID-ga.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="5a0b5-118">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-118">Select **Next**.</span></span>

1. <span data-ttu-id="5a0b5-119">Valige üks või mitu segmenti.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="5a0b5-120">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="5a0b5-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="5a0b5-121">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="5a0b5-121">Export the data</span></span>

<span data-ttu-id="5a0b5-122">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5a0b5-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="5a0b5-123">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5a0b5-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]