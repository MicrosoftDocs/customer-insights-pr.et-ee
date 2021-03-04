---
title: Rikastamine kolmanda osapoole rikastamisteenusega ettevõttelt HERE Technologies
description: Üldine teave ettevõtte HERE Technologies kolmanda osapoole rikastamise kohta.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269509"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="5a5de-103">Kliendiprofiilide rikastamine ettevõtte HERE Technologies teenuste abil (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="5a5de-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="5a5de-104">HERE Technologies on asukohaplatvormi ettevõte, mis pakub asukohapõhist teavet ja teenuseid.</span><span class="sxs-lookup"><span data-stu-id="5a5de-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="5a5de-105">Ettevõtte HERE Technologies andmete rikastamise teenuste abil saate luua täpsema ülevaate oma klientide asukohast aadressi normaliseerimise, laius- ja pikkuskraadide ekstraktimise ning palju muu kaudu.</span><span class="sxs-lookup"><span data-stu-id="5a5de-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a5de-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="5a5de-106">Prerequisites</span></span>

<span data-ttu-id="5a5de-107">Ettevõtte HERE Technologies rikastamisteenuse konfigureerimiseks peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="5a5de-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="5a5de-108">Teil peab olema aktiivne ettevõtte HERE Technologies tellimus.</span><span class="sxs-lookup"><span data-stu-id="5a5de-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="5a5de-109">Tellimuseks saate [registreeruda siin](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) või võtta otse [ühendust ettevõttega HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you).</span><span class="sxs-lookup"><span data-stu-id="5a5de-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="5a5de-110">Lisateave ettevõtte HERE Technologies asukohapõhise rikastamise kohta.</span><span class="sxs-lookup"><span data-stu-id="5a5de-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="5a5de-111">Teil on ettevõtte HERE Technologies API võti.</span><span class="sxs-lookup"><span data-stu-id="5a5de-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="5a5de-112">Teil on [administraatori](permissions.md#administrator) õigused.</span><span class="sxs-lookup"><span data-stu-id="5a5de-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="5a5de-113">Konfiguratsioon</span><span class="sxs-lookup"><span data-stu-id="5a5de-113">Configuration</span></span>

1. <span data-ttu-id="5a5de-114">Avage **Andmed** > **Rikastamine**.</span><span class="sxs-lookup"><span data-stu-id="5a5de-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="5a5de-115">Valige paanilt HERE Technologies **Rikasta mu andmeid**.</span><span class="sxs-lookup"><span data-stu-id="5a5de-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a5de-116">![Paan „HERE Technologies“](media/HERE-tile.png "Paan „HERE Technologies“")</span><span class="sxs-lookup"><span data-stu-id="5a5de-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="5a5de-117">Sisestage aktiivne **HERE Technologiese API võti**.</span><span class="sxs-lookup"><span data-stu-id="5a5de-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="5a5de-118">Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="5a5de-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="5a5de-119">Kinnitage mõlemad sisendid, valides **Loo ühendus HERE-ga**.</span><span class="sxs-lookup"><span data-stu-id="5a5de-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="5a5de-120">Valige **Lisa andmed** ja valige **Kliendiandmete kogum**, mida soovite HERE Technologiesi asukohaandmetega rikastada.</span><span class="sxs-lookup"><span data-stu-id="5a5de-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="5a5de-121">Saate valida olemi **Klient**, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.</span><span class="sxs-lookup"><span data-stu-id="5a5de-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendiandmete kogumi valimisel.":::

1. <span data-ttu-id="5a5de-123">Valige, kas soovite vastendada väljad esmase ja/või teisese aadressiga.</span><span class="sxs-lookup"><span data-stu-id="5a5de-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="5a5de-124">Saate määrata väljavastendused mõlema aadressi jaoks (nt kodu- ja ettevõtte aadress) ning rikastada mõlema aadressi profiile eraldi.</span><span class="sxs-lookup"><span data-stu-id="5a5de-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="5a5de-125">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="5a5de-125">Select **Next**.</span></span>

1. <span data-ttu-id="5a5de-126">Määratlege, milliseid teie koondatud profiilide välju tuleks kasutada, et otsida ettevõtte HERE Technologies teenuse kaudu ühtivaid asukohaandmeid.</span><span class="sxs-lookup"><span data-stu-id="5a5de-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="5a5de-127">Valitud esmase ja/või teisese aadressi jaoks on vajalikud väljad **Tänav 1** ja **Sihtnumber**.</span><span class="sxs-lookup"><span data-stu-id="5a5de-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="5a5de-128">Selleks et vasted oleksid täpsemad, saab lisada rohkem välju.</span><span class="sxs-lookup"><span data-stu-id="5a5de-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5a5de-129">![HERE Technologiese rikastamise konfigureerimise leht](media/enrichment-HERE-configuration.png "HERE Technologiese rikastamise konfigureerimise leht")</span><span class="sxs-lookup"><span data-stu-id="5a5de-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="5a5de-130">Valige **Rakenda**, et lõpetada väljade vastendamine.</span><span class="sxs-lookup"><span data-stu-id="5a5de-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="5a5de-131">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="5a5de-131">Enrichment results</span></span>

<span data-ttu-id="5a5de-132">Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="5a5de-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="5a5de-133">Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5a5de-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5a5de-134">Töötlemise aeg sõltub teie kliendiandmete mahust ja ettevõtte HERE Technologies API vastuseaegadest.</span><span class="sxs-lookup"><span data-stu-id="5a5de-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="5a5de-135">Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt.</span><span class="sxs-lookup"><span data-stu-id="5a5de-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="5a5de-136">Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="5a5de-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="5a5de-137">Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.</span><span class="sxs-lookup"><span data-stu-id="5a5de-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5a5de-138">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="5a5de-138">Next steps</span></span>

<span data-ttu-id="5a5de-139">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="5a5de-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="5a5de-140">Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [Ekspordi andmed](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="5a5de-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5a5de-141">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="5a5de-141">Data privacy and compliance</span></span>

<span data-ttu-id="5a5de-142">Kui lubate Dynamics 365 Customer Insightsil ettevõttesse HERE Technologies andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="5a5de-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5a5de-143">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et HERE Technologies täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="5a5de-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5a5de-144">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5a5de-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5a5de-145">Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="5a5de-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]