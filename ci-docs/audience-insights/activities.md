---
title: Klienditegevused
description: Määratlege klienditegevusi ja vaadake neid kliendi ajaskaalal.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866402"
---
# <a name="customer-activities"></a><span data-ttu-id="62ee6-103">Klienditegevused</span><span class="sxs-lookup"><span data-stu-id="62ee6-103">Customer activities</span></span>

<span data-ttu-id="62ee6-104">Erinevatest andmeallikatest [pärinevaid klienditegevusi](data-sources.md) saate ühendada Dynamics 365 Customer Insights ajaskaala loomiseks, mis sisaldab tegevuste kronoloogilist loendit.</span><span class="sxs-lookup"><span data-stu-id="62ee6-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="62ee6-105">Lisage ajajoon Dynamics 365 rakendustesse [kliendikaardi lisandmooduli](customer-card-add-in.md) lahendusega või Power BI juhtpaneelile.</span><span class="sxs-lookup"><span data-stu-id="62ee6-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="62ee6-106">Määratle tegevus</span><span class="sxs-lookup"><span data-stu-id="62ee6-106">Define an activity</span></span>

<span data-ttu-id="62ee6-107">Teie andmeallikad võivad hõlmata mitmesugustest andmeallikatest pärinevaid tehingute ja tegevustega seotud andmeid sisaldavaid olemeid.</span><span class="sxs-lookup"><span data-stu-id="62ee6-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="62ee6-108">Tuvastage need olemid ja valige tegevused, mida soovite kliendi ajajoonel kuvada.</span><span class="sxs-lookup"><span data-stu-id="62ee6-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="62ee6-109">Valige olem, mis hõlmab teie sihttegevust või -tegevusi.</span><span class="sxs-lookup"><span data-stu-id="62ee6-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="62ee6-110">Olemil peab olema vähemalt üks **Kuupäeva** tüüpi atribuut, mis lisatakse kliendi ajajoonele ning ilma **Kuupäeva** väljata olemeid ei saa lisada.</span><span class="sxs-lookup"><span data-stu-id="62ee6-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="62ee6-111">Kui sellist olemit ei leita, siis **Lisa tegevus** funktsioon keelatakse.</span><span class="sxs-lookup"><span data-stu-id="62ee6-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="62ee6-112">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Tegevused**.</span><span class="sxs-lookup"><span data-stu-id="62ee6-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="62ee6-113">Valige **Tegevuse lisamise** protsess, et käivitada tegevuse seadistamise juhendamine.</span><span class="sxs-lookup"><span data-stu-id="62ee6-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="62ee6-114">Määrake **tegevuse andmeetapis** järgmiste väljade väärtused:</span><span class="sxs-lookup"><span data-stu-id="62ee6-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="62ee6-115">**Tegevuse nimi**: valige oma tegevuse nimi.</span><span class="sxs-lookup"><span data-stu-id="62ee6-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="62ee6-116">**Olem**: valige olem, mis sisaldab tehingu või tegevuse andmeid.</span><span class="sxs-lookup"><span data-stu-id="62ee6-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="62ee6-117">**Primaarvõti**: valige väli, milles tuvastatakse kirje kordumatult.</span><span class="sxs-lookup"><span data-stu-id="62ee6-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="62ee6-118">See ei tohiks sisaldada korduvväärtusi, tühjasid väärtusi ega puuduvaid väärtusi.</span><span class="sxs-lookup"><span data-stu-id="62ee6-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Saate seadistada tegevuse andmed nimega, olemiga ja esmase võtmega.":::

