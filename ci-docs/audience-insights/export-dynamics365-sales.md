---
title: Customer Insightsi andmete eksportimine rakendusse Dynamics 365 Sales
description: Vaadake, kuidas konfigureerida ühendust rakendusega Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643813"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="fc0d5-103">Ühendus rakendusega Dynamics 365 for Sales (eelvaateversioon)</span><span class="sxs-lookup"><span data-stu-id="fc0d5-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="fc0d5-104">Kasutage kliendiandmeid turundusloendite loomiseks, töövoogude järeltegevusteks ja kampaaniate saatmiseks Dynamics 365 Salesi abil.</span><span class="sxs-lookup"><span data-stu-id="fc0d5-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="fc0d5-105">Eeltingimus</span><span class="sxs-lookup"><span data-stu-id="fc0d5-105">Prerequisite</span></span>

<span data-ttu-id="fc0d5-106">Kontaktikirjed [rakendusest Dynamics 365 Sales on valmendatud Common Data Service'i abil](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="fc0d5-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="fc0d5-107">Konnektori konfigureerimine Salesi jaoks</span><span class="sxs-lookup"><span data-stu-id="fc0d5-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="fc0d5-108">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="fc0d5-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fc0d5-109">Jaotises **Dynamics 365 Sales** valige suvand **Häälestamine**.</span><span class="sxs-lookup"><span data-stu-id="fc0d5-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="fc0d5-110">Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="fc0d5-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="fc0d5-111">Sisestage väljale **Serveri aadress** oma organisatsiooni Salesi URL.</span><span class="sxs-lookup"><span data-stu-id="fc0d5-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="fc0d5-112">Jaotises **Serveri administraatorikonto** valige suvand **Logi sisse** ja valige rakenduse Dynamics 365 Sales konto.</span><span class="sxs-lookup"><span data-stu-id="fc0d5-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="fc0d5-113">Vastendage kliendi ID väli Dynamics 365 kontakti ID-ga.</span><span class="sxs-lookup"><span data-stu-id="fc0d5-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="fc0d5-114">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="fc0d5-114">Select **Next**.</span></span>

1. <span data-ttu-id="fc0d5-115">Valige üks või mitu segmenti.</span><span class="sxs-lookup"><span data-stu-id="fc0d5-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="fc0d5-116">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="fc0d5-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="fc0d5-117">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="fc0d5-117">Export the data</span></span>

<span data-ttu-id="fc0d5-118">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="fc0d5-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="fc0d5-119">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fc0d5-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
