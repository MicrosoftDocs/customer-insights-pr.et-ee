---
title: Andmete eksportimine Customer Insights
description: Andmete jagamiseks hallake eksporti.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253035"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="3b408-103">Eksportimine (eelversioon) ülevaade</span><span class="sxs-lookup"><span data-stu-id="3b408-103">Exports (preview) overview</span></span>

<span data-ttu-id="3b408-104">Lehel **Ekspordid** näete kõiki konfigureeritud eksporte.</span><span class="sxs-lookup"><span data-stu-id="3b408-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="3b408-105">Ekspordid jagavad erinevate rakendustega konkreetseid andmeid.</span><span class="sxs-lookup"><span data-stu-id="3b408-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="3b408-106">Need võivad sisaldada kliendiprofiile või olemeid, skeeme ja kaardistamise üksikasju.</span><span class="sxs-lookup"><span data-stu-id="3b408-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="3b408-107">Iga ekspordi jaoks on vaja [ühendust, mille on seadistanud administraator, et hallata autentimist ja juurdepääsu](connections.md).</span><span class="sxs-lookup"><span data-stu-id="3b408-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="3b408-108">Minge **Andmed** > **Ekspordid**, et näha ekspordilehte.</span><span class="sxs-lookup"><span data-stu-id="3b408-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="3b408-109">Kõigil kasutajarollidel on juurdepääs konfigureeritud ekspordi vaatamiseks.</span><span class="sxs-lookup"><span data-stu-id="3b408-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="3b408-110">Kasutage käsuriba otsinguvälja, et leida eksport nende nime, ühenduse nime või ühenduse tüübi järgi.</span><span class="sxs-lookup"><span data-stu-id="3b408-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="3b408-111">Uue ekspordi seadistamine</span><span class="sxs-lookup"><span data-stu-id="3b408-111">Set up a new export</span></span>

<span data-ttu-id="3b408-112">Ekspordi seadistamiseks või redigeerimiseks peavad teil olema saadaval ühendused.</span><span class="sxs-lookup"><span data-stu-id="3b408-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="3b408-113">Ühendused sõltuvad teie [kasutajarollist](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="3b408-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="3b408-114">Administraatoritel on juurdepääs kõigile ühendustele.</span><span class="sxs-lookup"><span data-stu-id="3b408-114">Administrators have access to all connections.</span></span> <span data-ttu-id="3b408-115">Nad saavad ekspordi seadistamisel luua ka uusi ühendusi.</span><span class="sxs-lookup"><span data-stu-id="3b408-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="3b408-116">Kaastöötajatel on juurdepääs kindlatele ühendustele.</span><span class="sxs-lookup"><span data-stu-id="3b408-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="3b408-117">Nad sõltuvad administraatoritest, et ühendusi konfigureerida ja jagada.</span><span class="sxs-lookup"><span data-stu-id="3b408-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="3b408-118">Ekspordiloendis kuvatakse kaastöötajad, kes saavad veergu **Teie õigused** eksportimist muuta või ainult vaadata.</span><span class="sxs-lookup"><span data-stu-id="3b408-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="3b408-119">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3b408-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="3b408-120">Vaatajad saavad vaadata ainult olemasolevaid eksporte, kuid ei loo neid.</span><span class="sxs-lookup"><span data-stu-id="3b408-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="3b408-121">Uue ekspordi määratlemine</span><span class="sxs-lookup"><span data-stu-id="3b408-121">Define a new export</span></span>

