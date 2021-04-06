---
title: Kaasamisülevaadete veebiandmete integreerimine sihtrühmaülevaadetega
description: Saate tuua veebiteavet klientide kohta kaasamisülevaadetest sihtrühmaülevaadetesse.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 14ebff30d3ec7fc52dca6f86136309a3f454fa27
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597460"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="417d2-103">Kaasamisülevaadete veebiandmete integreerimine sihtrühmaülevaadetega</span><span class="sxs-lookup"><span data-stu-id="417d2-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="417d2-104">Kliendid teevad sageli oma igapäevaseid tehinguid veebis veebisaitide abil.</span><span class="sxs-lookup"><span data-stu-id="417d2-104">Customers often do their day to day transactions online using web sites.</span></span> <span data-ttu-id="417d2-105">Dynamics 365 Customer Insightsi kaasamisülevaadete võimalus on käepärane lahendus veebiandmete integreerimiseks allikana.</span><span class="sxs-lookup"><span data-stu-id="417d2-105">The engagement insights capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="417d2-106">Ühendatud kliendiprofiilides näete lisaks tehingute, demograafilistele või käitumuslikele andmetele ka veebitegevusi.</span><span class="sxs-lookup"><span data-stu-id="417d2-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="417d2-107">Selle profiili abil võime saada täiendavat ülevaadet, nagu segmente, mõõte või prognoose publiku aktiveerimiseks.</span><span class="sxs-lookup"><span data-stu-id="417d2-107">We can use this profile to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="417d2-108">Selles artiklis kirjeldatakse, kuidas tuua klientide veebitegevuse andmed kaasamisülevaadetest oma olemasolevasse sihtrühmaülevaadete keskkonda.</span><span class="sxs-lookup"><span data-stu-id="417d2-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="417d2-109">Selles näites kasutame keskkonda, mis sisaldab ühendatud kliendiprofiile.</span><span class="sxs-lookup"><span data-stu-id="417d2-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="417d2-110">Profiilid ühendati uuringutest, jaemüügist ja piletisüsteemist pärinevate allikate abil.</span><span class="sxs-lookup"><span data-stu-id="417d2-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="417d2-111">Samuti kuvatakse siin klientidega seotud tegevusi.</span><span class="sxs-lookup"><span data-stu-id="417d2-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="417d2-112">Me soovime nüüd teada, kas klient külastab meie veebiatribuute ja saada aru nende tegevustest.</span><span class="sxs-lookup"><span data-stu-id="417d2-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="417d2-113">Tegevuste hulka kuuluvad näiteks külastatud veebisaidid või meili teel saadetud lingi kaudu vaadatud tootelehed.</span><span class="sxs-lookup"><span data-stu-id="417d2-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="417d2-114">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="417d2-114">Prerequisites</span></span>

