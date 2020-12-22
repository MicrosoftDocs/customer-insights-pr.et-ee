---
title: Andmesubjekti õigused (DSR) vastavalt GDPR-ile | Microsoft Docs
description: Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsiooni andmesubjekti taotlustele vastamine.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405553"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="b177e-103">Andmesubjekti õigused (DSR) vastavalt GDPR-ile</span><span class="sxs-lookup"><span data-stu-id="b177e-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="b177e-104">Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsiooni GDPR-i andmesubjekti kustutamistaotlustele vastamine</span><span class="sxs-lookup"><span data-stu-id="b177e-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="b177e-105">Õigus isikuandmete eemaldamiseks ettevõtte kliendiandmetest on isikuandmete kaitse üldmääruse (GDPR-i) põhikaitse.</span><span class="sxs-lookup"><span data-stu-id="b177e-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="b177e-106">Isikuandmete eemaldamine hõlmab kogi isiklike andmete ja süsteemi loodud logide eemaldamist, va auditi logi teabe.</span><span class="sxs-lookup"><span data-stu-id="b177e-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="b177e-107">Andmete kustutamise taotluste haldamine</span><span class="sxs-lookup"><span data-stu-id="b177e-107">Manage data subject delete requests</span></span>

<span data-ttu-id="b177e-108">Sihtrühmaülevaadete funktsioon pakub järgmisi tootega seotud kogemusi, et kustutada teatud kliendi või kasutaja isikuandmed.</span><span class="sxs-lookup"><span data-stu-id="b177e-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="b177e-109">**Kliendiandmete kustutamise taotluste haldamine**: kliendi andmed Customer Insightsis on sisestatud algsest andmeallikast, mis on Customer Insightsi väline.</span><span class="sxs-lookup"><span data-stu-id="b177e-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="b177e-110">Kõik GDPR-i kustutamise taotlused tuleb teha algses andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="b177e-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="b177e-111">**Customer Insightsi kliendiandmete kustutamise taotluste haldamine**: kasutajate andmeid loob Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b177e-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="b177e-112">Kõik GDPR-i kustutamise taotlused tuleb teha Customer Insightsis.</span><span class="sxs-lookup"><span data-stu-id="b177e-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="b177e-113">Kliendiandmete kustutamise taotluste haldamine</span><span class="sxs-lookup"><span data-stu-id="b177e-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="b177e-114">Customer Insightsi administraator saab nende etappide abil eemaldada kliendiandmeid, mis kustutati andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="b177e-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="b177e-115">Logige sisse rakendusse Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b177e-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="b177e-116">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**</span><span class="sxs-lookup"><span data-stu-id="b177e-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="b177e-117">Tehke iga loendis oleva andmeallikaga, mis sisaldab kustutatud kliendiandmeid, järgmist.</span><span class="sxs-lookup"><span data-stu-id="b177e-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="b177e-118">Valige (...) ja seejärel valige nupp **Värskenda**.</span><span class="sxs-lookup"><span data-stu-id="b177e-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="b177e-119">Kontrollige andmeallikas olekut **Oleku** all.</span><span class="sxs-lookup"><span data-stu-id="b177e-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="b177e-120">Märge tähendab, et värskendamine õnnestus.</span><span class="sxs-lookup"><span data-stu-id="b177e-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="b177e-121">Ohukolmnurk tähendab, et midagi läks valesti.</span><span class="sxs-lookup"><span data-stu-id="b177e-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="b177e-122">Kui kuvatakse ohukolmnurk, võtke ühendust aadressil D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b177e-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b177e-123">![Kliendiandmete GDPR-i kustutamise taotluste käsitlemine](media/gdpr-data-sources.png "Kliendiandmete GDPR-i kustutamise taotluste käsitlemine")</span><span class="sxs-lookup"><span data-stu-id="b177e-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="b177e-124">Kasutajaandmete kustutamise taotluste haldamine</span><span class="sxs-lookup"><span data-stu-id="b177e-124">Manage delete requests for user data</span></span>

