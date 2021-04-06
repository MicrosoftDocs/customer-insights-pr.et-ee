---
title: Kasutajaõiguste haldamine
description: Lisateave õiguste ja kasutajarollide kohta.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e58bb1a3bd4c0920ff984daffabbf16162185f3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595697"
---
# <a name="user-permissions"></a><span data-ttu-id="ab0ad-103">Kasutajaõigused</span><span class="sxs-lookup"><span data-stu-id="ab0ad-103">User permissions</span></span>

<span data-ttu-id="ab0ad-104">Lehel **Õigused** saate seadistada rolle ja õigusi sihtrühmaülevaadete kasutamiseks.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="ab0ad-105">Lehe nägemiseks peavad teil olema administraatori õigused.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="ab0ad-106">Sihtrühmaülevaadetes õiguste lehe avamiseks minge jaotisse **Haldus** > **Õigused**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="ab0ad-107">Rolle on kolme tüüpi.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="ab0ad-108">Vaataja</span><span class="sxs-lookup"><span data-stu-id="ab0ad-108">Viewer</span></span>

- <span data-ttu-id="ab0ad-109">Tutvuge lehtedel **Avaleht** ja **Segmendid** ülevaadete ning segmentidega.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="ab0ad-110">Otsige ja filtreerige kliendiprofiile lehel **Kliendid**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="ab0ad-111">Väljad peavad olema otsitavad.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-111">Fields must be searchable.</span></span>
- <span data-ttu-id="ab0ad-112">Lehe **Rikastamine** kuvamine ja sellega tutvumine.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="ab0ad-113">Olemite avastamine ja eksportimine lehel **Olemid**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="ab0ad-114">Vaadake süsteemi protsesside olekut lehel **Süsteem**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="ab0ad-115">Eksportige segmendid lehelt **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-115">Export segments from the **Segments** page.</span></span>
- <span data-ttu-id="ab0ad-116">Installige ja kasutage armatuurlauda **Power BI Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="ab0ad-117">Kaasautor</span><span class="sxs-lookup"><span data-stu-id="ab0ad-117">Contributor</span></span>

- <span data-ttu-id="ab0ad-118">Kõik vaatajatele saadaval õigused.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="ab0ad-119">Laadige ja teisendage andmeid lehel **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="ab0ad-120">Viige lõpule *andmete koondamise* jaotised (**vastendamine**, **vastavusseviimine** ja **ühendamine**), mis loovad koondatud kliendiprofiili olemi.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="ab0ad-121">Määratlege **Suhted** ja **Tegevused**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="ab0ad-122">Looge segmente lehel **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="ab0ad-123">Mõõtude loomine lehe **Mõõdud** abil.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="ab0ad-124">Hallake konfiguratsiooni ja rikastage kliendiprofiile lehel **Rikastamine** (ainult esimese osapoole rikastamine).</span><span class="sxs-lookup"><span data-stu-id="ab0ad-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>

## <a name="administrator"></a><span data-ttu-id="ab0ad-125">Administraator</span><span class="sxs-lookup"><span data-stu-id="ab0ad-125">Administrator</span></span>

- <span data-ttu-id="ab0ad-126">Kõik kaasautorile saadaval õigused.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-126">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="ab0ad-127">Muutke lehel **Süsteem** sätteid, sealhulgas süsteemiprotsesside töökeel ja värskendamise ajakavad.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-127">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="ab0ad-128">Vaadake ja lisage õigusi lehel **Õigused**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-128">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="ab0ad-129">Sisestage klientide lehe otsingu- ja filtrimääratlused lehel **Otsingu- ja filtriregister** (sellele pääseb juurde lehelt **Kliendid**).</span><span class="sxs-lookup"><span data-stu-id="ab0ad-129">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="ab0ad-130">Määratlege Dynamics 365 Salesi segmendi sihtkohad lehel **Sihtkohtade eksportimine**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-130">Define Dynamics 365 Sales segment destinations using the **Export destinations** page.</span></span>
- <span data-ttu-id="ab0ad-131">Hallake konfiguratsiooni ja rikastage kliendiprofiile lehel **Rikastamine** (kõik rikastamised).</span><span class="sxs-lookup"><span data-stu-id="ab0ad-131">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="ab0ad-132">**Kliendikaardi lisandmooduli** paigaldamine ja kasutamine.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-132">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="ab0ad-133">Lisage ja kasutage **Power Appsi konnektorit**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-133">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="ab0ad-134">Lubage [Customer Insightsi API-de](apis.md) kasutamine.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-134">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="ab0ad-135">Rollide ja õiguste määramine</span><span class="sxs-lookup"><span data-stu-id="ab0ad-135">Assign roles and permissions</span></span>

1. <span data-ttu-id="ab0ad-136">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Õigused**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-136">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="ab0ad-137">Valige **Lisa kasutajad**, et avada paan **Õiguste lisamine/redigeerimine**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-137">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="ab0ad-138">Kasutage välja **Otsing** Azure Active Directory kasutaja või rühma leidmiseks, kelle õigusi soovite kohandada.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-138">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="ab0ad-139">Valige **Roll**, et määrata see kasutajale või rühmale.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-139">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="ab0ad-140">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-140">Select **Save**.</span></span> <span data-ttu-id="ab0ad-141">Praegust keskkonda jagatakse automaatselt selle rühma kasutaja või liikmetega, kelle õigusi olete muutnud.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-141">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="ab0ad-142">Kasutajad pääsevad juurde rakendusele Customer Insights ja töötavad vastavalt neile määratud rollile.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-142">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="ab0ad-143">Vaadake praeguseid õigusi</span><span class="sxs-lookup"><span data-stu-id="ab0ad-143">View current permissions</span></span>

<span data-ttu-id="ab0ad-144">Minge sihtrühmaülevaadetes jaotisse **Haldus** > **Õigused**, et näha, millised rollimäärangud on praegu aktiivsed.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-144">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="ab0ad-145">Veerg **Tüüp** määrab ühe kasutaja, rühma või rakenduse.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-145">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="ab0ad-146">Süsteem toetab üksikuid kasutajaid ja rühmi.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-146">The system supports individual users and groups.</span></span>
- <span data-ttu-id="ab0ad-147">Rollid on määratletud veerus **Roll**.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-147">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="ab0ad-148">Valige mis tahes veeru pealkiri, et sortida tulemeid selle veeru väärtusega.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-148">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="ab0ad-149">Kasutage lehe ülaservas välja **Otsing** kindlate kasutajate leidmiseks.</span><span class="sxs-lookup"><span data-stu-id="ab0ad-149">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]