1. <span data-ttu-id="3b408-122">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="3b408-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3b408-123">Uue ekspordi loomiseks valige **Lisa eksport**.</span><span class="sxs-lookup"><span data-stu-id="3b408-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="3b408-124">Valige **Ekspordi loomine** paanil ühendus, mida kasutada.</span><span class="sxs-lookup"><span data-stu-id="3b408-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="3b408-125">[Ühendusi](connections.md) haldavad administraatorid.</span><span class="sxs-lookup"><span data-stu-id="3b408-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="3b408-126">Sisestage nõutavad üksikasjad ja valige **Salvesta** eksportimise loomiseks.</span><span class="sxs-lookup"><span data-stu-id="3b408-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="3b408-127">Uue ekspordi määratlemine olemasoleva ekspordi põhjal</span><span class="sxs-lookup"><span data-stu-id="3b408-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="3b408-128">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="3b408-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3b408-129">Valige eksportide loendis eksport, mille soovite duplitseerida.</span><span class="sxs-lookup"><span data-stu-id="3b408-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="3b408-130">Valitud ekspordi üksikasjadega paani **Defineeri eksport** avamiseks valige käsuribal **Loo duplikaat**.</span><span class="sxs-lookup"><span data-stu-id="3b408-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="3b408-131">Vaadake eksportimine läbi ja kohandage seda ning valige uue ekspordi loomiseks käsk **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="3b408-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="3b408-132">Ekspordi redigeerimine</span><span class="sxs-lookup"><span data-stu-id="3b408-132">Edit an export</span></span>

1. <span data-ttu-id="3b408-133">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="3b408-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3b408-134">Valige eksportide loendis eksport, mille soovite redigeerida.</span><span class="sxs-lookup"><span data-stu-id="3b408-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="3b408-135">Valige käsuribal käsk **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="3b408-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="3b408-136">Muutke värskendatavad väärtused ja valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="3b408-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="3b408-137">Ekspordi ja ekspordi üksikasjade kuvamine</span><span class="sxs-lookup"><span data-stu-id="3b408-137">View exports and export details</span></span>

<span data-ttu-id="3b408-138">Pärast ekspordi sihtkoha loomist on need ära toodud **Andmed** > **Ekspordid** loendis.</span><span class="sxs-lookup"><span data-stu-id="3b408-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="3b408-139">Kõik kasutajad saavad vaadata, milliseid andmeid jagatud on ning nende värskeimat olekut.</span><span class="sxs-lookup"><span data-stu-id="3b408-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="3b408-140">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="3b408-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3b408-141">Redigeerimisõiguseta kasutajad valivad **Vaade** eksportimise üksikasjade vaatamiseks **Redigeeri** asemel.</span><span class="sxs-lookup"><span data-stu-id="3b408-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="3b408-142">Kõrvalpaanil kuvatakse ekspordi konfiguratsioon.</span><span class="sxs-lookup"><span data-stu-id="3b408-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="3b408-143">Ilma redigeerimisõiguseta ei saa väärtusi muuta.</span><span class="sxs-lookup"><span data-stu-id="3b408-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="3b408-144">Valige **Sulge** ekspordilehele naasmiseks.</span><span class="sxs-lookup"><span data-stu-id="3b408-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="3b408-145">Ajasta ja käivita ekspordid</span><span class="sxs-lookup"><span data-stu-id="3b408-145">Schedule and run exports</span></span>

