---
title: Customer Insightsi andmete eksportimine Adobe Experience Platformi
description: Lugege, kuidas kasutada Adobe Experience Platformi sihtrühmaülevaadete segmente.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596264"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="175ce-103">Customer Insightsi segmentide kasutamine Adobe Experience Platformis (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="175ce-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="175ce-104">Dynamics 365 Customer Insightsi sihtrühmaülevaadete kasutajana olete võib-olla loonud segmente turunduskampaaniate tõhusamaks muutmiseks asjakohaseid sihtrühmi määrates.</span><span class="sxs-lookup"><span data-stu-id="175ce-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="175ce-105">Adobe Experience Platformi ja rakendustest, nagu Adobe Campaign Standard pärit segmentide kasutamiseks peate järgima mõnda selles artiklis kirjeldatud juhist.</span><span class="sxs-lookup"><span data-stu-id="175ce-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Selles artiklis kirjeldatud juhiste protsessiskeem.":::

## <a name="prerequisites"></a><span data-ttu-id="175ce-107">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="175ce-107">Prerequisites</span></span>

-   <span data-ttu-id="175ce-108">Dynamics 365 Customer Insightsi litsents</span><span class="sxs-lookup"><span data-stu-id="175ce-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="175ce-109">Adobe Experience Platformi litsents</span><span class="sxs-lookup"><span data-stu-id="175ce-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="175ce-110">Adobe Campaign Standardi litsents</span><span class="sxs-lookup"><span data-stu-id="175ce-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="175ce-111">Azure’i bloobimälu konto</span><span class="sxs-lookup"><span data-stu-id="175ce-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="175ce-112">Kampaania ülevaade</span><span class="sxs-lookup"><span data-stu-id="175ce-112">Campaign Overview</span></span>

<span data-ttu-id="175ce-113">Et paremini mõista, kuidas kasutada Adobe Experience Platformi sihtrühmaülevaadete segmente, vaatame väljamõeldud näidiskampaaniat.</span><span class="sxs-lookup"><span data-stu-id="175ce-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="175ce-114">Oletame, et teie ettevõte pakub teie USA klientidele igakuiseid, tellimusepõhiseid teenuseid.</span><span class="sxs-lookup"><span data-stu-id="175ce-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="175ce-115">Soovite tuvastada kliendid, kelle kordustellimusi tuleb järgmise kaheksa päeva pärast uuendada, kuid kes pole veel oma kordustellimust pikendanud.</span><span class="sxs-lookup"><span data-stu-id="175ce-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="175ce-116">Nende klientide alleshoidmiseks, soovite meili teel saata neile reklaampakkumise Adobe Experience Platformi kaudu.</span><span class="sxs-lookup"><span data-stu-id="175ce-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="175ce-117">Selles näites soovime käivitada ühekordse reklaamikampaania meili teel.</span><span class="sxs-lookup"><span data-stu-id="175ce-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="175ce-118">See artikkel ei hõlma kampaania läbiviimist rohkem kui üks kord.</span><span class="sxs-lookup"><span data-stu-id="175ce-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="175ce-119">Sihtrühma tuvastamine</span><span class="sxs-lookup"><span data-stu-id="175ce-119">Identify your target audience</span></span>

<span data-ttu-id="175ce-120">Meie stsenaariumis eeldame, et klientide meiliaadressid on sihtrühmaülevaadetes saadaval ja nende reklaamieelistusi on analüüsitud segmendi liikmete tuvastamiseks.</span><span class="sxs-lookup"><span data-stu-id="175ce-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="175ce-121">[Sihtrühmaülevaadetes määratletud segmendi](segments.md) nimeks on **ChurnProneCustomers** ja plaanite neile klientidele saata meilikampaania.</span><span class="sxs-lookup"><span data-stu-id="175ce-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Kuvatõmmis loodud ChurnProneCustomersi segmendiga segmentide lehest.":::

<span data-ttu-id="175ce-123">Väljasaatmiseks mõeldud pakkumismeilis on eesnimi, perekonnanimi ja kliendi kordustellimuse lõppkuupäev.</span><span class="sxs-lookup"><span data-stu-id="175ce-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="175ce-124">See teavitab klienti allahindlusest, mille nad saavad, kui nad oma kordustellimuse enne aegumist pikendavad.</span><span class="sxs-lookup"><span data-stu-id="175ce-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="175ce-125">Sihtrühma eksportimine</span><span class="sxs-lookup"><span data-stu-id="175ce-125">Export your target audience</span></span>

<span data-ttu-id="175ce-126">Kui sihtrühm on tuvastatud, saame konfigureerida ekspordi sihtrühmaülevaadetest Azure'i bloobimälu kontole.</span><span class="sxs-lookup"><span data-stu-id="175ce-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="175ce-127">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="175ce-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="175ce-128">Tehke paanil **Azure'i bloobimälu** valik **Häälestamine**.</span><span class="sxs-lookup"><span data-stu-id="175ce-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure'i bloobimälu konfiguratsioonipaan.":::