1. <span data-ttu-id="62ee6-120">Valige **Edasi** järgmise etapi juurde minemiseks.</span><span class="sxs-lookup"><span data-stu-id="62ee6-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="62ee6-121">Konfigureerige **Seosed** etapis üksikasjad, et ühendada oma tegevuseandmed vastava kliendiga.</span><span class="sxs-lookup"><span data-stu-id="62ee6-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="62ee6-122">Selle sammuga visualiseeritakse olemite vaheline ühendus.</span><span class="sxs-lookup"><span data-stu-id="62ee6-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="62ee6-123">**Esimeseks**: Teie tegevusolemi tundmatu väli, mida kasutatakse seose loomiseks teise olemiga.</span><span class="sxs-lookup"><span data-stu-id="62ee6-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="62ee6-124">**Teiseks**: Vastava lähtekliendi olem, kellega teie tegevusolem on seoses.</span><span class="sxs-lookup"><span data-stu-id="62ee6-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="62ee6-125">Saate olla seotud ainult lähtekliendi olemitega, mida kasutatakse andmete ühendamise protsessis.</span><span class="sxs-lookup"><span data-stu-id="62ee6-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="62ee6-126">**Kolmandaks**: kui selle tegevuseolemi ja valitud lähtekliendi olemi vaheline seos on juba olemas, on seose nimi kirjutuskaitstud režiimis.</span><span class="sxs-lookup"><span data-stu-id="62ee6-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="62ee6-127">Kui sellist seost pole olemas, luuakse uus seos sellel väljal teie nimega.</span><span class="sxs-lookup"><span data-stu-id="62ee6-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Olemi seose määratlemine.":::

1. <span data-ttu-id="62ee6-129">Valige **Edasi** järgmise etapi juurde minemiseks.</span><span class="sxs-lookup"><span data-stu-id="62ee6-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="62ee6-130">Valige **tegevuse ühendamise** etapis tegevussündmus ja oma tegevuse algusaeg.</span><span class="sxs-lookup"><span data-stu-id="62ee6-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="62ee6-131">**Kohustuslikud väljad**</span><span class="sxs-lookup"><span data-stu-id="62ee6-131">**Required fields**</span></span>
      1. <span data-ttu-id="62ee6-132">**Sündmustegevus**: Väli, mis on selle tegevuse sündmus</span><span class="sxs-lookup"><span data-stu-id="62ee6-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="62ee6-133">**Ajatempel**: Väli, mis tähistab teie tegevuse algusaega.</span><span class="sxs-lookup"><span data-stu-id="62ee6-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="62ee6-134">**Valikulised väljad**</span><span class="sxs-lookup"><span data-stu-id="62ee6-134">**Optional fields**</span></span>
      1. <span data-ttu-id="62ee6-135">**Lisateave**: Väli, kus on selle tegevuse jaoks oluline teave.</span><span class="sxs-lookup"><span data-stu-id="62ee6-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="62ee6-136">**Ikoon**: ikoon, mis tähistab seda tegevusetüüpi kõige paremini.</span><span class="sxs-lookup"><span data-stu-id="62ee6-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="62ee6-137">**Veebiaadress**: Väli, mis sisaldab selle tegevuse kohta teavet sisaldavat URL-i.</span><span class="sxs-lookup"><span data-stu-id="62ee6-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="62ee6-138">Näiteks tehingute süsteem, mis on selle tegevuse allikaks.</span><span class="sxs-lookup"><span data-stu-id="62ee6-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="62ee6-139">See URL võib olla andmeallika mis tahes väli või seda saab luua uue väljana Power Query teisenduse abil.</span><span class="sxs-lookup"><span data-stu-id="62ee6-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="62ee6-140">URL-i andmed talletatakse olemis *Ühendatud tegevus*, mida saab ära kasutada edaspidi kasutades [API-sid](apis.md).</span><span class="sxs-lookup"><span data-stu-id="62ee6-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Määrake klienditegevuse andmed Ühendatud tegevuse olemis.":::

