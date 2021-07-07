---
title: Customer Insights andmete eksportimine Salesforce Marketing Cloud'i
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Salesforce Marketing Cloud'i.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314600"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="def8e-103">Segmentide ja muude andmete eksportimine Salesforce Marketing Cloud'i (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="def8e-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="def8e-104">Kasutage kliendiandmeid Salesforce Marketing Cloud'is, eksportides need turvalise failiedastuse protokolli (SFTP) asukoha kaudu.</span><span class="sxs-lookup"><span data-stu-id="def8e-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="def8e-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="def8e-105">Prerequisites for connection</span></span>

- <span data-ttu-id="def8e-106">SFTP-hosti saadavus ja vastav administraatori mandaat.</span><span class="sxs-lookup"><span data-stu-id="def8e-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="def8e-107">SFTP-asukohtade seadistamine Salesforce Marketing Cloud'is</span><span class="sxs-lookup"><span data-stu-id="def8e-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="def8e-108">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="def8e-108">Known limitations</span></span>

- <span data-ttu-id="def8e-109">Ekspordi käitusaeg sõltub teie süsteemi jõudlusest.</span><span class="sxs-lookup"><span data-stu-id="def8e-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="def8e-110">Soovitame teie serveri minimaalseks konfiguratsiooniks kahte protsessori tuuma ja 1 GB mälu.</span><span class="sxs-lookup"><span data-stu-id="def8e-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="def8e-111">Kuni 100 miljoni kliendiprofiiliga olemite eksportimiseks, kasutades soovitatavat minimaalset konfiguratsiooni, võib minna 90 minutit.</span><span class="sxs-lookup"><span data-stu-id="def8e-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="def8e-112">Ühenduse loomine Salesforce Marketing Cloud'iga</span><span class="sxs-lookup"><span data-stu-id="def8e-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="def8e-113">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="def8e-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="def8e-114">Valige **Lisa ühendus** ja valige **Salesforce Marketing Cloud** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="def8e-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="def8e-115">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="def8e-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="def8e-116">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="def8e-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="def8e-117">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="def8e-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="def8e-118">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="def8e-118">Choose who can use this connection.</span></span> <span data-ttu-id="def8e-119">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="def8e-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="def8e-120">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="def8e-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="def8e-121">Sisestage oma SFTP konto jaoks **Kasutajanimi**, **Parool**, **Hostinimi** ja **Ekspordikaust**.</span><span class="sxs-lookup"><span data-stu-id="def8e-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="def8e-122">Valige ühenduse testimiseks **Kinnita**.</span><span class="sxs-lookup"><span data-stu-id="def8e-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="def8e-123">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="def8e-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="def8e-124">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="def8e-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="def8e-125">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="def8e-125">Configure an export</span></span>

<span data-ttu-id="def8e-126">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="def8e-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="def8e-127">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="def8e-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="def8e-128">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="def8e-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="def8e-129">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="def8e-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="def8e-130">Valige **Ekspordiühendus** väljal ühendus SFTP jaotisest.</span><span class="sxs-lookup"><span data-stu-id="def8e-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="def8e-131">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="def8e-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="def8e-132">Valige, kas soovite eksportida oma andmed **Gzipped** või **Unzipped** ja **väljaeraldaja** eksporditavate failide jaoks.</span><span class="sxs-lookup"><span data-stu-id="def8e-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="def8e-133">Valige olemid, nt segmendid, mida soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="def8e-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="def8e-134">Iga valitud olem tükeldatakse eksportimisel kuni viieks väljundfailiks.</span><span class="sxs-lookup"><span data-stu-id="def8e-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="def8e-135">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="def8e-135">Select **Save**.</span></span>

<span data-ttu-id="def8e-136">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="def8e-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="def8e-137">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="def8e-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="def8e-138">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="def8e-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="def8e-139">Customer Insights andmete importimine Salesforce Marketing Cloud'i SFTP asukohast</span><span class="sxs-lookup"><span data-stu-id="def8e-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="def8e-140">Looge [andmelaiendid Salesforce Marketing Cloud'is](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), et importida Customer Insights andmefail SFTP asukohast.</span><span class="sxs-lookup"><span data-stu-id="def8e-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="def8e-141">[Importige andmed SFTP asukohast](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) Salesforce Marketing Cloud andmelaiendisse.</span><span class="sxs-lookup"><span data-stu-id="def8e-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="def8e-142">Seadistage automatiseerimine andmete importimiseks andmelaienditele.</span><span class="sxs-lookup"><span data-stu-id="def8e-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="def8e-143">Lisateave [failide kukutamise automaatika ja ajastatud automaatika](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="def8e-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="def8e-144">Määratle [faili kukutamise automaatika](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) või [ajastatud automaatika](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="def8e-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="def8e-145">Siin on näide [automatiseerimine SFTP-ga](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="def8e-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="def8e-146">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="def8e-146">Data privacy and compliance</span></span>

<span data-ttu-id="def8e-147">Kui lubate Dynamics 365 Customer Insightsil SFTP kaudu andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="def8e-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="def8e-148">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et ekspordisihtkohad täidavad kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="def8e-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="def8e-149">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="def8e-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="def8e-150">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="def8e-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
