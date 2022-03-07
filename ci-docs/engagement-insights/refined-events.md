---
title: Täpsemate sündmuste loomine ja muutmine
description: Täpsemate sündmuste loomine ja muutmine.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034769"
---
# <a name="create-and-modify-refined-events"></a>Täpsemate sündmuste loomine ja muutmine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Sündmus on andmed, mis tähistab kasutaja käitumist, nt tegevusi veebisaidil.

- *Põhi* sündmuse kirjed, kui kasutaja vaatab lehte (vaata sündmust) või suhtleb sisuga (toimingusündmus).
- *Täpsustatud* sündmus on baassündmuse virtuaalvaade. Sündmuste määratlemiseks eemaldage ja lisage atribuudid või filtreerige sündmused atribuudiväärtuste põhjal.

Kasutage nende sündmuste funktsiooni, et vähendada [eksporti](export-events.md) või eemaldada atribuute, mis pole eksportimiseks vajalikud.

## <a name="create-refined-events"></a>Täpsustatud sündmuste loomine

Baassündmusest täpsustatud sündmuse loomiseks on kolm võimalust. 

1. Minge **Andmed**> **Sündmused** ja valige üks järgmistest suvanditest:
    - Valige **Uued sündmused** ja seejärel valige **Täpsustatud sündmuste loomine**.
    - Valige baassündmus, et avada üksikasjalik vaade ja valida **Täpsustatud sündmuse loomine** ülemisest menüüst.
    - Valige **Veel [...]** kiirmenüü avamiseks baassündmuse jaoks. Seejärel valige **Täpsustatud sündmuste loomine**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Suvandid loomaks rafineeritud sündmuseid.":::

1. Sisestage dialoogis **Täpsustatud sündmuse loomine** järgmine teave:

- Uue sündmuse loomisel **Baassünddmuste** ripploendist soovitud sündmus.
- Sisestage **Täpsustatud sünmuse kuvatav nimi** väljale.
- Soovi korral värskendage **Tegelikku nime** tühikuid kasutamata.

3. Valige **Loo** sätete kuvamiseks.

1. Täpsustatud sündmuste üksikasjalikuks vaates valige **Lisa ja eemalda atribuudid**, et avada paanil **Redigeeri seadeid**. 

1. Märkige ruudud, mida soovite kuvada, ja atribuudid, mida soovite peita. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Täpsustatud sündmuste atribuutide redigeerimine.":::

1. Valige **Kinnita** valiku kuvamiseks.

1. Valige **Salvesta** konfiguratsiooni salvestamiseks.

## <a name="edit-refined-events"></a>Täpsustatud sündmuste redigeerimine

Saate muuta täpsustatud sündmuse nime ja atribuute.

### <a name="edit-event-name"></a>Redigeeri sündmuse nime

1. Mine **Andmed** > **Sündmused**. 
1. Valige **Veel [...]** sündmuse jaoks ja valige **Redigeeri nime**.
1. Värskendage sündmuse nime ja valige **Muuda nime**.

### <a name="edit-selected-properties"></a>Valitud atribuutide redigeerimine

1. Minge **Andmed** > **Sündmused** ja valige täpsustatud sündmused et avada üksikasjalikum vaade.
1. Valige **Lisa ja eemalda atribuudid**. 
1. Muutke märkeruute.
1. Valige **Kinnita** ja seejärel **Salvesta** muudatuste rakendamiseks.

Lisateavet sündmuste eksportimise kohta leiate teemast [Sündmuste eksportimine](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
