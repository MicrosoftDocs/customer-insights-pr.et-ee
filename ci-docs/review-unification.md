---
title: Andmete ühendamise ülevaatamine
description: Vaadake üle andmete ühendamise etapid, looge ühtsed kliendiprofiilid ja vaadake tulemused üle
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742973"
---
# <a name="review-data-unification"></a>Andmete ühendamise ülevaatamine

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

See viimane samm ühendamisprotsessis näitab protsessi etappide kokkuvõtet ja annab võimaluse teha muudatusi enne ühtse profiili loomist.

:::image type="content" source="media/m3_review.png" alt-text="Kuvatõmmis kliendiprofiilide ülevaatamisest ja loomisest.":::

## <a name="review-the-data-unification-steps"></a>Andmete ühendamise etappide ülevaatamine

1. **Läbivaatuseks ja muudatuste tegemiseks valige** redigeeri mis tahes andmete ühendamise etapis.

1. Kui olete oma valikutega rahul, valige **Loo kliendiprofiilid**. Leht **Ühenda kuvatakse** ühtse kliendiprofiili loomise ajal. Ühendamise algoritm võtab aega ja te ei saa konfiguratsiooni muuta enne, kui see on lõpule viidud.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Kui ühendamisprotsess on lõpule viidud, kuvatakse *ühtne kliendiprofiili olem nimega* Klient **jaotises Profiilid** lehel **Olemid**. Esimene edukas ühendamise käivita loob ühtse *kliendiolemi*. Kõik järgnevad jooksud laiendavad seda olemit.

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
