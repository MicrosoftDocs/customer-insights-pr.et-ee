---
title: Andmete ühendamise ülevaatamine
description: Andmete ühendamise etappide ülevaatamine, ühtsete kliendiprofiilide loomine ja tulemuste ülevaatamine
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303962"
---
# <a name="review-data-unification"></a>Andmete ühendamise ülevaatamine

Vaadake üle muudatuste kokkuvõte, looge ühtne profiil ja vaadake tulemused üle.

## <a name="review-and-create-customer-profiles"></a>Kliendiprofiilide ülevaatamine ja loomine

See ühendamisprotsessi viimane etapp näitab protsessi etappide kokkuvõtet ja annab võimaluse teha muudatusi enne ühtse profiili loomist.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Kuvatõmmis kliendiprofiilide ülevaatamisest ja loomisest.":::

1. Mis tahes andmete ühendamise etapis valige **Redigeeri**, et need üle vaadata ja muudatusi teha.

1. Kui olete oma valikutega rahul, valige **Loo kliendiprofiilid** (või **Loo kontoprofiilid** B-st B-ni). Leht **Ühenda** kuvatakse ühtse kliendiprofiili loomise ajal.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Kuvatõmmis lehest Ühenda paanid, kus on kuvatud järjestatud või värskendatud paanid.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Ühendamise algoritmi lõpuleviimine võtab aega ja te ei saa konfiguratsiooni muuta enne, kui see on lõpule viidud.

## <a name="view-the-results-of-data-unification"></a>Andmete ühendamise tulemuste vaatamine

Pärast ühendamist **kuvatakse lehel Andmete** > **ühendamine** ühendatud kliendiprofiilide (või B-B kontoprofiilide) arv. Ühendamisprotsessi iga etapi tulemused kuvatakse igal plaadil. Näiteks **allikaväljad** näitavad vastendatud atribuutide (väljade) arvu ja **duplikaatkirjed** leitud duplikaatkirjete arvu.

:::image type="content" source="media/m3_unified.png" alt-text="Kuvatõmmis lehest Andmete ühendamine pärast andmete ühendamist.":::

> [!TIP]
> Paan **Sobitamistingimused** kuvatakse ainult siis, kui on valitud mitu olemit.

Soovitame teil tulemused üle vaadata, eriti mängureeglite [kvaliteet](data-unification-update.md#manage-match-rules), ja neid vajaduse korral täpsustada.

Vajadusel [muutke ühendamissätteid](data-unification-update.md) ja käivitage ühtne profiil uuesti.

### <a name="verify-output-entities-from-data-unification"></a>Väljundolemite kontrollimine andmete ühendamisest

Väljundolemite kontrollimiseks minge jaotisse **Andmeüksused** > **·**.

Ühtne kliendiprofiili olem nimega *Klient* kuvatakse jaotises **Profiilid**. Esimene edukas ühendamiskäivitus loob ühtse *kliendi* olemi. Kõik järgnevad jooksud laiendavad seda olemit.

Duplikatsiooni- ja liitmisolemid luuakse ja kuvatakse jaotises **Süsteem**. Iga lähteolemi jaoks luuakse dubleeritud olem nimega **Deduplication_DataSource_Entity**. Olem **ConflationMatchPairs** sisaldab teavet olemitevaheliste vastete kohta.

Pöördduplitseeritava väljundi olem sisaldab järgmist teavet:
- ID-d/võtmed
  - Primaarvõtme ja alternatiivse ID väljad. Väli Alternatiivne ID koosneb kõigist kirje jaoks tuvastatud alternatiivsetest ID-dest.
  - Deduplication_GroupId väli näitab olemi sees tuvastatud rühma või klastrit, mis rühmitab kõik sarnased kirjed määratud pöördduplitseerimise väljade põhjal. Seda kasutatakse süsteemi töötlemise eesmärkidel. Kui pole määratud pole manuaalseid pöördduplitseerimise reegleid ja süsteemi määratletud pöördduplitseerimise väljade subjektireeglid kehtivad, ei pruugi te seda välja pöördduplitseerimise väljundi olemist leida.
  - Deduplication_WinnerId: see väli sisaldab tuvastatud rühma või klastri võitja ID-d. Kui Deduplication_WinnerId on sama, mis kirje primaarvõtme väärtus, tähendab see, et kirje on võitja kirje.
- Väljad, mida kasutatakse pöördduplitseerimise reeglite määratlemiseks.
- Reeglid ja punktisumma väljad, mis tähistavad rakendatavaid pöördduplitseerimise reegleid ja millist punktisummat tagastas sobitusalgoritm.

## <a name="next-step"></a>Järgmine etapp

- B-to-B puhul tehke [soovi korral kontaktide ühendamine](data-unification-contacts.md).

- B-to-C puhul konfigureerige [tegevusi](activities.md), [rikastamisi](enrichment-hub.md), [seoseid](relationships.md) või [meetmeid](measures.md), et saada oma klientide kohta rohkem teavet.

[!INCLUDE[footer-include](includes/footer-banner.md)]
