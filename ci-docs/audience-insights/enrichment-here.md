---
title: Rikastamine kolmanda osapoole rikastamisteenusega ettevõttelt HERE Technologies
description: Üldine teave ettevõtte HERE Technologies kolmanda osapoole rikastamise kohta.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668673"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="f8660-103">Kliendiprofiilide rikastamine ettevõtte HERE Technologies teenuste abil (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="f8660-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="f8660-104">HERE Technologies on asukohaplatvormi ettevõte, mis pakub asukohapõhist teavet ja teenuseid.</span><span class="sxs-lookup"><span data-stu-id="f8660-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="f8660-105">Ettevõtte HERE Technologies andmete rikastamise teenuste abil saate luua täpsema ülevaate oma klientide asukohast aadressi normaliseerimise, laius- ja pikkuskraadide ekstraktimise ning palju muu kaudu.</span><span class="sxs-lookup"><span data-stu-id="f8660-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f8660-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="f8660-106">Prerequisites</span></span>

<span data-ttu-id="f8660-107">Ettevõtte HERE Technologies rikastamisteenuse konfigureerimiseks peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="f8660-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f8660-108">Teil peab olema aktiivne ettevõtte HERE Technologies tellimus.</span><span class="sxs-lookup"><span data-stu-id="f8660-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="f8660-109">Tellimuseks saate [registreeruda siin](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) või võtta otse [ühendust ettevõttega HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="f8660-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="f8660-110">Lisateave ettevõtte HERE Technologies asukohapõhise rikastamise kohta.</span><span class="sxs-lookup"><span data-stu-id="f8660-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="f8660-111">Teil on ettevõtte HERE Technologies API võti.</span><span class="sxs-lookup"><span data-stu-id="f8660-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="f8660-112">Teil on [administraatori](permissions.md#administrator) õigused.</span><span class="sxs-lookup"><span data-stu-id="f8660-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="f8660-113">Konfiguratsioon</span><span class="sxs-lookup"><span data-stu-id="f8660-113">Configuration</span></span>

1. <span data-ttu-id="f8660-114">Avage **Andmed** > **Rikastamine**.</span><span class="sxs-lookup"><span data-stu-id="f8660-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="f8660-115">Valige paanilt HERE Technologies **Rikasta mu andmeid**.</span><span class="sxs-lookup"><span data-stu-id="f8660-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f8660-116">![Paan „HERE Technologies“](media/HERE-tile.png "Paan „HERE Technologies“")</span><span class="sxs-lookup"><span data-stu-id="f8660-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="f8660-117">Sisestage aktiivne **HERE Technologiese API võti**.</span><span class="sxs-lookup"><span data-stu-id="f8660-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="f8660-118">Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="f8660-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="f8660-119">Kinnitage mõlemad sisendid, valides **Loo ühendus HERE-ga**.</span><span class="sxs-lookup"><span data-stu-id="f8660-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1. <span data-ttu-id="f8660-120">Valige **Lisa andmed** ja valige, kas soovite vastendada väljad esmase ja/või teisese aadressiga.</span><span class="sxs-lookup"><span data-stu-id="f8660-120">Select **Add data** and choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="f8660-121">Saate määrata väljavastendused mõlema aadressi jaoks (nt kodu- ja ettevõtte aadress) ning rikastada mõlema aadressi profiile eraldi.</span><span class="sxs-lookup"><span data-stu-id="f8660-121">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="f8660-122">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="f8660-122">Select **Next**.</span></span>

1. <span data-ttu-id="f8660-123">Määratlege, milliseid teie koondatud profiilide välju tuleks kasutada, et otsida ettevõtte HERE Technologies teenuse kaudu ühtivaid asukohaandmeid.</span><span class="sxs-lookup"><span data-stu-id="f8660-123">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="f8660-124">Valitud esmase ja/või teisese aadressi jaoks on vajalikud väljad **Tänav 1** ja **Sihtnumber**.</span><span class="sxs-lookup"><span data-stu-id="f8660-124">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="f8660-125">Selleks et vasted oleksid täpsemad, saab lisada rohkem välju.</span><span class="sxs-lookup"><span data-stu-id="f8660-125">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f8660-126">![HERE Technologiese rikastamise konfigureerimise leht](media/enrichment-HERE-configuration.png "HERE Technologiese rikastamise konfigureerimise leht")</span><span class="sxs-lookup"><span data-stu-id="f8660-126">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="f8660-127">Valige **Rakenda**, et lõpetada väljade vastendamine.</span><span class="sxs-lookup"><span data-stu-id="f8660-127">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="f8660-128">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="f8660-128">Enrichment results</span></span>

<span data-ttu-id="f8660-129">Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="f8660-129">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="f8660-130">Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f8660-130">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f8660-131">Töötlemise aeg sõltub teie kliendiandmete mahust ja ettevõtte HERE Technologies API vastuseaegadest.</span><span class="sxs-lookup"><span data-stu-id="f8660-131">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="f8660-132">Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt.</span><span class="sxs-lookup"><span data-stu-id="f8660-132">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="f8660-133">Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="f8660-133">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="f8660-134">Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.</span><span class="sxs-lookup"><span data-stu-id="f8660-134">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f8660-135">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="f8660-135">Next steps</span></span>

<span data-ttu-id="f8660-136">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="f8660-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="f8660-137">Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [Ekspordi andmed](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f8660-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f8660-138">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="f8660-138">Data privacy and compliance</span></span>

<span data-ttu-id="f8660-139">Kui lubate Dynamics 365 Customer Insightsil ettevõttesse HERE Technologies andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="f8660-139">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f8660-140">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et HERE Technologies täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="f8660-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f8660-141">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f8660-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f8660-142">Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="f8660-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
