---
title: Looge oma klientidest ühtne vaade
description: Läbige oma andmetega andmete ühendamise protsess, et luua konto või kliendiprofiilide ühtne koondandmestik.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304422"
---
# <a name="data-unification-overview"></a>Andmete koondamise ülevaade

Pärast [andmeallikate seadistamist](data-sources.md) saate andmed ühtlustada. Andmete ühendamine võimaldab teil ühendada üks kord erinevad andmeallikad üheks koondandmestikuks, mis pakub nendest andmetest ühtset vaadet.

Üksiktarbijatele (B-C), kus andmed on koondunud üksikisikute ümber, pakub ühendamine teie klientidest ühtset vaadet. Ärikontode (B-kuni B) puhul, kus andmed on koondunud kontode ümber, annab ühendamine teie kontodest ühtse ülevaate. [Kontaktide ühendamine (eelvaade)](data-unification-contacts.md) võimaldab nende kontode kontakte eraldi ühendada ja kontodega seostada.

Andmeid saab ühendada ühe või mitme olemiga.

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

Ühendamisprotsess vastendab kliendiandmed teie andmeallikatest, eemaldab duplikaadid, vastendab olemite andmed ja loob ühtse profiili. Ühendamine toimub järgmises järjekorras:

1. [Lähteväljad](map-entities.md) (varasema nimega Kaart): valige lähteväljade etapis olemid ja väljad, mida ühendamisprotsessi kaasata. Vastendage väljad levinud semantilise tüübiga, mis kirjeldab välja eesmärki.

1. [Duplikaatkirjed](remove-duplicates.md) (varem vastenduse osa): soovi korral määratlege etapis duplikaatkirjed, et eemaldada kliendikirjete duplikaatkirjed igast olemist.

1. [Vastendustingimused](match-entities.md) (varasema nimega Vastendamine): määratlege vastavusseviimise tingimuste etapis reeglid, mis ühtivad kliendikirjetega olemite vahel. Kui klient leitakse kahest või enamast olemist, luuakse üks konsolideeritud kirje iga olemi kõigi veergude ja andmetega.

1. [Ühtsed kliendiväljad](merge-entities.md) (varasema nimega Ühenda): määrake etapis Ühendatud kliendiväljad, millised lähteväljad tuleks kaasata, välistada või ühendada ühtseks kliendiprofiiliks.  

1. [Vaadake üle](review-unification.md) ja looge ühtne profiil.

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

Ühendamisprotsess vastendab kontoandmed teie andmeallikatest, eemaldab duplikaadid, vastendab olemite andmed ja loob ühtse profiili. Ühendamine toimub järgmises järjekorras:

1. [Lähteväljad](map-entities.md) (varasema nimega Kaart): valige lähteväljade etapis olemid ja väljad, mida konto ühendamise protsessi kaasata. Vastendage väljad levinud semantilise tüübiga, mis kirjeldab välja eesmärki.

1. [Kirjete duplikaatkirjed](remove-duplicates.md) (varem vastenduse osa): määratlege etapi duplikaatkirjed valikuliselt reeglid kontokirjete duplikaatfailide eemaldamiseks igast olemist.

1. [Vastendamistingimused](match-entities.md) (varem vastendatavad): määratlege vastavusseviimise tingimuste etapis reeglid, mis vastendavad kontokirjeid olemite vahel. Kui konto leitakse kahes või enamas olemis, luuakse üks konsolideeritud kirje kõigi veergude ja andmetega igast olemist.

1. [Ühtsed kliendiväljad](merge-entities.md) (varasema nimega Ühenda): määrake etapis Ühendatud kliendiväljad, millised lähteväljad tuleks kaasata, välistada või ühendada ühtseks kliendiprofiiliks.  

1. [Vaadake üle](review-unification.md) ja looge ühtne profiil.

Pärast kontode ühendamist saate soovi korral [nende kontode kontaktid ühendada (eelvaate)](data-unification-contacts.md) ja siduda ühendatud kontaktid ühendatud kontodega.

---

Pärast andmete ühendamist saate soovi korral teha järgmist.

- [Seadistage olemite](relationships.md) vahelised seosed keerukate segmentide loomiseks.
- [Rikastage oma andmeid](enrichment-hub.md), et saada oma klientide kohta rohkem statistikat.
- [Määratlege tegevused](activities.md) mõne allaneelatud atribuudi põhjal.
- [Koostage meetmed](measures.md) klientide käitumise ja äritegevuse tulemuslikkuse paremaks mõistmiseks.

[!INCLUDE [footer-include](includes/footer-banner.md)]
