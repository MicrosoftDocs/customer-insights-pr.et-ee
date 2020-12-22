---
title: Klienditegevused
description: Määratlege klienditegevusi ja vaadake neid kliendi ajaskaalal.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667224"
---
# <a name="customer-activities"></a><span data-ttu-id="2d082-103">Klienditegevused</span><span class="sxs-lookup"><span data-stu-id="2d082-103">Customer activities</span></span>

<span data-ttu-id="2d082-104">Kombineerige [mitmesugustest andmeallikatest](data-sources.md) pärit klienditegevused Dynamics 365 Customer Insightsis, et luua kliendi ajaskaala, mis loetleb tegevused kronoloogilises järjestuses.</span><span class="sxs-lookup"><span data-stu-id="2d082-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="2d082-105">Saate kaasata ajaskaala Customer Engagementi rakendustesse Dynamics 365-s [kliendikaardi lisandmooduli](customer-card-add-in.md) või Power BI armatuurlaua kaudu.</span><span class="sxs-lookup"><span data-stu-id="2d082-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="2d082-106">Määratle tegevus</span><span class="sxs-lookup"><span data-stu-id="2d082-106">Define an activity</span></span>

<span data-ttu-id="2d082-107">Teie andmeallikad hõlmavad mitmesugustest andmeallikatest pärinevaid tehingute ja tegevustega seotud andmeid sisaldavaid olemeid.</span><span class="sxs-lookup"><span data-stu-id="2d082-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="2d082-108">Tuvastage need olemid ja valige tegevused, mida soovite kliendi ajajoonel kuvada.</span><span class="sxs-lookup"><span data-stu-id="2d082-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="2d082-109">Valige olem, mis hõlmab teie sihttegevust või -tegevusi.</span><span class="sxs-lookup"><span data-stu-id="2d082-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="2d082-110">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Tegevused**.</span><span class="sxs-lookup"><span data-stu-id="2d082-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="2d082-111">Valige **Lisa tegevus**.</span><span class="sxs-lookup"><span data-stu-id="2d082-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2d082-112">Olemil peab olema vähemalt üks **Kuupäeva** tüüpi atribuut, mis lisatakse kliendi ajajoonele ning ilma **Kuupäeva** väljata olemeid ei saa lisada.</span><span class="sxs-lookup"><span data-stu-id="2d082-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="2d082-113">Kui sellist olemit ei leita, siis **Lisa tegevus** funktsioon keelatakse.</span><span class="sxs-lookup"><span data-stu-id="2d082-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="2d082-114">Määrake paanil **Lisa tegevus** järgmiste väljade väärtused.</span><span class="sxs-lookup"><span data-stu-id="2d082-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="2d082-115">**Olem**: valige olem, mis sisaldab tehingu või tegevuse andmeid.</span><span class="sxs-lookup"><span data-stu-id="2d082-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="2d082-116">**Primaarvõti**: valige väli, milles tuvastatakse kirje kordumatult.</span><span class="sxs-lookup"><span data-stu-id="2d082-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="2d082-117">See ei tohiks sisaldada korduvväärtusi, tühjasid väärtusi ega puuduvaid väärtusi.</span><span class="sxs-lookup"><span data-stu-id="2d082-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="2d082-118">**Ajatempel**: valige väli, mis tähistab teie tegevuse algusaega.</span><span class="sxs-lookup"><span data-stu-id="2d082-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="2d082-119">**Sündmus**: valige väli, mis on tegevuse sündmus.</span><span class="sxs-lookup"><span data-stu-id="2d082-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="2d082-120">**Veebiaadress**: valige väli, mis tähistab URL-i, mis annab selle tegevuse kohta täiendavat teavet.</span><span class="sxs-lookup"><span data-stu-id="2d082-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="2d082-121">Näiteks tehingute süsteem, mis on selle tegevuse allikaks.</span><span class="sxs-lookup"><span data-stu-id="2d082-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="2d082-122">See URL võib olla andmeallika mis tahes väli või seda saab luua uue väljana Power Query teisenduse abil.</span><span class="sxs-lookup"><span data-stu-id="2d082-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="2d082-123">Need URL-i andmed salvestatakse Unified Activity olemisse, mida saab kasutada allavoolu API-de abil.</span><span class="sxs-lookup"><span data-stu-id="2d082-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="2d082-124">**Üksikasjad**: soovi korral valige väli, mis on lisatud täiendava teabena.</span><span class="sxs-lookup"><span data-stu-id="2d082-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="2d082-125">**Ikoon**: soovi korral valige tegevust tähistav ikoon.</span><span class="sxs-lookup"><span data-stu-id="2d082-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="2d082-126">**Tegevuse tüüp**: määratlege Common Data Modeli tegevuse tüübi viide, mis kirjeldab kõige paremini tegevuse semantilist määratlust.</span><span class="sxs-lookup"><span data-stu-id="2d082-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="2d082-127">Konfigureerige jaotises **Seose seadistamine** üksikasjad oma tegevuse andmete ühendamiseks vastava kliendiga.</span><span class="sxs-lookup"><span data-stu-id="2d082-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d082-128">![Olemi seose määratlemine](media/activities-entities-define.png "Olemi seose määratlemine")</span><span class="sxs-lookup"><span data-stu-id="2d082-128">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

    - <span data-ttu-id="2d082-129">**Tegevuse olemi väli**: valige oma tegevuse olemis väli, mida kasutatakse teise olemiga seose loomiseks.</span><span class="sxs-lookup"><span data-stu-id="2d082-129">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="2d082-130">**Kliendi olem**: valige vastav lähtekliendi olem, millega teie tegevuse olem siduda.</span><span class="sxs-lookup"><span data-stu-id="2d082-130">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="2d082-131">Saate seostada ainult neid lähtekliendi olemeid, mida kasutatakse andmete ühendamise protsessis.</span><span class="sxs-lookup"><span data-stu-id="2d082-131">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="2d082-132">**Kliendi olemi väli**: sellel väljal kuvatakse vastendamisel valitud lähtekliendi olemi primaarvõti.</span><span class="sxs-lookup"><span data-stu-id="2d082-132">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="2d082-133">Seda lähtekliendi olemi primaarvõtme välja kasutatakse tegevuse olemiga seose loomiseks.</span><span class="sxs-lookup"><span data-stu-id="2d082-133">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="2d082-134">**Nimi**: kui selle tegevuse olemi ja valitud lähtekliendi olemi vaheline seos on juba olemas, on seose nimi kirjutuskaitstud režiimis.</span><span class="sxs-lookup"><span data-stu-id="2d082-134">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="2d082-135">Kui sellist seost pole olemas, luuakse uus seos siin esitatud nimega.</span><span class="sxs-lookup"><span data-stu-id="2d082-135">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>

