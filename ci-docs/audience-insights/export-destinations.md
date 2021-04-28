---
title: Andmete eksportimine Customer Insights
description: Andmete jagamiseks hallake eksporti.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896138"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="66ac5-103">Eksportimine (eelversioon) ülevaade</span><span class="sxs-lookup"><span data-stu-id="66ac5-103">Exports (preview) overview</span></span>

<span data-ttu-id="66ac5-104">Lehel **Ekspordid** näete kõiki konfigureeritud eksporte.</span><span class="sxs-lookup"><span data-stu-id="66ac5-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="66ac5-105">Ekspordid jagavad erinevate rakendustega konkreetseid andmeid.</span><span class="sxs-lookup"><span data-stu-id="66ac5-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="66ac5-106">Need võivad sisaldada kliendiprofiile või olemeid, skeeme ja kaardistamise üksikasju.</span><span class="sxs-lookup"><span data-stu-id="66ac5-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="66ac5-107">Iga ekspordi jaoks on vaja [ühendust, mille on seadistanud administraator, et hallata autentimist ja juurdepääsu](connections.md).</span><span class="sxs-lookup"><span data-stu-id="66ac5-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="66ac5-108">Kuni 2021. aasta märtsini lõi eksport ühenduse vastava teenusega automaatselt.</span><span class="sxs-lookup"><span data-stu-id="66ac5-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="66ac5-109">Ekspordiks on nüüd vaja [ühendust, mille administraator on loonud ja ühiskasutusse andnud](connections.md) enne kui saate neid luua.</span><span class="sxs-lookup"><span data-stu-id="66ac5-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="66ac5-110">Minge **Andmed** > **Ekspordid**, et näha ekspordilehte.</span><span class="sxs-lookup"><span data-stu-id="66ac5-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="66ac5-111">Kõigil kasutajarollidel on juurdepääs konfigureeritud ekspordi vaatamiseks.</span><span class="sxs-lookup"><span data-stu-id="66ac5-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="66ac5-112">Kasutage käsuriba otsinguvälja, et leida eksport nende nime, ühenduse nime või ühenduse tüübi järgi.</span><span class="sxs-lookup"><span data-stu-id="66ac5-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="66ac5-113">Uue ekspordi seadistamine</span><span class="sxs-lookup"><span data-stu-id="66ac5-113">Set up a new export</span></span>

<span data-ttu-id="66ac5-114">Ekspordi seadistamiseks või redigeerimiseks peavad teil olema saadaval ühendused.</span><span class="sxs-lookup"><span data-stu-id="66ac5-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="66ac5-115">Ühendused sõltuvad teie [kasutajarollist](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="66ac5-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="66ac5-116">Administraatoritel on juurdepääs kõigile ühendustele.</span><span class="sxs-lookup"><span data-stu-id="66ac5-116">Administrators have access to all connections.</span></span> <span data-ttu-id="66ac5-117">Nad saavad ekspordi seadistamisel luua ka uusi ühendusi.</span><span class="sxs-lookup"><span data-stu-id="66ac5-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="66ac5-118">Kaastöötajatel on juurdepääs kindlatele ühendustele.</span><span class="sxs-lookup"><span data-stu-id="66ac5-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="66ac5-119">Nad sõltuvad administraatoritest, et ühendusi konfigureerida ja jagada.</span><span class="sxs-lookup"><span data-stu-id="66ac5-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="66ac5-120">Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="66ac5-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="66ac5-121">Vaatajad saavad vaadata ainult olemasolevaid eksporte, kuid ei loo neid.</span><span class="sxs-lookup"><span data-stu-id="66ac5-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="66ac5-122">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="66ac5-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="66ac5-123">Valige uue ekspordi sihtkoha loomiseks **Lisa eksport**.</span><span class="sxs-lookup"><span data-stu-id="66ac5-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="66ac5-124">Valige **Ekspordi loomine** paanil ühendus, mida kasutada.</span><span class="sxs-lookup"><span data-stu-id="66ac5-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="66ac5-125">[Ühendusi](connections.md) haldavad administraatorid.</span><span class="sxs-lookup"><span data-stu-id="66ac5-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="66ac5-126">Sisestage nõutavad üksikasjad ja valige **Salvesta** eksportimise loomiseks.</span><span class="sxs-lookup"><span data-stu-id="66ac5-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="66ac5-127">Ekspordi redigeerimine</span><span class="sxs-lookup"><span data-stu-id="66ac5-127">Edit an export</span></span>