<span data-ttu-id="3b408-146">Igal konfigureeritud ekspordil on värskendusgraafik.</span><span class="sxs-lookup"><span data-stu-id="3b408-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="3b408-147">Värskendamise ajal otsib süsteem uusi või värskendatud andmeid, mida eksporti kaasata.</span><span class="sxs-lookup"><span data-stu-id="3b408-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="3b408-148">Vaikimisi käitatakse eksport iga [kavandatud süsteemivärskenduse](system.md#schedule-tab) osana.</span><span class="sxs-lookup"><span data-stu-id="3b408-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3b408-149">Saate värskendamise ajakava kohandada või selle käsitsi eksportimise käivitamiseks välja lülitada.</span><span class="sxs-lookup"><span data-stu-id="3b408-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="3b408-150">Ekspordigraafikud sõltuvad teie keskkonna olekust.</span><span class="sxs-lookup"><span data-stu-id="3b408-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="3b408-151">Kui plaanitud eksportimisel on [sõltuvuste](system.md#refresh-policies) värskendusi juba tehtud, viib süsteem esmalt sõltuvused lõpule ja käivitab seejärel ekspordi.</span><span class="sxs-lookup"><span data-stu-id="3b408-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="3b408-152">Näete, millal eksporti viimati veerus **Värskendati**.</span><span class="sxs-lookup"><span data-stu-id="3b408-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="3b408-153">Eksportide ajastamine</span><span class="sxs-lookup"><span data-stu-id="3b408-153">Schedule exports</span></span>

<span data-ttu-id="3b408-154">Kohandatud värskendusgraafikuid saab määratleda nii üksiku ekspordi kui ka mitme ekspordi jaoks korraga.</span><span class="sxs-lookup"><span data-stu-id="3b408-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="3b408-155">Praegu määratletud ajakava on ära toodud ekspordiloendi veerus **Ajakava**.</span><span class="sxs-lookup"><span data-stu-id="3b408-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="3b408-156">Ajakava muutmise õigus on sama, mis [eksportide redigeerimise ja määratlemise](export-destinations.md#set-up-a-new-export) õigus.</span><span class="sxs-lookup"><span data-stu-id="3b408-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="3b408-157">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="3b408-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3b408-158">Valige eksport, mille soovite ajastada.</span><span class="sxs-lookup"><span data-stu-id="3b408-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="3b408-159">Valige käsuribal käsk **Ajasta**.</span><span class="sxs-lookup"><span data-stu-id="3b408-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="3b408-160">Määrake paanil **Ajasta eksportimine**, et muuta suvandi **Ajasta käivitus** väärtuseks **Sees** käitamisel automaatselt.</span><span class="sxs-lookup"><span data-stu-id="3b408-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="3b408-161">Käsitsi värskendamiseks seadke selle väärtuseks **Väljas**.</span><span class="sxs-lookup"><span data-stu-id="3b408-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="3b408-162">Valige automaatselt värskendatud ekspordi korral väärtus **Korduvus** ja määrake selle üksikasjad.</span><span class="sxs-lookup"><span data-stu-id="3b408-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="3b408-163">Määratletud aeg kehtib kõigile korduvuse eksemplaridele.</span><span class="sxs-lookup"><span data-stu-id="3b408-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="3b408-164">On aeg, mil eksport peaks käivituma värskendamisel.</span><span class="sxs-lookup"><span data-stu-id="3b408-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="3b408-165">Muudatuste rakendamiseks ja aktiveerimiseks klõpsake nuppu **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="3b408-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="3b408-166">Mitme ekspordi ajakava redigeerimisel peate tegema valiku jaotises **Säilita või kirjuta graafikud üle**.</span><span class="sxs-lookup"><span data-stu-id="3b408-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="3b408-167">**Säilitage üksikud ajakavad**. Saate säilitada valitud ekspordi jaoks varem määratletud ajakava ja ainult keelata või lubada neid.</span><span class="sxs-lookup"><span data-stu-id="3b408-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="3b408-168">**Kõigi valitud ekspordite jaoks uue ajakava määratlemine**: valitud ekspordi olemasolevate graafikute ülekirjutamine.</span><span class="sxs-lookup"><span data-stu-id="3b408-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="3b408-169">Käita ekspordid nõudmisel</span><span class="sxs-lookup"><span data-stu-id="3b408-169">Run exports on demand</span></span>

<span data-ttu-id="3b408-170">Andmete eksportimiseks ilma ajastatud värskendamist ootamata minge **Andmed** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="3b408-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="3b408-171">Kõigi ekspordite käivitamiseks valige **Käivita kõik** käsuribalt.</span><span class="sxs-lookup"><span data-stu-id="3b408-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="3b408-172">Selle toiminguga käitatakse ainult aktiivse ajakavaga eksport.</span><span class="sxs-lookup"><span data-stu-id="3b408-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="3b408-173">Ühe ekspordi käivitamiseks valige see loendist ja valige käsuribalt **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="3b408-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="3b408-174">Nii käitate eksportimist ilma aktiivse ajakavata.</span><span class="sxs-lookup"><span data-stu-id="3b408-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="3b408-175">Ekspordi eemaldamine</span><span class="sxs-lookup"><span data-stu-id="3b408-175">Remove an Export</span></span>

1. <span data-ttu-id="3b408-176">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="3b408-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3b408-177">Valige eksport, mille soovite eemaldada.</span><span class="sxs-lookup"><span data-stu-id="3b408-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="3b408-178">Valige käsuribal käsk **Eemalda**.</span><span class="sxs-lookup"><span data-stu-id="3b408-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="3b408-179">Eemaldamise kinnitamiseks valige kinnitusekraanil **Eemalda**.</span><span class="sxs-lookup"><span data-stu-id="3b408-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
