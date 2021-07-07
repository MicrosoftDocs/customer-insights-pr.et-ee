---
title: Kaasamisülevaadete veebiandmete integreerimine sihtrühmaülevaadetega
description: Saate tuua veebiteavet klientide kohta kaasamisülevaadetest sihtrühmaülevaadetesse.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 76a53a897e90152707a7c1255ed5ed93a5f3b5a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305013"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="3fe02-103">Kaasamisülevaadete veebiandmete integreerimine sihtrühmaülevaadetega</span><span class="sxs-lookup"><span data-stu-id="3fe02-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="3fe02-104">Kliendid teevad sageli oma igapäevaseid veebitehinguid veebisaitide abil.</span><span class="sxs-lookup"><span data-stu-id="3fe02-104">Customers often do their day-to-day transactions online using web sites.</span></span> <span data-ttu-id="3fe02-105">Kaasamisülevaadete (eelversioon) võimalus tarkvaras Dynamics 365 Customer Insights on käepärane lahendus veebiandmete integreerimiseks lähteandmetega.</span><span class="sxs-lookup"><span data-stu-id="3fe02-105">The engagement insights (preview) capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="3fe02-106">Ühendatud kliendiprofiilides näete lisaks tehingute, demograafilistele või käitumuslikele andmetele ka veebitegevusi.</span><span class="sxs-lookup"><span data-stu-id="3fe02-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="3fe02-107">Me võime kasutada neid profiile, et saada täiendavaid ülevaateid, nagu vaatajaskonna aktiveerimise segmendid, mõõdikud või prognoosid.</span><span class="sxs-lookup"><span data-stu-id="3fe02-107">We can use these profiles to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="3fe02-108">Selles artiklis kirjeldatakse, kuidas tuua klientide veebitegevuse andmed kaasamisülevaadetest oma olemasolevasse sihtrühmaülevaadete keskkonda.</span><span class="sxs-lookup"><span data-stu-id="3fe02-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="3fe02-109">Selles näites kasutame keskkonda, mis sisaldab ühendatud kliendiprofiile.</span><span class="sxs-lookup"><span data-stu-id="3fe02-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="3fe02-110">Profiilid ühendati uuringutest, jaemüügist ja piletisüsteemist pärinevate allikate abil.</span><span class="sxs-lookup"><span data-stu-id="3fe02-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="3fe02-111">Samuti kuvatakse siin klientidega seotud tegevusi.</span><span class="sxs-lookup"><span data-stu-id="3fe02-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="3fe02-112">Me soovime nüüd teada, kas klient külastab meie veebiatribuute ja saada aru nende tegevustest.</span><span class="sxs-lookup"><span data-stu-id="3fe02-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="3fe02-113">Tegevuste hulka kuuluvad näiteks külastatud veebisaidid või meili teel saadetud lingi kaudu vaadatud tootelehed.</span><span class="sxs-lookup"><span data-stu-id="3fe02-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3fe02-114">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="3fe02-114">Prerequisites</span></span>

