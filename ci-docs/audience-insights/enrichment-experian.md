---
title: Rikastamine kolmanda osapoole rikastamisega Experian
description: Üldine teave Experian kolmanda osapoole rikastamise kohta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309815"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="89b79-103">Kliendiprofiilide rikastamine demograafiaga Experian (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="89b79-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="89b79-104">Experian on tarbija- ja ärikrediidi aruandluse ja turundusteenuste ülemaailmne liider.</span><span class="sxs-lookup"><span data-stu-id="89b79-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="89b79-105">Andmete rikastamise teenuste Experian abil saate oma kliente sügavamalt mõista, rikastades oma kliendiprofiile demograafiliste andmetega, nagu leibkonna suurus, sissetulek ja palju muud.</span><span class="sxs-lookup"><span data-stu-id="89b79-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="89b79-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="89b79-106">Prerequisites</span></span>

<span data-ttu-id="89b79-107">Experian konfigureerimiseks peavad olema täidetud järgmised eeltingimused:</span><span class="sxs-lookup"><span data-stu-id="89b79-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="89b79-108">Teil peab olema aktiivne rakenduse Experian kordustellimus.</span><span class="sxs-lookup"><span data-stu-id="89b79-108">You have an active Experian subscription.</span></span> <span data-ttu-id="89b79-109">Kordustellimuse saamiseks [võtke Experian](https://www.experian.com/marketing-services/contact) otse ühendust.</span><span class="sxs-lookup"><span data-stu-id="89b79-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="89b79-110">[Lugege lisateavet Experian andmerikastamine](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="89b79-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="89b79-111">Administraator on Experian ühenduse juba konfigureerinud *või* teil on [administraatori](permissions.md#administrator) õigused.</span><span class="sxs-lookup"><span data-stu-id="89b79-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="89b79-112">Teil on vaja ka kasutaja ID-d, osapoole ID-d ja mudelinumbrit SSH-toega turvalise transpordi (ST) konto jaoks, mille lõi teile Experian.</span><span class="sxs-lookup"><span data-stu-id="89b79-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="89b79-113">Toetatud riigid/piirkonnad</span><span class="sxs-lookup"><span data-stu-id="89b79-113">Supported countries/regions</span></span>

<span data-ttu-id="89b79-114">Praegu toetame kliendiprofiilide rikastamist ainult Ameerika Ühendriikides.</span><span class="sxs-lookup"><span data-stu-id="89b79-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="89b79-115">Rikastamise konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="89b79-115">Configure the enrichment</span></span>

1. <span data-ttu-id="89b79-116">Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.</span><span class="sxs-lookup"><span data-stu-id="89b79-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="89b79-117">Valige **Rikasta minu andmed** Experian paanil.</span><span class="sxs-lookup"><span data-stu-id="89b79-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="89b79-118">![Experian paan](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="89b79-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="89b79-119">Valige [ühendus](connections.md) ripploendist.</span><span class="sxs-lookup"><span data-stu-id="89b79-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="89b79-120">Kui ühendusi pole saadaval, pöörduge administraatori poole.</span><span class="sxs-lookup"><span data-stu-id="89b79-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="89b79-121">Kui olete administraator, saate ühenduse luua, valides **Lisa ühendus** käsu ja valides ripploendist Experian.</span><span class="sxs-lookup"><span data-stu-id="89b79-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="89b79-122">Valige **Ühenda Experian**, et kinnitada ühenduse valik.</span><span class="sxs-lookup"><span data-stu-id="89b79-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="89b79-123">Valige **Edasi** ja valige **Kliendi andmekomplekt**, mille andmeid soovite Experian demograafiliste andmetega rikastada.</span><span class="sxs-lookup"><span data-stu-id="89b79-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="89b79-124">Saate valida olemi **Klient**, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.</span><span class="sxs-lookup"><span data-stu-id="89b79-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendiandmete kogumi valimisel.":::

1. <span data-ttu-id="89b79-126">Valige **Edasi** ja määrake, millist tüüpi välju teie ühendatud profiilidest tuleks kasutada Experian andmetest demograafiliste andmete sobitamiseks.</span><span class="sxs-lookup"><span data-stu-id="89b79-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="89b79-127">Vähemalt üks väljadest **Nimi ja aadress**, **Telefon** või **E-post** on nõutav.</span><span class="sxs-lookup"><span data-stu-id="89b79-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="89b79-128">Suurema sobivuse täpsuse saavutamiseks saab lisada kuni kaks muud välja.</span><span class="sxs-lookup"><span data-stu-id="89b79-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="89b79-129">See valik mõjutab kaardistamisvälju, millele teil on järgmises etapis juurdepääs.</span><span class="sxs-lookup"><span data-stu-id="89b79-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="89b79-130">Rohkem võtmeidentifikaatori atribuute, mis Experian-ile saadetakse, tõenäoliselt annab suurema vaste määra.</span><span class="sxs-lookup"><span data-stu-id="89b79-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="89b79-131">Valige **Edasi**, et alustada väljade kaardistamist.</span><span class="sxs-lookup"><span data-stu-id="89b79-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="89b79-132">Määratlege, milliseid väljad teie ühendatud profiilidest tuleks kasutada Experian sobivate demograafiliste andmete otsimiseks.</span><span class="sxs-lookup"><span data-stu-id="89b79-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="89b79-133">Nõutud väljad on vastavalt tähistatud.</span><span class="sxs-lookup"><span data-stu-id="89b79-133">Required fields are marked.</span></span>

1. <span data-ttu-id="89b79-134">Sisestage rikastamise nimi ja väljundolemi nimi.</span><span class="sxs-lookup"><span data-stu-id="89b79-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="89b79-135">Valige **Salvesta rikastamine** pärast valikute läbivaatamist.</span><span class="sxs-lookup"><span data-stu-id="89b79-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="89b79-136">Konfigureerige Experian ühendus</span><span class="sxs-lookup"><span data-stu-id="89b79-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="89b79-137">Ühenduste konfigureerimiseks peate olema administraator.</span><span class="sxs-lookup"><span data-stu-id="89b79-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="89b79-138">Valige rikastamise konfigureerimisel **Lisa ühendus** *või* minge **Administraator** > **Ühendused** ja valige **Seadista** Experian paanil.</span><span class="sxs-lookup"><span data-stu-id="89b79-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="89b79-139">Seejärel valige suvand **Alustamine**.</span><span class="sxs-lookup"><span data-stu-id="89b79-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="89b79-140">Sisestage ühenduse nimi **Kuvatav nimi** väljale.</span><span class="sxs-lookup"><span data-stu-id="89b79-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="89b79-141">Sisestage oma Experian turvalise transpordi konto kehtiv kasutaja ID, osapoole ID ja mudeli number.</span><span class="sxs-lookup"><span data-stu-id="89b79-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="89b79-142">Vaadake üle ja esitage oma nõusolek **Andmete privaatsuse ja nõuetele vastavus** kohta, valides suvandi **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="89b79-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="89b79-143">Valige **Kontrolli** konfiguratsiooni valideerimiseks.</span><span class="sxs-lookup"><span data-stu-id="89b79-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="89b79-144">Pärast kontrollimise lõpuleviimist valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="89b79-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian ühenduse konfiguratsiooni paan.":::

## <a name="enrichment-results"></a><span data-ttu-id="89b79-146">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="89b79-146">Enrichment results</span></span>

<span data-ttu-id="89b79-147">Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="89b79-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="89b79-148">Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="89b79-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="89b79-149">Töötlemisaeg sõltub teie kliendiandmete suurusest ja teie Experian konto jaoks seadistatud rikastamisprotsessidest.</span><span class="sxs-lookup"><span data-stu-id="89b79-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="89b79-150">Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt.</span><span class="sxs-lookup"><span data-stu-id="89b79-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="89b79-151">Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="89b79-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="89b79-152">Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.</span><span class="sxs-lookup"><span data-stu-id="89b79-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="89b79-153">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="89b79-153">Next steps</span></span>

<span data-ttu-id="89b79-154">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="89b79-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="89b79-155">Looge [segmente](segments.md) ja [näitajaid](measures.md) ning isegi [eksportige andmed](export-destinations.md), et pakkuda oma klientidele isikupärastatud kogemust.</span><span class="sxs-lookup"><span data-stu-id="89b79-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="89b79-156">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="89b79-156">Data privacy and compliance</span></span>

<span data-ttu-id="89b79-157">Kui lubate Dynamics 365 Customer Insights edastada andmeid Experian-ile, lubate andmete edastamist väljapoole vastavuse piiri Dynamics 365 Customer Insights jaoks, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid.</span><span class="sxs-lookup"><span data-stu-id="89b79-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="89b79-158">Microsoft edastab sellised andmed teie juhiste alusel, kuid teie vastutate selle eest, et Experian täidaks kõiki privaatsus- või turvakohustusi, mis teil võivad olla.</span><span class="sxs-lookup"><span data-stu-id="89b79-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="89b79-159">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="89b79-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="89b79-160">Teie Dynamics 365 Customer Insights administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="89b79-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
