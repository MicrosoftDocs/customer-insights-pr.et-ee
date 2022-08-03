---
title: Andmete ühendamise ülevaatamine
description: Andmete ühendamise etappide ülevaatamine, ühtsete kliendiprofiilide loomine ja tulemuste ülevaatamine
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139572"
---
# <a name="review-data-unification"></a>Andmete ühendamise ülevaatamine

See ühendamisprotsessi viimane etapp näitab protsessi etappide kokkuvõtet ja annab võimaluse teha muudatusi enne ühtse profiili loomist.

:::image type="content" source="media/m3_review.png" alt-text="Kuvatõmmis kliendiprofiilide ülevaatamisest ja loomisest.":::

## <a name="review-the-data-unification-steps"></a>Andmete ühendamise etappide ülevaatamine

1. Mis tahes andmete ühendamise etapis valige **Redigeeri**, et need üle vaadata ja muudatusi teha.

1. Kui olete oma valikutega rahul, valige **Loo kliendiprofiilid**. Leht **Ühenda** kuvatakse ühtse kliendiprofiili loomise ajal. Kõigil paanidel, välja arvatud **allikaväljadel**, on **kuvatud** järjestatud või **värskendav olek**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Kuvatõmmis lehest Ühenda paanid, kus on kuvatud järjestatud või värskendatud paanid.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Ühendamise algoritmi lõpuleviimine võtab aega ja te ei saa konfiguratsiooni muuta enne, kui see on lõpule viidud. Kui ühendamisprotsess on lõpule viidud, kuvatakse *ühtne kliendiprofiili olem nimega* Klient **lehel** Olem **jaotises Profiilid**. Esimene edukas ühendamiskäivitus loob ühtse *kliendi* olemi. Kõik järgnevad jooksud laiendavad seda olemit.

## <a name="review-the-results-of-data-unification"></a>Andmete ühendamise tulemuste ülevaatamine

Pärast ühendamist **kuvatakse lehel Andmete** > **ühendamine** ühendatud kliendiprofiilide arv. Ühendamisprotsessi iga etapi tulemused kuvatakse igal plaadil. Näiteks **allikaväljad** näitavad vastendatud atribuutide (väljade) arvu ja **duplikaatkirjed** leitud duplikaatkirjete arvu.

:::image type="content" source="media/m3_unified.png" alt-text="Kuvatõmmis lehest Andmete ühendamine pärast andmete ühendamist.":::

> [!TIP]
> Paan **Sobitamistingimused** kuvatakse ainult siis, kui on valitud mitu olemit.

Soovitame teil tulemused üle vaadata, eriti mängureeglite [kvaliteet](data-unification-update.md#manage-match-rules), ja neid vajaduse korral täpsustada.

Vajadusel [muutke ühendamissätteid](data-unification-update.md) ja käivitage ühtne profiil uuesti.

## <a name="next-step"></a>Järgmine etapp

Konfigureerige tegevusi, rikastamist [,](activities.md) suhteid või [mõõdikuid](enrichment-hub.md)[, et saada oma klientide kohta rohkem teavet.](relationships.md)[...](measures.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