<span data-ttu-id="3fe02-115">Kaasamisülevaadetest andmete integreerimiseks peavad olema täidetud mõned eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="3fe02-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="3fe02-116">Integreerige kaasamisülevaadete SDK oma veebisaidiga.</span><span class="sxs-lookup"><span data-stu-id="3fe02-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="3fe02-117">Lisateavet leiate [Arendaja ressursside ülevaade](../engagement-insights/developer-resources.md).</span><span class="sxs-lookup"><span data-stu-id="3fe02-117">For more information, see [Developer resources overview](../engagement-insights/developer-resources.md).</span></span>
- <span data-ttu-id="3fe02-118">Veebisündmuste eksportimiseks kaasamisülevaadetest on vaja juurdepääsu Azure Data Lake Storage kontole, mida kasutatakse veebisündmuste andmete vaatajaskonna ülevaate saamiseks.</span><span class="sxs-lookup"><span data-stu-id="3fe02-118">Exporting web events from engagement insights requires access to an Azure Data Lake Storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="3fe02-119">Lisateavet leiate teemast [Sündmuste eksportimine](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="3fe02-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="3fe02-120">Kaasamisülevaadete täpsustatud sündmuste konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="3fe02-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="3fe02-121">Kui administraator kasutab kaasamisülevaadetega SDK-ga veebisaiti, kogutakse *baassündmused* kokku, kui kasutaja vaatab veebilehte või klõpsab soovitud teavet.</span><span class="sxs-lookup"><span data-stu-id="3fe02-121">After an administrator instruments a website with the engagement insights SDK, *base events* are gathered when a user views a webpage or clicks somewhere.</span></span> <span data-ttu-id="3fe02-122">Baassündmused võivad sisaldada paljusid üksikasju.</span><span class="sxs-lookup"><span data-stu-id="3fe02-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="3fe02-123">Sõltuvalt kasutusjuhtumist vajate baassündmuses andmete alamhulka.</span><span class="sxs-lookup"><span data-stu-id="3fe02-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="3fe02-124">Kaasamisülevaadete abil saate luua *täpsustatud sündmusi*, mis sisaldavad ainult teie valitud baassündmuse atribuute.</span><span class="sxs-lookup"><span data-stu-id="3fe02-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="3fe02-125">Lisateavet leiate teemast [Täpsustatud sündmuste loomine ja muutmine](../engagement-insights/refined-events.md).</span><span class="sxs-lookup"><span data-stu-id="3fe02-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="3fe02-126">Mida võtta arvesse täpsustatud sündmuste loomisel.</span><span class="sxs-lookup"><span data-stu-id="3fe02-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="3fe02-127">Pange täpsustatud sündmusele tähenduslik nimi.</span><span class="sxs-lookup"><span data-stu-id="3fe02-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="3fe02-128">Seda kasutatakse sihtrühma ülevaadetes tegevuse nimena.</span><span class="sxs-lookup"><span data-stu-id="3fe02-128">It will be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="3fe02-129">Valige sihtrühmaülevaadetes tegevuse loomiseks vähemalt järgmised atribuudid.</span><span class="sxs-lookup"><span data-stu-id="3fe02-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="3fe02-130">Signal.Action.Name – tähistab tegevuse üksikasju.</span><span class="sxs-lookup"><span data-stu-id="3fe02-130">Signal.Action.Name – indicates the activity details.</span></span>
    - <span data-ttu-id="3fe02-131">Signal.User.Id – kasutatakse kliendi ID-ga kaardistamiseks.</span><span class="sxs-lookup"><span data-stu-id="3fe02-131">Signal.User.Id – used to map with the customer ID.</span></span>
    - <span data-ttu-id="3fe02-132">Signal.View.Uri – kasutatakse veebiaadressina segmentide või mõõtude alusena.</span><span class="sxs-lookup"><span data-stu-id="3fe02-132">Signal.View.Uri – used as a web address as a basis for segments or measures.</span></span>
    - <span data-ttu-id="3fe02-133">Signal.Export.Id – kasutatakse sündmuste primaarvõtmena.</span><span class="sxs-lookup"><span data-stu-id="3fe02-133">Signal.Export.Id – used as a primary key for events.</span></span>
    - <span data-ttu-id="3fe02-134">Signal.Timestamp – kuvab tegevuse edastuse kuupäeva ja kellaaja.</span><span class="sxs-lookup"><span data-stu-id="3fe02-134">Signal.Timestamp – determines the date and time for the activity.</span></span>

<span data-ttu-id="3fe02-135">Valige filtrid, et keskenduda sündmustele ja lehtedele, mis teie kasutusjuhtumi jaoks olulised on.</span><span class="sxs-lookup"><span data-stu-id="3fe02-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="3fe02-136">Selles näites kasutame tegevuse nime „Meilikampaania”.</span><span class="sxs-lookup"><span data-stu-id="3fe02-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="3fe02-137">Täpsustatud veebisündmuste eksportimine</span><span class="sxs-lookup"><span data-stu-id="3fe02-137">Export the refined web events</span></span> 

<span data-ttu-id="3fe02-138">Pärast täpsustatud sündmuse määratlemist peate konfigureerima sündmuse andmete eksportimise Azure Data Lake Storage, mille saab seada vaatajaskonna statistikasse sisestamise andmeallikaks.</span><span class="sxs-lookup"><span data-stu-id="3fe02-138">After defining the refined event, you have to configure the export of the event data to Azure Data Lake Storage, which can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="3fe02-139">Ekspordid toimuvad pidevalt sündmuste voolamisel veebiatribuudist.</span><span class="sxs-lookup"><span data-stu-id="3fe02-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="3fe02-140">Lisateavet leiate teemast [Sündmuste eksportimine](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="3fe02-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="3fe02-141">Sündmuse andmete valmendamine sihtrühmaülevaadetesse</span><span class="sxs-lookup"><span data-stu-id="3fe02-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="3fe02-142">Kui olete määratlenud täpsustatud sündmused ja konfigureerinud selle eksportimise, liigume edasi andmete valmendamisega sihtrühmaülevaadetesse.</span><span class="sxs-lookup"><span data-stu-id="3fe02-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="3fe02-143">Peate looma uue andmeallika Common Data Modeli kausta põhjal.</span><span class="sxs-lookup"><span data-stu-id="3fe02-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="3fe02-144">Sisestage selle salvestusruumikonto üksikasjad, kuhu sündmused ekspordite.</span><span class="sxs-lookup"><span data-stu-id="3fe02-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="3fe02-145">Valige failis *default.cdm.json* täpsustatud sündmus, mida valmendada ja looge olem sihtrühmaülevaadetes.</span><span class="sxs-lookup"><span data-stu-id="3fe02-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="3fe02-146">Lisateavet leiate teemast [Common Data Modeli kaustaga ühendamine Azure Data Lake'i konto abil](connect-common-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="3fe02-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md).</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="3fe02-147">Täpsustatud sündmuse andmete seostamine kliendiprofiili tegevusega</span><span class="sxs-lookup"><span data-stu-id="3fe02-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="3fe02-148">Pärast olemi valmendamise lõpule viimist saate konfigureerida tegevuse kliendiprofiili jaoks.</span><span class="sxs-lookup"><span data-stu-id="3fe02-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="3fe02-149">Lisateavet vt teemast [Klienditegevused](activities.md).</span><span class="sxs-lookup"><span data-stu-id="3fe02-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="Tegevuste leht laiendatud Redigeeri toimingupaaniga ja täidetud väljadega.":::