<span data-ttu-id="b177e-125">Customer Insightsi administraator saab Customer Insightsi kasutaja andmete kustutamiseks toimida järgmiselt.</span><span class="sxs-lookup"><span data-stu-id="b177e-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="b177e-126">Logige sisse rakendusse Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b177e-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="b177e-127">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Õigused**.</span><span class="sxs-lookup"><span data-stu-id="b177e-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="b177e-128">Valige märkeruutude abil kasutaja, kelle soovite kustutada.</span><span class="sxs-lookup"><span data-stu-id="b177e-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="b177e-129">Valige **Eemalda**.</span><span class="sxs-lookup"><span data-stu-id="b177e-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b177e-130">![Kasutajaandmete GDPR-i põhiste kustutamistaotluste haldamine](media/gdpr-permissions.png "Kasutajaandmete GDPR-i põhiste kustutamistaotluste haldamine")</span><span class="sxs-lookup"><span data-stu-id="b177e-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="b177e-131">GDPR-i andmesubjekti eksportimistaotlustele vastamine</span><span class="sxs-lookup"><span data-stu-id="b177e-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="b177e-132">Osana meie pühendumusest saatmaks teid teekonnal isikuandmete kaitse üldmääruseni (GDPR) oleme välja töötanud dokumendid, mis aitavad teil valmistuda.</span><span class="sxs-lookup"><span data-stu-id="b177e-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="b177e-133">Selles dokumentatsioonis kirjeldatakse toiminguid, mida saate kohe teha, et toetada GDPR-i täitmist sihtrühmaülevaadete kasutamisel.</span><span class="sxs-lookup"><span data-stu-id="b177e-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="b177e-134">Ekspordi ja vaate taotluste haldamine</span><span class="sxs-lookup"><span data-stu-id="b177e-134">Manage export and view requests</span></span>

<span data-ttu-id="b177e-135">Andmete teisaldamise õigus võimaldab andmesubjektil taotleda oma isikuandmete koopiat elektrooniliselt (määratletakse kui „struktureeritud, tavaliselt kasutatav, masinloetav ja koostalitlusvõimeline vorming“), mida võib edastada teisele andmetöötlejale.</span><span class="sxs-lookup"><span data-stu-id="b177e-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="b177e-136">Kliendiandmete eksportimine (rentniku administraator)</span><span class="sxs-lookup"><span data-stu-id="b177e-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="b177e-137">Rentniku administraator võib järgida andmete eksportimisel järgmisi etappe.</span><span class="sxs-lookup"><span data-stu-id="b177e-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="b177e-138">Saatke meili aadressile D365CI@microsoft.com, et määrata taotluses kliendi meiliaadress.</span><span class="sxs-lookup"><span data-stu-id="b177e-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="b177e-139">Customer Insightsi meeskond saadab registreeritud rentniku administraatori meiliaadressile meili, paludes kinnitust andmete eksportimiseks.</span><span class="sxs-lookup"><span data-stu-id="b177e-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="b177e-140">Kinnitage taotletud kliendile andmete eksportimise luba.</span><span class="sxs-lookup"><span data-stu-id="b177e-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="b177e-141">Saage eksporditud andmed rentniku administraatori meiliaadressi kaudu.</span><span class="sxs-lookup"><span data-stu-id="b177e-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="b177e-142">Kasutajaandmete eksportimine (rentniku administraator)</span><span class="sxs-lookup"><span data-stu-id="b177e-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="b177e-143">Saatke meil aadressile D365CI@microsoft.com, et määrata taotluses kasutaja meiliaadress.</span><span class="sxs-lookup"><span data-stu-id="b177e-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="b177e-144">Customer Insightsi meeskond saadab registreeritud rentniku administraatori meiliaadressile meili, paludes kinnitust andmete eksportimiseks.</span><span class="sxs-lookup"><span data-stu-id="b177e-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="b177e-145">Kinnitage taotletud kasutajale andmete eksportimise luba.</span><span class="sxs-lookup"><span data-stu-id="b177e-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="b177e-146">Saage eksporditud andmed rentniku administraatori meiliaadressi kaudu.</span><span class="sxs-lookup"><span data-stu-id="b177e-146">Receive the exported data through the tenant admin email address.</span></span>
