---
title: Segmendid põhinevad prognoosväljundil
description: Segmentide loomine ärimudeli väljundolemi prognoos põhjal.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741424"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="43706-103">Segmendi loomine prognoosmudelil (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="43706-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="43706-104">Prognoosi tulemused rakenduvad mõnikord ainult teie klientide alamhulgale.</span><span class="sxs-lookup"><span data-stu-id="43706-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="43706-105">Suurendage soovituste isikupärastamist, luues prognoosmudelite tulemustest segmendid.</span><span class="sxs-lookup"><span data-stu-id="43706-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="43706-106">Näiteks võite anda konkreetseid soovitusi klientidele, kes eelistavad teatud tüüpi teenuseid.</span><span class="sxs-lookup"><span data-stu-id="43706-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="43706-107">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="43706-107">Prerequisites</span></span>

- <span data-ttu-id="43706-108">Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.</span><span class="sxs-lookup"><span data-stu-id="43706-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="43706-109">Tootesoovitus, tehinguvoolavus, tellimusvoolavus või kliendi eluea väärtuse mudel, mis on konfigureeritud jaotises Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="43706-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="43706-110">Vaadake läbi erinevate mudelite häälestamise nõuded:</span><span class="sxs-lookup"><span data-stu-id="43706-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="43706-111">Tootesoovitusmudel</span><span class="sxs-lookup"><span data-stu-id="43706-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="43706-112">Tellimusvoolavuse mudel</span><span class="sxs-lookup"><span data-stu-id="43706-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="43706-113">Tehinguvoolavuse mudel</span><span class="sxs-lookup"><span data-stu-id="43706-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="43706-114">Kliendi eluea väärtuse mudel</span><span class="sxs-lookup"><span data-stu-id="43706-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="43706-115">Prognooside põhjal kliendisegmendi loomine</span><span class="sxs-lookup"><span data-stu-id="43706-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="43706-116">Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="43706-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="43706-117">Valige ülevaatamiseks soovitud mudeli kõrval vertikaalsed valipsed ja valige **vaade**.</span><span class="sxs-lookup"><span data-stu-id="43706-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="43706-118">Klõpsake tulemustelehel käsku **Loo segment**.</span><span class="sxs-lookup"><span data-stu-id="43706-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="43706-119">Tulemuste lehe kohta lisateabe saamiseks vaadake üle mudeli kohta käiv artikkel.</span><span class="sxs-lookup"><span data-stu-id="43706-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Prognooside tulemuste kuvatõmmis, koos esiletõstmisega toimingus Loo segment.":::

1. <span data-ttu-id="43706-121">Looge uus segment valitud mudeli väljundüksuse põhjal.</span><span class="sxs-lookup"><span data-stu-id="43706-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="43706-122">Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).</span><span class="sxs-lookup"><span data-stu-id="43706-122">For more information, see [Create and manage segments](segments.md).</span></span>