---
title: Customer Insightsi andmete eksportimine SFTP hostidesse
description: Lugege, kuidas konfigureerida ühendust ja eksportida SFTP asukohta.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760414"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="48030-103">Segmendiloendite ja muude andmete eksportimine SFTPsse (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="48030-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="48030-104">Kliendiandmete kasutamiseks muude tootjate rakendustes eksportige need turvalise failiedastuse protokolli (SFTP) asukohta.</span><span class="sxs-lookup"><span data-stu-id="48030-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="48030-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="48030-105">Prerequisites for connection</span></span>

- <span data-ttu-id="48030-106">SFTP-hosti saadavus ja vastav identimisteave.</span><span class="sxs-lookup"><span data-stu-id="48030-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="48030-107">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="48030-107">Known limitations</span></span>

- <span data-ttu-id="48030-108">Ekspordi käitusaeg sõltub teie süsteemi jõudlusest.</span><span class="sxs-lookup"><span data-stu-id="48030-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="48030-109">Soovitame teie serveri minimaalseks konfiguratsiooniks kahte protsessori tuuma ja 1 GB mälu.</span><span class="sxs-lookup"><span data-stu-id="48030-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="48030-110">Kuni 100 miljoni kliendiprofiiliga olemite eksportimiseks võib kuluda 90 minutit, kui kasutate soovitatud minimaalset kahe protsessori tuuma ja 1 GB mäluga konfiguratsiooni.</span><span class="sxs-lookup"><span data-stu-id="48030-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="48030-111">SFTP ühenduse loomine</span><span class="sxs-lookup"><span data-stu-id="48030-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="48030-112">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="48030-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="48030-113">Valige **Lisa ühendus** ja valige **SFTP** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="48030-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="48030-114">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="48030-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="48030-115">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="48030-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="48030-116">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="48030-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="48030-117">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="48030-117">Choose who can use this connection.</span></span> <span data-ttu-id="48030-118">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="48030-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="48030-119">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="48030-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="48030-120">Sisestage oma SFTP konto jaoks **Kasutajanimi**, **Parool**, **Hostinimi** ja **Ekspordikaust**.</span><span class="sxs-lookup"><span data-stu-id="48030-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="48030-121">Valige ühenduse testimiseks **Kinnita**.</span><span class="sxs-lookup"><span data-stu-id="48030-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="48030-122">Valige, kas soovite eksportida oma andmed **Gzipped** või **Unzipped** ja **väljaeraldaja** eksporditavate failide jaoks.</span><span class="sxs-lookup"><span data-stu-id="48030-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="48030-123">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="48030-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="48030-124">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="48030-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="48030-125">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="48030-125">Configure an export</span></span>

<span data-ttu-id="48030-126">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="48030-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="48030-127">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="48030-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="48030-128">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="48030-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="48030-129">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="48030-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="48030-130">Valige **Ekspordiühendus** väljal ühendus SFTP jaotisest.</span><span class="sxs-lookup"><span data-stu-id="48030-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="48030-131">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="48030-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="48030-132">Valige olemid, nt segmendid, mida soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="48030-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="48030-133">Iga valitud olem tükeldatakse eksportimisel kuni viieks väljundfailiks.</span><span class="sxs-lookup"><span data-stu-id="48030-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="48030-134">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="48030-134">Select **Save**.</span></span>

<span data-ttu-id="48030-135">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="48030-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="48030-136">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="48030-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="48030-137">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="48030-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="48030-138">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="48030-138">Data privacy and compliance</span></span>

<span data-ttu-id="48030-139">Kui lubate Dynamics 365 Customer Insightsil SFTP kaudu andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="48030-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="48030-140">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et ekspordisihtkohad täidavad kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="48030-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="48030-141">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="48030-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="48030-142">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="48030-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
