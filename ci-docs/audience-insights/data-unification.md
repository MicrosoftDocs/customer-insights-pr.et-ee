---
title: Andmete ühtlustamine
description: Õppige, kuidas koondada valmendatud andmeid.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405530"
---
# <a name="data-unification"></a><span data-ttu-id="9b441-103">Andmete ühtlustamine</span><span class="sxs-lookup"><span data-stu-id="9b441-103">Data unification</span></span>

<span data-ttu-id="9b441-104">Pärast [andmeallikate seadistamist](data-sources.md) saate andmed ühtlustada.</span><span class="sxs-lookup"><span data-stu-id="9b441-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="9b441-105">Andmete ühendamisel on kolm etappi: **Kaardistamine**, **Vastendamine** ja **Ühendamine**.</span><span class="sxs-lookup"><span data-stu-id="9b441-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="9b441-106">Andmete ühendamise protsess võimaldab teil ühendada ühekordse erinevusega andmeallikad üheks põhiandmekogumiks, mis pakub klientidele ühendatud vaadet.</span><span class="sxs-lookup"><span data-stu-id="9b441-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="9b441-107">Ühendamise etapid on kohustuslikud ja need tehakse järgmises järjestuses.</span><span class="sxs-lookup"><span data-stu-id="9b441-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="9b441-108">Vastenda</span><span class="sxs-lookup"><span data-stu-id="9b441-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="9b441-109">Match</span><span class="sxs-lookup"><span data-stu-id="9b441-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="9b441-110">Ühendamine</span><span class="sxs-lookup"><span data-stu-id="9b441-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="9b441-111">Pärast andmete ühendamise lõpuleviimist saate soovi korral</span><span class="sxs-lookup"><span data-stu-id="9b441-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="9b441-112">[seadistada olemitevahelised seosed](relationships.md), et luua keerukaid segmente,</span><span class="sxs-lookup"><span data-stu-id="9b441-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="9b441-113">[rikastada oma andmeid](enrichment-hub.md), et saada oma klientide kohta paremat ülevaadet,</span><span class="sxs-lookup"><span data-stu-id="9b441-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="9b441-114">[määratleda tegevusi](activities.md) mõnest valmendatud atribuudist</span><span class="sxs-lookup"><span data-stu-id="9b441-114">[define activities](activities.md) from some of the ingested attributes</span></span>