1. <span data-ttu-id="66ac5-128">Valige redigeeritava ekspordi sihtkoha vertikaalsed kolm punkti.</span><span class="sxs-lookup"><span data-stu-id="66ac5-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="66ac5-129">Valige ripploendist **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="66ac5-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="66ac5-130">Muutke värskendatavad väärtused ja valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="66ac5-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="66ac5-131">Ekspordi ja ekspordi üksikasjade kuvamine</span><span class="sxs-lookup"><span data-stu-id="66ac5-131">View Exports and export details</span></span>

<span data-ttu-id="66ac5-132">Pärast ekspordi sihtkoha loomist on need ära toodud **Andmed** > **Ekspordid** loendis.</span><span class="sxs-lookup"><span data-stu-id="66ac5-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="66ac5-133">Kõik kasutajad saavad vaadata, milliseid andmeid jagatud on ning nende värskeimat olekut.</span><span class="sxs-lookup"><span data-stu-id="66ac5-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="66ac5-134">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="66ac5-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="66ac5-135">Redigeerimisõiguseta kasutajad valivad **Vaade** eksportimise üksikasjade vaatamiseks **Redigeeri** asemel.</span><span class="sxs-lookup"><span data-stu-id="66ac5-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="66ac5-136">Sellel kõrvalpaanil kuvatakse ekspordi seadistus.</span><span class="sxs-lookup"><span data-stu-id="66ac5-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="66ac5-137">Ilma redigeerimisõiguseta ei saa väärtusi muuta.</span><span class="sxs-lookup"><span data-stu-id="66ac5-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="66ac5-138">Valige **Sulge** ekspordilehele naasmiseks.</span><span class="sxs-lookup"><span data-stu-id="66ac5-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="66ac5-139">Käita ekspordid nõudmisel</span><span class="sxs-lookup"><span data-stu-id="66ac5-139">Run exports on demand</span></span>

<span data-ttu-id="66ac5-140">Pärast ekspordi konfigureerimist käitatakse see iga [kavandatud värskendusega](system.md#schedule-tab) kui on olemas töötav ühendus.</span><span class="sxs-lookup"><span data-stu-id="66ac5-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="66ac5-141">Andmete eksportimiseks ilma ajastatud värskendamist ootamata minge **Andmed** > **Eksport**.</span><span class="sxs-lookup"><span data-stu-id="66ac5-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="66ac5-142">Teil on kaks varianti.</span><span class="sxs-lookup"><span data-stu-id="66ac5-142">You have two options:</span></span>

- <span data-ttu-id="66ac5-143">Kõigi ekspordite käivitamiseks valige **Käivita kõik** käsuribalt.</span><span class="sxs-lookup"><span data-stu-id="66ac5-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="66ac5-144">Üksikekspordi käivitamiseks valige loendiüksuses vertikaalsed kolm punkti (...) ja valige siis **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="66ac5-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="66ac5-145">Ekspordi eemaldamine</span><span class="sxs-lookup"><span data-stu-id="66ac5-145">Remove an Export</span></span>

1. <span data-ttu-id="66ac5-146">Minge **Andmed** > **Ekspordid**.</span><span class="sxs-lookup"><span data-stu-id="66ac5-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="66ac5-147">Klõpsake eemaldatava ekspordi juures kolmel vertikaalsel punktil.</span><span class="sxs-lookup"><span data-stu-id="66ac5-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="66ac5-148">Valige rippmenüüst **Eemalda**.</span><span class="sxs-lookup"><span data-stu-id="66ac5-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="66ac5-149">Eemaldamise kinnitamiseks valige kinnitusekraanil **Eemalda**.</span><span class="sxs-lookup"><span data-stu-id="66ac5-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
