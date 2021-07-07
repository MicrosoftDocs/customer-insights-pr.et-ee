---
title: Rikastamine kolmanda osapoole rikastamisega HERE Technologies
description: Üldine teave ettevõtte HERE Technologies kolmanda osapoole rikastamise kohta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305289"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="fd955-103">Kliendiprofiilide rikastamine ettevõtte HERE Technologies teenuste abil (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="fd955-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="fd955-104">HERE Technologies on asukohaplatvormi ettevõte, mis pakub asukohapõhist teavet ja teenuseid.</span><span class="sxs-lookup"><span data-stu-id="fd955-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="fd955-105">Ettevõtte HERE Technologies andmete rikastamise teenuste abil saate luua täpsema ülevaate oma klientide asukohast aadressi normaliseerimise, laius- ja pikkuskraadide ekstraktimise ning palju muu kaudu.</span><span class="sxs-lookup"><span data-stu-id="fd955-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd955-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="fd955-106">Prerequisites</span></span>

<span data-ttu-id="fd955-107">Ettevõtte HERE Technologies rikastamisteenuse konfigureerimiseks peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="fd955-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="fd955-108">Teil peab olema aktiivne ettevõtte HERE Technologies tellimus.</span><span class="sxs-lookup"><span data-stu-id="fd955-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="fd955-109">Tellimuseks saate [registreeruda siin](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) või [kontakteeruda ettevõttega HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) otse.</span><span class="sxs-lookup"><span data-stu-id="fd955-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="fd955-110">Lisateave ettevõtte HERE Technologies asukohapõhise rikastamise kohta.</span><span class="sxs-lookup"><span data-stu-id="fd955-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="fd955-111">HERE [ühendus](connections.md) on saadaval *või* teil on [administraatori](permissions.md#administrator) õigused ja HERE Technologies API võti.</span><span class="sxs-lookup"><span data-stu-id="fd955-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="fd955-112">Rikastamise konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="fd955-112">Configure the enrichment</span></span>

1. <span data-ttu-id="fd955-113">Avage **Andmed** > **Rikastamine**.</span><span class="sxs-lookup"><span data-stu-id="fd955-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="fd955-114">Valige **Mu andmete rikastamine** HERE Technologies paanil ja valige **Alustamine**.</span><span class="sxs-lookup"><span data-stu-id="fd955-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd955-115">![Paan „HERE Technologies“](media/HERE-tile.png "Paan „HERE Technologies“")</span><span class="sxs-lookup"><span data-stu-id="fd955-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="fd955-116">Valige [ühendus](connections.md) ripploendist.</span><span class="sxs-lookup"><span data-stu-id="fd955-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="fd955-117">Kui ühendus pole saadaval, pöörduge administraatori poole.</span><span class="sxs-lookup"><span data-stu-id="fd955-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="fd955-118">Kui olete administraator, saate ühenduse luua, kui valite suvandi **Lisa ühendus**.</span><span class="sxs-lookup"><span data-stu-id="fd955-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="fd955-119">Valige **HERE Technologies** ripploendist.</span><span class="sxs-lookup"><span data-stu-id="fd955-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="fd955-120">Valige **Ühenda HERE Technologies**, et kinnitada valik.</span><span class="sxs-lookup"><span data-stu-id="fd955-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="fd955-121">Valige **Edasi** ja valige **Kliendi andmekomplekt**, mida soovite HERE Technologies asukoha andmetega rikastada.</span><span class="sxs-lookup"><span data-stu-id="fd955-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="fd955-122">Saate valida olemi **Klient**, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.</span><span class="sxs-lookup"><span data-stu-id="fd955-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendiandmete kogumi valimisel.":::

1. <span data-ttu-id="fd955-124">Valige, kas soovite vastendada väljad esmase ja/või teisese aadressiga.</span><span class="sxs-lookup"><span data-stu-id="fd955-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="fd955-125">Mõlemale aadressile saate määrata välja kaardistamise ja mõlema aadressi profiilid eraldi rikastada.</span><span class="sxs-lookup"><span data-stu-id="fd955-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="fd955-126">Näiteks kui olemas on kodu- ja äriaadress.</span><span class="sxs-lookup"><span data-stu-id="fd955-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="fd955-127">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="fd955-127">Select **Next**.</span></span>

1. <span data-ttu-id="fd955-128">Määratlege, milliseid teie koondatud profiilide välju tuleks kasutada, et otsida ettevõtte HERE Technologies teenuse kaudu ühtivaid asukohaandmeid.</span><span class="sxs-lookup"><span data-stu-id="fd955-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="fd955-129">Valitud esmase ja/või teisese aadressi jaoks on vajalikud väljad **Tänav 1** ja **Sihtnumber**.</span><span class="sxs-lookup"><span data-stu-id="fd955-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="fd955-130">Selleks et vasted oleksid täpsemad, saab lisada rohkem välju.</span><span class="sxs-lookup"><span data-stu-id="fd955-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd955-131">![HERE Technologiese rikastamise konfigureerimise leht](media/enrichment-HERE-configuration.png "HERE Technologiese rikastamise konfigureerimise leht")</span><span class="sxs-lookup"><span data-stu-id="fd955-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="fd955-132">Valige **Edasi**, et lõpetada väljade kaardistamine.</span><span class="sxs-lookup"><span data-stu-id="fd955-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="fd955-133">Peate rikastamise jaoks sisestama nime.</span><span class="sxs-lookup"><span data-stu-id="fd955-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="fd955-134">Valige **Salvesta rikastamine** pärast valikute läbivaatamist.</span><span class="sxs-lookup"><span data-stu-id="fd955-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="fd955-135">Konfigureerige ühendus HERE Technologies jaoks</span><span class="sxs-lookup"><span data-stu-id="fd955-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="fd955-136">Ühenduste konfigureerimiseks peate olema administraator.</span><span class="sxs-lookup"><span data-stu-id="fd955-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="fd955-137">Valige **Lisa ühendus** rikastamise konfigureerimisel *või* minge **Administraator** > **Ühendused** ja valige **Seadista** HERE Technologies paanil.</span><span class="sxs-lookup"><span data-stu-id="fd955-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="fd955-138">Sisestage ühenduse nimi **Kuvatav nimi** väljale.</span><span class="sxs-lookup"><span data-stu-id="fd955-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="fd955-139">Sisestage sobiv HERE Technologies API võti.</span><span class="sxs-lookup"><span data-stu-id="fd955-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="fd955-140">Vaadake üle ja esitage oma nõusolek **Andmete privaatsuse ja nõuetele vastavus** kohta, valides suvandi **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="fd955-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="fd955-141">Valige **Kontrolli** konfiguratsiooni valideerimiseks.</span><span class="sxs-lookup"><span data-stu-id="fd955-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="fd955-142">Pärast kontrollimise lõpuleviimist valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="fd955-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="fd955-143">![HERE technologies ühenduse konfiguratsiooni leht](media/enrichment-HERE-connection.png "HERE technologies ühenduse konfiguratsiooni leht")</span><span class="sxs-lookup"><span data-stu-id="fd955-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="fd955-144">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="fd955-144">Enrichment results</span></span>

<span data-ttu-id="fd955-145">Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="fd955-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="fd955-146">Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fd955-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fd955-147">Töötlemise aeg sõltub teie kliendiandmete mahust ja ettevõtte HERE Technologies API vastuseaegadest.</span><span class="sxs-lookup"><span data-stu-id="fd955-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="fd955-148">Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt.</span><span class="sxs-lookup"><span data-stu-id="fd955-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="fd955-149">Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="fd955-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="fd955-150">Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.</span><span class="sxs-lookup"><span data-stu-id="fd955-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fd955-151">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="fd955-151">Next steps</span></span>

<span data-ttu-id="fd955-152">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="fd955-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="fd955-153">Looge [segmente](segments.md) ja [näitajaid](measures.md) ning isegi [eksportige andmed](export-destinations.md), et pakkuda oma klientidele isikupärastatud kogemust.</span><span class="sxs-lookup"><span data-stu-id="fd955-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fd955-154">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="fd955-154">Data privacy and compliance</span></span>

<span data-ttu-id="fd955-155">Kui lubate Dynamics 365 Customer Insightsil ettevõttesse HERE Technologies andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="fd955-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fd955-156">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et HERE Technologies täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="fd955-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="fd955-157">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fd955-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fd955-158">Teie Dynamics 365 Customer Insights administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="fd955-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
