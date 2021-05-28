---
title: Andmete eksportimine Customer Insights
description: Andmete jagamiseks hallake eksporti.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016609"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="0e812-103">Eksportimine (eelversioon) ülevaade</span><span class="sxs-lookup"><span data-stu-id="0e812-103">Exports (preview) overview</span></span>

<span data-ttu-id="0e812-104">Lehel **Ekspordid** näete kõiki konfigureeritud eksporte.</span><span class="sxs-lookup"><span data-stu-id="0e812-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="0e812-105">Ekspordid jagavad erinevate rakendustega konkreetseid andmeid.</span><span class="sxs-lookup"><span data-stu-id="0e812-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="0e812-106">Need võivad sisaldada kliendiprofiile või olemeid, skeeme ja kaardistamise üksikasju.</span><span class="sxs-lookup"><span data-stu-id="0e812-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="0e812-107">Iga ekspordi jaoks on vaja [ühendust, mille on seadistanud administraator, et hallata autentimist ja juurdepääsu](connections.md).</span><span class="sxs-lookup"><span data-stu-id="0e812-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="0e812-108">Minge **Andmed** > **Ekspordid**, et näha ekspordilehte.</span><span class="sxs-lookup"><span data-stu-id="0e812-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="0e812-109">Kõigil kasutajarollidel on juurdepääs konfigureeritud ekspordi vaatamiseks.</span><span class="sxs-lookup"><span data-stu-id="0e812-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="0e812-110">Kasutage käsuriba otsinguvälja, et leida eksport nende nime, ühenduse nime või ühenduse tüübi järgi.</span><span class="sxs-lookup"><span data-stu-id="0e812-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="0e812-111">Uue ekspordi seadistamine</span><span class="sxs-lookup"><span data-stu-id="0e812-111">Set up a new export</span></span>

<span data-ttu-id="0e812-112">Ekspordi seadistamiseks või redigeerimiseks peavad teil olema saadaval ühendused.</span><span class="sxs-lookup"><span data-stu-id="0e812-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="0e812-113">Ühendused sõltuvad teie [kasutajarollist](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="0e812-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="0e812-114">Administraatoritel on juurdepääs kõigile ühendustele.</span><span class="sxs-lookup"><span data-stu-id="0e812-114">Administrators have access to all connections.</span></span> <span data-ttu-id="0e812-115">Nad saavad ekspordi seadistamisel luua ka uusi ühendusi.</span><span class="sxs-lookup"><span data-stu-id="0e812-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="0e812-116">Kaastöötajatel on juurdepääs kindlatele ühendustele.</span><span class="sxs-lookup"><span data-stu-id="0e812-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="0e812-117">Nad sõltuvad administraatoritest, et ühendusi konfigureerida ja jagada.</span><span class="sxs-lookup"><span data-stu-id="0e812-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="0e812-118">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0e812-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="0e812-119">Vaatajad saavad vaadata ainult olemasolevaid eksporte, kuid ei loo neid.</span><span class="sxs-lookup"><span data-stu-id="0e812-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="0e812-120">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="0e812-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0e812-121">Valige uue ekspordi sihtkoha loomiseks **Lisa eksport**.</span><span class="sxs-lookup"><span data-stu-id="0e812-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="0e812-122">Valige **Ekspordi loomine** paanil ühendus, mida kasutada.</span><span class="sxs-lookup"><span data-stu-id="0e812-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="0e812-123">[Ühendusi](connections.md) haldavad administraatorid.</span><span class="sxs-lookup"><span data-stu-id="0e812-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="0e812-124">Sisestage nõutavad üksikasjad ja valige **Salvesta** eksportimise loomiseks.</span><span class="sxs-lookup"><span data-stu-id="0e812-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="0e812-125">Ekspordi redigeerimine</span><span class="sxs-lookup"><span data-stu-id="0e812-125">Edit an export</span></span>

1. <span data-ttu-id="0e812-126">Valige redigeeritava ekspordi sihtkoha vertikaalsed kolm punkti.</span><span class="sxs-lookup"><span data-stu-id="0e812-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="0e812-127">Valige ripploendist **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="0e812-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="0e812-128">Muutke värskendatavad väärtused ja valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="0e812-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="0e812-129">Ekspordi ja ekspordi üksikasjade kuvamine</span><span class="sxs-lookup"><span data-stu-id="0e812-129">View Exports and export details</span></span>

<span data-ttu-id="0e812-130">Pärast ekspordi sihtkoha loomist on need ära toodud **Andmed** > **Ekspordid** loendis.</span><span class="sxs-lookup"><span data-stu-id="0e812-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="0e812-131">Kõik kasutajad saavad vaadata, milliseid andmeid jagatud on ning nende värskeimat olekut.</span><span class="sxs-lookup"><span data-stu-id="0e812-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="0e812-132">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="0e812-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0e812-133">Redigeerimisõiguseta kasutajad valivad **Vaade** eksportimise üksikasjade vaatamiseks **Redigeeri** asemel.</span><span class="sxs-lookup"><span data-stu-id="0e812-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="0e812-134">Sellel kõrvalpaanil kuvatakse ekspordi seadistus.</span><span class="sxs-lookup"><span data-stu-id="0e812-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="0e812-135">Ilma redigeerimisõiguseta ei saa väärtusi muuta.</span><span class="sxs-lookup"><span data-stu-id="0e812-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="0e812-136">Valige **Sulge** ekspordilehele naasmiseks.</span><span class="sxs-lookup"><span data-stu-id="0e812-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="0e812-137">Käita ekspordid nõudmisel</span><span class="sxs-lookup"><span data-stu-id="0e812-137">Run exports on demand</span></span>

<span data-ttu-id="0e812-138">Pärast ekspordi konfigureerimist käitatakse see iga [kavandatud värskendusega](system.md#schedule-tab) kui on olemas töötav ühendus.</span><span class="sxs-lookup"><span data-stu-id="0e812-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="0e812-139">Andmete eksportimiseks ilma ajastatud värskendamist ootamata minge **Andmed** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="0e812-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="0e812-140">Teil on kaks varianti.</span><span class="sxs-lookup"><span data-stu-id="0e812-140">You have two options:</span></span>

- <span data-ttu-id="0e812-141">Kõigi ekspordite käivitamiseks valige **Käivita kõik** käsuribalt.</span><span class="sxs-lookup"><span data-stu-id="0e812-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="0e812-142">Üksikekspordi käivitamiseks valige loendiüksuses vertikaalsed kolm punkti (...) ja valige siis **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="0e812-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="0e812-143">Ekspordi eemaldamine</span><span class="sxs-lookup"><span data-stu-id="0e812-143">Remove an Export</span></span>

1. <span data-ttu-id="0e812-144">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="0e812-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0e812-145">Klõpsake eemaldatava ekspordi juures kolmel vertikaalsel punktil.</span><span class="sxs-lookup"><span data-stu-id="0e812-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="0e812-146">Valige rippmenüüst **Eemalda**.</span><span class="sxs-lookup"><span data-stu-id="0e812-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="0e812-147">Eemaldamise kinnitamiseks valige kinnitusekraanil **Eemalda**.</span><span class="sxs-lookup"><span data-stu-id="0e812-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
