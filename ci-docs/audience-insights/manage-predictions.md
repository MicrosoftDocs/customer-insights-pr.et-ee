---
title: Jagatud ülesanded prognoosistsenaariumide jaoks
description: Vaadake, kuidas ennustusi hallata, tõrkeotsingut teha ja prognoose määratleda.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095702"
---
# <a name="manage-predictions"></a><span data-ttu-id="46bc7-103">Prognooside haldamine</span><span class="sxs-lookup"><span data-stu-id="46bc7-103">Manage predictions</span></span>

<span data-ttu-id="46bc7-104">Selles artiklis käsitletakse mõningaid toiminguid, mida enamik prognoosistsenaariume jagavad.</span><span class="sxs-lookup"><span data-stu-id="46bc7-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="46bc7-105">Nurjunud prognoosi tõrkeotsing</span><span class="sxs-lookup"><span data-stu-id="46bc7-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="46bc7-106">Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="46bc7-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="46bc7-107">Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mille tõrkelogisid soovite vaadata.</span><span class="sxs-lookup"><span data-stu-id="46bc7-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="46bc7-108">Valige **Logid**.</span><span class="sxs-lookup"><span data-stu-id="46bc7-108">Select **Logs**.</span></span>

1. <span data-ttu-id="46bc7-109">Kõikide tõrgete läbivaatamine.</span><span class="sxs-lookup"><span data-stu-id="46bc7-109">Review all the errors.</span></span> <span data-ttu-id="46bc7-110">Esineda võib mitmesuguseid tüüpe tõrkeid ja need kirjeldavad, mis olukord selle tõrke tekitad.</span><span class="sxs-lookup"><span data-stu-id="46bc7-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="46bc7-111">Näiteks tõrge, et täpse prognoosi tegemiseks pole piisavalt andmeid, lahendatakse tavaliselt täiendavate andmete laadimisel Customer Insightsis.</span><span class="sxs-lookup"><span data-stu-id="46bc7-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="46bc7-112">Sisendandmete kasutatavusaruanne</span><span class="sxs-lookup"><span data-stu-id="46bc7-112">Input data usability report</span></span>

<span data-ttu-id="46bc7-113">Sisendandmete kasutatavuse aruanne annab konsolideeritud ülevaate tõrgetest ja hoiatustest, mida teie "karbist-väljas" prognoosid võivad tekitada.</span><span class="sxs-lookup"><span data-stu-id="46bc7-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="46bc7-114">See annab ka soovitusi, kuidas mudeli tulemuslikkust parandada.</span><span class="sxs-lookup"><span data-stu-id="46bc7-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="46bc7-115">Aruanne on saadaval pärast seda, kui mudel on oma treeninguprotsessi lõpetanud.</span><span class="sxs-lookup"><span data-stu-id="46bc7-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="46bc7-116">See luuakse iga mudeli jaoks eraldi, olenemata sellest, kas see on edukalt lõpule viidud või mitte.</span><span class="sxs-lookup"><span data-stu-id="46bc7-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="46bc7-117">Praegu töötab see funktsioon ainult mudeli Transaction Churn puhul.</span><span class="sxs-lookup"><span data-stu-id="46bc7-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="46bc7-118">Vaata sisendandmete kasutatavusaruannet</span><span class="sxs-lookup"><span data-stu-id="46bc7-118">View the input data usability report</span></span>

<span data-ttu-id="46bc7-119">Pärast seda, kui "karbist väljas" mudel on läbinud oma koolitusetapi, vaadake aruannet.</span><span class="sxs-lookup"><span data-stu-id="46bc7-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="46bc7-120">Valige mudeli nime kõrval kolmikpunkt ja valige **Sisendandmete kasutatavuse aruanne**.</span><span class="sxs-lookup"><span data-stu-id="46bc7-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="46bc7-121">Valige mudeli olek ja valige külgpaanil käsk **Kuva sisendandmete kasutatavuse** aruanne.</span><span class="sxs-lookup"><span data-stu-id="46bc7-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="46bc7-122">Valige loendist üks mudelitest ja valige käsuribal **Sisendandmete kasutatavuse aruanne**.</span><span class="sxs-lookup"><span data-stu-id="46bc7-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="46bc7-123">Avage mudeli tulemuste leht ja valige käsuribal **Sisendandmete kasutatavuse aruanne**.</span><span class="sxs-lookup"><span data-stu-id="46bc7-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="46bc7-124">Sisendandmete kasutatavusaruande teave</span><span class="sxs-lookup"><span data-stu-id="46bc7-124">Information in the input data usability report</span></span>

<span data-ttu-id="46bc7-125">Aruande järgmised veerud sisaldavad kasulikku teavet mudeli andmete täiustamiseks.</span><span class="sxs-lookup"><span data-stu-id="46bc7-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Sisendandmete kasutatavuse aruande näide, milles on kuvatud tõrgete, hoiatuste ja soovitustega tabel.":::

- <span data-ttu-id="46bc7-127">Nimi: tõrke, hoiatuse või soovituse kirjeldav nimi.</span><span class="sxs-lookup"><span data-stu-id="46bc7-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="46bc7-128">Etapp: mudeli faas, treening või skoor, millele teave viitab.</span><span class="sxs-lookup"><span data-stu-id="46bc7-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="46bc7-129">Olek: teabe raskusaste (viga, hoiatus, soovitus).</span><span class="sxs-lookup"><span data-stu-id="46bc7-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="46bc7-130">Veeru nimi: olemi veerg, mida tuleb mudeli jõudluse parandamiseks muuta.</span><span class="sxs-lookup"><span data-stu-id="46bc7-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="46bc7-131">Oleku nimi: olemi nimi, mida tuleb mudeli jõudluse parandamiseks muuta.</span><span class="sxs-lookup"><span data-stu-id="46bc7-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="46bc7-132">Üksikasjad: tõrke, hoiatuse või soovituse üksikasjad.</span><span class="sxs-lookup"><span data-stu-id="46bc7-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="46bc7-133">Prognoosi värskendamine</span><span class="sxs-lookup"><span data-stu-id="46bc7-133">Refresh a prediction</span></span>

<span data-ttu-id="46bc7-134">Prognoose värskendatakse automaatselt [teie andmete värskendamiste ajakava](system.md#schedule-tab) järgi, mis on sätetes konfigureeritud.</span><span class="sxs-lookup"><span data-stu-id="46bc7-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="46bc7-135">Neid saab värskendada ka käsitsi.</span><span class="sxs-lookup"><span data-stu-id="46bc7-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="46bc7-136">Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="46bc7-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="46bc7-137">Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mida soovite värskendada.</span><span class="sxs-lookup"><span data-stu-id="46bc7-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="46bc7-138">Valige **Värskenda**.</span><span class="sxs-lookup"><span data-stu-id="46bc7-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="46bc7-139">Prognoosi kustutamine</span><span class="sxs-lookup"><span data-stu-id="46bc7-139">Delete a prediction</span></span>

<span data-ttu-id="46bc7-140">Prognoosi kustutamisel eemaldatakse ka selle väljundolem.</span><span class="sxs-lookup"><span data-stu-id="46bc7-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="46bc7-141">Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.</span><span class="sxs-lookup"><span data-stu-id="46bc7-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="46bc7-142">Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mida soovite kustutada.</span><span class="sxs-lookup"><span data-stu-id="46bc7-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="46bc7-143">Valige **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="46bc7-143">Select **Delete**.</span></span>
