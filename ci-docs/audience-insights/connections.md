---
title: Ühendused muude teenustega Customer Insights kaudu.
description: Andmete jagamine muude teenustega.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896092"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="c5f04-103">Ühenduste (eelversioon) ülevaade</span><span class="sxs-lookup"><span data-stu-id="c5f04-103">Connections (preview) overview</span></span>

<span data-ttu-id="c5f04-104">Ühendused on võti andmete jagamise lubamiseks Customer Insights kaudu.</span><span class="sxs-lookup"><span data-stu-id="c5f04-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="c5f04-105">Iga ühendus loob andmete jagamise konkreetse teenusega.</span><span class="sxs-lookup"><span data-stu-id="c5f04-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="c5f04-106">Ühendused on aluseks [kolmanda osapoole rikastamise konfigureerimiseks](enrichment-hub.md) ja [ekspordi konfigureerimiseks](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c5f04-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="c5f04-107">Sama ühendust saab kasutada mitmeid kordi.</span><span class="sxs-lookup"><span data-stu-id="c5f04-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="c5f04-108">Näiteks üks ühendus Dynamics 365 Marketing'iga töötab mitme ekspordi jaoks ja ühe Leadspace ühenduse abil saab kasutada mitut rikastamist.</span><span class="sxs-lookup"><span data-stu-id="c5f04-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="c5f04-109">Minge **Administraator** > **Ühendused**, et luua ja vaadata ühendusi.</span><span class="sxs-lookup"><span data-stu-id="c5f04-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="c5f04-110">Vahekaardil **Ühendused** kuvatakse kõik aktiivsed ühendused.</span><span class="sxs-lookup"><span data-stu-id="c5f04-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="c5f04-111">Loendis kuvatakse rida iga ühenduse jaoks.</span><span class="sxs-lookup"><span data-stu-id="c5f04-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="c5f04-112">Vaadake vahekaardil **Avastamine** kiirülevaadet, kirjeldust ja saate teada, mida iga laiendatavuse suvandiga teha.</span><span class="sxs-lookup"><span data-stu-id="c5f04-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="c5f04-113">Eksportimised</span><span class="sxs-lookup"><span data-stu-id="c5f04-113">Exports</span></span>

<span data-ttu-id="c5f04-114">Uusi ühendusi saavad konfigureerida ainult administraatorid, kuid nad saavad anda kaastöötajatele juurdepääsu olemasolevate ühenduste kasutamiseks.</span><span class="sxs-lookup"><span data-stu-id="c5f04-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="c5f04-115">Administraatorid määravad, kuhu andmed võivad minna, kaastöötajad määratlevad koormuse ja sageduse, mis nende vajadustele vastab.</span><span class="sxs-lookup"><span data-stu-id="c5f04-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="c5f04-116">Lisateavet leiate teemast [Luba toetajatel kasutada ühendust ekspordi jaoks](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c5f04-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="c5f04-117">Rikastamised</span><span class="sxs-lookup"><span data-stu-id="c5f04-117">Enrichments</span></span>

<span data-ttu-id="c5f04-118">Uusi ühendusi saavad konfigureerida ainult administraatorid, kuid loodud ühendused on alati saadaval nii administraatoritele kui ka kaastöötajatele.</span><span class="sxs-lookup"><span data-stu-id="c5f04-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="c5f04-119">Administraatorid haldavad volitusi ja nõustuvad andmete edastamisega.</span><span class="sxs-lookup"><span data-stu-id="c5f04-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="c5f04-120">Ühendusi saavad seejärel kasutada rikastamiseks nii administraatorid kui ka kaastöötajad.</span><span class="sxs-lookup"><span data-stu-id="c5f04-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="c5f04-121">Uue ühenduse lisamine</span><span class="sxs-lookup"><span data-stu-id="c5f04-121">Add a new connection</span></span>

<span data-ttu-id="c5f04-122">Ühenduste lisamiseks peavad teil olema [administraatoriõigused](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c5f04-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="c5f04-123">Kui loote ühenduse muude Microsofti teenustega, siis eeldame, et mõlemad teenused on samas organisatsioonis.</span><span class="sxs-lookup"><span data-stu-id="c5f04-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="c5f04-124">Minge **Administraator** > **Ühendused (eelversioon)**.</span><span class="sxs-lookup"><span data-stu-id="c5f04-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="c5f04-125">Avage vahekaart **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="c5f04-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="c5f04-126">Valige uue ühenduse loomiseks **Lisa ühendus**.</span><span class="sxs-lookup"><span data-stu-id="c5f04-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="c5f04-127">Valige ripploendist, millist tüüpi ühendust te soovite luua.</span><span class="sxs-lookup"><span data-stu-id="c5f04-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="c5f04-128">Sisestage **Loo ühendus** seadistuse paanil nõutavad üksikasjad.</span><span class="sxs-lookup"><span data-stu-id="c5f04-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="c5f04-129">**Kuva nimi** ja ühenduse tüüp kirjeldavad ühendust.</span><span class="sxs-lookup"><span data-stu-id="c5f04-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="c5f04-130">Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.</span><span class="sxs-lookup"><span data-stu-id="c5f04-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="c5f04-131">Täpsed väljad sõltuvad teenusest, millega loote ühenduse.</span><span class="sxs-lookup"><span data-stu-id="c5f04-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="c5f04-132">Saate teavet konkreetse ühendusetüübi kohta sihtteenuse artklis.</span><span class="sxs-lookup"><span data-stu-id="c5f04-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="c5f04-133">Uue ühenduse loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="c5f04-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="c5f04-134">Samuti saate valida vahekaardi **Tuvastamine** paanil suvandi **Häälestamine**.</span><span class="sxs-lookup"><span data-stu-id="c5f04-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="c5f04-135">Luba kaastöötajatel kasutada ühendust ekspordi jaoks</span><span class="sxs-lookup"><span data-stu-id="c5f04-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="c5f04-136">Ekspordiühenduse seadistamisel või redigeerimisel saate valida, millistel kasutajatel on lubatud kasutada seda kindlat ühendust [ekspordi](export-destinations.md)määratlemiseks.</span><span class="sxs-lookup"><span data-stu-id="c5f04-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="c5f04-137">Vaikimisi on ühendus saadaval administraatorirollis kasutajatele.</span><span class="sxs-lookup"><span data-stu-id="c5f04-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="c5f04-138">Saate seda sätet muuta jaotises **Valige, kes saab seda ühendust kasutada** ja lubada kaastöötaja rollis kasutajatel seda ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="c5f04-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="c5f04-139">Kaastöötajad ei saa ühendust vaadata ega redigeerida.</span><span class="sxs-lookup"><span data-stu-id="c5f04-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="c5f04-140">Nad näevad ekspordi loomisel ainult kuvatavat nime ja selle tüüpi.</span><span class="sxs-lookup"><span data-stu-id="c5f04-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="c5f04-141">Ühenduse jagamisel lubate kaastöötajatel ühendust kasutada.</span><span class="sxs-lookup"><span data-stu-id="c5f04-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="c5f04-142">Kaastöötajad näevad ekspordi seadistamisel ühisühendusi.</span><span class="sxs-lookup"><span data-stu-id="c5f04-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="c5f04-143">Nad saavad hallata igat eksporti, mis kasutab seda kindlat ühendust.</span><span class="sxs-lookup"><span data-stu-id="c5f04-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="c5f04-144">Saate seda sätet muuta, hoides ekspordi alles, mille kaastöötajad on juba määratlenud.</span><span class="sxs-lookup"><span data-stu-id="c5f04-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="c5f04-145">Ühenduse redigeerimine</span><span class="sxs-lookup"><span data-stu-id="c5f04-145">Edit a connection</span></span>

1. <span data-ttu-id="c5f04-146">Minge **Administraator** > **Ühendused (eelversioon)**.</span><span class="sxs-lookup"><span data-stu-id="c5f04-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="c5f04-147">Avage vahekaart **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="c5f04-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="c5f04-148">Valige redigeeritava ühenduse jaoks vertikaalne ellips.</span><span class="sxs-lookup"><span data-stu-id="c5f04-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="c5f04-149">Valige **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="c5f04-149">Select **Edit**.</span></span>

1. <span data-ttu-id="c5f04-150">Muutke värskendatavad väärtused ja valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="c5f04-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="c5f04-151">Eemaldage ühendus</span><span class="sxs-lookup"><span data-stu-id="c5f04-151">Remove a connection</span></span>

<span data-ttu-id="c5f04-152">Kui eemaldatav ühendus on kasutusel rikastamise või ekspordi puhul, peate need esmalt lahti võtma või eemaldama.</span><span class="sxs-lookup"><span data-stu-id="c5f04-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="c5f04-153">Eemaldamise dialoog juhendab teid vastavalt rikastamise või eksportimise osas.</span><span class="sxs-lookup"><span data-stu-id="c5f04-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="c5f04-154">Eraldatud rikastamine ja eksport muutuvad passiivseks.</span><span class="sxs-lookup"><span data-stu-id="c5f04-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="c5f04-155">Aktiveerite need uuesti, lisades neile teise ühenduse [Rikastamised](enrichment-hub.md) või [Ekspordid](export-destinations.md) lehel.</span><span class="sxs-lookup"><span data-stu-id="c5f04-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="c5f04-156">Minge **Administraator** > **Ühendused (eelversioon)**.</span><span class="sxs-lookup"><span data-stu-id="c5f04-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="c5f04-157">Avage vahekaart **Ühendused**.</span><span class="sxs-lookup"><span data-stu-id="c5f04-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="c5f04-158">Valige eemaldatava ühenduse jaoks vertikaalne ellips.</span><span class="sxs-lookup"><span data-stu-id="c5f04-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="c5f04-159">Valige rippmenüüst **Eemalda**.</span><span class="sxs-lookup"><span data-stu-id="c5f04-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="c5f04-160">Ilmub kinnituse dialoog.</span><span class="sxs-lookup"><span data-stu-id="c5f04-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="c5f04-161">Kui seda ühendust kasutatakse rikastamiseks või eksportimiseks, valige nupp, et näha, mis seda ühendust kasutab.</span><span class="sxs-lookup"><span data-stu-id="c5f04-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="c5f04-162">**Eksport:** Ühenduse eemaldamiseks saate ekspordi eemaldada või katkestada.</span><span class="sxs-lookup"><span data-stu-id="c5f04-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="c5f04-163">Ekspordi katkestamiseks saavad administraatorid kasutada **Katkesta** toimingut.</span><span class="sxs-lookup"><span data-stu-id="c5f04-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="c5f04-164">See toiming on saadaval nii üksik- kui ka mitme ekspordi jaoks.</span><span class="sxs-lookup"><span data-stu-id="c5f04-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="c5f04-165">Ühenduse katkestamisel säilitate ekspordikonfiguratsiooni, kuid seda ei käitata enne, kui failile on lisatud mõni muu ühendus.</span><span class="sxs-lookup"><span data-stu-id="c5f04-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="c5f04-166">**Rikastamine:** Ühenduse eemaldamiseks saate rikastamise deaktiveerida või eemaldada.</span><span class="sxs-lookup"><span data-stu-id="c5f04-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="c5f04-167">Kui ühendusel pole rohkem sõltuvusi, minge tagasi **Administraator** > **Ühendused** ja proovige ühendus uuesti eemaldada.</span><span class="sxs-lookup"><span data-stu-id="c5f04-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="c5f04-168">Valige käsk **Eemalda**, et kinnitada kustutamine.</span><span class="sxs-lookup"><span data-stu-id="c5f04-168">To confirm the deletion select **Remove**.</span></span>