1. <span data-ttu-id="62ee6-142">Järgmise etapi juurde liikumiseks klõpsake nuppu **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="62ee6-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="62ee6-143">Vvõite valida suvandi **Valmis ja ülevaade**, et salvestada tegevus tüüpiga **Muud**.</span><span class="sxs-lookup"><span data-stu-id="62ee6-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="62ee6-144">Valige etapis **Tegevuse tüüp** tegevuse tüüp ja soovi korral valige, kas soovite mõnda tegevusetüüpi semantiliselt kaardistada, et neid oleks võimalik kasutada Customer Insights muudes alades.</span><span class="sxs-lookup"><span data-stu-id="62ee6-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="62ee6-145">Praegu saab *Tellimus* & *Müügitellimuste rida* tegevustüübid pärast väljade kaardistamisega nõustumist semantiliselt kaardistada.</span><span class="sxs-lookup"><span data-stu-id="62ee6-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="62ee6-146">Kui tegevustüüp pole uue tegevuse jaoks oluline, võite kohandatud tegevustüübi jaoks valida valiku *Muu* või *Loo uus*.</span><span class="sxs-lookup"><span data-stu-id="62ee6-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="62ee6-147">Järgmise etapi juurde liikumiseks klõpsake nuppu **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="62ee6-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="62ee6-148">Kontrollige **Vaata üle** etapis oma valikuid.</span><span class="sxs-lookup"><span data-stu-id="62ee6-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="62ee6-149">Minge tagasi ükskõik millise eelmise etapi juurde ja värskendage vajadusel teavet.</span><span class="sxs-lookup"><span data-stu-id="62ee6-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Vaadake läbi tegevuse määratud väljad.":::
   
1. <span data-ttu-id="62ee6-151">Valige **Salvestage tegevus**, et muudatused rakendada ja seejärel valige **Valmis**, et minna tagasi **Andmed** > **Tegevused** juurde.</span><span class="sxs-lookup"><span data-stu-id="62ee6-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="62ee6-152">Siin näete, millised tegevused on seatud ajaskaalal kuvamiseks.</span><span class="sxs-lookup"><span data-stu-id="62ee6-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="62ee6-153">Valige **Tegevused** lehel suvand **Käita** tegevuse töötlemiseks.</span><span class="sxs-lookup"><span data-stu-id="62ee6-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="62ee6-154">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="62ee6-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="62ee6-155">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="62ee6-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="62ee6-156">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="62ee6-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="62ee6-157">Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="62ee6-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="62ee6-158">Olemasolevate tegevuste haldamine</span><span class="sxs-lookup"><span data-stu-id="62ee6-158">Manage existing activities</span></span>

<span data-ttu-id="62ee6-159">Suvandil **Andmed** > **Tegevused** saate vaadata salvestatud tegevusi ja hallata neid.</span><span class="sxs-lookup"><span data-stu-id="62ee6-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="62ee6-160">Iga tegevust tähistab rida, mis sisaldab ka lähteallika, olemi- ja tegevustüübi üksikasju.</span><span class="sxs-lookup"><span data-stu-id="62ee6-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="62ee6-161">Järgmised toimingud on saadaval tegevuse valimiseks.</span><span class="sxs-lookup"><span data-stu-id="62ee6-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="62ee6-162">**Redigeeri**: avab tegevuse seadistuse läbivaatuse etapi.</span><span class="sxs-lookup"><span data-stu-id="62ee6-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="62ee6-163">Selles etapis saate muuta kõiki praeguseid konfiguratsioone.</span><span class="sxs-lookup"><span data-stu-id="62ee6-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="62ee6-164">Pärast konfiguratsiooni muutmist valige **Salvesta tegevus** ja seejärel valige **Käivita** käsk muudatuste töötlemiseks.</span><span class="sxs-lookup"><span data-stu-id="62ee6-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="62ee6-165">**Nimeta ümber**: avab dialoogi, kuhu sisestada valitud tegevusele muu nimi.</span><span class="sxs-lookup"><span data-stu-id="62ee6-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="62ee6-166">Vajutage nuppu **Salvesta**, et muudatused rakendada.</span><span class="sxs-lookup"><span data-stu-id="62ee6-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="62ee6-167">**Kustuta**: Avab dialoogi, mis kinnitab valitud tegevuse kustutamise.</span><span class="sxs-lookup"><span data-stu-id="62ee6-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="62ee6-168">Korraga saate kustutada ka mitu tegevust, valides tegevused ja seejärel valides kustutamisikooni.</span><span class="sxs-lookup"><span data-stu-id="62ee6-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="62ee6-169">Valige käsk **Kustuta**, et kinnitada kustutamine.</span><span class="sxs-lookup"><span data-stu-id="62ee6-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