<span data-ttu-id="417d2-115">Kaasamisülevaadetest andmete integreerimiseks peavad olema täidetud mõned eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="417d2-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="417d2-116">Integreerige kaasamisülevaadete SDK oma veebisaidiga.</span><span class="sxs-lookup"><span data-stu-id="417d2-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="417d2-117">Lisateavet leiate teemast [Veebi SDK-ga alustamine](../engagement-insights/instrument-website.md).</span><span class="sxs-lookup"><span data-stu-id="417d2-117">For more information, see [Get started with the web SDK](../engagement-insights/instrument-website.md).</span></span>
- <span data-ttu-id="417d2-118">Veebisündmuste eksportimiseks kaasamisülevaadetest vajate juurdepääsu ADLS Gen 2 salvestusruumi kontole, mida kasutatakse veebisündmuste andmete valmendamiseks sihtrühmaülevaadetesse.</span><span class="sxs-lookup"><span data-stu-id="417d2-118">Exporting web events from engagement insights requires access to an ADLS Gen 2 storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="417d2-119">Lisateavet leiate teemast [Sündmuste eksportimine](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="417d2-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="417d2-120">Kaasamisülevaadete täpsustatud sündmuste konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="417d2-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="417d2-121">Kui administraator on täiendanud veebisaiti kaasamisülevaadete SDK-ga, kogutakse *baassündmusi*, kui kasutaja vaatab veebilehte või klõpsab midagi.</span><span class="sxs-lookup"><span data-stu-id="417d2-121">After an administrator instrumented a website with the engagement insights SDK, *base events* are gathered when a user views a web page or clicks somewhere.</span></span> <span data-ttu-id="417d2-122">Baassündmused võivad sisaldada paljusid üksikasju.</span><span class="sxs-lookup"><span data-stu-id="417d2-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="417d2-123">Sõltuvalt kasutusjuhtumist vajate baassündmuses andmete alamhulka.</span><span class="sxs-lookup"><span data-stu-id="417d2-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="417d2-124">Kaasamisülevaadete abil saate luua *täpsustatud sündmusi*, mis sisaldavad ainult teie valitud baassündmuse atribuute.</span><span class="sxs-lookup"><span data-stu-id="417d2-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="417d2-125">Lisateavet leiate teemast [Täpsustatud sündmuste loomine ja muutmine](../engagement-insights/refined-events.md).</span><span class="sxs-lookup"><span data-stu-id="417d2-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="417d2-126">Mida võtta arvesse täpsustatud sündmuste loomisel.</span><span class="sxs-lookup"><span data-stu-id="417d2-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="417d2-127">Pange täpsustatud sündmusele tähenduslik nimi.</span><span class="sxs-lookup"><span data-stu-id="417d2-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="417d2-128">Seda kasutatakse sihtrühmaülevaadetes tegevuse nimena.</span><span class="sxs-lookup"><span data-stu-id="417d2-128">It's be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="417d2-129">Valige sihtrühmaülevaadetes tegevuse loomiseks vähemalt järgmised atribuudid.</span><span class="sxs-lookup"><span data-stu-id="417d2-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="417d2-130">Signal.Action.Name – tähistab tegevuse üksikasju</span><span class="sxs-lookup"><span data-stu-id="417d2-130">Signal.Action.Name - indicating the activity details</span></span>
    - <span data-ttu-id="417d2-131">Signal.User.Id – kasutatakse kliendi ID-ga vastendamiseks</span><span class="sxs-lookup"><span data-stu-id="417d2-131">Signal.User.Id - used to map with the customer ID</span></span>
    - <span data-ttu-id="417d2-132">Signal.View.Uri – kasutatakse veebiaadressina segmentide või mõõtude alusena</span><span class="sxs-lookup"><span data-stu-id="417d2-132">Signal.View.Uri - used as a web address as a basis for segments or measures</span></span>
    - <span data-ttu-id="417d2-133">Signal.Export.Id – kasutatakse sündmuste primaarvõtmena</span><span class="sxs-lookup"><span data-stu-id="417d2-133">Signal.Export.Id - to use as a primary key for events</span></span> <!-- system generated, do we need to list?-->
    - <span data-ttu-id="417d2-134">Signal.Timestamp – määratleb tegevuse kuupäeva ja kellaaja</span><span class="sxs-lookup"><span data-stu-id="417d2-134">Signal.Timestamp - to determine the date and time for the activity</span></span>

<span data-ttu-id="417d2-135">Valige filtrid, et keskenduda sündmustele ja lehtedele, mis teie kasutusjuhtumi jaoks olulised on.</span><span class="sxs-lookup"><span data-stu-id="417d2-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="417d2-136">Selles näites kasutame tegevuse nime „Meilikampaania”.</span><span class="sxs-lookup"><span data-stu-id="417d2-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="417d2-137">Täpsustatud veebisündmuste eksportimine</span><span class="sxs-lookup"><span data-stu-id="417d2-137">Export the Refined Web Events</span></span> 

<span data-ttu-id="417d2-138">Kui täpsustatud sündmus on määratletud, peate konfigureerima sündmuse andmete ekspordi Azure Data Lake Storage'iks, mida saab määrata valmenduse andmeallikaks sihtrühmaülevaadetes.</span><span class="sxs-lookup"><span data-stu-id="417d2-138">After defining the refined event is defined, you have to configure the export of the event data to an Azure Data Lake Storage, that can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="417d2-139">Ekspordid toimuvad pidevalt sündmuste voolamisel veebiatribuudist.</span><span class="sxs-lookup"><span data-stu-id="417d2-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="417d2-140">Lisateavet leiate teemast [Sündmuste eksportimine](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="417d2-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="417d2-141">Sündmuse andmete valmendamine sihtrühmaülevaadetesse</span><span class="sxs-lookup"><span data-stu-id="417d2-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="417d2-142">Kui olete määratlenud täpsustatud sündmused ja konfigureerinud selle eksportimise, liigume edasi andmete valmendamisega sihtrühmaülevaadetesse.</span><span class="sxs-lookup"><span data-stu-id="417d2-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="417d2-143">Peate looma uue andmeallika Common Data Modeli kausta põhjal.</span><span class="sxs-lookup"><span data-stu-id="417d2-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="417d2-144">Sisestage selle salvestusruumikonto üksikasjad, kuhu sündmused ekspordite.</span><span class="sxs-lookup"><span data-stu-id="417d2-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="417d2-145">Valige failis *default.cdm.json* täpsustatud sündmus, mida valmendada ja looge olem sihtrühmaülevaadetes.</span><span class="sxs-lookup"><span data-stu-id="417d2-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="417d2-146">Lisateavet leiate teemast [Common Data Modeli kaustaga ühendamine Azure Data Lake'i konto abil](connect-common-data-model.md)</span><span class="sxs-lookup"><span data-stu-id="417d2-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md)</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="417d2-147">Täpsustatud sündmuse andmete seostamine kliendiprofiili tegevusega</span><span class="sxs-lookup"><span data-stu-id="417d2-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="417d2-148">Pärast olemi valmendamise lõpule viimist saate konfigureerida tegevuse kliendiprofiili jaoks.</span><span class="sxs-lookup"><span data-stu-id="417d2-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="417d2-149">Lisateavet vt teemast [Klienditegevused](activities.md).</span><span class="sxs-lookup"><span data-stu-id="417d2-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="Tegevuste leht laiendatud toimingupaaniga Redigeeri ja täidetud väljadega.":::