1. <span data-ttu-id="2d082-136">Vajutage nuppu **Salvesta**, et muudatused rakendada.</span><span class="sxs-lookup"><span data-stu-id="2d082-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="2d082-137">Valige lehel **Tegevused** käsk **Käita**.</span><span class="sxs-lookup"><span data-stu-id="2d082-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="2d082-138">Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types).</span><span class="sxs-lookup"><span data-stu-id="2d082-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2d082-139">Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2d082-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2d082-140">Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku.</span><span class="sxs-lookup"><span data-stu-id="2d082-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2d082-141">Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.</span><span class="sxs-lookup"><span data-stu-id="2d082-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="2d082-142">Tegevuse redigeerimine</span><span class="sxs-lookup"><span data-stu-id="2d082-142">Edit an activity</span></span>

1. <span data-ttu-id="2d082-143">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Tegevused**.</span><span class="sxs-lookup"><span data-stu-id="2d082-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="2d082-144">Valige tegevuse olem, mida soovite redigeerida, ja valige **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="2d082-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="2d082-145">Võite ka liikuda üle olemi rea ja valida ikooni **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="2d082-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="2d082-146">Klõpsake ikoonil **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="2d082-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="2d082-147">Värskendage paanis **Redigeeri tegevust** sisalduvad väärtused ja valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="2d082-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="2d082-148">Valige lehel **Tegevused** käsk **Käita**.</span><span class="sxs-lookup"><span data-stu-id="2d082-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="2d082-149">Tegevuse kustutamine</span><span class="sxs-lookup"><span data-stu-id="2d082-149">Delete an activity</span></span>

1. <span data-ttu-id="2d082-150">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Tegevused**.</span><span class="sxs-lookup"><span data-stu-id="2d082-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="2d082-151">Valige tegevuse olem, mida soovite eemaldada, ja valige **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="2d082-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="2d082-152">Võite ka liikuda üle olemi rea ja valida ikooni **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="2d082-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="2d082-153">Lisaks võite valida mitu tegevuse olemit korraga kustutamiseks.</span><span class="sxs-lookup"><span data-stu-id="2d082-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d082-154">![Olemi seose redigeerimine või kustutamine](media/activities-entities-edit-delete.png "Olemi seose redigeerimine või kustutamine")</span><span class="sxs-lookup"><span data-stu-id="2d082-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="2d082-155">Valige ikoon **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="2d082-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="2d082-156">Kinnitage, et soovite kustutada.</span><span class="sxs-lookup"><span data-stu-id="2d082-156">Confirm your deletion.</span></span>
