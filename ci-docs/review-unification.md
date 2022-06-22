---
title: Andmete ühendamise ülevaatamine
description: Vaadake üle andmete ühendamise etapid, looge ühtsed kliendiprofiilid ja vaadake tulemused üle
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
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844081"
---
# <a name="review-data-unification"></a>Andmete ühendamise ülevaatamine

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

See viimane samm ühendamisprotsessis näitab protsessi etappide kokkuvõtet ja annab võimaluse teha muudatusi enne ühtse profiili loomist.

:::image type="content" source="media/m3_review.png" alt-text="Kuvatõmmis kliendiprofiilide ülevaatamisest ja loomisest.":::

## <a name="review-the-data-unification-steps"></a>Andmete ühendamise etappide ülevaatamine

1. **Läbivaatuseks ja muudatuste tegemiseks valige** redigeeri mis tahes andmete ühendamise etapis.

1. Kui olete oma valikutega rahul, valige **Loo kliendiprofiilid**. Leht **Ühenda kuvatakse** ühtse kliendiprofiili loomise ajal. Kõigil paanidel peale **allika kuvatakse** **oleku järjekord või** **värskendamine**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Kuvatõmmis lehest Ühendamine, mille paanid näitavad järjekorda või värskendamist.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Ühendamise algoritm võtab aega ja te ei saa konfiguratsiooni muuta enne, kui see on lõpule viidud. Kui ühendamisprotsess on lõpule viidud, kuvatakse *ühtne kliendiprofiili olem nimega* Klient **jaotises Profiilid** lehel **Olemid**. Esimene edukas ühendamise käivita loob ühtse *kliendiolemi*. Kõik järgnevad jooksud laiendavad seda olemit.

## <a name="review-the-results-of-data-unification"></a>Andmete ühendamise tulemuste ülevaatamine

Pärast ühendamist **kuvatakse lehel Andmete** > **ühendamine** ühendatud kliendiprofiilide arv. Iga paanil kuvatava ühendamisprotsessi iga etapi tulemused. Näiteks **väljadel** Allikas kuvatakse vastendatud atribuutide (väljade) arv ja **Duplikaatkirjete** arv näitab leitud duplikaatkirjete arvu.

:::image type="content" source="media/m3_unified.png" alt-text="Kuvatõmmis lehest Andmete ühendamine pärast andmete ühendamist.":::

> [!TIP]
> Paanil **Sobivad tingimused** kuvatakse ainult siis, kui on valitud mitu olemit.

Soovitame teil tulemused üle vaadata, eriti mängureeglite [kvaliteet](data-unification-update.md#manage-match-rules), ja vajadusel neid täpsustada.

Vajadusel [muutke ühendamissätteid](data-unification-update.md) ja käivitage ühtne profiil uuesti.

## <a name="next-step"></a>Järgmine etapp

Konfigureerige [tegevusi](activities.md), [rikastamist](enrichment-hub.md), [seoseid](relationships.md) või [meetmeid](measures.md), et saada oma klientide kohta rohkem teavet.

[!INCLUDE[footer-include](includes/footer-banner.md)]
