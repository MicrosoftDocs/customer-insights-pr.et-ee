---
title: Customer Insights -i andmete eksportimine Azure Synapse Analytic -usse
description: Lugege, kuidas konfigureerida ühendust Azure Synapse Analytic -ule.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977372"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="6cf57-103">Ekspordi andmed Azure Synapse Analytics -i (Eelvaatesse)</span><span class="sxs-lookup"><span data-stu-id="6cf57-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="6cf57-104">Azure Synapse on analüüsiteenus, mis kiirendab andmeladude ja suurandmesüsteemide läbivaatava ülevaatamise aega.</span><span class="sxs-lookup"><span data-stu-id="6cf57-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="6cf57-105">Customer Insights -i andmeid saate sisse tuua ja kasutada jaotises [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="6cf57-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6cf57-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="6cf57-106">Prerequisites</span></span>

<span data-ttu-id="6cf57-107">Ühenduse konfigureerimiseks Customer Insights rakendusest Azure Synapse -i peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="6cf57-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="6cf57-108">Seadke kindlasti kõik **rollimäärangud** vastavalt kirjeldatusele.</span><span class="sxs-lookup"><span data-stu-id="6cf57-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="6cf57-109">Eeltingimused Customer Insights -is</span><span class="sxs-lookup"><span data-stu-id="6cf57-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="6cf57-110">Teil on **Administraatori** roll publiku ülevaadetes.</span><span class="sxs-lookup"><span data-stu-id="6cf57-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="6cf57-111">Lisateave [kasutajaõiguste seadmise kohta vaatajaskonna ülevaates](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="6cf57-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="6cf57-112">Azure -is:</span><span class="sxs-lookup"><span data-stu-id="6cf57-112">In Azure:</span></span> 

- <span data-ttu-id="6cf57-113">Töötav Azure -i tellimus.</span><span class="sxs-lookup"><span data-stu-id="6cf57-113">An active Azure subscription.</span></span>

- <span data-ttu-id="6cf57-114">Kui kasutate uut Azure Data Lake Storage Gen2 kontot, *vajab publiku ülevaadete teenusejuht* **salvestusruumi bloobiandmete kaasautori** õigusi.</span><span class="sxs-lookup"><span data-stu-id="6cf57-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="6cf57-115">Lisateavet vaata [Azure Data Lake Storage -i Gen2 konto ühendamine Azure service -i esindatavaga publiku ülevaadetes](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="6cf57-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="6cf57-116">Data Lake Storage Gen2 **peab olema** [hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace) lubatud.</span><span class="sxs-lookup"><span data-stu-id="6cf57-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="6cf57-117">Ressursirühmas, Azure Synapse kus tööruum asub, *teenise esindatavas* ja *publiku ülevaate kasutaja* peab olema määratud vähemalt **Lugeja** õigused.</span><span class="sxs-lookup"><span data-stu-id="6cf57-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="6cf57-118">Lisateavet leiate teemast [Azure'i rollide määramine Azure'i portaali abil](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="6cf57-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="6cf57-119">*Kasutaja* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol, kus andmed asuvad ja on lingitud tööruumiga Azure Synapse .</span><span class="sxs-lookup"><span data-stu-id="6cf57-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="6cf57-120">Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="6cf57-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="6cf57-121">*[Azure Synapse identiteeti haldav tööruum](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol kus asuvad andmed, mis on lingitud Azure Synapse tööruumiga.</span><span class="sxs-lookup"><span data-stu-id="6cf57-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="6cf57-122">Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="6cf57-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="6cf57-123">Azure Synapse tööruumis *vaatajaskonna ülevaate teenusejuht* vajab **sünapsiadministraatori** rolli määramist.</span><span class="sxs-lookup"><span data-stu-id="6cf57-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="6cf57-124">Lisateavet leiate teemast [Sünapsi tööruumi juurdepääsujuhtelemendiüles seadmine](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="6cf57-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="6cf57-125">Loo ühendusja eksport Azure Synapse -ile</span><span class="sxs-lookup"><span data-stu-id="6cf57-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="6cf57-126">Ühenduse konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="6cf57-126">Configure a connection</span></span>

1. <span data-ttu-id="6cf57-127">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="6cf57-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6cf57-128">Valige **Lisa ühendus** ja valige  **Azure Synapse Analytics**  või valige **Loo** paanil **Azure Synapse Analytics** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="6cf57-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="6cf57-129">Andke oma ühendusele äratuntav nimi väljal Kuvatav nimi.</span><span class="sxs-lookup"><span data-stu-id="6cf57-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="6cf57-130">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="6cf57-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="6cf57-131">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="6cf57-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6cf57-132">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="6cf57-132">Choose who can use this connection.</span></span> <span data-ttu-id="6cf57-133">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="6cf57-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6cf57-134">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6cf57-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6cf57-135">Valige või otsige tellimust, milles soovite Customer Insights -i andmeid kasutada.</span><span class="sxs-lookup"><span data-stu-id="6cf57-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="6cf57-136">Kohe, kui tellimus on valitud, saate valida ka **Tööruumi**, **Salvestusruumikonto** ja **Konteineri**.</span><span class="sxs-lookup"><span data-stu-id="6cf57-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="6cf57-137">Uue ühenduse salvestamiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="6cf57-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="6cf57-138">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="6cf57-138">Configure an export</span></span>

<span data-ttu-id="6cf57-139">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="6cf57-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6cf57-140">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6cf57-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6cf57-141">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="6cf57-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6cf57-142">Valige uue ekspordi loomiseks **Lisa eksport**.</span><span class="sxs-lookup"><span data-stu-id="6cf57-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="6cf57-143">Väljal **Ekspordiühendus** valige ühendus jaotisest **Azure Synapse Analytics** .</span><span class="sxs-lookup"><span data-stu-id="6cf57-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="6cf57-144">Kui te seda jaotisenime ei näe, pole seda tüüpi [ühendusi](connections.md) teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="6cf57-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="6cf57-145">Sisestage ekspordile äratuntav **Kuvatav nimi** ja **Andmebaasi nimi**.</span><span class="sxs-lookup"><span data-stu-id="6cf57-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="6cf57-146">Valige, milliseid olemeid soovite Azure Synapse Analytics -isse eksportida.</span><span class="sxs-lookup"><span data-stu-id="6cf57-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="6cf57-147">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="6cf57-147">Select **Save**.</span></span>

<span data-ttu-id="6cf57-148">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="6cf57-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6cf57-149">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6cf57-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6cf57-150">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6cf57-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="6cf57-151">Ekspordi värskendamine</span><span class="sxs-lookup"><span data-stu-id="6cf57-151">Update an export</span></span>

1. <span data-ttu-id="6cf57-152">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="6cf57-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6cf57-153">Valige **Redigeeri** ekspordil, mida soovite värskendada.</span><span class="sxs-lookup"><span data-stu-id="6cf57-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="6cf57-154">**Lisa** või **Eemalda** valikust olemeid.</span><span class="sxs-lookup"><span data-stu-id="6cf57-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="6cf57-155">Kui olemid on valikust eemaldatud, ei kustutata neid Synapse Analyticsi andmebaasist.</span><span class="sxs-lookup"><span data-stu-id="6cf57-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="6cf57-156">Kuid tulevased andmete värskendamised ei värskenda selles andmebaasis eemaldatud olemeid.</span><span class="sxs-lookup"><span data-stu-id="6cf57-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="6cf57-157">**Andmebaasi Nime Muutmine** loob uue Synapse Analytics -ii andmebaasi.</span><span class="sxs-lookup"><span data-stu-id="6cf57-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="6cf57-158">Varem konfigureeritud nimega andmebaas ei saa tulevaste värskenduste ajal värskendusi.</span><span class="sxs-lookup"><span data-stu-id="6cf57-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
