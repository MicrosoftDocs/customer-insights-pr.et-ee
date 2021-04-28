---
title: Rikastamine kolmanda osapoole rikastamisteenusega Experianilt
description: Üldine teave Experiani kolmanda osapoole rikastamise kohta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896368"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="dca16-103">Kliendi profiilide rikastamine Experiani demograafiliste andmetega (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="dca16-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="dca16-104">Experian on üleilmne liider tarbijate ja ärikrediidi aruandluse ning turundusega seotud teenuste valdkonnas.</span><span class="sxs-lookup"><span data-stu-id="dca16-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="dca16-105">Experiani andmete rikastamise teenustega saate oma klientidest luua põhjalikuma ülevaate, rikastades klientide profiile selliste demograafiliste andmetega nagu leibkonna suurus, sissetulek ja palju muud.</span><span class="sxs-lookup"><span data-stu-id="dca16-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dca16-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="dca16-106">Prerequisites</span></span>

<span data-ttu-id="dca16-107">Experiani konfigureerimiseks peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="dca16-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="dca16-108">Teil on olemas aktiivne Experiani kordustellimus.</span><span class="sxs-lookup"><span data-stu-id="dca16-108">You have an active Experian subscription.</span></span> <span data-ttu-id="dca16-109">Kordustellimuse saamiseks [võtke otse ühendust Experianiga](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="dca16-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="dca16-110">[vaadake lisateavet Experiani andmete rikastamise kohta](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="dca16-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="dca16-111">Administraator on Experian ühenduse juba konfigureerinud *või* teil on [administraatori](permissions.md#administrator) õigused.</span><span class="sxs-lookup"><span data-stu-id="dca16-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="dca16-112">Samuti on teil vaja SSH-toega turvalise transpordi (ST) konto kasutaja ID-d, osapoole ID-d ja mudelinumbrit, mille Experian on teie jaoks loonud.</span><span class="sxs-lookup"><span data-stu-id="dca16-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="dca16-113">Rikastamise konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="dca16-113">Configure the enrichment</span></span>

1. <span data-ttu-id="dca16-114">Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.</span><span class="sxs-lookup"><span data-stu-id="dca16-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="dca16-115">Valige Experiani paanilt suvand **Rikasta minu andmeid**.</span><span class="sxs-lookup"><span data-stu-id="dca16-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dca16-116">![Experiani paan](media/experian-tile.png "Experiani paan")</span><span class="sxs-lookup"><span data-stu-id="dca16-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="dca16-117">Valige ripploendist [ühendus](connections.md).</span><span class="sxs-lookup"><span data-stu-id="dca16-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="dca16-118">Kui ühendusi pole saadaval, pöörduge administraatori poole.</span><span class="sxs-lookup"><span data-stu-id="dca16-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="dca16-119">Kui olete administraator, saate ühenduse luua, valides ripploendist suvandi **Lisa ühendus** ja valides Experian.</span><span class="sxs-lookup"><span data-stu-id="dca16-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="dca16-120">Valige **Ühenda Experianiga**, et kinnitada ühenduse valik.</span><span class="sxs-lookup"><span data-stu-id="dca16-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="dca16-121">Valige **Edasi** ja valige **Kliendi andmekomplekt**, mida soovite Experian demograafiliste andmetega rikastada.</span><span class="sxs-lookup"><span data-stu-id="dca16-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="dca16-122">Saate valida olemi **Klient**, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.</span><span class="sxs-lookup"><span data-stu-id="dca16-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendiandmete kogumi valimisel.":::

1. <span data-ttu-id="dca16-124">Valige **Edasi** ja määratlege, millist tüüpi välju teie ühendatud profiilidest tuleks kasutada Experian demograafiliste andmete sobitamiseks.</span><span class="sxs-lookup"><span data-stu-id="dca16-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="dca16-125">Vähemalt üks väljadest **Nimi ja aadress**, **Telefon** või **E-post** on nõutav.</span><span class="sxs-lookup"><span data-stu-id="dca16-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="dca16-126">Suurema sobivuse täpsuse saavutamiseks saab lisada kuni kaks muud välja.</span><span class="sxs-lookup"><span data-stu-id="dca16-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="dca16-127">See valik mõjutab kaardistamisvälju, millele teil on järgmises etapis juurdepääs.</span><span class="sxs-lookup"><span data-stu-id="dca16-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="dca16-128">Rohkemate võtmeidentifikaatori atribuutide saatmine Experianile annab tõenäoliselt suurema vastavuse määra.</span><span class="sxs-lookup"><span data-stu-id="dca16-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="dca16-129">Valige **Edasi**, et alustada väljade kaardistamist.</span><span class="sxs-lookup"><span data-stu-id="dca16-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="dca16-130">Määratlege, milliseid väljad teie ühendatud profiilidest tuleks kasutada Experianist sobivate demograafiliste andmete otsimiseks.</span><span class="sxs-lookup"><span data-stu-id="dca16-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="dca16-131">Nõutud väljad on vastavalt tähistatud.</span><span class="sxs-lookup"><span data-stu-id="dca16-131">Required fields are marked.</span></span>

1. <span data-ttu-id="dca16-132">Sisestage rikastamise nimi ja väljundolemi nimi.</span><span class="sxs-lookup"><span data-stu-id="dca16-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="dca16-133">Valige **Salvesta rikastamine** pärast valikute läbivaatamist.</span><span class="sxs-lookup"><span data-stu-id="dca16-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="dca16-134">Konfigureerige ühendus Experianiga</span><span class="sxs-lookup"><span data-stu-id="dca16-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="dca16-135">Ühenduste konfigureerimiseks peate olema administraator.</span><span class="sxs-lookup"><span data-stu-id="dca16-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="dca16-136">Valige **Lisa ühendus** rikastamise konfigureerimisel *või* minge **Administraator** > **Ühendused** ja valige **Seadista** Experian paanil.</span><span class="sxs-lookup"><span data-stu-id="dca16-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="dca16-137">Seejärel valige suvand **Alustamine**.</span><span class="sxs-lookup"><span data-stu-id="dca16-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="dca16-138">Sisestage ühenduse nimi **Kuvatav nimi** väljale.</span><span class="sxs-lookup"><span data-stu-id="dca16-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="dca16-139">Sisestage oma Experian Secure Transport konto kehtiv kasutajanimi, osapoole ID ja mudeli number.</span><span class="sxs-lookup"><span data-stu-id="dca16-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="dca16-140">Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides **Nõustun** märkeruudu</span><span class="sxs-lookup"><span data-stu-id="dca16-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="dca16-141">Valige **Kontrolli** konfiguratsiooni valideerimiseks.</span><span class="sxs-lookup"><span data-stu-id="dca16-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="dca16-142">Pärast kontrollimise lõpuleviimist valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="dca16-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian ühenduse konfiguratsiooni paan.":::

## <a name="enrichment-results"></a><span data-ttu-id="dca16-144">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="dca16-144">Enrichment results</span></span>

<span data-ttu-id="dca16-145">Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="dca16-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="dca16-146">Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dca16-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dca16-147">Töötlemisaeg sõltub teie kliendiandmete mahust ja rikastamistoimingutest, mille Experian on teie konto jaoks seadistanud.</span><span class="sxs-lookup"><span data-stu-id="dca16-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="dca16-148">Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt.</span><span class="sxs-lookup"><span data-stu-id="dca16-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="dca16-149">Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="dca16-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="dca16-150">Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.</span><span class="sxs-lookup"><span data-stu-id="dca16-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dca16-151">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="dca16-151">Next steps</span></span>

<span data-ttu-id="dca16-152">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="dca16-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dca16-153">Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [Ekspordi andmed](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="dca16-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dca16-154">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="dca16-154">Data privacy and compliance</span></span>

<span data-ttu-id="dca16-155">Kui lubate Dynamics 365 Customer Insightsil Experiani andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="dca16-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dca16-156">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Experian täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="dca16-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dca16-157">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dca16-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dca16-158">Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="dca16-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
