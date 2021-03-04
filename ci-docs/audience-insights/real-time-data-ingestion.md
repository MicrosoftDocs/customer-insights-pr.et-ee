---
title: Reaalajas andmete valmendamine ja selle piirangud
description: Üldine teave reaalajas võimaluste kohta sihtrühmaülevaadetes.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7421ed9d2cb399d546815b2d1b0ea5ec51ca6b6d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270275"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="ce5d9-103">Reaalajas andmete valmendamine (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="ce5d9-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="ce5d9-104">Peaaegu reaalajaline funktsionaalsus võimaldab teil vaadata mõne sekundi jooksul viimaseid suhtlusi, mida teie kliendid on teie toodete või teenuste osas teinud.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="ce5d9-105">[Ajastatud värskendamised](system.md#schedule-tab) hõlmavad palju kirjeid ja mitmesuguseid keerukaid toiminguid.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="ce5d9-106">Esmalt tuuakse andmed andmeallikast.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="ce5d9-107">Edasi andmed koondatakse ja seejärel rikastatakse täiendava teabega.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="ce5d9-108">Selle protsessi iga tsükkel võib kesta minutitest tundideni.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="ce5d9-109">Reaalajas funktsioon pakub andmeid kohe tarbimiseks, kuni järgmine ajastatud värskendamine toob need andmed andmeallikast.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="ce5d9-110">Reaalajalised värskendused aeguvad aja jooksul, mille möödumisel nad enam andmeallikas väärtust ei tühista.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="ce5d9-111">Profiiliuuendusi säilitatakse 4 tundi</span><span class="sxs-lookup"><span data-stu-id="ce5d9-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="ce5d9-112">Tegevusi säilitatakse 30 päeva</span><span class="sxs-lookup"><span data-stu-id="ce5d9-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="ce5d9-113">Need väärtused on API kõne parameetrid, mida saate muuta.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="ce5d9-114">Nende eesmärk on tagada, et teie lähteandmed oleksid teie tõe allikas.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="ce5d9-115">Kui soovite, et reaalajas värskendusi kaasataks kauem, peate need lisama andmeallikasse, et neid saaks järgmise ajastatud värskendamise ajal tuua.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="ce5d9-116">Ühendatud kliendi profiili väljade reaalajaline värskendamine</span><span class="sxs-lookup"><span data-stu-id="ce5d9-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="ce5d9-117">Värskendatud profiilid kuvatakse kliendikaardi vaates või mõnes muus visualiseeringus mõne sekundi jooksul.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="ce5d9-118">Kuna reaalajalised toimingud toimuvad pärast andmete ühendamise toimumist, kehtivad need ainult ühendatud kliendiprofiilide kohta.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="ce5d9-119">Seega ei värskenda reaalajas profiili muudatused meetmeid, segmendi liikmestaatust ega rikastamist.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="ce5d9-120">Piirangud</span><span class="sxs-lookup"><span data-stu-id="ce5d9-120">Limitations</span></span>

- <span data-ttu-id="ce5d9-121">Kliendiprofiile saab värskendada, kuid mitte luua ega kustutada.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="ce5d9-122">Praegu ei ole võimalik eksportida reaalajas värskendusi välistesse süsteemidesse nagu Power BI.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="ce5d9-123">Tegevuste loomine reaalajas</span><span class="sxs-lookup"><span data-stu-id="ce5d9-123">Real-time creation of activities</span></span>

<span data-ttu-id="ce5d9-124">Reaalajas API võimaldab teil avaldada uue tegevuse oma lähtesüsteemist (individuaalne lähtekirje) koondatud kliendiprofiilile.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="ce5d9-125">Uus tegevus on saadaval ühendatud tegevusena selles kliendiprofiilis mõne sekundi jooksul.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="ce5d9-126">Ajaskaalat saate vaadata kliendikaardi vaates või mõnes muus teie konfigureeritud ajaskaala integratsioonis.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="ce5d9-127">Tegevused on püsivad.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-127">Activities are immutable.</span></span> <span data-ttu-id="ce5d9-128">Nad ei muutu pärast loomist.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-128">They don't change once created.</span></span>
> - <span data-ttu-id="ce5d9-129">Praegu ei värskendata segmente ega meetmeid uue tegevuse põhjal.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="ce5d9-130">Ainult reaalajas API kaudu lisatud tegevused ei kuulu ekspordi hulka ja neid ei kuvata PowerBI-s.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="ce5d9-131">Reaalajas API-ga ühenduse loomiseks on kaks võimalust.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="ce5d9-132">[kaudselt](#connect-via-the-dynamics-365-customer-insights-connector), kasutades [Dynamics 365 Customer Insightskonnektorit](https://docs.microsoft.com/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="ce5d9-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/)</span></span>
- <span data-ttu-id="ce5d9-133">[otse](#connect-directly-to-the-real-time-api), koodiga</span><span class="sxs-lookup"><span data-stu-id="ce5d9-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="ce5d9-134">Mõlemal viisil on järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="ce5d9-135">Customer Insightsi keskkond</span><span class="sxs-lookup"><span data-stu-id="ce5d9-135">A Customer Insights environment</span></span>
- <span data-ttu-id="ce5d9-136">Kliendi koondprofiilid</span><span class="sxs-lookup"><span data-stu-id="ce5d9-136">Unified customer profiles</span></span>
- <span data-ttu-id="ce5d9-137">Konfigureeritud ja käivitatud tegevused</span><span class="sxs-lookup"><span data-stu-id="ce5d9-137">Activities configured and run</span></span>
- <span data-ttu-id="ce5d9-138">Kaasautori või administraatori õigused teie konto autentimiseks</span><span class="sxs-lookup"><span data-stu-id="ce5d9-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="ce5d9-139">Ühenduse loomine Dynamics 365 Customer Insights-i konnektori kaudu</span><span class="sxs-lookup"><span data-stu-id="ce5d9-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="ce5d9-140">Reaalaja API saab alla laadida andmeid spetsiaalsest Power Platform-i konnektorist, [Dynamics 365 Customer Insights-i konnektor](https://docs.microsoft.com/connectors/customerinsights/), ilma et oleks vaja kirjutada ja kasutada mis tahes koodi.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](https://docs.microsoft.com/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="ce5d9-141">Konnektor saab teha samu reaalajalisi toiminguid nagu API.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="ce5d9-142">Premium-taseme konnektorite jaoks vajate sobivat litsentsi.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="ce5d9-143">Lisateavet vt teemast [Power Apps-i ja Power Automate-i litsentsimise KKK](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="ce5d9-143">For more information, see [Power Apps and Power Automate licensing FAQs](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="ce5d9-144">Power Platform [Power Apps ja/või Power Automate](https://docs.microsoft.com/connectors/)</span><span class="sxs-lookup"><span data-stu-id="ce5d9-144">Power Platform [Power Apps and/or Power Automate](https://docs.microsoft.com/connectors/)</span></span>
- <span data-ttu-id="ce5d9-145">Azure [Logicu rakendused](https://docs.microsoft.com/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="ce5d9-145">Azure [Logic Apps](https://docs.microsoft.com/azure/connectors/apis-list)</span></span>

<span data-ttu-id="ce5d9-146">Voogude loomise üksikasjad leiate [Power Automate-i dokumentatsioonist](https://docs.microsoft.com/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="ce5d9-146">For details about creating flows, see the [Power Automate documentation](https://docs.microsoft.com/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="ce5d9-147">Otse reaalajas API-ga ühenduse loomine</span><span class="sxs-lookup"><span data-stu-id="ce5d9-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="ce5d9-148">Saate kasutada reaalajalisi võimalusi, luues oma konveieri ja ühendudes otse reaalajas API-ga.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="ce5d9-149">Võite tegevuse postitada oma lähtekoodisüsteemi vormingus või UnifiedActivity vormingus.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="ce5d9-150">Vormingu saamiseks tehke API kõne/API/instances/{instanceId}/Manage/Entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="ce5d9-151">Selle API üksikasjad, sh parameetrid ja vastused, leiate jaotisest **EntityData**, mis asub artiklis [Customer Insightsi API-de ülevaade](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="ce5d9-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="ce5d9-152">Lisateavet leiate teemast [Customer Insightsi API-dega töötamine](apis.md).</span><span class="sxs-lookup"><span data-stu-id="ce5d9-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="ce5d9-153">Oma reaalajas kasutuse mõistmine telemeetria abil</span><span class="sxs-lookup"><span data-stu-id="ce5d9-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="ce5d9-154">Teil on võimalik vaadata ülevaadet reaalajas API-le saadetud päringute arvu ja süsteemi võimalike probleemide kohta.</span><span class="sxs-lookup"><span data-stu-id="ce5d9-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="ce5d9-155">Pääsete [ligi reaalajalisele telemeetriale](system.md#api-usage-tab)</span><span class="sxs-lookup"><span data-stu-id="ce5d9-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]