---
title: Customer Insightsi andmete eksportimine DotDigitali
description: Lugege, kuidas konfigureerida ühendust ja eksportida DotDigitali.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759954"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="775e2-103">Segmendiloendite eksportimine DotDigitali (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="775e2-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="775e2-104">Eksportige koondatud kliendiprofiilid DotDigitali aadressiraamatutesse ning kasutage neid kampaaniate ja e-turunduse jaoks ning DotDigitali abil kliendisegmentide loomiseks.</span><span class="sxs-lookup"><span data-stu-id="775e2-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="775e2-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="775e2-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="775e2-106">Teil on [DotDigitali konto](https://dotdigital.com/) ja asjakohane administraatori identimisteave.</span><span class="sxs-lookup"><span data-stu-id="775e2-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="775e2-107">DotDigitalis on olemas aadressiraamatud ja asjakohased ID-d.</span><span class="sxs-lookup"><span data-stu-id="775e2-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="775e2-108">ID leiate URL-ist, kui valite ja avate aadressiraamatu.</span><span class="sxs-lookup"><span data-stu-id="775e2-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="775e2-109">Lisateavet leiate teemast [DotDigitali aadressiraamatud](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="775e2-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="775e2-110">Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).</span><span class="sxs-lookup"><span data-stu-id="775e2-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="775e2-111">Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="775e2-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="775e2-112">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="775e2-112">Known limitations</span></span>

- <span data-ttu-id="775e2-113">DotDigitali saab eksportida korraga kuni miljon profiili.</span><span class="sxs-lookup"><span data-stu-id="775e2-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="775e2-114">DotDigitali saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="775e2-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="775e2-115">Miljoni profiiliga segmentide eksportimiseks võib teenusepakkuja tõttu kuluda kuni kolm tundi.</span><span class="sxs-lookup"><span data-stu-id="775e2-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="775e2-116">DotDigitali eksporditavate profiilide arv sõltub DotDigitaliga sõlmitud lepingust.</span><span class="sxs-lookup"><span data-stu-id="775e2-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="775e2-117">Ühenduse loomine DotDigitaliga</span><span class="sxs-lookup"><span data-stu-id="775e2-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="775e2-118">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="775e2-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="775e2-119">Valige **Lisa ühendus** ja valige **DotDigital** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="775e2-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="775e2-120">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="775e2-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="775e2-121">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="775e2-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="775e2-122">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="775e2-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="775e2-123">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="775e2-123">Choose who can use this connection.</span></span> <span data-ttu-id="775e2-124">Kui te midagi ei tee, on vaikeväärtuseks Administraatorid.</span><span class="sxs-lookup"><span data-stu-id="775e2-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="775e2-125">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="775e2-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="775e2-126">Sisestage oma **DotDigitali kasutajanimi ja parool**.</span><span class="sxs-lookup"><span data-stu-id="775e2-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="775e2-127">Sisestage oma **[DotDigitali aadressiraamatu ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="775e2-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="775e2-128">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="775e2-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="775e2-129">Valige **Ühenda**, et käivitada ühendus DotDigitaliga.</span><span class="sxs-lookup"><span data-stu-id="775e2-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="775e2-130">Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.</span><span class="sxs-lookup"><span data-stu-id="775e2-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="775e2-131">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="775e2-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="775e2-132">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="775e2-132">Configure an export</span></span>

<span data-ttu-id="775e2-133">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="775e2-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="775e2-134">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="775e2-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="775e2-135">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="775e2-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="775e2-136">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="775e2-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="775e2-137">Valige **Ekspordiühendus** väljal ühendus DotDigital jaotisest.</span><span class="sxs-lookup"><span data-stu-id="775e2-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="775e2-138">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="775e2-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="775e2-139">Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi.</span><span class="sxs-lookup"><span data-stu-id="775e2-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="775e2-140">Korrake samu juhiseid muude valikuliste väljade puhul, nagu **Eesnimi**, **Perekonnanimi**, **Täisnimi**, **Sugu** ja **Sihtnumber**.</span><span class="sxs-lookup"><span data-stu-id="775e2-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="775e2-141">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="775e2-141">Select the segments you want to export.</span></span> <span data-ttu-id="775e2-142">DotDigitali saate eksportida kuni miljon kliendiprofiili.</span><span class="sxs-lookup"><span data-stu-id="775e2-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="775e2-143">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="775e2-143">Select **Save**.</span></span>

<span data-ttu-id="775e2-144">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="775e2-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="775e2-145">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="775e2-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="775e2-146">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="775e2-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="775e2-147">DotDigitalis leiate nüüd oma segmendid [DotDigitali aadressiraamatutest](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="775e2-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="775e2-148">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="775e2-148">Data privacy and compliance</span></span>

<span data-ttu-id="775e2-149">Kui lubate Dynamics 365 Customer Insightsil DotDigitali andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="775e2-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="775e2-150">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et DotDigital täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="775e2-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="775e2-151">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="775e2-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="775e2-152">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="775e2-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
