---
title: Customer Insightsi andmete eksportimine Facebooki reklaamihaldurisse
description: Lugege, kuidas konfigureerida ühendust ja eksportida Facebook Ads Manageri.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 37d25aa038ea32b98f2d1850d7b42b701292438d
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976037"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="bd2c0-103">Segmentide loendi eksportimine Facebook Ads Manageri (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="bd2c0-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="bd2c0-104">Ühtlustatud kliendiprofiilide segmentide eksport Facebooki reklaamikampaaniasse, et luua Facebooki ja Instagrami kampaaniaid.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="bd2c0-105">Ühenduse eeltingimus</span><span class="sxs-lookup"><span data-stu-id="bd2c0-105">Prerequisites for connection</span></span>

- <span data-ttu-id="bd2c0-106">Teil peab olema [**Facebook Ad konto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), mis sisaldab [**Facebook Business kontot**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="bd2c0-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="bd2c0-107">Peate olema [**Facebooki reklaamikonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) administraator.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="bd2c0-108">Teadaolevad piirangud</span><span class="sxs-lookup"><span data-stu-id="bd2c0-108">Known limitations</span></span>

- <span data-ttu-id="bd2c0-109">Facebook Ads Manageri saab eksportida korraga kuni 10 miljonit profiili.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="bd2c0-110">Facebook Ads Manager saab eksportida ainult segmente.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="bd2c0-111">Looge või värskendage kohandatud vaatajaskondi ainult Facebook *kliendiloendi* tüüpides.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="bd2c0-112">10 miljoni profiiliga segmentide eksportimine võib kesta kuni 90 minutit.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="bd2c0-113">Ühenduse loomine Facebook Ads Manageriga</span><span class="sxs-lookup"><span data-stu-id="bd2c0-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="bd2c0-114">Enne, kui kasutajad saavad luua ekspordi, peab administraator konfigureerima teenusega ühenduse ja lubama kaastöötajatel ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="bd2c0-115">Minge **Administraator** > **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bd2c0-116">Valige **Lisa ühendus** ja valige **Facebook Ads Manager** ühenduse konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="bd2c0-117">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bd2c0-118">Ühenduse nimi ja tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bd2c0-119">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bd2c0-120">Valige, kes saavad seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-120">Choose who can use this connection.</span></span> <span data-ttu-id="bd2c0-121">Kui te midagi ei tee, on vaikeväärtuseks **Administraatorid**.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="bd2c0-122">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bd2c0-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bd2c0-123">Autendi Facebook Adsiga:</span><span class="sxs-lookup"><span data-stu-id="bd2c0-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="bd2c0-124">Valige **Jätka rakendusega Facebook**, et logida oma Facebooki reklaamikampaaniasse sisse.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="bd2c0-125">Lubage õigus **ads_management** pärast Facebookiga autentimist.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="bd2c0-126">Valige **Facebooki reklaamikonto**, millega soovite töötada.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="bd2c0-127">Valige ripploendist **olemasolev kohandatud sihtrühm** või looge **uus kohandatud sihtrühm**.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="bd2c0-128">Lisateavet vt teemast [**Sihtrühmad Facebooki reklaamihalduris**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="bd2c0-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="bd2c0-129">Selle ekspordiga saate kohandatud vaatajaskondi luua või värskendada teenuses Facebook ainult tüübiga *kliendiloend*.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="bd2c0-130">Mõnel juhul näete rippmenüüs erinevat tüüpi kohandatud vaatajaskondi.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="bd2c0-131">Kui valite *kliendiloendist* erineva tüübi, toob see kaasa ebaõnnestunud ekspordi.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="bd2c0-132">Vaadake üle **Andmete privaatsus ja vastavaus** ja valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="bd2c0-133">Ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="bd2c0-134">Ekspordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="bd2c0-134">Configure an export</span></span>

<span data-ttu-id="bd2c0-135">Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bd2c0-136">Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bd2c0-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bd2c0-137">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bd2c0-138">Valige uue ekspordi loomiseks **Lisa sihtkoht**.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="bd2c0-139">Valige **Ekspordiühendus** väljal ühendus **Facebook Ads Manager** jaotisest.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="bd2c0-140">Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bd2c0-141">Suvandis **Põhiidentifikaatori välja valimine** valige **Meil**, **Nimi ja aadress** või **Telefon**, et saata Facebooki reklaamihaldurile.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="bd2c0-142">Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="bd2c0-143">Vastendage vastavad atribuudid valitud põhiidentifikaatori ühtsest kliendiolemist.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="bd2c0-144">[NÄPUNÄIDE] Parim võimalus vaste ilmnemiseks on, kui valite põhiidentifikaatoriks **Meil**.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="bd2c0-145">Täiendavate identifikaatorite lisamine võib vastendamist parandada.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="bd2c0-146">Valige **Lisa atribuut**, et kaardistada rohkem atribuute Facebook Ads Managerile saatmiseks.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="bd2c0-147">Facebook Ads Manageri atribuudid kaardistavad järgmisi kasutajasõbralikke nimesid: **FN** = **Eesnimi**, **LN** = **Perekonnanimi**, **FI** = **Esinimetäht**, **PHONE** = **Telefon**, **GEN** = **Sugu**, **DOB** = **Sünnikuupäev**, **ST** = **Osariik**, **CT** = **Linn**, **ZIP** = **Sihtnumber**, **COUNTRY** = **Riik/Regioon**</span><span class="sxs-lookup"><span data-stu-id="bd2c0-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="bd2c0-148">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="bd2c0-149">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-149">Select **Save**.</span></span>

<span data-ttu-id="bd2c0-150">Ekspordi salvestamine ei käivita eksporti kohe.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bd2c0-151">Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bd2c0-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bd2c0-152">Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bd2c0-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bd2c0-153">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="bd2c0-153">Data privacy and compliance</span></span>

<span data-ttu-id="bd2c0-154">Kui lubate Dynamics 365 Customer Insightsil Facebooki reklaamihaldurisse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="bd2c0-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bd2c0-155">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Facebook Ads täidab kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="bd2c0-156">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bd2c0-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bd2c0-157">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="bd2c0-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
