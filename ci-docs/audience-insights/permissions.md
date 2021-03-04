---
title: Kasutajaõiguste haldamine
description: Lisateave õiguste ja kasutajarollide kohta.
ms.date: 10/27/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f7fcecdea8dc49666dd5c45bf4109c205993f326
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268405"
---
# <a name="user-permissions"></a><span data-ttu-id="d0fca-103">Kasutajaõigused</span><span class="sxs-lookup"><span data-stu-id="d0fca-103">User permissions</span></span>

<span data-ttu-id="d0fca-104">Lehel **Õigused** saate seadistada rolle ja õigusi sihtrühmaülevaadete kasutamiseks.</span><span class="sxs-lookup"><span data-stu-id="d0fca-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="d0fca-105">Lehe nägemiseks peavad teil olema administraatori õigused.</span><span class="sxs-lookup"><span data-stu-id="d0fca-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="d0fca-106">Sihtrühmaülevaadetes õiguste lehe avamiseks minge jaotisse **Haldus** > **Õigused**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="d0fca-107">Rolle on kolme tüüpi.</span><span class="sxs-lookup"><span data-stu-id="d0fca-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="d0fca-108">Vaataja</span><span class="sxs-lookup"><span data-stu-id="d0fca-108">Viewer</span></span>

- <span data-ttu-id="d0fca-109">Tutvuge lehtedel **Avaleht** ja **Segmendid** ülevaadete ning segmentidega.</span><span class="sxs-lookup"><span data-stu-id="d0fca-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="d0fca-110">Otsige ja filtreerige kliendiprofiile lehel **Kliendid**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="d0fca-111">Väljad peavad olema otsitavad.</span><span class="sxs-lookup"><span data-stu-id="d0fca-111">Fields must be searchable.</span></span>
- <span data-ttu-id="d0fca-112">Lehe **Rikastamine** kuvamine ja sellega tutvumine.</span><span class="sxs-lookup"><span data-stu-id="d0fca-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="d0fca-113">Olemite avastamine ja eksportimine lehel **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="d0fca-114">Vaadake süsteemi protsesside olekut lehel **Süsteem**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="d0fca-115">Eksportige segmendid lehelt **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="d0fca-116">Installige ja kasutage armatuurlauda **Power BI Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="d0fca-117">Kaasautor</span><span class="sxs-lookup"><span data-stu-id="d0fca-117">Contributor</span></span>

- <span data-ttu-id="d0fca-118">Kõik vaatajatele saadaval õigused.</span><span class="sxs-lookup"><span data-stu-id="d0fca-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="d0fca-119">Laadige ja teisendage andmeid lehel **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="d0fca-120">Viige lõpule *andmete koondamise* jaotised (**vastendamine**, **vastavusseviimine** ja **ühendamine**), mis loovad koondatud kliendiprofiili olemi.</span><span class="sxs-lookup"><span data-stu-id="d0fca-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="d0fca-121">Määratlege **Suhted** ja **Tegevused**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="d0fca-122">Looge segmente lehel **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="d0fca-123">Mõõtude loomine lehe **Mõõdud** abil.</span><span class="sxs-lookup"><span data-stu-id="d0fca-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="d0fca-124">Hallake konfiguratsiooni ja rikastage kliendiprofiile lehel **Rikastamine** (ainult esimese osapoole rikastamine).</span><span class="sxs-lookup"><span data-stu-id="d0fca-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="d0fca-125">Administraator</span><span class="sxs-lookup"><span data-stu-id="d0fca-125">Administrator</span></span>

- <span data-ttu-id="d0fca-126">Kõik kaasautorile saadaval õigused.</span><span class="sxs-lookup"><span data-stu-id="d0fca-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="d0fca-127">Muutke lehel **Süsteem** sätteid, sealhulgas süsteemiprotsesside töökeel ja värskendamise ajakavad.</span><span class="sxs-lookup"><span data-stu-id="d0fca-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="d0fca-128">Vaadake ja lisage õigusi lehel **Õigused**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="d0fca-129">Sisestage klientide lehe otsingu- ja filtrimääratlused lehel **Otsingu- ja filtriregister** (sellele pääseb juurde lehelt **Kliendid**).</span><span class="sxs-lookup"><span data-stu-id="d0fca-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="d0fca-130">Määratlege Dynamics 365 Salesi segmendi sihtkohad lehel **Sihtkohtade eksportimine**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="d0fca-131">Hallake konfiguratsiooni ja rikastage kliendiprofiile lehel **Rikastamine** (kõik rikastamised).</span><span class="sxs-lookup"><span data-stu-id="d0fca-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="d0fca-132">**Kliendikaardi lisandmooduli** paigaldamine ja kasutamine.</span><span class="sxs-lookup"><span data-stu-id="d0fca-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="d0fca-133">Lisage ja kasutage **Power Appsi konnektorit**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="d0fca-134">Lubage [Customer Insightsi API-de](apis.md) kasutamine.</span><span class="sxs-lookup"><span data-stu-id="d0fca-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="d0fca-135">Rollide ja õiguste määramine</span><span class="sxs-lookup"><span data-stu-id="d0fca-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="d0fca-136">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Õigused**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="d0fca-137">Valige **Lisa kasutajad**, et avada paan **Õiguste lisamine/redigeerimine**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="d0fca-138">Kasutage välja **Otsing** Azure Active Directory kasutaja või rühma leidmiseks, kelle õigusi soovite kohandada.</span><span class="sxs-lookup"><span data-stu-id="d0fca-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="d0fca-139">Valige **Roll**, et määrata see kasutajale või rühmale.</span><span class="sxs-lookup"><span data-stu-id="d0fca-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="d0fca-140">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-140">Select **Save**.</span></span> <span data-ttu-id="d0fca-141">Praegust keskkonda jagatakse automaatselt selle rühma kasutaja või liikmetega, kelle õigusi olete muutnud.</span><span class="sxs-lookup"><span data-stu-id="d0fca-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="d0fca-142">Kasutajad pääsevad juurde rakendusele Customer Insights ja töötavad vastavalt neile määratud rollile.</span><span class="sxs-lookup"><span data-stu-id="d0fca-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="d0fca-143">Vaadake praeguseid õigusi</span><span class="sxs-lookup"><span data-stu-id="d0fca-143">View current permissions</span></span>

<span data-ttu-id="d0fca-144">Minge sihtrühmaülevaadetes jaotisse **Haldus** > **Õigused**, et näha, millised rollimäärangud on praegu aktiivsed.</span><span class="sxs-lookup"><span data-stu-id="d0fca-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="d0fca-145">Veerg **Tüüp** määrab ühe kasutaja, rühma või rakenduse.</span><span class="sxs-lookup"><span data-stu-id="d0fca-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="d0fca-146">Süsteem toetab üksikuid kasutajaid ja rühmi.</span><span class="sxs-lookup"><span data-stu-id="d0fca-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="d0fca-147">Rollid on määratletud veerus **Roll**.</span><span class="sxs-lookup"><span data-stu-id="d0fca-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="d0fca-148">Valige mis tahes veeru pealkiri, et sortida tulemeid selle veeru väärtusega.</span><span class="sxs-lookup"><span data-stu-id="d0fca-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="d0fca-149">Kasutage lehe ülaservas välja **Otsing** kindlate kasutajate leidmiseks.</span><span class="sxs-lookup"><span data-stu-id="d0fca-149">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]