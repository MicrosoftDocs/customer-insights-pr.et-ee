---
title: Customer Insightsi andmete eksportimine rakendusse Adobe Campaign Standard
description: Lugege, kuidas kasutada Adobe Campaign Standardi sihtrühmaülevaadete segmente.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596310"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="fd464-103">Customer Insightsi segmentide kasutamine Adobe Campaign Standardis (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="fd464-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="fd464-104">Dynamics 365 Customer Insightsi sihtrühmaülevaadete kasutajana olete võib-olla loonud segmente turunduskampaaniate tõhusamaks muutmiseks asjakohaseid sihtrühmi määrates.</span><span class="sxs-lookup"><span data-stu-id="fd464-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="fd464-105">Adobe Experience Platformi ja rakendustest, nagu Adobe Campaign Standard pärit segmentide kasutamiseks peate järgima mõnda selles artiklis kirjeldatud juhist.</span><span class="sxs-lookup"><span data-stu-id="fd464-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Selles artiklis kirjeldatud juhiste protsessiskeem.":::

## <a name="prerequisites"></a><span data-ttu-id="fd464-107">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="fd464-107">Prerequisites</span></span>

-   <span data-ttu-id="fd464-108">Dynamics 365 Customer Insightsi litsents</span><span class="sxs-lookup"><span data-stu-id="fd464-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="fd464-109">Adobe Campaign Standardi litsents</span><span class="sxs-lookup"><span data-stu-id="fd464-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="fd464-110">Azure’i bloobimälu konto</span><span class="sxs-lookup"><span data-stu-id="fd464-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="fd464-111">Kampaania ülevaade</span><span class="sxs-lookup"><span data-stu-id="fd464-111">Campaign Overview</span></span>

<span data-ttu-id="fd464-112">Et paremini mõista, kuidas kasutada Adobe Experience Platformi sihtrühmaülevaadete segmente, vaatame väljamõeldud näidiskampaaniat.</span><span class="sxs-lookup"><span data-stu-id="fd464-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="fd464-113">Oletame, et teie ettevõte pakub teie USA klientidele igakuiseid, tellimusepõhiseid teenuseid.</span><span class="sxs-lookup"><span data-stu-id="fd464-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="fd464-114">Soovite tuvastada kliendid, kelle kordustellimusi tuleb järgmise kaheksa päeva pärast uuendada, kuid kes pole veel oma kordustellimust pikendanud.</span><span class="sxs-lookup"><span data-stu-id="fd464-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="fd464-115">Nende klientide alleshoidmiseks, soovite meili teel saata neile reklaampakkumise Adobe Campaign Standardi kaudu.</span><span class="sxs-lookup"><span data-stu-id="fd464-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="fd464-116">Selles näites soovime käivitada ühekordse reklaamikampaania meili teel.</span><span class="sxs-lookup"><span data-stu-id="fd464-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="fd464-117">See artikkel ei hõlma kampaania läbiviimist rohkem kui üks kord.</span><span class="sxs-lookup"><span data-stu-id="fd464-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="fd464-118">Sihtrühmaülevaateid ja rakendust Adobe Campaign Standard saab siiski konfigureerida töötama ka korduvate kampaaniastsenaariumide jaoks.</span><span class="sxs-lookup"><span data-stu-id="fd464-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="fd464-119">Sihtrühma tuvastamine</span><span class="sxs-lookup"><span data-stu-id="fd464-119">Identify your target audience</span></span>

<span data-ttu-id="fd464-120">Meie stsenaariumis eeldame, et klientide meiliaadressid on sihtrühmaülevaadetes saadaval ja nende reklaamieelistusi on analüüsitud segmendi liikmete tuvastamiseks.</span><span class="sxs-lookup"><span data-stu-id="fd464-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="fd464-121">[Sihtrühmaülevaadetes määratletud segmendi](segments.md) nimeks on **ChurnProneCustomers** ja plaanite neile klientidele saata meilikampaania.</span><span class="sxs-lookup"><span data-stu-id="fd464-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Kuvatõmmis loodud ChurnProneCustomersi segmendiga segmentide lehest.":::