<span data-ttu-id="417d2-151">Konfigureerige uus tegevus järgmise vastendusega.</span><span class="sxs-lookup"><span data-stu-id="417d2-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="417d2-152">**Primaarvõti:** Signal.Export.Id, kordumatu ID, mis on saadaval iga kaasamisülevaadete sündmusekirje jaoks.</span><span class="sxs-lookup"><span data-stu-id="417d2-152">**Primary Key:** Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="417d2-153">See atribuut luuakse automaatselt.</span><span class="sxs-lookup"><span data-stu-id="417d2-153">This property is automatically generated.</span></span>

- <span data-ttu-id="417d2-154">**Ajatempel:** Signal.Timestamp sündmuse atribuudis.</span><span class="sxs-lookup"><span data-stu-id="417d2-154">**Timestamp:** Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="417d2-155">**Sündmus:** Signal.Name, sündmuse nimi, mida soovite jälgida.</span><span class="sxs-lookup"><span data-stu-id="417d2-155">**Event:** Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="417d2-156">**Veebiaadress:** Signal.View.Uri, mis viitab sündmuse loonud lehe URI-le.</span><span class="sxs-lookup"><span data-stu-id="417d2-156">**Web address:** Signal.View.Uri referring to the uri of the page that created the event.</span></span>

- <span data-ttu-id="417d2-157">**Üksikasjad:** Signal.Action.Name, mis tähistab sündmusega seostatavat teavet.</span><span class="sxs-lookup"><span data-stu-id="417d2-157">**Details:** Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="417d2-158">Valitud atribuut näitab antud juhul seda, et sündmus on meilikampaania jaoks.</span><span class="sxs-lookup"><span data-stu-id="417d2-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="417d2-159">**Tegevuse tüüp:** selles näites valime olemasoleva tegevusetüübi WebLog.</span><span class="sxs-lookup"><span data-stu-id="417d2-159">**Activity type:** In this example, we choose the exsting activity type WebLog.</span></span> <span data-ttu-id="417d2-160">See valik on kasulik filtrisuvand prognoosimudelite käitamiseks või segmentide loomiseks selle tegevusetüübi põhjal.</span><span class="sxs-lookup"><span data-stu-id="417d2-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="417d2-161">**Seose seadistamine:** see oluline säte seob tegevuse olemasolevate kliendiprofiilidega.</span><span class="sxs-lookup"><span data-stu-id="417d2-161">**Set up relationship:** This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="417d2-162">**Signal.User.Id** on SDK-s konfigureeritud kogutav identifikaator, mis on seotud sihtrühmaülevaadetes konfigureeritud muude andmeallikate kasutaja ID-ga.</span><span class="sxs-lookup"><span data-stu-id="417d2-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="417d2-163">Selles näites konfigureerime seose üksuste Signal.User.Id ja RetailCustomers:CustomerRetailId vahel, mis on esmane võti, mis lisati andmete ühendamise protsessi vastendamise etapis.</span><span class="sxs-lookup"><span data-stu-id="417d2-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was deinfed in the map step of the data unification process.</span></span>


<span data-ttu-id="417d2-164">Pärast tegevuste töötlemist saate vaadata üle kliendikirjed ja avada kliendikaardi, et kuvada ajajoonel kaasamisülevaadete tegevused.</span><span class="sxs-lookup"><span data-stu-id="417d2-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="417d2-165">Kaasamisülevaadete tegevusega kliendi ID leidmiseks avage **Olemid** ja vaadake üle olemi UnifiedActivity andmed.</span><span class="sxs-lookup"><span data-stu-id="417d2-165">To find a customer id that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="417d2-166">ActivityTypeDisplay = WebLog sisaldab ülaltoodud näites konfigureeritud kaasamisülevaadete tegevust.</span><span class="sxs-lookup"><span data-stu-id="417d2-166">ActivityTypeDisplay = WebLog contain the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="417d2-167">Kopeerige üks kirjetest ja selle ID kliendi ID lehel **Kliendid**.</span><span class="sxs-lookup"><span data-stu-id="417d2-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="417d2-168">Järgmised toimingud</span><span class="sxs-lookup"><span data-stu-id="417d2-168">Next Steps</span></span>

<span data-ttu-id="417d2-169">Nüüd saate luua [segmente](segments.md), [mõõte](measures.md) ja [prognoose](predictions.md), et luua klientidega mõtestatud ühendus.</span><span class="sxs-lookup"><span data-stu-id="417d2-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]