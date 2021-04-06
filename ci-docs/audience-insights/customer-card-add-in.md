---
title: Kliendikaardi lisandmooduli installimine ja konfigureerimine
description: Kliendikaardi lisandmooduli installimine ja konfigureerimine teenuse Dynamics 365 Customer Insights jaoks.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597322"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="9d31d-103">Kliendikaardi lisandmoodul (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="9d31d-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9d31d-104">Saate oma klientide kohta täieliku ülevaate otse Dynamics 365 rakendustes.</span><span class="sxs-lookup"><span data-stu-id="9d31d-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="9d31d-105">Saate vaadata kliendikaardi lisandmooduliga seotud demograafiat, ülevaateid ja tegevuse ajajooni.</span><span class="sxs-lookup"><span data-stu-id="9d31d-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9d31d-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="9d31d-106">Prerequisites</span></span>

- <span data-ttu-id="9d31d-107">Dynamics 365 rakendus (nt müügikeskus või klienditeeninduskeskus), versioon 9.0 ja uuem, kus Unified Interface on lubatud.</span><span class="sxs-lookup"><span data-stu-id="9d31d-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="9d31d-108">Kliendiprofiilid, [mis on valmendatud Dynamics 365 rakendusest Common Data Service'i abil](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9d31d-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="9d31d-109">Kliendikaardi lisandmooduli kasutajad tuleb sihtrühmaülevaadetes [lisada kasutajatena](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="9d31d-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="9d31d-110">[Konfigureeritud otsingu- ja filtrifunktsioonid](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="9d31d-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="9d31d-111">Demograafiliste andmete juhtelement: demograafilised väljad (nt vanus või sugu) on saadaval koondatud kliendiprofiilis.</span><span class="sxs-lookup"><span data-stu-id="9d31d-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="9d31d-112">Rikastamise juhtelement: nõuab kliendiprofiilile aktiivsete [rikastamiste](enrichment-hub.md) rakendamist.</span><span class="sxs-lookup"><span data-stu-id="9d31d-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="9d31d-113">Ärianalüüsi juhtelement: nõuab Azure'i masinõppe ([prognoosid](predictions.md) või [kohandatud mudelid](custom-models.md)) abil genereeritud andmeid</span><span class="sxs-lookup"><span data-stu-id="9d31d-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="9d31d-114">Näitajate juhtelement: nõuab [konfigureeritud näitajaid](measures.md).</span><span class="sxs-lookup"><span data-stu-id="9d31d-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="9d31d-115">Ajaskaala juhtelement: nõuab [konfigureeritud tegevusi](activities.md).</span><span class="sxs-lookup"><span data-stu-id="9d31d-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="9d31d-116">Kliendikaardi lisandmooduli installimine</span><span class="sxs-lookup"><span data-stu-id="9d31d-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="9d31d-117">Kliendikaardi lisandmoodul on rakenduste Customer engagement lahendus Dynamics 365-s.</span><span class="sxs-lookup"><span data-stu-id="9d31d-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="9d31d-118">Lahenduse installimiseks avage AppSource ja otsige jaotist **Dynamicsi kliendikaart**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="9d31d-119">Valige [AppSource'is kliendikaardi lisandmoodul](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ja valige **Hangi kohe**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="9d31d-120">Lahenduse installimiseks võib olla vajalik rakenduse Dynamics 365 administraatori mandaadiga sisse logida.</span><span class="sxs-lookup"><span data-stu-id="9d31d-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="9d31d-121">Lahenduse installimiseks teie keskkonda võib kuluda pisut aega.</span><span class="sxs-lookup"><span data-stu-id="9d31d-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="9d31d-122">Kliendikaardi lisandmooduli konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="9d31d-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="9d31d-123">Administraatorina minge teenuses Dynamics 365 jaotisesse **Sätted** ja valige **Lahendused**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="9d31d-124">Valige link **Kuvatav nimi** lahendusele **Dynamics 365 Customer Insightsi kliendikaardi lisandmoodul (eelvaade)**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9d31d-125">![Valige kuvatav nimi](media/select-display-name.png "Valige kuvatav nimi")</span><span class="sxs-lookup"><span data-stu-id="9d31d-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="9d31d-126">Valige **Logi sisse** ja sisestage administraatori konto mandaat, mida kasutate rakenduse Customer Insights konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="9d31d-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9d31d-127">Kontrollige, et brauseri hüpikakende blokeerija ei blokeeriks autentimise akent, kui valite nupu **Logi sisse**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="9d31d-128">Valige keskkond, kust soovite andmeid tuua.</span><span class="sxs-lookup"><span data-stu-id="9d31d-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="9d31d-129">Määratlege, millised väljad vastendada Dynamics 365 rakenduse kirjetega.</span><span class="sxs-lookup"><span data-stu-id="9d31d-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="9d31d-130">Kontaktiga vastendamiseks valige kliendiolemi väli, mis vastab teie kontaktiolemi ID-le.</span><span class="sxs-lookup"><span data-stu-id="9d31d-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="9d31d-131">Kontoga vastendamiseks valige kliendiolemi väli, mis vastab teie kontoolemi ID-le.</span><span class="sxs-lookup"><span data-stu-id="9d31d-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9d31d-132">![Kontakti ID väli](media/contact-id-field.png "Kontakti ID väli")</span><span class="sxs-lookup"><span data-stu-id="9d31d-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="9d31d-133">Sätete salvestamiseks valige **Salvesta konfiguratsioon**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="9d31d-134">Järgmisena peate määrama rakenduses Dynamics 365 turberollid, et kasutajad saaksid kliendikaarti kohandada ja näha.</span><span class="sxs-lookup"><span data-stu-id="9d31d-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="9d31d-135">Avage lahenduses Dynamics 365 **Sätted** > **Turvalisus** > **Kasutajad**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="9d31d-136">Valige kasutajarollide redigeerimiseks kasutajad ja valige **Halda rolle**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="9d31d-137">Määrake roll **Customer Insightsi kaardikohandaja** nendele kasutajatele, kes kohandavad kogu ettevõtte kaardil kuvatavat sisu.</span><span class="sxs-lookup"><span data-stu-id="9d31d-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="9d31d-138">Kliendikaardi juhtelementide lisamine vormidele</span><span class="sxs-lookup"><span data-stu-id="9d31d-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="9d31d-139">Kliendikaardi juhtelementide lisamiseks kontaktivormile avage lahenduses Dynamics 365 **Sätted** > **Kohandused**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="9d31d-140">Valige **Süsteemi kohandamine**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="9d31d-141">Sirvige olemi **Kontakt** juurde, laiendage see ja valige **Vormid**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="9d31d-142">Valige kontaktivorm, kuhu soovite kliendikaardi juhtelemendid lisada.</span><span class="sxs-lookup"><span data-stu-id="9d31d-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9d31d-143">![Kontaktivormi valimine](media/contact-active-forms.png "Kontaktivormi valimine")</span><span class="sxs-lookup"><span data-stu-id="9d31d-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="9d31d-144">Juhtelemendi lisamiseks lohistage väljaredaktoris mistahes väli **Väljauurijast** sinna, kuhu soovite juhtelemendi paigutada.</span><span class="sxs-lookup"><span data-stu-id="9d31d-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="9d31d-145">Valige äsja lisatud vormi väli ja seejärel valige **Muuda atribuute**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="9d31d-146">Minge vahekaardile **Juhtelemendid** ja valige **Lisa juhtelement**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="9d31d-147">Valige üks saadaolevatest kohandatud juhtelementidest ja valige **Lisa**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="9d31d-148">**Välja atribuutide** dialoogis tühjendage märkeruut **Kuva vormil silt**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="9d31d-149">Valige juhtelemendi jaoks suvand **Veeb**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="9d31d-150">Valige rikastamise juhtelemendi jaoks, millist rikastamise tüüpi soovite kuvada, konfigureerides välja **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="9d31d-151">Lisage igale rikastamistüübile eraldi rikastamise juhtelement.</span><span class="sxs-lookup"><span data-stu-id="9d31d-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="9d31d-152">Värskendatud kontaktivormi avaldamiseks valige **Salvesta** ja **Avalda**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="9d31d-153">Minge avaldatud kontakti vormile.</span><span class="sxs-lookup"><span data-stu-id="9d31d-153">Go to the published contact form.</span></span> <span data-ttu-id="9d31d-154">Näete äsja lisatud juhtelementi.</span><span class="sxs-lookup"><span data-stu-id="9d31d-154">You'll see the newly added control.</span></span> <span data-ttu-id="9d31d-155">Võimalik, et peate esmakordsel kasutusel sisse logima.</span><span class="sxs-lookup"><span data-stu-id="9d31d-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="9d31d-156">Selleks et kohandada seda, mida soovite kohandatud juhtelemendil kuvada, valige paremas ülanurgas redigeerimise nupp.</span><span class="sxs-lookup"><span data-stu-id="9d31d-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="9d31d-157">Kliendikaardi lisandmooduli täiendamine</span><span class="sxs-lookup"><span data-stu-id="9d31d-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="9d31d-158">Kliendikaardi lisandmoodulit ei täiendata automaatselt.</span><span class="sxs-lookup"><span data-stu-id="9d31d-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="9d31d-159">Uusimale versioonile täiendamiseks järgige neid juhiseid Dynamics 365 rakenduses, kuhu on installitud lisandmoodul.</span><span class="sxs-lookup"><span data-stu-id="9d31d-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="9d31d-160">Avage Dynamics 365 rakenduse jaotises **Sätted** > **Kohandamine** ja valige **Lahendused**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="9d31d-161">Otsige lisandmoodulite tabelist **CustomerInsightsCustomerCard** ja valige see rida.</span><span class="sxs-lookup"><span data-stu-id="9d31d-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="9d31d-162">Valige tegumiribalt **Rakenda lahenduse täiendus**.</span><span class="sxs-lookup"><span data-stu-id="9d31d-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Lahenduse täiendamine Dynamics 365 rakenduste kohandamisalal":::

1. <span data-ttu-id="9d31d-164">Pärast täiendamisprotsessi käivitamist kuvatakse laadimisnäidik kuni täienduse lõpuleviimiseni.</span><span class="sxs-lookup"><span data-stu-id="9d31d-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="9d31d-165">Kui uuemat versiooni pole, kuvab täiendus tõrketeate.</span><span class="sxs-lookup"><span data-stu-id="9d31d-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]