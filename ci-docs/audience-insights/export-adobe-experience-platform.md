---
title: Customer Insightsi andmete eksportimine Adobe Experience Platformi
description: Lugege, kuidas kasutada Adobe Experience Platformi sihtrühmaülevaadete segmente.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760096"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="3b303-103">Customer Insightsi segmentide kasutamine Adobe Experience Platformis (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="3b303-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="3b303-104">Dynamics 365 Customer Insightsi sihtrühmaülevaadete kasutajana olete võib-olla loonud segmente turunduskampaaniate tõhusamaks muutmiseks asjakohaseid sihtrühmi määrates.</span><span class="sxs-lookup"><span data-stu-id="3b303-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="3b303-105">Adobe Experience Platformi ja rakendustest, nagu Adobe Campaign Standard pärit segmentide kasutamiseks peate järgima mõnda selles artiklis kirjeldatud juhist.</span><span class="sxs-lookup"><span data-stu-id="3b303-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Selles artiklis kirjeldatud juhiste protsessiskeem.":::

## <a name="prerequisites"></a><span data-ttu-id="3b303-107">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="3b303-107">Prerequisites</span></span>

-   <span data-ttu-id="3b303-108">Dynamics 365 Customer Insightsi litsents</span><span class="sxs-lookup"><span data-stu-id="3b303-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="3b303-109">Adobe Experience Platformi litsents</span><span class="sxs-lookup"><span data-stu-id="3b303-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="3b303-110">Adobe Campaign Standardi litsents</span><span class="sxs-lookup"><span data-stu-id="3b303-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="3b303-111">Azure’i bloobimälu konto</span><span class="sxs-lookup"><span data-stu-id="3b303-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="3b303-112">Kampaania ülevaade</span><span class="sxs-lookup"><span data-stu-id="3b303-112">Campaign Overview</span></span>

<span data-ttu-id="3b303-113">Et paremini mõista, kuidas kasutada Adobe Experience Platformi sihtrühmaülevaadete segmente, vaatame väljamõeldud näidiskampaaniat.</span><span class="sxs-lookup"><span data-stu-id="3b303-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="3b303-114">Oletame, et teie ettevõte pakub teie USA klientidele igakuiseid, tellimusepõhiseid teenuseid.</span><span class="sxs-lookup"><span data-stu-id="3b303-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="3b303-115">Soovite tuvastada kliendid, kelle kordustellimusi tuleb järgmise kaheksa päeva pärast uuendada, kuid kes pole veel oma kordustellimust pikendanud.</span><span class="sxs-lookup"><span data-stu-id="3b303-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="3b303-116">Nende klientide alleshoidmiseks, soovite meili teel saata neile reklaampakkumise Adobe Experience Platformi kaudu.</span><span class="sxs-lookup"><span data-stu-id="3b303-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="3b303-117">Selles näites soovime käivitada ühekordse reklaamikampaania meili teel.</span><span class="sxs-lookup"><span data-stu-id="3b303-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="3b303-118">See artikkel ei hõlma kampaania läbiviimist rohkem kui üks kord.</span><span class="sxs-lookup"><span data-stu-id="3b303-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="3b303-119">Sihtrühma tuvastamine</span><span class="sxs-lookup"><span data-stu-id="3b303-119">Identify your target audience</span></span>

<span data-ttu-id="3b303-120">Meie stsenaariumis eeldame, et klientide meiliaadressid on sihtrühmaülevaadetes saadaval ja nende reklaamieelistusi on analüüsitud segmendi liikmete tuvastamiseks.</span><span class="sxs-lookup"><span data-stu-id="3b303-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="3b303-121">[Sihtrühmaülevaadetes määratletud segmendi](segments.md) nimeks on **ChurnProneCustomers** ja plaanite neile klientidele saata meilikampaania.</span><span class="sxs-lookup"><span data-stu-id="3b303-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Kuvatõmmis loodud ChurnProneCustomersi segmendiga segmentide lehest.":::

<span data-ttu-id="3b303-123">Väljasaatmiseks mõeldud pakkumismeilis on eesnimi, perekonnanimi ja kliendi kordustellimuse lõppkuupäev.</span><span class="sxs-lookup"><span data-stu-id="3b303-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="3b303-124">See teavitab klienti allahindlusest, mille nad saavad, kui nad oma kordustellimuse enne aegumist pikendavad.</span><span class="sxs-lookup"><span data-stu-id="3b303-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="3b303-125">Sihtrühma eksportimine</span><span class="sxs-lookup"><span data-stu-id="3b303-125">Export your target audience</span></span>

<span data-ttu-id="3b303-126">Kui sihtrühm on tuvastatud, saame konfigureerida ekspordi sihtrühmaülevaadetest Azure'i bloobimälu kontole.</span><span class="sxs-lookup"><span data-stu-id="3b303-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="3b303-127">Ühenduse konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="3b303-127">Configure a connection</span></span>

1. <span data-ttu-id="3b303-128">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="3b303-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3b303-129">Valige **Lisa ühendus** ja valige **Azure Blob Storage** või valige **Seadista** **Azure Blob Storage** paanil:</span><span class="sxs-lookup"><span data-stu-id="3b303-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure'i bloobimälu konfiguratsioonipaan."::: <span data-ttu-id="3b303-131">ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="3b303-131">to configure the connection.</span></span>

