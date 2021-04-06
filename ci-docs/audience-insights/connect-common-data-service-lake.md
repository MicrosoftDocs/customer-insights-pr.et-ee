---
title: Ühenduse loomine Common Data Service'i hallatava andmejärve olemitega
description: Andmete importimine Common Data Service'i hallatavast andmejärvest.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596954"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="0884d-103">Andmetega ühendamine Common Data Service’i hallatavas andmejärves</span><span class="sxs-lookup"><span data-stu-id="0884d-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0884d-104">See artikkel annab teavet selle kohta, kuidas olemasolevad Dynamics 365 kliendid saavad kiiresti ühendada oma analüütiliste üksustega Common Data Service'i hallatavas järves.</span><span class="sxs-lookup"><span data-stu-id="0884d-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="0884d-105">Peate olema Common Data Service'i organisatsiooni administraator, et jätkata ja näha hallatavas järves saadaolevate olemite loendit.</span><span class="sxs-lookup"><span data-stu-id="0884d-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="0884d-106">Olulised kaalutlused</span><span class="sxs-lookup"><span data-stu-id="0884d-106">Important considerations</span></span>

<span data-ttu-id="0884d-107">Võrguteenustes nagu Azure Data Lake Storage talletatavaid andmeid saab talletada muus asukohas kui see, kus andmeid rakenduses Dynamics 365 Customer Insights töödeldakse või talletatakse.</span><span class="sxs-lookup"><span data-stu-id="0884d-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="0884d-108"> Kui impordite võrguteenustes talletatavaid andmeid või ühendate konto teenusega, siis nõustute, et andmeid võidakse transportida ja salvestada rakenduses Dynamics 365 Customer Insights. [Lisateavet leiate Microsofti usalduskeskusest.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="0884d-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="0884d-109">Teenuse Common Data Service hallatava järvega ühenduse loomine</span><span class="sxs-lookup"><span data-stu-id="0884d-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="0884d-110">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="0884d-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0884d-111">Valige **Lisa andmeallikas**.</span><span class="sxs-lookup"><span data-stu-id="0884d-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="0884d-112">Valige **Teenusega Common Data Service ühenduse loomine** ja valige suvand **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="0884d-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="0884d-113">Sisestage andmeallika **Nimi** ja valige **Järgmine**.</span><span class="sxs-lookup"><span data-stu-id="0884d-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="0884d-114">Nime juhised:</span><span class="sxs-lookup"><span data-stu-id="0884d-114">Name guidelines:</span></span> 
   - <span data-ttu-id="0884d-115">peab algama tähega;</span><span class="sxs-lookup"><span data-stu-id="0884d-115">Start with a letter.</span></span>
   - <span data-ttu-id="0884d-116">kasutage ainult tähti ja numbreid;</span><span class="sxs-lookup"><span data-stu-id="0884d-116">Use letters and numbers only.</span></span> <span data-ttu-id="0884d-117">erimärkide ja tühikute sisestamine pole lubatud;</span><span class="sxs-lookup"><span data-stu-id="0884d-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="0884d-118">kasutage 3–64 tähemärki.</span><span class="sxs-lookup"><span data-stu-id="0884d-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="0884d-119">Sisestage oma Common Data Service’i organisatsiooni **serveri aadress** ja valige suvand **Logi sisse**.</span><span class="sxs-lookup"><span data-stu-id="0884d-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0884d-120">![Dialoogiaken Common Data Service’i serveri aadressi sisestamiseks](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="0884d-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="0884d-121">Valige saadaolevate olemite loendist need olemid, mida soovite valmendada.</span><span class="sxs-lookup"><span data-stu-id="0884d-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="0884d-122">Kui mõni olem on juba valitud, võidakse neid kasutada teistes Dynamics 365 rakendustes (nt Dynamics 365 Sales Insights või Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="0884d-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="0884d-123">Valikut ei saa muuta.</span><span class="sxs-lookup"><span data-stu-id="0884d-123">You can't change the selection.</span></span> <span data-ttu-id="0884d-124">Need olemid on saadaval pärast andmeallikas loomist.</span><span class="sxs-lookup"><span data-stu-id="0884d-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0884d-125">![Common Data Service’i organisatsiooni olemite loendit näitav dialoogiaken](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="0884d-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="0884d-126">Salvestage oma valik, et alustada valitud olemite sünkroonimist Common Data Service’i hallatava järvega.</span><span class="sxs-lookup"><span data-stu-id="0884d-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="0884d-127">Äsja lisatud ühenduse leiate lehelt **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="0884d-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="0884d-128">See pannakse värskendamiseks järjekorda ja kuvab olemite arvuna 0, kuni kõik olemid on sünkroonitud.</span><span class="sxs-lookup"><span data-stu-id="0884d-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="0884d-129">Sama Common Data Service'i hallatavat andmejärve saab ühel ajal kasutada ainult üks keskkonna andmeallikas.</span><span class="sxs-lookup"><span data-stu-id="0884d-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="0884d-130">Common Data Service’i hallatava järve andmeallika muutmine</span><span class="sxs-lookup"><span data-stu-id="0884d-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="0884d-131">Olemi valikut redigeerite alles pärast andmeallika loomist.</span><span class="sxs-lookup"><span data-stu-id="0884d-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="0884d-132">Näiteks, kui Common Data Service'ile lisati täiendavaid olemeid ja soovite ka need importida.</span><span class="sxs-lookup"><span data-stu-id="0884d-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="0884d-133">Muu Common Data Service’iga ühenduse loomiseks [looge uus andmeallikas](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="0884d-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="0884d-134">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.</span><span class="sxs-lookup"><span data-stu-id="0884d-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="0884d-135">Valige uuendatava andmeallika kõrval suvand kolm punkti.</span><span class="sxs-lookup"><span data-stu-id="0884d-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="0884d-136">Valige loetelust valik **Redigeeri**.</span><span class="sxs-lookup"><span data-stu-id="0884d-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="0884d-137">Valige saadaolevate olemite loendist täiendavad olemid ja valige suvand **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="0884d-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]