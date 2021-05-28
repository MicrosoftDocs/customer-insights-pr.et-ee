---
title: Rakenduse Dynamics 365 kliendikaardi lisandmoodul
description: Saate selle lisandmooduliga kuvada Dynamics 365 rakenduste sihtrühma ülevaadete andmeid.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059583"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="03d3c-103">Kliendikaardi lisandmoodul (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="03d3c-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="03d3c-104">Saate oma klientide kohta täieliku ülevaate otse Dynamics 365 rakendustes.</span><span class="sxs-lookup"><span data-stu-id="03d3c-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="03d3c-105">Kui kliendikaardi lisandmoodul on installitud toetatud Dynamics 365 rakendusse, saate valida demograafia, ülevaadete ja tegevuse ajaskaala kuvamise.</span><span class="sxs-lookup"><span data-stu-id="03d3c-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="03d3c-106">Lisandmoodul toob andmed Customer Insights -i kaudu, mõjutamata ühendatud Dynamics 365 rakenduse andmeid.</span><span class="sxs-lookup"><span data-stu-id="03d3c-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="03d3c-107">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="03d3c-107">Prerequisites</span></span>

- <span data-ttu-id="03d3c-108">Lisandmoodul töötab ainult Dynamics 365 mudelipõhiste rakendustega (nt Müük või Klienditeenindus, versioon 9.0 ja uuemad).</span><span class="sxs-lookup"><span data-stu-id="03d3c-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="03d3c-109">Et Dynamics 365 andmed vastendaks sihtrühma ülevaadetega kliendiprofiilidega, tuleb neid [Dynamics 365 rakendusest konnektori abil alla laadida Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="03d3c-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="03d3c-110">Kõik Dynamics 365 kliendikaardi lisandmooduli kasutajad peavad andmete nägemiseks olema [lisatud kasutajatena](permissions.md) publiku ülevaadetes.</span><span class="sxs-lookup"><span data-stu-id="03d3c-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="03d3c-111">[Konfigureeritud otsing ja võimekuste filtreerimine](search-filter-index.md) on publiku ülevaadetes nõutud andmete otsingu töötamise jaoks.</span><span class="sxs-lookup"><span data-stu-id="03d3c-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="03d3c-112">Iga lisandmooduli juhtelement kasutab publiku ülevaadetes teatud andmeid:</span><span class="sxs-lookup"><span data-stu-id="03d3c-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="03d3c-113">Näitajate juhtelement: nõuab [konfigureeritud näitajaid](measures.md).</span><span class="sxs-lookup"><span data-stu-id="03d3c-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="03d3c-114">Jälitusteabe juhtelement: Nõuab andmeid, mis on loodud kasutades [prognoosimist](predictions.md) või [kohandatud mudeleid](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="03d3c-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="03d3c-115">Demograafiliste andmete juhtelement: demograafilised väljad (nt vanus või sugu) on saadaval koondatud kliendiprofiilis.</span><span class="sxs-lookup"><span data-stu-id="03d3c-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="03d3c-116">Rikastamise juhtelement: nõuab kliendiprofiilile aktiivsete [rikastamiste](enrichment-hub.md) rakendamist.</span><span class="sxs-lookup"><span data-stu-id="03d3c-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="03d3c-117">Ajaskaala juhtelement: nõuab [konfigureeritud tegevusi](activities.md).</span><span class="sxs-lookup"><span data-stu-id="03d3c-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="03d3c-118">Kliendikaardi lisandmooduli installimine</span><span class="sxs-lookup"><span data-stu-id="03d3c-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="03d3c-119">Kliendikaardi lisandmoodul on rakenduste Customer engagement lahendus Dynamics 365-s.</span><span class="sxs-lookup"><span data-stu-id="03d3c-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="03d3c-120">Lahenduse installimiseks avage AppSource ja otsige jaotist **Dynamicsi kliendikaart**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="03d3c-121">Valige [AppSource'is kliendikaardi lisandmoodul](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ja valige **Hangi kohe**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="03d3c-122">Lahenduse installimiseks võib olla vajalik rakenduse Dynamics 365 administraatori mandaadiga sisse logida.</span><span class="sxs-lookup"><span data-stu-id="03d3c-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="03d3c-123">Lahenduse installimiseks teie keskkonda võib kuluda pisut aega.</span><span class="sxs-lookup"><span data-stu-id="03d3c-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="03d3c-124">Kliendikaardi lisandmooduli konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="03d3c-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="03d3c-125">Administraatorina minge teenuses Dynamics 365 jaotisesse **Sätted** ja valige **Lahendused**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="03d3c-126">Valige link **Kuvatav nimi** lahendusele **Dynamics 365 Customer Insightsi kliendikaardi lisandmoodul (eelvaade)**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03d3c-127">![Valige kuvatav nimi](media/select-display-name.png "Valige kuvatav nimi")</span><span class="sxs-lookup"><span data-stu-id="03d3c-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="03d3c-128">Valige **Logi sisse** ja sisestage administraatori konto mandaat, mida kasutate rakenduse Customer Insights konfigureerimiseks.</span><span class="sxs-lookup"><span data-stu-id="03d3c-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="03d3c-129">Kontrollige, et brauseri hüpikakende blokeerija ei blokeeriks autentimise akent, kui valite nupu **Logi sisse**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="03d3c-130">Valige Customer Insights -i keskkond, kust soovite andmeid tuua.</span><span class="sxs-lookup"><span data-stu-id="03d3c-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="03d3c-131">Määratlege väljavastendus Dynamics 365 rakenduses kirjete jaoks.</span><span class="sxs-lookup"><span data-stu-id="03d3c-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="03d3c-132">Customer Insights -i andmetest olenevalt saate valida järgmiste suvandite vastendamise:</span><span class="sxs-lookup"><span data-stu-id="03d3c-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="03d3c-133">Kontaktiga vastendamiseks valige kliendiolemi väli, mis vastab teie kontaktiolemi ID-le.</span><span class="sxs-lookup"><span data-stu-id="03d3c-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="03d3c-134">Kontoga vastendamiseks valige kliendiolemi väli, mis vastab teie kontoolemi ID-le.</span><span class="sxs-lookup"><span data-stu-id="03d3c-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="03d3c-135">![Kontakti ID väli](media/contact-id-field.png "Kontakti ID väli")</span><span class="sxs-lookup"><span data-stu-id="03d3c-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="03d3c-136">Sätete salvestamiseks valige **Salvesta konfiguratsioon**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="03d3c-137">Järgmisena peate määrama rakenduses Dynamics 365 turberollid, et kasutajad saaksid kliendikaarti kohandada ja näha.</span><span class="sxs-lookup"><span data-stu-id="03d3c-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="03d3c-138">Avage lahenduses Dynamics 365 **Sätted** > **Turvalisus** > **Kasutajad**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="03d3c-139">Valige kasutajarollide redigeerimiseks kasutajad ja valige **Halda rolle**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="03d3c-140">Määrake roll **Customer Insightsi kaardikohandaja** nendele kasutajatele, kes kohandavad kogu ettevõtte kaardil kuvatavat sisu.</span><span class="sxs-lookup"><span data-stu-id="03d3c-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="03d3c-141">Kliendikaardi juhtelementide lisamine vormidele</span><span class="sxs-lookup"><span data-stu-id="03d3c-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="03d3c-142">Kliendikaardi juhtelementide lisamiseks kontaktivormile avage lahenduses Dynamics 365 **Sätted** > **Kohandused**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="03d3c-143">Valige **Süsteemi kohandamine**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="03d3c-144">Sirvige olemi **Kontakt** juurde, laiendage see ja valige **Vormid**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="03d3c-145">Valige kontaktivorm, kuhu soovite kliendikaardi juhtelemendid lisada.</span><span class="sxs-lookup"><span data-stu-id="03d3c-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="03d3c-146">![Kontaktivormi valimine](media/contact-active-forms.png "Kontaktivormi valimine")</span><span class="sxs-lookup"><span data-stu-id="03d3c-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="03d3c-147">Juhtelemendi lisamiseks lohistage väljaredaktoris mistahes väli **Väljauurijast** sinna, kuhu soovite juhtelemendi paigutada.</span><span class="sxs-lookup"><span data-stu-id="03d3c-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="03d3c-148">Valige äsja lisatud vormi väli ja seejärel valige **Muuda atribuute**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="03d3c-149">Minge vahekaardile **Juhtelemendid** ja valige **Lisa juhtelement**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="03d3c-150">Valige üks saadaolevatest kohandatud juhtelementidest ja valige **Lisa**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="03d3c-151">**Välja atribuutide** dialoogis tühjendage märkeruut **Kuva vormil silt**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="03d3c-152">Valige juhtelemendi jaoks suvand **Veeb**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="03d3c-153">Valige rikastamise juhtelemendi jaoks, millist rikastamise tüüpi soovite kuvada, konfigureerides välja **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="03d3c-154">Lisage igale rikastamistüübile eraldi rikastamise juhtelement.</span><span class="sxs-lookup"><span data-stu-id="03d3c-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="03d3c-155">Värskendatud kontaktivormi avaldamiseks valige **Salvesta** ja **Avalda**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="03d3c-156">Minge avaldatud kontakti vormile.</span><span class="sxs-lookup"><span data-stu-id="03d3c-156">Go to the published contact form.</span></span> <span data-ttu-id="03d3c-157">Näete äsja lisatud juhtelementi.</span><span class="sxs-lookup"><span data-stu-id="03d3c-157">You'll see the newly added control.</span></span> <span data-ttu-id="03d3c-158">Võimalik, et peate esmakordsel kasutusel sisse logima.</span><span class="sxs-lookup"><span data-stu-id="03d3c-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="03d3c-159">Selleks et kohandada seda, mida soovite kohandatud juhtelemendil kuvada, valige paremas ülanurgas redigeerimise nupp.</span><span class="sxs-lookup"><span data-stu-id="03d3c-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="03d3c-160">Kliendikaardi lisandmooduli täiendamine</span><span class="sxs-lookup"><span data-stu-id="03d3c-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="03d3c-161">Kliendikaardi lisandmoodulit ei täiendata automaatselt.</span><span class="sxs-lookup"><span data-stu-id="03d3c-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="03d3c-162">Uusimale versioonile täiendamiseks järgige neid juhiseid Dynamics 365 rakenduses, kuhu on installitud lisandmoodul.</span><span class="sxs-lookup"><span data-stu-id="03d3c-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="03d3c-163">Avage Dynamics 365 rakenduse jaotises **Sätted** > **Kohandamine** ja valige **Lahendused**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="03d3c-164">Otsige lisandmoodulite tabelist **CustomerInsightsCustomerCard** ja valige see rida.</span><span class="sxs-lookup"><span data-stu-id="03d3c-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="03d3c-165">Valige tegumiribalt **Rakenda lahenduse täiendus**.</span><span class="sxs-lookup"><span data-stu-id="03d3c-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Lahenduse täiendamine Dynamics 365 rakenduste kohandamisalal":::

1. <span data-ttu-id="03d3c-167">Pärast täiendamisprotsessi käivitamist kuvatakse laadimisnäidik kuni täienduse lõpuleviimiseni.</span><span class="sxs-lookup"><span data-stu-id="03d3c-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="03d3c-168">Kui uuemat versiooni pole, kuvab täiendus tõrketeate.</span><span class="sxs-lookup"><span data-stu-id="03d3c-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
