---
title: Rikastamine kolmanda osapoole rikastamisteenusega Experianilt
description: Üldine teave Experiani kolmanda osapoole rikastamise kohta.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269555"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="97080-103">Kliendi profiilide rikastamine Experiani demograafiliste andmetega (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="97080-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="97080-104">Experian on üleilmne liider tarbijate ja ärikrediidi aruandluse ning turundusega seotud teenuste valdkonnas.</span><span class="sxs-lookup"><span data-stu-id="97080-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="97080-105">Experiani andmete rikastamise teenustega saate oma klientidest luua põhjalikuma ülevaate, rikastades klientide profiile selliste demograafiliste andmetega nagu leibkonna suurus, sissetulek ja palju muud.</span><span class="sxs-lookup"><span data-stu-id="97080-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="97080-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="97080-106">Prerequisites</span></span>

<span data-ttu-id="97080-107">Experiani konfigureerimiseks peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="97080-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="97080-108">Teil on olemas aktiivne Experiani kordustellimus.</span><span class="sxs-lookup"><span data-stu-id="97080-108">You have an active Experian subscription.</span></span> <span data-ttu-id="97080-109">Kordustellimuse saamiseks [võtke otse ühendust Experianiga](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="97080-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="97080-110">[vaadake lisateavet Experiani andmete rikastamise kohta](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="97080-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="97080-111">Teil on olemas kasutaja ID, poole ID ja mudeli number SSH-toega teenuse Secure Transport (ST) konto jaoks, mille Experian teie jaoks lõi.</span><span class="sxs-lookup"><span data-stu-id="97080-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="97080-112">Omate sihtrühmaülevaadetes [administraatori](permissions.md#administrator) õigusi.</span><span class="sxs-lookup"><span data-stu-id="97080-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="97080-113">Konfiguratsioon</span><span class="sxs-lookup"><span data-stu-id="97080-113">Configuration</span></span>

1. <span data-ttu-id="97080-114">Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.</span><span class="sxs-lookup"><span data-stu-id="97080-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="97080-115">Valige Experiani paanilt suvand **Rikasta minu andmeid**.</span><span class="sxs-lookup"><span data-stu-id="97080-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="97080-116">![Experiani paan](media/experian-tile.png "Experiani paan")</span><span class="sxs-lookup"><span data-stu-id="97080-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="97080-117">Valige suvand **Alusta** ja sisestage oma Experian Secure Transporti konto kasutaja ID, poole ID ja mudeli number.</span><span class="sxs-lookup"><span data-stu-id="97080-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="97080-118">Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="97080-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="97080-119">Kinnitage kogu sisestatud teave, valides suvandi **Rakenda**.</span><span class="sxs-lookup"><span data-stu-id="97080-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="97080-120">Väljade vastendamine</span><span class="sxs-lookup"><span data-stu-id="97080-120">Map your fields</span></span>

1.  <span data-ttu-id="97080-121">Valige **Lisa andmed** ja valige **Kliendiandmete kogum**, mida soovite Experiani demograafiliste andmetega rikastada.</span><span class="sxs-lookup"><span data-stu-id="97080-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="97080-122">Saate valida olemi **Klient**, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.</span><span class="sxs-lookup"><span data-stu-id="97080-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="97080-123">Valige oma peamised identifikaatorid üksusest **Nimi ja aadress**, **E-post** või **Telefon**, et saata need Experiani identiteedi lahenduseks.</span><span class="sxs-lookup"><span data-stu-id="97080-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="97080-124">Rohkemate võtmeidentifikaatori atribuutide saatmine Experianile annab tõenäoliselt suurema vastavuse määra.</span><span class="sxs-lookup"><span data-stu-id="97080-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="97080-125">Valige suvand **Edasi** ja vastendage oma koondatud kliendiolemi asjakohased atribuudid valitud võtmeidentifikaatori väljade jaoks.</span><span class="sxs-lookup"><span data-stu-id="97080-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="97080-126">Valige suvand **Lisa atribuut**, et vastendada mis tahes täiendavaid atribuute, mida soovite Experianile saata.</span><span class="sxs-lookup"><span data-stu-id="97080-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="97080-127">Väljavastenduse lõpule viimiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="97080-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="97080-128">![Experiani väljade vastendamine](media/experian-field-mapping.png "Experiani väljade vastendamine")</span><span class="sxs-lookup"><span data-stu-id="97080-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="97080-129">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="97080-129">Enrichment results</span></span>

<span data-ttu-id="97080-130">Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="97080-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="97080-131">Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="97080-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="97080-132">Töötlemisaeg sõltub teie kliendiandmete mahust ja rikastamistoimingutest, mille Experian on teie konto jaoks seadistanud.</span><span class="sxs-lookup"><span data-stu-id="97080-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="97080-133">Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt.</span><span class="sxs-lookup"><span data-stu-id="97080-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="97080-134">Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="97080-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="97080-135">Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.</span><span class="sxs-lookup"><span data-stu-id="97080-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="97080-136">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="97080-136">Next steps</span></span>

<span data-ttu-id="97080-137">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="97080-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="97080-138">Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [Ekspordi andmed](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="97080-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="97080-139">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="97080-139">Data privacy and compliance</span></span>

<span data-ttu-id="97080-140">Kui lubate Dynamics 365 Customer Insightsil Experiani andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="97080-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="97080-141">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Experian täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="97080-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="97080-142">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="97080-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="97080-143">Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="97080-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]