1. <span data-ttu-id="175ce-130">Sisestage uue ekspordisihtkoha jaoks **Kuvatav nimi** ja seejärel sisestage **Konto nimi**, **Konto võti** ja selle Azure'i bloobimälu **Ümbris**, kuhu soovite segmendi eksportida.</span><span class="sxs-lookup"><span data-stu-id="175ce-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Salvestusruumi konto konfiguratsiooni kuvatõmmis. "::: 

   - <span data-ttu-id="175ce-132">Lisateavet Azure'i bloobimälu konto nime ja kontovõtme kohta vaadake teemast [Salvestuskonto sätete haldamine Azure'i portaalis](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="175ce-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="175ce-133">Lisateavet konteineri loomise kohta leiate teemast [Konteineri loomine](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="175ce-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="175ce-134">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="175ce-134">Select **Next**.</span></span>

1. <span data-ttu-id="175ce-135">Valige segment, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="175ce-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="175ce-136">Selles näites on selleks **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="175ce-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Valitud segmendiga ChurnProneCustomers segmendivaliku kasutajaliidese kuvatõmmis.":::

1. <span data-ttu-id="175ce-138">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="175ce-138">Select **Save**.</span></span>

<span data-ttu-id="175ce-139">Pärast ekspordisihtkoha valimist leiate selle asukohast **Haldus** > **Ekspordid** > **Minu ekspordisihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="175ce-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Esiletõstetud eksportide loendi ja näidissegmendi kuvatõmmis.":::

<span data-ttu-id="175ce-141">Nüüd saate [nõudmisel segmendi](export-destinations.md#export-data-on-demand)</span><span class="sxs-lookup"><span data-stu-id="175ce-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="175ce-142">Eksport käivitub ka iga [ajastatud värskendamisega](system.md).</span><span class="sxs-lookup"><span data-stu-id="175ce-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="175ce-143">Veenduge, et eksporditud segmendi kirjete arv jääb Adobe Campaign Standardi litsentsi lubatud piiridesse.</span><span class="sxs-lookup"><span data-stu-id="175ce-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="175ce-144">Eksporditud andmed talletatakse eespool konfigureeritud Azure'i bloobimälu ümbrisesse.</span><span class="sxs-lookup"><span data-stu-id="175ce-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="175ce-145">Ümbrisesse luuakse automaatselt järgmine kaustatee:</span><span class="sxs-lookup"><span data-stu-id="175ce-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="175ce-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="175ce-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="175ce-147">Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="175ce-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="175ce-148">Eksporditud olemite *model.json* asub tasemel *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="175ce-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="175ce-149">Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="175ce-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="175ce-150">Experience Data Modeli (XDM) määratlemine Adobe Experience Platformil</span><span class="sxs-lookup"><span data-stu-id="175ce-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="175ce-151">Enne sihtrühmaülevaadetest eksporditu andmete kasutamist Adobe Experience Platformil peame määratlema Experience Data Modeli skeemi ja [konfigureerima reaalajas kliendiprofiili andmed](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="175ce-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="175ce-152">Lugege, [mis on XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ja tutvuge [skeemi loomise põhitõdedega](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="175ce-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="175ce-153">Andmete importimine Adobe Experience Platformile</span><span class="sxs-lookup"><span data-stu-id="175ce-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="175ce-154">Nüüd, kui kõik on valmis, peame profiilide loomiseks importima ettevalmistatud sihtrühmaandmed sihtrühmaülevaadetest Adobe Experience Platformile.</span><span class="sxs-lookup"><span data-stu-id="175ce-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="175ce-155">Esmalt looge [Azure'i bloobimälu l'hteühendus](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="175ce-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="175ce-156">Pärast lähteühenduse määratlemist [konfigureerige andmevoog](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pilvsalvestusruumi pakettühenduse jaoks, et importida sihtrühmaülevaadete segmendiväljund Adobe Experience Platformi.</span><span class="sxs-lookup"><span data-stu-id="175ce-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="175ce-157">Adobe Campaign Standardi sihtrühma loomine</span><span class="sxs-lookup"><span data-stu-id="175ce-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="175ce-158">Selle kampaania meili saatmiseks kasutame Adobe Campaign Standardit.</span><span class="sxs-lookup"><span data-stu-id="175ce-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="175ce-159">Pärast andmete importimist Adobe Experience Platformi peame [looma sihtrühma](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) Adobe Campaign Standardis Adobe Experience Platformi andmete abil.</span><span class="sxs-lookup"><span data-stu-id="175ce-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="175ce-160">Lugege, kuidas [kasutada segmendikoosturit](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) Adobe Campaign Standardis, et määratleda sihtrühm Adobe Experience Platformi andmete põhjal.</span><span class="sxs-lookup"><span data-stu-id="175ce-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="175ce-161">Meili loomine ja saatmine Adobe Campaign Standardi kaudu</span><span class="sxs-lookup"><span data-stu-id="175ce-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="175ce-162">Looge meilisisu ja seejärel [testige ja saatke](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) oma meil.</span><span class="sxs-lookup"><span data-stu-id="175ce-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standardi uuenduspakkumisega näidismeil.":::