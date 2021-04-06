---
title: Customer Insightsi andmete eksportimine Facebooki reklaamihaldurisse
description: Teave selle kohta, kuidas konfigureerida ühendust Facebooki reklaamihalduriga.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596677"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="c416c-103">Facebooki reklaamihalduri konnektor (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="c416c-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="c416c-104">Ühtlustatud kliendiprofiilide segmentide eksport Facebooki reklaamikampaaniasse, et luua Facebooki ja Instagrami kampaaniaid.</span><span class="sxs-lookup"><span data-stu-id="c416c-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c416c-105">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="c416c-105">Prerequisites</span></span>

- <span data-ttu-id="c416c-106">Vajate [**Facebooki reklaamikontot**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), mis hõlmab [**Facebooki ärikontot**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="c416c-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="c416c-107">Peate olema [**Facebooki reklaamikonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) administraator.</span><span class="sxs-lookup"><span data-stu-id="c416c-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="c416c-108">Facebooki reklaamihalduriga ühenduse loomine</span><span class="sxs-lookup"><span data-stu-id="c416c-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="c416c-109">Avage **Haldus** > **Ekspordi sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="c416c-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c416c-110">Valige jaotises **Facebooki reklaamihaldur** suvand **Seadistus**.</span><span class="sxs-lookup"><span data-stu-id="c416c-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="c416c-111">Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="c416c-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c416c-112">Valige **Jätka rakendusega Facebook**, et logida oma Facebooki reklaamikampaaniasse sisse.</span><span class="sxs-lookup"><span data-stu-id="c416c-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="c416c-113">Lubage õigus **ads_management** pärast Facebookiga autentimist.</span><span class="sxs-lookup"><span data-stu-id="c416c-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="c416c-114">Valige **Facebooki reklaamikonto**, millega soovite töötada.</span><span class="sxs-lookup"><span data-stu-id="c416c-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="c416c-115">Valige ripploendist **olemasolev kohandatud sihtrühm** või looge **uus kohandatud sihtrühm**.</span><span class="sxs-lookup"><span data-stu-id="c416c-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="c416c-116">Lisateavet vt teemast [**Sihtrühmad Facebooki reklaamihalduris**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="c416c-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="c416c-117">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="c416c-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c416c-118">Ekspordi konfigureerimiseks valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="c416c-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c416c-119">Konnektori konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="c416c-119">Configure the connector</span></span>

1. <span data-ttu-id="c416c-120">Suvandis **Põhiidentifikaatori välja valimine** valige **Meil**, **Nimi ja aadress** või **Telefon**, et saata Facebooki reklaamihaldurile.</span><span class="sxs-lookup"><span data-stu-id="c416c-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="c416c-121">Vastendage vastavad atribuudid valitud põhiidentifikaatori ühtsest kliendiolemist.</span><span class="sxs-lookup"><span data-stu-id="c416c-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="c416c-122">[NÄPUNÄIDE] Parim võimalus vaste ilmnemiseks on, kui valite põhiidentifikaatoriks **Meil**.</span><span class="sxs-lookup"><span data-stu-id="c416c-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="c416c-123">Täiendavate identifikaatorite lisamine võib vastendamist parandada.</span><span class="sxs-lookup"><span data-stu-id="c416c-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="c416c-124">Valige **Lisa atribuut**, et vastendada täiendavaid atribuute, mida Facebooki reklaamihaldurile saata.</span><span class="sxs-lookup"><span data-stu-id="c416c-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="c416c-125">Facebooki reklaamihalduri atribuudid vastendavad järgmisi kasutajasõbralikke nimesid: **FN** = **eesnimi**, **LN** = **perekonnanimi**, **FI** = **esinimetäht**, **PHONE** = **telefon**, **GEN** = **sugu**, **DOB** = **sünnikuupäev**, **ST** = **osariik**, **CT** = **linn**, **ZIP** = **sihtnumber**, **COUNTRY** = **riik/regioon**</span><span class="sxs-lookup"><span data-stu-id="c416c-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="c416c-126">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="c416c-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="c416c-127">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="c416c-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c416c-128">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="c416c-128">Export the data</span></span>

<span data-ttu-id="c416c-129">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c416c-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c416c-130">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c416c-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c416c-131">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="c416c-131">Known limitations</span></span>

- <span data-ttu-id="c416c-132">Facebooki reklaamihaldurisse saab eksportida korraga kuni kümme miljonit profiili.</span><span class="sxs-lookup"><span data-stu-id="c416c-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="c416c-133">Facebooki reklaamihaldurisse saab eksportida ainult segmente</span><span class="sxs-lookup"><span data-stu-id="c416c-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="c416c-134">Kümne miljoni profiiliga segmentide eksportimine võib kesta kuni 90 minutit.</span><span class="sxs-lookup"><span data-stu-id="c416c-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c416c-135">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="c416c-135">Data privacy and compliance</span></span>

<span data-ttu-id="c416c-136">Kui lubate Dynamics 365 Customer Insightsil Facebooki reklaamihaldurisse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="c416c-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c416c-137">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Facebook Ads täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="c416c-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="c416c-138">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c416c-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c416c-139">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="c416c-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]