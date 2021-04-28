---
title: LiveRamp konnektor
description: Lugege, kuidas konfigureerida ühendust ja eksportida LiveRampi.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760322"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="dfc1e-103">Segmentide eksportimine LiveRamp&reg; (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="dfc1e-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="dfc1e-104">Aktiveerige oma andmed LiveRampis, et luua ühendus üle 500 platvormiga nii digitaalmeedias, sotsiaalmeedias kui ka televisioonis.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="dfc1e-105">Töötage LiveRampis oma andmetega, et sihistada, tõkestada ja isikupärastada reklaamikampaaniaid.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="dfc1e-106">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="dfc1e-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="dfc1e-107">Selle konnektori kasutamiseks vajate LiveRampi tellimust.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="dfc1e-108">Tellimuse hankimiseks võtke otse [LiveRampiga ühendust](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="dfc1e-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="dfc1e-109">[Lisateave LiveRampi kasutuselevõtu kohta](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="dfc1e-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="dfc1e-110">Ühenduse loomine LiveRampiga</span><span class="sxs-lookup"><span data-stu-id="dfc1e-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="dfc1e-111">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="dfc1e-112">Valige **Lisa ühendus** ja valige **LiveRamp** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="dfc1e-113">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="dfc1e-114">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="dfc1e-115">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="dfc1e-116">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-116">Choose who can use this connection.</span></span> <span data-ttu-id="dfc1e-117">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="dfc1e-118">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="dfc1e-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="dfc1e-119">Sisestage oma LiveRampi Secure FTP (SFTP) konto **kasutajanimi** ja **parool**.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="dfc1e-120">See identimisteave võib erineda teie LiveRampi kasutuselevõtu identimisteabest.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="dfc1e-121">Valige suvand **Kinnita**, et testida LiveRampi ühendust.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="dfc1e-122">Pärast edukat kinnitamist andke oma nõusolek **Andmete privaatsus ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="dfc1e-123">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="dfc1e-124">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="dfc1e-124">Configure an export</span></span>

<span data-ttu-id="dfc1e-125">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="dfc1e-126">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="dfc1e-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="dfc1e-127">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="dfc1e-128">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="dfc1e-129">Valige **Ekspordiühendus** väljal ühendus LiveRamp jaotisest.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="dfc1e-130">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="dfc1e-131">Valige väljal **Peamise identifikaatori valimine** kas **Meil**, **Nimi ja aadress** või **Telefon**, et saata LiveRampi identimise jaoks.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dfc1e-132">![LiveRampi konnektor atribuutide vastendamisega](media/export-liveramp-segments.png "LiveRampi konnektor atribuutide vastendamisega")</span><span class="sxs-lookup"><span data-stu-id="dfc1e-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="dfc1e-133">Vastendage vastavad atribuudid valitud põhiidentifikaatori ühtsest kliendiolemist.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="dfc1e-134">Valige **Lisa atribuut**, et kaardistada rohkem atribuute LiveRampile saatmiseks.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="dfc1e-135">Rohkemate põhiidentifikaatorite LiveRampi saatmisel on vastete määr tõenäoliselt suurem.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="dfc1e-136">Valige segmendid, mida soovite LiveRampi eksportida.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="dfc1e-137">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-137">Select **Save**.</span></span>

<span data-ttu-id="dfc1e-138">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="dfc1e-139">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dfc1e-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dfc1e-140">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="dfc1e-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dfc1e-141">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="dfc1e-141">Data privacy and compliance</span></span>

<span data-ttu-id="dfc1e-142">Kui lubate Dynamics 365 Customer Insightsil Liverampi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="dfc1e-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dfc1e-143">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Liveramp täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="dfc1e-144">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dfc1e-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dfc1e-145">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="dfc1e-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
