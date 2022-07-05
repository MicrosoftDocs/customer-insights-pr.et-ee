---
title: Andmete koondamise ülevaade
description: Läbige andmete ühendamise protsess oma andmetega, et luua ühtne kliendiprofiilide ühtne andmekogum.
ms.date: 05/10/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: v-wendysmith
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: 0dbc3b2c75365e94758a1b6330e8cb557e6bd768
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082215"
---
# <a name="data-unification-overview"></a>Andmete koondamise ülevaade

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Pärast [andmeallikate seadistamist](data-sources.md) saate andmed ühtlustada. Andmete ühendamine võimaldab teil ühendada kord erinevad andmeallikad üheks põhiandmestikuks, mis pakub nendest andmetest ühtset ülevaadet. Üksiktarbijatele (B-C), kus andmed keskenduvad üksikisikutele, pakub ühendamine teie klientidest ühtset ülevaadet. Ärikontode (B-B) puhul, kus andmed keskenduvad kontodele, annab ühendamine teie kontodele ühtse ülevaate.

Andmeid saab ühendada ühes olemis või mitmes olemis. Ühendamine toimub järgmises järjekorras:

1. [Lähteväljad](map-entities.md) (varasema nimega Kaart): lähteväljade etapis valige ühendamisprotsessi kaasamiseks olemid ja väljad. Vastenda väljad ühise semantilise tüübiga, mis kirjeldab välja eesmärki.

1. [Duplikaatkirjed](remove-duplicates.md) (varem vaste osa): duplikaatkirjete etapis määratlege valikuliselt reeglid, et eemaldada duplikaatkliendikirjed igast olemist.

1. [Sobivad tingimused](match-entities.md) (varasema nimega Vastendamine): määratlege vastavate tingimuste etapis reeglid, mis vastavad kliendikirjetele olemite vahel. Kui klient leitakse kahest või enamast olemist, luuakse üks konsolideeritud kirje kõigi veergude ja andmetega igast olemist.

1. [Ühtsed kliendiväljad](merge-entities.md) (varasema nimega Ühendamine): määrake ühtses kliendiväljade etapis, millised lähteväljad tuleks kaasata, välistada või ühendada ühtseks kliendiprofiiliks.  

1. [Vaadake üle](review-unification.md) ja looge ühtne profiil.

Pärast andmete ühendamise lõpetamist saate soovi korral teha järgmist.

- [Saate keerukate segmentide loomiseks häälestada olemite](relationships.md) vahelisi seoseid.
- [Rikastage oma andmeid](enrichment-hub.md), et saada oma klientide kohta laiemat teavet.
- [Määratlege tegevused](activities.md) mõnest allaneelatud atribuudist.
- [Ehitage meetmeid](measures.md), et paremini mõista klientide käitumist ja äritulemusi.

[!INCLUDE [footer-include](includes/footer-banner.md)]
