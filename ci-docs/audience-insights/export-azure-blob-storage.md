---
title: Customer Insights andmete eksportimine Azure Blob Storage'isse
description: Lugege, kuidas konfigureerida ühendust ja eksportida Blob storage'isse.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760184"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="70b29-103">Segmendiloendi ja muude andmete eksportimine Azure'i Blob Storage'isse (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="70b29-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="70b29-104">Saate salvestada oma Customer Insights andmed bloobimällu või kasutada seda oma andmete edastamiseks teistesse rakendustesse.</span><span class="sxs-lookup"><span data-stu-id="70b29-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="70b29-105">Loo Azure Bloobimälu ühendus</span><span class="sxs-lookup"><span data-stu-id="70b29-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="70b29-106">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="70b29-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="70b29-107">Valige **Lisa ühendus** ja valige **Azure Blob Storage** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="70b29-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="70b29-108">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="70b29-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="70b29-109">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="70b29-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="70b29-110">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="70b29-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="70b29-111">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="70b29-111">Choose who can use this connection.</span></span> <span data-ttu-id="70b29-112">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="70b29-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="70b29-113">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="70b29-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="70b29-114">Sisestage **Konto nimi**, **Konto võti** ja **Konteiner** bloobimälu konto jaoks.</span><span class="sxs-lookup"><span data-stu-id="70b29-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="70b29-115">Lisateavet bloobimälu konto nime ja konto võtme otsimise kohta leiate [Azure portaalis salvestusruumi konto sätete haldamine](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="70b29-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="70b29-116">Lisateavet konteineri loomise kohta leiate teemast [Konteineri loomine](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="70b29-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="70b29-117">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="70b29-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="70b29-118">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="70b29-118">Configure an export</span></span>

<span data-ttu-id="70b29-119">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="70b29-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="70b29-120">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="70b29-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="70b29-121">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="70b29-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="70b29-122">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="70b29-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="70b29-123">Valige **Ekspordiühendus** väljal ühendus Azure Blob Storage jaotisest.</span><span class="sxs-lookup"><span data-stu-id="70b29-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="70b29-124">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="70b29-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="70b29-125">Märgistage lahter iga olemi kõrval, mida soovite antud sihtkohta eksportida.</span><span class="sxs-lookup"><span data-stu-id="70b29-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="70b29-126">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="70b29-126">Select **Save**.</span></span>

<span data-ttu-id="70b29-127">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="70b29-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="70b29-128">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="70b29-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="70b29-129">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="70b29-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="70b29-130">Eksporditud andmed salvestatakse konfigureeritud bloobimälukonteinerisse.</span><span class="sxs-lookup"><span data-stu-id="70b29-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="70b29-131">Konteineris luuakse automaatselt järgmised kaustateed.</span><span class="sxs-lookup"><span data-stu-id="70b29-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="70b29-132">Lähteolemite ja süsteemi loodud olemite jaoks: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="70b29-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="70b29-133">Näide: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="70b29-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="70b29-134">Model.json eksporditud olemitele on %ExportDestinationName% tasemel</span><span class="sxs-lookup"><span data-stu-id="70b29-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="70b29-135">Näide: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="70b29-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
