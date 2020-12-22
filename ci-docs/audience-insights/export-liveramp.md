---
title: LiveRamp konnektor
description: Vaadake, kuidas eksportida andmeid LiveRampi.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667179"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="f1f37-103">LiveRamp&reg;i konnektor (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="f1f37-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="f1f37-104">Aktiveerige oma andmed LiveRampis, et luua ühendus üle 500 digi-, sotsiaal- ja teleökosüsteemi platvormiga.</span><span class="sxs-lookup"><span data-stu-id="f1f37-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="f1f37-105">Töötage LiveRampis oma andmetega, et sihistada, tõkestada ja isikupärastada reklaamikampaaniaid.</span><span class="sxs-lookup"><span data-stu-id="f1f37-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f1f37-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="f1f37-106">Prerequisites</span></span>

- <span data-ttu-id="f1f37-107">Selle konnektori kasutamiseks vajate LiveRampi tellimust.</span><span class="sxs-lookup"><span data-stu-id="f1f37-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="f1f37-108">Tellimuse hankimiseks võtke otse [LiveRampiga ühendust](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="f1f37-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="f1f37-109">[Lisateave LiveRampi kasutuselevõtu kohta](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="f1f37-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="f1f37-110">LiveRampiga ühendamine</span><span class="sxs-lookup"><span data-stu-id="f1f37-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="f1f37-111">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="f1f37-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f1f37-112">Valige paanil **LiveRamp** suvand **Seadista**.</span><span class="sxs-lookup"><span data-stu-id="f1f37-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="f1f37-113">Sisestage väljale **Kuvatav nimi** oma sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="f1f37-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f1f37-114">Sisestage oma LiveRampi Secure FTP (SFTP) konto **kasutajanimi** ja **parool**.</span><span class="sxs-lookup"><span data-stu-id="f1f37-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="f1f37-115">See identimisteave võib erineda teie LiveRampi kasutuselevõtu identimisteabest.</span><span class="sxs-lookup"><span data-stu-id="f1f37-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="f1f37-116">Valige suvand **Kinnita**, et testida LiveRampi ühendust.</span><span class="sxs-lookup"><span data-stu-id="f1f37-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="f1f37-117">Pärast edukat kinnitamist andke oma nõusolek **Andmete privaatsus ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="f1f37-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="f1f37-118">Valige suvand **Järgmine**, et häälestada LiveRampi konnektor.</span><span class="sxs-lookup"><span data-stu-id="f1f37-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f1f37-119">Konnektori konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="f1f37-119">Configure the connector</span></span>

1. <span data-ttu-id="f1f37-120">Valige väljal **Peamise identifikaatori valimine** kas **Meil**, **Nimi ja aadress** või **Telefon**, et saata LiveRampi identimise jaoks.</span><span class="sxs-lookup"><span data-stu-id="f1f37-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="f1f37-121">Vastendage vastavad atribuudid valitud põhiidentifikaatori ühtsest kliendiolemist.</span><span class="sxs-lookup"><span data-stu-id="f1f37-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="f1f37-122">Valige suvand **Lisa atribuut**, et vastendada LiveRampi saatmiseks täiendavaid atribuute.</span><span class="sxs-lookup"><span data-stu-id="f1f37-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="f1f37-123">Rohkemate põhiidentifikaatorite LiveRampi saatmisel on vastete määr tõenäoliselt suurem.</span><span class="sxs-lookup"><span data-stu-id="f1f37-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="f1f37-124">Valige segmendid, mida soovite LiveRampi eksportida.</span><span class="sxs-lookup"><span data-stu-id="f1f37-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="f1f37-125">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="f1f37-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f1f37-126">![LiveRampi konnektor atribuutide vastendamisega](media/export-liveramp-segments.png "LiveRampi konnektor atribuutide vastendamisega")</span><span class="sxs-lookup"><span data-stu-id="f1f37-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f1f37-127">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="f1f37-127">Export the data</span></span>

<span data-ttu-id="f1f37-128">Eksportimine algab varsti, kui kõik eksportimiseks vajalikud eeltingimused on täidetud.</span><span class="sxs-lookup"><span data-stu-id="f1f37-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="f1f37-129">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f1f37-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="f1f37-130">Pärast eksportimise lõpuleviimist saate oma andmete aktiveerimiseks ja levitamiseks LiveRampi kasutuselevõttu sisse logida.</span><span class="sxs-lookup"><span data-stu-id="f1f37-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f1f37-131">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="f1f37-131">Data privacy and compliance</span></span>

<span data-ttu-id="f1f37-132">Kui lubate Dynamics 365 Customer Insightsil Liverampi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="f1f37-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f1f37-133">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Liveramp täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="f1f37-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f1f37-134">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f1f37-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f1f37-135">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="f1f37-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>