<span data-ttu-id="3fe02-151">Konfigureerige uus tegevus järgmise vastendusega.</span><span class="sxs-lookup"><span data-stu-id="3fe02-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="3fe02-152">**Primaarvõti**: Signal.Export.Id, kordumatu ID, mis on saadaval iga kaasamisülevaadete sündmusekirje jaoks.</span><span class="sxs-lookup"><span data-stu-id="3fe02-152">**Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="3fe02-153">See atribuut luuakse automaatselt.</span><span class="sxs-lookup"><span data-stu-id="3fe02-153">This property is automatically generated.</span></span>

- <span data-ttu-id="3fe02-154">**Ajatempel**: Signal.Timestamp sündmuse atribuudis.</span><span class="sxs-lookup"><span data-stu-id="3fe02-154">**Timestamp**: Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="3fe02-155">**Sündmus**: Signal.Name, sündmuse nimi, mida soovite jälgida.</span><span class="sxs-lookup"><span data-stu-id="3fe02-155">**Event**: Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="3fe02-156">**Veebiaadress**: Signal.View.Uri, mis viitab sündmuse loonud lehe URI-le.</span><span class="sxs-lookup"><span data-stu-id="3fe02-156">**Web address**: Signal.View.Uri referring to the URI of the page that created the event.</span></span>

- <span data-ttu-id="3fe02-157">**Üksikasjad**: Signal.Action.Name, mis tähistab sündmusega seostatavat teavet.</span><span class="sxs-lookup"><span data-stu-id="3fe02-157">**Details**: Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="3fe02-158">Valitud atribuut näitab antud juhul seda, et sündmus on meilikampaania jaoks.</span><span class="sxs-lookup"><span data-stu-id="3fe02-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="3fe02-159">**Tegevuse tüüp**: selles näites valime olemasoleva tegevusetüübi WebLog.</span><span class="sxs-lookup"><span data-stu-id="3fe02-159">**Activity type**: In this example, we choose the existing activity type WebLog.</span></span> <span data-ttu-id="3fe02-160">See valik on kasulik filtrisuvand prognoosimudelite käitamiseks või segmentide loomiseks selle tegevusetüübi põhjal.</span><span class="sxs-lookup"><span data-stu-id="3fe02-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="3fe02-161">**Seose seadistamine**: See oluline säte seob tegevuse olemasolevate kliendiprofiilidega.</span><span class="sxs-lookup"><span data-stu-id="3fe02-161">**Set up relationship**: This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="3fe02-162">**Signal.User.Id** on SDK-s konfigureeritud kogutav identifikaator, mis on seotud sihtrühmaülevaadetes konfigureeritud muude andmeallikate kasutaja ID-ga.</span><span class="sxs-lookup"><span data-stu-id="3fe02-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="3fe02-163">Selles näites konfigureerime seose Signal.User.Id ja RetailCustomers:CustomerRetailId vahel, mis on primaarvõti, mis määratleti andmete ühendamise protsessi kaardietapis.</span><span class="sxs-lookup"><span data-stu-id="3fe02-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.</span></span>

<span data-ttu-id="3fe02-164">Pärast tegevuste töötlemist saate vaadata üle kliendikirjed ja avada kliendikaardi, et kuvada ajajoonel kaasamisülevaadete tegevused.</span><span class="sxs-lookup"><span data-stu-id="3fe02-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="3fe02-165">Kaasamisülevaadete tegevusega kliendi ID leidmiseks avage **Olemid** ja vaadake üle olemi UnifiedActivity andmed.</span><span class="sxs-lookup"><span data-stu-id="3fe02-165">To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="3fe02-166">ActivityTypeDisplay = WebLog sisaldab ülaltoodud näites konfigureeritud kaasamisülevaadete tegevust.</span><span class="sxs-lookup"><span data-stu-id="3fe02-166">ActivityTypeDisplay = WebLog contains the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="3fe02-167">Kopeerige üks kirjetest ja selle ID kliendi ID lehel **Kliendid**.</span><span class="sxs-lookup"><span data-stu-id="3fe02-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3fe02-168">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="3fe02-168">Next steps</span></span>

<span data-ttu-id="3fe02-169">Nüüd saate luua [segmente](segments.md), [mõõte](measures.md) ja [prognoose](predictions.md), et luua klientidega mõtestatud ühendus.</span><span class="sxs-lookup"><span data-stu-id="3fe02-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