<span data-ttu-id="fd464-123">Väljasaatmiseks mõeldud pakkumismeilis on eesnimi, perekonnanimi ja kliendi kordustellimuse lõppkuupäev.</span><span class="sxs-lookup"><span data-stu-id="fd464-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="fd464-124">See teavitab klienti allahindlusest, mille nad saavad, kui nad oma kordustellimuse enne aegumist pikendavad.</span><span class="sxs-lookup"><span data-stu-id="fd464-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="fd464-125">Sihtrühma eksportimine</span><span class="sxs-lookup"><span data-stu-id="fd464-125">Export your target audience</span></span>

<span data-ttu-id="fd464-126">Kui sihtrühm on tuvastatud, saame konfigureerida ekspordi sihtrühmaülevaadetest Azure'i bloobimälu kontole.</span><span class="sxs-lookup"><span data-stu-id="fd464-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="fd464-127">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="fd464-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="fd464-128">Valige paanil **Adobe Campaign** suvand **Häälesta**.</span><span class="sxs-lookup"><span data-stu-id="fd464-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standardi konfiguratsioonipaan.":::

1. <span data-ttu-id="fd464-130">Sisestage uue ekspordisihtkoha jaoks **Kuvatav nimi** ja seejärel sisestage **Konto nimi**, **Konto võti** ja selle Azure'i bloobimälu **Ümbris**, kuhu soovite segmendi eksportida.</span><span class="sxs-lookup"><span data-stu-id="fd464-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Salvestusruumi konto konfiguratsiooni kuvatõmmis. "::: 

   - <span data-ttu-id="fd464-132">Lisateavet Azure'i bloobimälu konto nime ja kontovõtme kohta vaadake teemast [Salvestuskonto sätete haldamine Azure'i portaalis](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="fd464-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="fd464-133">Lisateavet konteineri loomise kohta leiate teemast [Konteineri loomine](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="fd464-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="fd464-134">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="fd464-134">Select **Next**.</span></span>

1. <span data-ttu-id="fd464-135">Valige segment, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="fd464-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="fd464-136">Selles näites on selleks **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="fd464-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Valitud segmendiga ChurnProneCustomers segmendivaliku kasutajaliidese kuvatõmmis.":::

1. <span data-ttu-id="fd464-138">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="fd464-138">Select **Next**.</span></span>

1. <span data-ttu-id="fd464-139">Nüüd vastendame sihtrühmaülevaadete segmendi väljad **Lähtekoht** Adobe Campaign Standardi profiiliskeemi väljanimedele **Sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="fd464-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standardi konnektori väljade vastendamine.":::

   <span data-ttu-id="fd464-141">Kui soovite lisada veel atribuute, valige **Lisa atribuut**.</span><span class="sxs-lookup"><span data-stu-id="fd464-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="fd464-142">Sihtvälja nimi võib lähtevälja nimest erineda, et saaksite endiselt vastendada sihtrühmaülevaadete segmendiväljundi Adobe Campaign Standardiga, kui väljade nimed kahes süsteemis ei kattu.</span><span class="sxs-lookup"><span data-stu-id="fd464-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fd464-143">Meiliaadressi kasutatakse nende väljade tuvastamiseks, mida saate kasutada muu ID-na oma sihtrühmaülevaadete profiilist, et vastendada andmed Adobe Campaign Standard andmetega.</span><span class="sxs-lookup"><span data-stu-id="fd464-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="fd464-144">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="fd464-144">Select **Save**.</span></span>

<span data-ttu-id="fd464-145">Pärast ekspordisihtkoha valimist leiate selle asukohast **Haldus** > **Ekspordid** > **Minu ekspordisihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="fd464-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="Esiletõstetud eksportide loendi ja näidissegmendi kuvatõmmis.":::

<span data-ttu-id="fd464-147">Nüüd saate [nõudmisel segmendi](export-destinations.md#export-data-on-demand)</span><span class="sxs-lookup"><span data-stu-id="fd464-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="fd464-148">Eksport käivitub ka iga [ajastatud värskendamisega](system.md).</span><span class="sxs-lookup"><span data-stu-id="fd464-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fd464-149">Veenduge, et eksporditud segmendi kirjete arv jääb Adobe Campaign Standardi litsentsi lubatud piiridesse.</span><span class="sxs-lookup"><span data-stu-id="fd464-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="fd464-150">Eksporditud andmed talletatakse eespool konfigureeritud Azure'i bloobimälu ümbrisesse.</span><span class="sxs-lookup"><span data-stu-id="fd464-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="fd464-151">Ümbrisesse luuakse automaatselt järgmine kaustatee:</span><span class="sxs-lookup"><span data-stu-id="fd464-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="fd464-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="fd464-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="fd464-153">Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="fd464-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="fd464-154">Adobe Campaign Standardi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="fd464-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="fd464-155">Kui eksporditakse sihtrühmaülevaadetest pärit segment, sisaldab see veerge, mille olete ekspordi sihtkoha määratlemisel eelmises toimingus valinud.</span><span class="sxs-lookup"><span data-stu-id="fd464-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="fd464-156">Nende andmete abil saab [luua profiile rakenduses Adobe Campaign Standard ](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="fd464-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="fd464-157">Segmendi kasutamiseks Adobe Campaign Standardis peame laiendama Adobe Campaign Standardi profiiliskeemi ja kaasama kaks lisavälja.</span><span class="sxs-lookup"><span data-stu-id="fd464-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="fd464-158">Siit leiate teavet [profiiliressursside laiendamise](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) kohta uute väljadega Adobe Campaign Standardis.</span><span class="sxs-lookup"><span data-stu-id="fd464-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="fd464-159">Meie näites on need väljad *Segmendi nimi ja segmendi kuupäev (valikuline).*</span><span class="sxs-lookup"><span data-stu-id="fd464-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="fd464-160">Nende väljade abil tuvastame profiile, mida soovime selle kampaania jaoks Adobe Campaign Standardis määrata.</span><span class="sxs-lookup"><span data-stu-id="fd464-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="fd464-161">Kui Adobe Campaign Standardis pole muid kirjeid, kui need, mille plaanite importida, võite selle juhise vahele jätta.</span><span class="sxs-lookup"><span data-stu-id="fd464-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="fd464-162">Andmete importimine Adobe Campaign Standardisse</span><span class="sxs-lookup"><span data-stu-id="fd464-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="fd464-163">Nüüd, kui kõik on valmis, peame profiilide loomiseks importima ettevalmistatud sihtrühmaandmed sihtrühmaülevaadetest Adobe Campaign Standardisse.</span><span class="sxs-lookup"><span data-stu-id="fd464-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="fd464-164">Lugege, [kuidas importida Adobe Campaign Standardi profiile](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) töövoo abil.</span><span class="sxs-lookup"><span data-stu-id="fd464-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="fd464-165">Alloleval pildil oleva impordi töövoog on konfigureeritud käitama iga 8 tunni järel ja see otsib eksporditud sihtrühmaülevaadete segmente (Azure'i bloobimälu CSV-fail).</span><span class="sxs-lookup"><span data-stu-id="fd464-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="fd464-166">Töövoog ekstraktib CSV-faili sisu määratud veerujärjestuses.</span><span class="sxs-lookup"><span data-stu-id="fd464-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="fd464-167">See töövoog on rajatud tegema peamisi tõrketöötlusi ja tagama, et igal kirjel oleks meiliaadress enne enne domeeniandmete laadimist Adobe Campaign Standardis.</span><span class="sxs-lookup"><span data-stu-id="fd464-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="fd464-168">Töövoog ekstraktib ka segmendi nime failinimest enne ACS-i profiiliandmetesse sisestamist või selle värskendamist.</span><span class="sxs-lookup"><span data-stu-id="fd464-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standardi kasutajaliidese töövoo importimise kuvatõmmis.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="fd464-170">Adobe Campaign Standardi sihtrühma toomine</span><span class="sxs-lookup"><span data-stu-id="fd464-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="fd464-171">Kui andmed on Adobe Campaign Standardisse imporditud, [saate luua töövoo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ja saata [päringu](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klientide kohta väljade *Segmendi nimi* ja *Segmendi kuupäev* alusel, et valida profiilid, mis tuvastati meie näidiskampaania jaoks.</span><span class="sxs-lookup"><span data-stu-id="fd464-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="fd464-172">Meili loomine ja saatmine Adobe Campaign Standardi kaudu</span><span class="sxs-lookup"><span data-stu-id="fd464-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="fd464-173">Looge meilisisu ja seejärel [testige ja saatke](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) oma meil.</span><span class="sxs-lookup"><span data-stu-id="fd464-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standardi uuenduspakkumisega näidismeil.":::