1. <span data-ttu-id="3b303-132">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="3b303-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3b303-133">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="3b303-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3b303-134">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="3b303-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3b303-135">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="3b303-135">Choose who can use this connection.</span></span> <span data-ttu-id="3b303-136">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="3b303-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3b303-137">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3b303-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3b303-138">Sisestage **Konto nimi**, **Konto võti**, ja **Konteiner** Azure Blob Storage kontol, kuhu soovite segmendi eksportida.</span><span class="sxs-lookup"><span data-stu-id="3b303-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Salvestusruumi konto konfiguratsiooni kuvatõmmis. "::: 
   
    - <span data-ttu-id="3b303-140">Lisateavet bloobimälu konto nime ja konto võtme otsimise kohta leiate [Azure portaalis salvestusruumi konto sätete haldamine](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="3b303-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="3b303-141">Lisateavet konteineri loomise kohta leiate teemast [Konteineri loomine](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="3b303-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="3b303-142">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="3b303-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="3b303-143">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="3b303-143">Configure an export</span></span>

<span data-ttu-id="3b303-144">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="3b303-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3b303-145">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3b303-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3b303-146">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="3b303-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3b303-147">Valige uue ekspordi loomiseks **Lisa eksport**.</span><span class="sxs-lookup"><span data-stu-id="3b303-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="3b303-148">Valige **Ekspordiühendus** väljal ühendus Azure Blob Storage jaotisest.</span><span class="sxs-lookup"><span data-stu-id="3b303-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="3b303-149">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="3b303-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3b303-150">Valige segment, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="3b303-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="3b303-151">Selles näites on selleks **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="3b303-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Valitud segmendiga ChurnProneCustomers segmendivaliku kasutajaliidese kuvatõmmis.":::

1. <span data-ttu-id="3b303-153">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="3b303-153">Select **Save**.</span></span>

<span data-ttu-id="3b303-154">Pärast ekspordi sihtkoha salvestamist leiate selle **Andmed** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="3b303-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="3b303-155">Nüüd saate [nõudmisel segmendi](export-destinations.md#run-exports-on-demand)</span><span class="sxs-lookup"><span data-stu-id="3b303-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="3b303-156">Eksport käivitub ka iga [ajastatud värskendamisega](system.md).</span><span class="sxs-lookup"><span data-stu-id="3b303-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3b303-157">Veenduge, et eksporditud segmendi kirjete arv jääb Adobe Campaign Standardi litsentsi lubatud piiridesse.</span><span class="sxs-lookup"><span data-stu-id="3b303-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="3b303-158">Eksporditud andmed talletatakse eespool konfigureeritud Azure'i bloobimälu ümbrisesse.</span><span class="sxs-lookup"><span data-stu-id="3b303-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="3b303-159">Ümbrisesse luuakse automaatselt järgmine kaustatee:</span><span class="sxs-lookup"><span data-stu-id="3b303-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="3b303-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="3b303-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="3b303-161">Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="3b303-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="3b303-162">Eksporditud olemite *model.json* asub tasemel *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="3b303-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="3b303-163">Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="3b303-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="3b303-164">Experience Data Modeli (XDM) määratlemine Adobe Experience Platformil</span><span class="sxs-lookup"><span data-stu-id="3b303-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="3b303-165">Enne sihtrühmaülevaadetest eksporditu andmete kasutamist Adobe Experience Platformil peame määratlema Experience Data Modeli skeemi ja [konfigureerima reaalajas kliendiprofiili andmed](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="3b303-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="3b303-166">Lugege, [mis on XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ja tutvuge [skeemi loomise põhitõdedega](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="3b303-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="3b303-167">Andmete importimine Adobe Experience Platformile</span><span class="sxs-lookup"><span data-stu-id="3b303-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="3b303-168">Nüüd, kui kõik on valmis, peame profiilide loomiseks importima ettevalmistatud sihtrühmaandmed sihtrühmaülevaadetest Adobe Experience Platformile.</span><span class="sxs-lookup"><span data-stu-id="3b303-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="3b303-169">Esmalt looge [Azure'i bloobimälu l'hteühendus](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="3b303-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="3b303-170">Pärast lähteühenduse määratlemist [konfigureerige andmevoog](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pilvsalvestusruumi pakettühenduse jaoks, et importida sihtrühmaülevaadete segmendiväljund Adobe Experience Platformi.</span><span class="sxs-lookup"><span data-stu-id="3b303-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="3b303-171">Adobe Campaign Standardi sihtrühma loomine</span><span class="sxs-lookup"><span data-stu-id="3b303-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="3b303-172">Selle kampaania meili saatmiseks kasutame Adobe Campaign Standardit.</span><span class="sxs-lookup"><span data-stu-id="3b303-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="3b303-173">Pärast andmete importimist Adobe Experience Platformi peame [looma sihtrühma](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) Adobe Campaign Standardis Adobe Experience Platformi andmete abil.</span><span class="sxs-lookup"><span data-stu-id="3b303-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="3b303-174">Lugege, kuidas [kasutada segmendikoosturit](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) Adobe Campaign Standardis, et määratleda sihtrühm Adobe Experience Platformi andmete põhjal.</span><span class="sxs-lookup"><span data-stu-id="3b303-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="3b303-175">Meili loomine ja saatmine Adobe Campaign Standardi kaudu</span><span class="sxs-lookup"><span data-stu-id="3b303-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="3b303-176">Looge meilisisu ja seejärel [testige ja saatke](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) oma meil.</span><span class="sxs-lookup"><span data-stu-id="3b303-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standardi uuenduspakkumisega näidismeil.":::
