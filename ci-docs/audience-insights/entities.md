---
title: Olemid ja andmekomplektid
description: Saate vaadata andmeid olemite lehel.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 383523bad5105e08e57758838e90a49e805b5f9b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596402"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="010af-103">Olemid sihtrühmaülevaadetes</span><span class="sxs-lookup"><span data-stu-id="010af-103">Entities in audience insights</span></span>

<span data-ttu-id="010af-104">Pärast [andmeallikate konfigureerimist](data-sources.md)minge lehele **Olemid**, et hinnata sisestatud andmete kvaliteeti.</span><span class="sxs-lookup"><span data-stu-id="010af-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="010af-105">Olemeid käsitletakse andmekogumitena.</span><span class="sxs-lookup"><span data-stu-id="010af-105">Entities are considered datasets.</span></span> <span data-ttu-id="010af-106">Nende olemite põhjal on loodud mitu Dynamics 365 Customer Insightsi funktsiooni.</span><span class="sxs-lookup"><span data-stu-id="010af-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="010af-107">Nende lähedasem läbivaatamine aitab teil nende võimaluste väljundit valideerida.</span><span class="sxs-lookup"><span data-stu-id="010af-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="010af-108">**Olemite** lehel loetletakse olemid ja see sisaldab mitut veergu.</span><span class="sxs-lookup"><span data-stu-id="010af-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="010af-109">**Nimi**: teie andmete olemi nimi.</span><span class="sxs-lookup"><span data-stu-id="010af-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="010af-110">Kui olemi nime kõrval kuvatakse hoiatuse sümbol, tähendab see, et selle olemi andmeid ei laaditud edukalt.</span><span class="sxs-lookup"><span data-stu-id="010af-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="010af-111">**Allikas**: andmeallika tüüp, mis olemisse sisestati</span><span class="sxs-lookup"><span data-stu-id="010af-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="010af-112">**Looja**: olemi loonud inimese nimi</span><span class="sxs-lookup"><span data-stu-id="010af-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="010af-113">**Loodud**: olemi loomise kuupäev ja kellaaeg</span><span class="sxs-lookup"><span data-stu-id="010af-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="010af-114">**Värskendaja**: olemit värskendanud inimese nimi</span><span class="sxs-lookup"><span data-stu-id="010af-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="010af-115">**Viimati värskendatud**: olemi viimase värskendamise kuupäev ja kellaaeg</span><span class="sxs-lookup"><span data-stu-id="010af-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="010af-116">**Viimane värskendatud**: viimase andmete värskendamise kuupäev ja kellaaeg</span><span class="sxs-lookup"><span data-stu-id="010af-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="010af-117">Kindla olemi andmete avastamine</span><span class="sxs-lookup"><span data-stu-id="010af-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="010af-118">Valige olem, et avastada selles olemis sisalduvaid erinevaid välju ja kirjeid.</span><span class="sxs-lookup"><span data-stu-id="010af-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="010af-119">![Vali olem](media/data-manager-entities-data.png "Vali olem")</span><span class="sxs-lookup"><span data-stu-id="010af-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="010af-120">Vahekaart **Andmed** on valitud vaikimisi ja selles kuvatakse tabel, kus loetletakse olemi individuaalsete kirjete üksikasjad.</span><span class="sxs-lookup"><span data-stu-id="010af-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="010af-121">![Väljade tabel](media/data-manager-entities-fields.PNG "Väljade tabel")</span><span class="sxs-lookup"><span data-stu-id="010af-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="010af-122">Vahekaardil **Väljad** kuvatakse tabel, kus saate vaadata valitud olemi üksikasju, nt väljade nimesid, andmetüüpe ja tüüpe.</span><span class="sxs-lookup"><span data-stu-id="010af-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="010af-123">Veerus **Tüüp** kuvatakse ühise andmemudeli seostatavad tüübid, mis on süsteemi poolt automaatselt tuvastatud või mille on kasutajad [käsitsi vastendanud](map-entities.md).</span><span class="sxs-lookup"><span data-stu-id="010af-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="010af-124">Need on semantilised tüübid, mis võivad atribuutide andmetüüpide hulgast erineda, nt allpool on *Meili* välja andmetüüp *Tekst*, kuid selle (semantiline) ühine andmemudel võib olla *Meil* või *Meiliaadress*.</span><span class="sxs-lookup"><span data-stu-id="010af-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="010af-125">Mõlemad tabelid näitavad ainult teie olemi andmete näidiseid.</span><span class="sxs-lookup"><span data-stu-id="010af-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="010af-126">Täieliku andmekogumise vaatamiseks minge lehele **Andmeallikad**, valige olem, valige **Redigeeri** ja seejärel vaadake selle olemi andmeid Power Query redaktoriga, nagu on selgitatud [andmeallikates](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="010af-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="010af-127">Kui soovite lisateavet olemisse sisestatud andmete kohta, on **Kokkuvõtte** veerus toodud teie jaoks olulised kohaldatavad andmed, nt nullid, puuduvad väärtused, kordumatud väärtused, arvud ja jaotused.</span><span class="sxs-lookup"><span data-stu-id="010af-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="010af-128">Andmete kokkuvõtte kuvamiseks valige diagrammi ikoon.</span><span class="sxs-lookup"><span data-stu-id="010af-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="010af-129">![Kokkuvõtte sümbol](media/data-manager-entities-summary.png "Andmete kokkuvõtte tabel")</span><span class="sxs-lookup"><span data-stu-id="010af-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="010af-130">Järgmine etapp</span><span class="sxs-lookup"><span data-stu-id="010af-130">Next step</span></span>

<span data-ttu-id="010af-131">Vaadake jaotise [Ühendamine](data-unification.md) teemat, et õppida sisestatud andmete *kaardistamist*, *vastendamist* ja *ühendamist*.</span><span class="sxs-lookup"><span data-stu-id="010af-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]