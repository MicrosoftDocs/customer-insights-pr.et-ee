---
title: LiveRamp konnektor
description: Vaadake, kuidas eksportida andmeid LiveRampi.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597552"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="d839a-103">LiveRamp&reg;i konnektor (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="d839a-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="d839a-104">Aktiveerige oma andmed LiveRampis, et luua ühendus üle 500 digi-, sotsiaal- ja teleökosüsteemi platvormiga.</span><span class="sxs-lookup"><span data-stu-id="d839a-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="d839a-105">Töötage LiveRampis oma andmetega, et sihistada, tõkestada ja isikupärastada reklaamikampaaniaid.</span><span class="sxs-lookup"><span data-stu-id="d839a-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d839a-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="d839a-106">Prerequisites</span></span>

- <span data-ttu-id="d839a-107">Selle konnektori kasutamiseks vajate LiveRampi tellimust.</span><span class="sxs-lookup"><span data-stu-id="d839a-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="d839a-108">Tellimuse hankimiseks võtke otse [LiveRampiga ühendust](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="d839a-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="d839a-109">[Lisateave LiveRampi kasutuselevõtu kohta](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="d839a-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="d839a-110">LiveRampiga ühendamine</span><span class="sxs-lookup"><span data-stu-id="d839a-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="d839a-111">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="d839a-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d839a-112">Valige paanil **LiveRamp** suvand **Seadista**.</span><span class="sxs-lookup"><span data-stu-id="d839a-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="d839a-113">Sisestage väljale **Kuvatav nimi** oma sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="d839a-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="d839a-114">Sisestage oma LiveRampi Secure FTP (SFTP) konto **kasutajanimi** ja **parool**.</span><span class="sxs-lookup"><span data-stu-id="d839a-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="d839a-115">See identimisteave võib erineda teie LiveRampi kasutuselevõtu identimisteabest.</span><span class="sxs-lookup"><span data-stu-id="d839a-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="d839a-116">Valige suvand **Kinnita**, et testida LiveRampi ühendust.</span><span class="sxs-lookup"><span data-stu-id="d839a-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="d839a-117">Pärast edukat kinnitamist andke oma nõusolek **Andmete privaatsus ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="d839a-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="d839a-118">Valige suvand **Järgmine**, et häälestada LiveRampi konnektor.</span><span class="sxs-lookup"><span data-stu-id="d839a-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="d839a-119">Konnektori konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="d839a-119">Configure the connector</span></span>

1. <span data-ttu-id="d839a-120">Valige väljal **Peamise identifikaatori valimine** kas **Meil**, **Nimi ja aadress** või **Telefon**, et saata LiveRampi identimise jaoks.</span><span class="sxs-lookup"><span data-stu-id="d839a-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="d839a-121">Vastendage vastavad atribuudid valitud põhiidentifikaatori ühtsest kliendiolemist.</span><span class="sxs-lookup"><span data-stu-id="d839a-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="d839a-122">Valige suvand **Lisa atribuut**, et vastendada LiveRampi saatmiseks täiendavaid atribuute.</span><span class="sxs-lookup"><span data-stu-id="d839a-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="d839a-123">Rohkemate põhiidentifikaatorite LiveRampi saatmisel on vastete määr tõenäoliselt suurem.</span><span class="sxs-lookup"><span data-stu-id="d839a-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="d839a-124">Valige segmendid, mida soovite LiveRampi eksportida.</span><span class="sxs-lookup"><span data-stu-id="d839a-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="d839a-125">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="d839a-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d839a-126">![LiveRampi konnektor atribuutide vastendamisega](media/export-liveramp-segments.png "LiveRampi konnektor atribuutide vastendamisega")</span><span class="sxs-lookup"><span data-stu-id="d839a-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d839a-127">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="d839a-127">Export the data</span></span>

<span data-ttu-id="d839a-128">Eksportimine algab varsti, kui kõik eksportimiseks vajalikud eeltingimused on täidetud.</span><span class="sxs-lookup"><span data-stu-id="d839a-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="d839a-129">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d839a-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="d839a-130">Pärast eksportimise lõpuleviimist saate oma andmete aktiveerimiseks ja levitamiseks LiveRampi kasutuselevõttu sisse logida.</span><span class="sxs-lookup"><span data-stu-id="d839a-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d839a-131">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="d839a-131">Data privacy and compliance</span></span>

<span data-ttu-id="d839a-132">Kui lubate Dynamics 365 Customer Insightsil Liverampi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="d839a-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d839a-133">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Liveramp täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="d839a-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d839a-134">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d839a-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d839a-135">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="d839a-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]