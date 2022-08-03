---
title: Andmete koondamise ülevaade
description: Läbige oma andmetega andmete ühendamise protsess, et luua ühtne andmestik ühtsetest kliendiprofiilidest.
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
ms.openlocfilehash: 766e688cb80c50a0d620943f87b76eb84a2fb89a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139480"
---
# <a name="data-unification-overview"></a>Andmete koondamise ülevaade

Pärast [andmeallikate seadistamist](data-sources.md) saate andmed ühtlustada. Andmete ühendamine võimaldab teil ühendada üks kord erinevad andmeallikad üheks koondandmestikuks, mis pakub nendest andmetest ühtset vaadet. Üksiktarbijatele (B-C), kus andmed on koondunud üksikisikute ümber, pakub ühendamine teie klientidest ühtset vaadet. Ärikontode (B-kuni B) puhul, kus andmed on koondunud kontode ümber, annab ühendamine teie kontodest ühtse ülevaate.

Andmeid saab ühendada ühe või mitme olemiga. Ühendamine toimub järgmises järjekorras:

1. [Lähteväljad](map-entities.md) (varasema nimega Kaart): valige lähteväljade etapis olemid ja väljad, mida ühendamisprotsessi kaasata. Vastendage väljad levinud semantilise tüübiga, mis kirjeldab välja eesmärki.

1. [Duplikaatkirjed](remove-duplicates.md) (varem vastenduse osa): soovi korral määratlege etapis duplikaatkirjed, et eemaldada kliendikirjete duplikaatkirjed igast olemist.

1. [Vastendustingimused](match-entities.md) (varasema nimega Vastendamine): määratlege vastavusseviimise tingimuste etapis reeglid, mis ühtivad kliendikirjetega olemite vahel. Kui klient leitakse kahest või enamast olemist, luuakse üks konsolideeritud kirje iga olemi kõigi veergude ja andmetega.

1. [Ühtsed kliendiväljad](merge-entities.md) (varasema nimega Ühenda): määrake etapis Ühendatud kliendiväljad, millised lähteväljad tuleks kaasata, välistada või ühendada ühtseks kliendiprofiiliks.  

1. [Vaadake üle](review-unification.md) ja looge ühtne profiil.

Pärast andmete ühendamist saate soovi korral teha järgmist.

- [Seadistage olemite](relationships.md) vahelised seosed keerukate segmentide loomiseks.
- [Rikastage oma andmeid](enrichment-hub.md), et saada oma klientide kohta rohkem statistikat.
- [Määratlege tegevused](activities.md) mõne allaneelatud atribuudi põhjal.
- [Koostage meetmed](measures.md) klientide käitumise ja äritegevuse tulemuslikkuse paremaks mõistmiseks.

[!INCLUDE [footer-include](includes/footer-banner.md)]
