---
title: Customer Insightsi andmete eksportimine Azure Data Lake Storage Gen2-sse
description: Vaadake, kuidas konfigureerida ühendust Azure Data Lake Storage Gen2-ga.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477174"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="dbd9e-103">Azure Data Lake Storage Gen2 konnektor (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="dbd9e-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="dbd9e-104">Saate salvestada oma Customer Insightsi andmed Azure Data Lake Storage Gen2-sse või kasutada seda oma andmete edastamiseks teistesse rakendustesse.</span><span class="sxs-lookup"><span data-stu-id="dbd9e-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="dbd9e-105">Azure Data Lake Storage Gen2 konnektori konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="dbd9e-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="dbd9e-106">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="dbd9e-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dbd9e-107">Tehke jaotises **Azure Data Lake Storage Gen2** valik **Seadista**.</span><span class="sxs-lookup"><span data-stu-id="dbd9e-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="dbd9e-108">Sisestage väljale **Kuvatav nimi** oma sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="dbd9e-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="dbd9e-109">Sisestage oma Azure Data Lake Storage Gen2 **Konto nimi**, **Konto võti** ja **Konteiner**.</span><span class="sxs-lookup"><span data-stu-id="dbd9e-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="dbd9e-110">Lisateavet selle kohta, kuidas luua salvestusruumi kontot koos Azure Data Lake Storage Gen2-ga kasutamiseks, leiate teemast [Salvestusruumi konto loomine](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="dbd9e-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="dbd9e-111">Lisateavet Azure Data Lake Gen2 salvestusruumi konto nime ja konto võtme otsimise kohta leiate teemast [Salvestusruumi konto sätete haldamine Azure'i portaalis](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="dbd9e-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="dbd9e-112">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="dbd9e-112">Select **Next**.</span></span>

1. <span data-ttu-id="dbd9e-113">Märgistage lahter iga olemi kõrval, mida soovite antud sihtkohta eksportida.</span><span class="sxs-lookup"><span data-stu-id="dbd9e-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="dbd9e-114">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="dbd9e-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="dbd9e-115">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="dbd9e-115">Export the data</span></span>

<span data-ttu-id="dbd9e-116">Saate [vajadusel andmeid eksportida](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dbd9e-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="dbd9e-117">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dbd9e-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
