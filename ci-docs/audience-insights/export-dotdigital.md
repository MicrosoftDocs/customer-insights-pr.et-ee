---
title: Customer Insightsi andmete eksportimine DotDigitali
description: Vaadake, kuidas konfigureerida ühendust DotDigitaliga.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269095"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="1780a-103">DotDigitali konnektor (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="1780a-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="1780a-104">Eksportige koondatud kliendiprofiilid DotDigitali aadressiraamatutesse ning kasutage neid kampaaniate ja e-turunduse jaoks ning DotDigitali abil kliendisegmentide loomiseks.</span><span class="sxs-lookup"><span data-stu-id="1780a-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="1780a-105">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="1780a-105">Prerequisites</span></span>

-   <span data-ttu-id="1780a-106">Teil on [DotDigitali konto](https://dotdigital.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="1780a-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1780a-107">DotDigitalis on olemas aadressiraamatud ja asjakohased ID-d.</span><span class="sxs-lookup"><span data-stu-id="1780a-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="1780a-108">ID leiate URL-ist, kui valite ja avate aadressiraamatu.</span><span class="sxs-lookup"><span data-stu-id="1780a-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="1780a-109">Lisateavet leiate teemast [DotDigitali aadressiraamatud](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="1780a-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="1780a-110">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1780a-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1780a-111">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="1780a-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="1780a-112">DotDigitaliga ühenduse loomine</span><span class="sxs-lookup"><span data-stu-id="1780a-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="1780a-113">Avage **Haldus** > **Ekspordi sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="1780a-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="1780a-114">Tehke jaotises **DotDigital** valik **Seadista**.</span><span class="sxs-lookup"><span data-stu-id="1780a-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="1780a-115">Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="1780a-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="DotDigitali konfigureerimise paan.":::

1. <span data-ttu-id="1780a-117">Sisestage oma **DotDigitali kasutajanimi ja parool**.</span><span class="sxs-lookup"><span data-stu-id="1780a-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="1780a-118">Sisestage oma **[DotDigitali aadressiraamatu ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="1780a-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="1780a-119">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="1780a-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1780a-120">Valige **Ühenda**, et käivitada ühendus DotDigitaliga.</span><span class="sxs-lookup"><span data-stu-id="1780a-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="1780a-121">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="1780a-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1780a-122">Ekspordi konfigureerimiseks valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="1780a-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="1780a-123">Konnektori konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="1780a-123">Configure the connector</span></span>

1. <span data-ttu-id="1780a-124">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="1780a-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1780a-125">Korrake samu juhiseid muude valikuliste väljade puhul, nagu **Eesnimi**, **Perekonnanimi**, **Täisnimi**, **Sugu** ja **Sihtnumber**.</span><span class="sxs-lookup"><span data-stu-id="1780a-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="1780a-126">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="1780a-126">Select the segments you want to export.</span></span> <span data-ttu-id="1780a-127">DotDigitali saate eksportida kuni miljon kliendiprofiili.</span><span class="sxs-lookup"><span data-stu-id="1780a-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="1780a-128">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="1780a-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="1780a-129">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="1780a-129">Export the data</span></span>

<span data-ttu-id="1780a-130">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="1780a-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="1780a-131">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1780a-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1780a-132">DotDigitalis leiate nüüd oma segmendid [DotDigitali aadressiraamatutest](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="1780a-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1780a-133">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="1780a-133">Known limitations</span></span>

- <span data-ttu-id="1780a-134">DotDigitali saab eksportida korraga kuni miljon profiili.</span><span class="sxs-lookup"><span data-stu-id="1780a-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="1780a-135">DotDigitali saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="1780a-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="1780a-136">Miljoni profiiliga segmentide eksportimiseks võib teenusepakkuja tõttu kuluda kuni kolm tundi.</span><span class="sxs-lookup"><span data-stu-id="1780a-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="1780a-137">DotDigitali eksporditavate profiilide arv sõltub DotDigitaliga sõlmitud lepingust.</span><span class="sxs-lookup"><span data-stu-id="1780a-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1780a-138">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="1780a-138">Data privacy and compliance</span></span>

<span data-ttu-id="1780a-139">Kui lubate Dynamics 365 Customer Insightsil DotDigitali andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="1780a-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1780a-140">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et DotDigital täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="1780a-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="1780a-141">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1780a-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1780a-142">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="1780a-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]