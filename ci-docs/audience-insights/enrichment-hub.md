---
title: Koondatud kliendiprofiilide rikastamine
description: Kasutage võimalusi kliendiandmete rikastamiseks.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269463"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="50ccb-103">Kliendiprofiilide rikastamine (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="50ccb-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="50ccb-104">Kliendiandmete rikastamiseks saate kasutada andmeid allikatest, nagu Microsoft ja teised partnerid.</span><span class="sxs-lookup"><span data-stu-id="50ccb-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamisekeskuse leht":::

<span data-ttu-id="50ccb-106">Minge sihtrühmaülevaadetes jaotisse **Andmed** > **Rikastamine**, et töötada rikastamissuvanditega.</span><span class="sxs-lookup"><span data-stu-id="50ccb-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="50ccb-107">Rikastamiste loomiseks või redigeerimiseks peavad teil olema kaasautori või administraatori õigused.</span><span class="sxs-lookup"><span data-stu-id="50ccb-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="50ccb-108">Lisateavet vt teemast [Õigused](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="50ccb-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="50ccb-109">Vahekaardilt **Avastamine** leiate järgmised rikastamised.</span><span class="sxs-lookup"><span data-stu-id="50ccb-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="50ccb-110">[Tootemarke](enrichment-microsoft-graph.md) esitab Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="50ccb-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="50ccb-111">[Huvisid](enrichment-microsoft-graph.md) esitab Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="50ccb-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="50ccb-112">[Ettevõtte andmeid](enrichment-leadspace.md) esitab Leadspace</span><span class="sxs-lookup"><span data-stu-id="50ccb-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="50ccb-113">[Demograafilisi andmeid](enrichment-experian.md) esitab Experian</span><span class="sxs-lookup"><span data-stu-id="50ccb-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="50ccb-114">[Asukohaandmeid](enrichment-here.md) esitab HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="50ccb-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="50ccb-115">[Kohandatud andmed](enrichment-SFTP-custom-import.md) turvalise failiedastuse protokolli (SFTP) kaudu</span><span class="sxs-lookup"><span data-stu-id="50ccb-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="50ccb-116">Saate kuvada oma konfigureeritud rikastamisi ja redigeerida nende atribuute vahekaardil **Minu rikastamised**.</span><span class="sxs-lookup"><span data-stu-id="50ccb-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="50ccb-117">Olemasolevate rikastamiste haldamine</span><span class="sxs-lookup"><span data-stu-id="50ccb-117">Manage existing enrichments</span></span>

<span data-ttu-id="50ccb-118">Avage **Minu rikastamised**, et näha kõiki konfigureeritud rikastamisi.</span><span class="sxs-lookup"><span data-stu-id="50ccb-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="50ccb-119">Iga rikastamine on esindatud reana, mis sisaldab täiendavat teavet rikastamise kohta.</span><span class="sxs-lookup"><span data-stu-id="50ccb-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="50ccb-120">Saadaolevate suvandite kuvamiseks valige rikastamine.</span><span class="sxs-lookup"><span data-stu-id="50ccb-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="50ccb-121">Samuti saate suvandite kuvamiseks valida loendiüksuse kolmikpunkti (...).</span><span class="sxs-lookup"><span data-stu-id="50ccb-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Rikastamiste haldamise suvandid rikastamiste loendis":::

- <span data-ttu-id="50ccb-123">Rikastamise üksikasjade **Vaade** koos rikastatud kliendiprofiilide arvuga.</span><span class="sxs-lookup"><span data-stu-id="50ccb-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="50ccb-124">Rikastamise konfiguratsiooni **Redigeerimine**.</span><span class="sxs-lookup"><span data-stu-id="50ccb-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="50ccb-125">Rikastamise **käivitamine**, et värskendada kliendiprofiile uusimate andmetega.</span><span class="sxs-lookup"><span data-stu-id="50ccb-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="50ccb-126">Olemasoleva rikastamise **Desaktiveerimine**, et peatada selle automaatne värskendamine iga ajastatud värskendamisega.</span><span class="sxs-lookup"><span data-stu-id="50ccb-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="50ccb-127">Viimasest edukast värskendamisest pärinevad andmed jäävad jätkuvalt kättesaadavaks.</span><span class="sxs-lookup"><span data-stu-id="50ccb-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="50ccb-128">Passiivse rikastamise **Aktiveerimine**, et taaskäivitada automaatne värskendamine iga ajastatud värskendamisega.</span><span class="sxs-lookup"><span data-stu-id="50ccb-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="50ccb-129">Rikastamise **kustutamine**.</span><span class="sxs-lookup"><span data-stu-id="50ccb-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="50ccb-130">Saate korraga käivitada või desaktiveerida mitu rikastamist, valides need loendist.</span><span class="sxs-lookup"><span data-stu-id="50ccb-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="50ccb-131">Vaatamise ja redigeerimise suvandid ei ole saadaval hulgitoiminguna ja töötavad korraga ainult ühe rikastamisega.</span><span class="sxs-lookup"><span data-stu-id="50ccb-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]