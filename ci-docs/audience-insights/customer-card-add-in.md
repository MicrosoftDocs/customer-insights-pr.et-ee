---
title: Kliendikaardi lisandmooduli installimine ja konfigureerimine
description: Kliendikaardi lisandmooduli installimine ja konfigureerimine teenuse Dynamics 365 Customer Insights jaoks.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644038"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="daa3f-103">Kliendikaardi lisandmoodul (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="daa3f-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="daa3f-104">Saate oma klientide kohta täieliku ülevaate otse Dynamics 365 rakendustes.</span><span class="sxs-lookup"><span data-stu-id="daa3f-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="daa3f-105">Saate vaadata kliendikaardi lisandmooduliga seotud demograafiat, ülevaateid ja tegevuse ajajooni.</span><span class="sxs-lookup"><span data-stu-id="daa3f-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="daa3f-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="daa3f-106">Prerequisites</span></span>

- <span data-ttu-id="daa3f-107">Dynamics 365 rakendus (nt müügikeskus või klienditeeninduskeskus), versioon 9.0 ja uuem, kus Unified Interface on lubatud.</span><span class="sxs-lookup"><span data-stu-id="daa3f-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="daa3f-108">Kliendiprofiilid, [mis on valmendatud Dynamics 365 rakendusest Common Data Service'i abil](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="daa3f-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="daa3f-109">Kliendikaardi lisandmooduli kasutajad tuleb sihtrühmaülevaadetes [lisada kasutajatena](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="daa3f-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="daa3f-110">[Konfigureeritud otsingu- ja filtrifunktsioonid](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="daa3f-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="daa3f-111">Demograafiliste andmete juhtelement: demograafilised väljad (nt vanus või sugu) on saadaval koondatud kliendiprofiilis.</span><span class="sxs-lookup"><span data-stu-id="daa3f-111">Demographic control: Demographic fields, such as age or gender are available in the unified customer profile.</span></span>
- <span data-ttu-id="daa3f-112">Rikastamise juhtelement: nõuab kliendiprofiilile aktiivsete [rikastamiste](enrichment-hub.md) rakendamist.</span><span class="sxs-lookup"><span data-stu-id="daa3f-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="daa3f-113">Ärianalüüsi juhtelement: nõuab Azure'i masinõppe ([prognoosid](predictions.md) või [kohandatud mudelid](custom-models.md)) abil genereeritud andmeid</span><span class="sxs-lookup"><span data-stu-id="daa3f-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="daa3f-114">Näitajate juhtelement: nõuab [konfigureeritud näitajaid](measures.md).</span><span class="sxs-lookup"><span data-stu-id="daa3f-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="daa3f-115">Ajaskaala juhtelement: nõuab [konfigureeritud tegevusi](activities.md).</span><span class="sxs-lookup"><span data-stu-id="daa3f-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="daa3f-116">Kliendikaardi lisandmooduli installimine</span><span class="sxs-lookup"><span data-stu-id="daa3f-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="daa3f-117">Kliendikaardi lisandmoodul on rakenduste Customer engagement lahendus Dynamics 365-s.</span><span class="sxs-lookup"><span data-stu-id="daa3f-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="daa3f-118">Lahenduse installimiseks avage AppSource ja otsige jaotist **Dynamicsi kliendikaart**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="daa3f-119">Valige [AppSource'is kliendikaardi lisandmoodul](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ja valige **Hangi kohe**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="daa3f-120">Lahenduse installimiseks võib olla vajalik rakenduse Dynamics 365 administraatori mandaadiga sisse logida.</span><span class="sxs-lookup"><span data-stu-id="daa3f-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="daa3f-121">Lahenduse installimiseks teie keskkonda võib kuluda pisut aega.</span><span class="sxs-lookup"><span data-stu-id="daa3f-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="daa3f-122">Kliendikaardi lisandmooduli konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="daa3f-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="daa3f-123">Administraatorina minge teenuses Dynamics 365 jaotisesse **Sätted** ja valige **Lahendused**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="daa3f-124">Valige link **Kuvatav nimi** lahendusele **Dynamics 365 Customer Insightsi kliendikaardi lisandmoodul (eelvaade)**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="daa3f-125">![Valige kuvatav nimi](media/select-display-name.png "Valige kuvatav nimi")</span><span class="sxs-lookup"><span data-stu-id="daa3f-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="daa3f-126">Valige **Logi sisse** ja sisestage administraatori konto mandaat, mida kasutate rakenduse Customer Insights konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="daa3f-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="daa3f-127">Kontrollige, et brauseri hüpikakende blokeerija ei blokeeriks autentimise akent, kui valite nupu **Logi sisse**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="daa3f-128">Valige keskkond, kust soovite andmeid tuua.</span><span class="sxs-lookup"><span data-stu-id="daa3f-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="daa3f-129">Määratlege, millised väljad vastendada Dynamics 365 rakenduse kirjetega.</span><span class="sxs-lookup"><span data-stu-id="daa3f-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="daa3f-130">Kontaktiga vastendamiseks valige kliendiolemi väli, mis vastab teie kontaktiolemi ID-le.</span><span class="sxs-lookup"><span data-stu-id="daa3f-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="daa3f-131">Kontoga vastendamiseks valige kliendiolemi väli, mis vastab teie kontoolemi ID-le.</span><span class="sxs-lookup"><span data-stu-id="daa3f-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="daa3f-132">![Kontakti ID väli](media/contact-id-field.png "Kontakti ID väli")</span><span class="sxs-lookup"><span data-stu-id="daa3f-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="daa3f-133">Sätete salvestamiseks valige **Salvesta konfiguratsioon**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="daa3f-134">Järgmisena peate määrama rakenduses Dynamics 365 turberollid, et kasutajad saaksid kliendikaarti kohandada ja näha.</span><span class="sxs-lookup"><span data-stu-id="daa3f-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="daa3f-135">Avage lahenduses Dynamics 365 **Sätted** > **Turvalisus** > **Kasutajad**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="daa3f-136">Valige kasutajarollide redigeerimiseks kasutajad ja valige **Halda rolle**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="daa3f-137">Määrake roll **Customer Insightsi kaardikohandaja** nendele kasutajatele, kes kohandavad kogu ettevõtte kaardil kuvatavat sisu.</span><span class="sxs-lookup"><span data-stu-id="daa3f-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="daa3f-138">Kliendikaardi juhtelementide lisamine vormidele</span><span class="sxs-lookup"><span data-stu-id="daa3f-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="daa3f-139">Kliendikaardi juhtelementide lisamiseks kontaktivormile avage lahenduses Dynamics 365 **Sätted** > **Kohandused**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="daa3f-140">Valige **Süsteemi kohandamine**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="daa3f-141">Sirvige olemi **Kontakt** juurde, laiendage see ja valige **Vormid**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="daa3f-142">Valige kontaktivorm, kuhu soovite kliendikaardi juhtelemendid lisada.</span><span class="sxs-lookup"><span data-stu-id="daa3f-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="daa3f-143">![Kontaktivormi valimine](media/contact-active-forms.png "Kontaktivormi valimine")</span><span class="sxs-lookup"><span data-stu-id="daa3f-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="daa3f-144">Juhtelemendi lisamiseks lohistage väljaredaktoris mistahes väli **Väljauurijast** sinna, kuhu soovite juhtelemendi paigutada.</span><span class="sxs-lookup"><span data-stu-id="daa3f-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="daa3f-145">Valige äsja lisatud vormi väli ja seejärel valige **Muuda atribuute**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="daa3f-146">Minge vahekaardile **Juhtelemendid** ja valige **Lisa juhtelement**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="daa3f-147">Valige üks saadaolevatest kohandatud juhtelementidest ja valige **Lisa**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="daa3f-148">**Välja atribuutide** dialoogis tühjendage märkeruut **Kuva vormil silt**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="daa3f-149">Valige juhtelemendi jaoks suvand **Veeb**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="daa3f-150">Valige rikastamise juhtelemendi jaoks, millist rikastamise tüüpi soovite kuvada, konfigureerides välja **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="daa3f-151">Peate igale rikastamise tüübile lisama eraldi rikastamise juhtelemendi.</span><span class="sxs-lookup"><span data-stu-id="daa3f-151">You need to add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="daa3f-152">Värskendatud kontaktivormi avaldamiseks valige **Salvesta** ja **Avalda**.</span><span class="sxs-lookup"><span data-stu-id="daa3f-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="daa3f-153">Minge avaldatud kontakti vormile.</span><span class="sxs-lookup"><span data-stu-id="daa3f-153">Go to the published contact form.</span></span> <span data-ttu-id="daa3f-154">Näete äsja lisatud juhtelementi.</span><span class="sxs-lookup"><span data-stu-id="daa3f-154">You'll see the newly added control.</span></span> <span data-ttu-id="daa3f-155">Võimalik, et peate esmakordsel kasutusel sisse logima.</span><span class="sxs-lookup"><span data-stu-id="daa3f-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="daa3f-156">Selleks et kohandada seda, mida soovite kohandatud juhtelemendil kuvada, valige paremas ülanurgas redigeerimise nupp.</span><span class="sxs-lookup"><span data-stu-id="daa3f-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>
