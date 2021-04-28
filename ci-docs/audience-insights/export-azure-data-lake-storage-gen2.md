---
title: Customer Insightsi andmete eksportimine Azure Data Lake Storage Gen2-sse
description: Vaadake, kuidas konfigureerida ühendust Azure Data Lake Storage Gen2-ga.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760046"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="bd2fa-103">Ühenduse loomine Azure Data Lake Storage Gen2 (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="bd2fa-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="bd2fa-104">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bd2fa-105">Valige **Lisa ühendus** ja valige **Azure Data Lake Gen 2** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="bd2fa-106">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bd2fa-107">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bd2fa-108">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bd2fa-109">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-109">Choose who can use this connection.</span></span> <span data-ttu-id="bd2fa-110">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bd2fa-111">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bd2fa-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bd2fa-112">Sisestage oma Azure Data Lake Storage Gen2 **Konto nimi**, **Konto võti** ja **Konteiner**.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="bd2fa-113">Lisateavet selle kohta, kuidas luua salvestusruumi kontot koos Azure Data Lake Storage Gen2-ga kasutamiseks, leiate teemast [Salvestusruumi konto loomine](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="bd2fa-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="bd2fa-114">Lisateavet Azure Data Lake Gen2 storage konto nime ja konto võtme otsimise kohta leiate [Azure portaalis salvestusruumi konto sätete haldamine](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="bd2fa-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="bd2fa-115">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="bd2fa-116">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="bd2fa-116">Configure an export</span></span>

<span data-ttu-id="bd2fa-117">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bd2fa-118">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bd2fa-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bd2fa-119">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bd2fa-120">Valige uue ekspordi loomiseks **Lisa eksport**.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="bd2fa-121">Valige **Ekspordiühendus** väljal ühendus **Azure Data Lake** jaotisest.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="bd2fa-122">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bd2fa-123">Märgistage lahter iga olemi kõrval, mida soovite antud sihtkohta eksportida.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="bd2fa-124">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-124">Select **Save**.</span></span>

<span data-ttu-id="bd2fa-125">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bd2fa-126">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bd2fa-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bd2fa-127">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bd2fa-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="bd2fa-128">Eksporditud andmed salvestatakse konfigureeritud Azure Data Lake Gen 2 storage konteinerisse.</span><span class="sxs-lookup"><span data-stu-id="bd2fa-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
