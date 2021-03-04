---
title: Customer Insightsi andmete eksportimine SFTP hostidesse
description: Teave selle kohta, kuidas konfigureerida ühendust SFTP hostiga.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267993"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="97483-103">SFTP konnektor (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="97483-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="97483-104">Kasutage oma kliendiandmeid kolmanda osapoole rakendustes, eksportides need turvalise failiedastuse protokolli (SFTP) hosti.</span><span class="sxs-lookup"><span data-stu-id="97483-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="97483-105">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="97483-105">Prerequisites</span></span>

- <span data-ttu-id="97483-106">SFTP-hosti saadavus ja vastav identimisteave.</span><span class="sxs-lookup"><span data-stu-id="97483-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="97483-107">Ühenduse loomine SFTP-ga</span><span class="sxs-lookup"><span data-stu-id="97483-107">Connect to SFTP</span></span>

1. <span data-ttu-id="97483-108">Avage **Haldus** > **Ekspordi sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="97483-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="97483-109">Valige jaotises **SFTP** suvand **Seadistamine**.</span><span class="sxs-lookup"><span data-stu-id="97483-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="97483-110">Sisestage väljale **Kuvatav nimi** oma sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="97483-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="97483-111">Sisestage oma SFTP konto jaoks **Kasutajanimi**, **Parool**, **Hostinimi** ja **Ekspordikaust**.</span><span class="sxs-lookup"><span data-stu-id="97483-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="97483-112">Valige ühenduse testimiseks **Kinnita**.</span><span class="sxs-lookup"><span data-stu-id="97483-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="97483-113">Pärast edukat kontrollimist valige, kas soovite eksportida oma andmed **GZIP-iks tihendatud** või **Tihendamata** kujul ja valige eksporditud failidele **väljaeraldaja**.</span><span class="sxs-lookup"><span data-stu-id="97483-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="97483-114">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="97483-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="97483-115">Ekspordi konfigureerimise alustamiseks valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="97483-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="97483-116">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="97483-116">Configure the export</span></span>

1. <span data-ttu-id="97483-117">Valige olemid, nt segmendid, mida soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="97483-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="97483-118">Igal valitud olemil on eksportimisel kuni viis väljundfaili.</span><span class="sxs-lookup"><span data-stu-id="97483-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="97483-119">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="97483-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="97483-120">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="97483-120">Export the data</span></span>

<span data-ttu-id="97483-121">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="97483-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="97483-122">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="97483-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="97483-123">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="97483-123">Known limitations</span></span>

- <span data-ttu-id="97483-124">Ekspordi käitusaeg sõltub teie süsteemi jõudlusest.</span><span class="sxs-lookup"><span data-stu-id="97483-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="97483-125">Soovitame teie serveri minimaalseks konfiguratsiooniks kahte protsessori tuuma ja 1 GB mälu.</span><span class="sxs-lookup"><span data-stu-id="97483-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="97483-126">Kuni 100 miljoni kliendiprofiiliga olemite eksportimiseks võib kuluda 90 minutit, kui kasutate soovitatud minimaalset kahe protsessori tuuma ja 1 GB mäluga konfiguratsiooni.</span><span class="sxs-lookup"><span data-stu-id="97483-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="97483-127">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="97483-127">Data privacy and compliance</span></span>

<span data-ttu-id="97483-128">Kui lubate Dynamics 365 Customer Insightsil SFTP kaudu andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="97483-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="97483-129">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et ekspordisihtkohad täidavad kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="97483-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="97483-130">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="97483-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="97483-131">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="97483-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]