---
title: Power Query põhiste andmeallikate astmeline värskendamine
description: Suurte Power Query põhiste andmeallikate uute ja värskendatud andmete värskendamine.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268543"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="cce0c-103">Power Query põhiste andmeallikate astmeline värskendamine</span><span class="sxs-lookup"><span data-stu-id="cce0c-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="cce0c-104">Andmeallikate astmelisel värskendamisel on järgmised eelised.</span><span class="sxs-lookup"><span data-stu-id="cce0c-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="cce0c-105">**Kiiremad värskendamised** – värskendatakse ainult muudetud andmeid.</span><span class="sxs-lookup"><span data-stu-id="cce0c-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="cce0c-106">Näiteks võite värskendada ainult ajaloolise andmekomplekti viimased viis päeva.</span><span class="sxs-lookup"><span data-stu-id="cce0c-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="cce0c-107">**Suurem töökindlus** – väiksemate värskendamistega ei pea te hoidma hävivate lähtesüsteemidega nii kaua ühendust, vähendades ühenduse probleemide ohtu.</span><span class="sxs-lookup"><span data-stu-id="cce0c-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="cce0c-108">**Vähenenud ressursside tarbimine** – värskendades ainult teie kõikide andmete alamhulka toob kaasa palju tõhusama arvutusressursside kasutamise ja vähendab ökoloogilist jalajälge.</span><span class="sxs-lookup"><span data-stu-id="cce0c-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="cce0c-109">Astmelise värskendamise konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="cce0c-109">Configure incremental refresh</span></span>

<span data-ttu-id="cce0c-110">Sihtrühmaülevaated võimaldavad värskendada astmeliselt Power Query kaudu imporditud andmeallikaid, mille korral toetatakse astmelist valmendamist.</span><span class="sxs-lookup"><span data-stu-id="cce0c-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="cce0c-111">Näiteks Azure SQL-i andmebaasid kuupäeva ja kellaaja väljadega, mis näitavad, millal andmete kirjeid viimati värskendati.</span><span class="sxs-lookup"><span data-stu-id="cce0c-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="cce0c-112">[Looge Power Queryl põhinev uus andmeallikas](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="cce0c-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="cce0c-113">Andke andmeallikale nimi.</span><span class="sxs-lookup"><span data-stu-id="cce0c-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="cce0c-114">Valige andmeallikas, mis toetab astmelist värskendamist (nt Azure SQL-i andmebaas).</span><span class="sxs-lookup"><span data-stu-id="cce0c-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="cce0c-115">Valige olemid või tabelid, mida soovite sisestada.</span><span class="sxs-lookup"><span data-stu-id="cce0c-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="cce0c-116">Viige teisenduse sammud lõpule ja valige suvand **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="cce0c-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="cce0c-117">Dialoogiboksis **Astmelise värskendamise seadistamine** valige suvand **Seadista**, et avada suvand **Astmelise värskendamise sätted**.</span><span class="sxs-lookup"><span data-stu-id="cce0c-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="cce0c-118">Kui valite suvandi **Jäta vahele**, värskendab andmeallikas kogu andmekomplekti.</span><span class="sxs-lookup"><span data-stu-id="cce0c-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="cce0c-119">Saate astmelise värskendamise rakendada ka hiljem, redigeerides olemasolevat andmeallikat.</span><span class="sxs-lookup"><span data-stu-id="cce0c-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="cce0c-120">Suvandis **Astmelise värskendamise sätted** konfigureerite astmelise värskendamise kõigi olemite jaoks, mille andmeallikate loomisel valisite.</span><span class="sxs-lookup"><span data-stu-id="cce0c-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="cce0c-121">![Andmeallika olemite konfigureerimine astmeliseks värskendamiseks](media/incremental-refresh-settings.png "Andmeallika olemite konfigureerimine astmeliseks värskendamiseks")</span><span class="sxs-lookup"><span data-stu-id="cce0c-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="cce0c-122">Valige olem ja sisestage järgmised üksikasjad.</span><span class="sxs-lookup"><span data-stu-id="cce0c-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="cce0c-123">**Määratle primaarvõti**: valige olemi või tabeli primaarvõti.</span><span class="sxs-lookup"><span data-stu-id="cce0c-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="cce0c-124">**Määratle väli „Viimati värskendatud”**: see väli kuvab ainult tüübi kuupäeva või kellaaja atribuudid.</span><span class="sxs-lookup"><span data-stu-id="cce0c-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="cce0c-125">Valige atribuut, mis näitab, millal kirjed viimati värskendati.</span><span class="sxs-lookup"><span data-stu-id="cce0c-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="cce0c-126">Seda kasutatakse selliste kirjete tuvastamiseks, mis jäävad astmelise värskendamise ajavahemikku.</span><span class="sxs-lookup"><span data-stu-id="cce0c-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="cce0c-127">**Otsi värskendusi iga järgmise vahemiku järel**: määrake kui pika te soovite, astmelise värskendamise ajavahemik oleks.</span><span class="sxs-lookup"><span data-stu-id="cce0c-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="cce0c-128">Andmeallika loomise lõpetamiseks valige suvand **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="cce0c-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="cce0c-129">Esmane andmete värskendamine on täielik värskendamine.</span><span class="sxs-lookup"><span data-stu-id="cce0c-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="cce0c-130">Pärast seda leiavad astmelised andmete värskendused aset vastavalt eelmises etapis konfigureeritule.</span><span class="sxs-lookup"><span data-stu-id="cce0c-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]