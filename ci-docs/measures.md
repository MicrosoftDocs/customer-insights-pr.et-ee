---
title: Meetmete ülevaade
description: Siit saate teada, kuidas meetmed aitavad teie ettevõtte tulemuslikkust analüüsida ja kajastada.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170815"
---
# <a name="measures-overview"></a>Meetmete ülevaade

See aitab teil paremini mõista kliendi käitumist ja äritegevust. Nad vaatavad asjakohaseid [ühendatud profilide](data-unification.md) väärtusi. Näiteks soovib ettevõte näha, kui palju on *kogukulud kliendi kohta*, et mõista üksikkliendi ostuajalugu või mõõta *ettevõtte kogumüüki*, et aru saada kogu ettevõtte kogutaseme tuludest.

Saate luua meetmeid äritegevuse kavandamiseks, küsides kliendiandmeid ja ekstraktides ülevaateid. Näiteks looge kogukulu kliendi kohta ja *kogutulu mõõdik* kliendi *kohta*, et aidata tuvastada klientide rühma, kellel on suured kulutused, kuid suur tootlus. Seejärel looge nende meetmete põhjal segment [,](segments.md) et juhtida järgmisi parimaid toiminguid.

## <a name="create-a-measure"></a>Meetme loomine

Valige, kuidas luua mõõt oma sihtrühma põhjal.

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

- Nullist mõõtu ehitajaga: [Ehitage ise](measure-builder.md).
- Sageli kasutatavatest mõõtudest: [kasutage eelmääratletud malle](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

Nullist mõõtu ehitajaga: [Ehitage ise](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Olemasolevate meetmete haldamine

Minge **lehele Mõõdud**, et vaadata loodud mõõtusid, nende olekut, mõõtude tüüpi ja viimast korda, millal andmeid värskendati. Saate sortida mõõtude loendi mis tahes veeru järgi või kasutada otsinguvälja, et leida mõõt, mida soovite hallata.

Valige mõõdu kõrval, et vaadata saadaolevaid toiminguid. Valige mõõdu nimi, et vaadata väljundi eelvaadet ja laadida alla CSV-fail.

:::image type="content" source="media/measures-actions.png" alt-text="Toimingud üksikute näitajate haldamiseks."lightbox="media/measures-actions.png":::

- **Redigeerige** mõõtu selle atribuutide muutmiseks.
- **Värskendage** mõõtu, et kaasata uusimad andmed.
- Meetme **Ümbernimetamine**.
- **Aktiveerige** või **inaktiveerige** meede. Passiivseid mõõtühikuid ei värskendata ajastatud värskendamise [ajal](system.md#schedule-tab) ja nende olekuks on **märgitud** vahelejäetud **olek**, mis näitab, et värskendamist isegi ei proovitud.
- **Silt** mõõdu siltide [haldamiseks](work-with-tags-columns.md#manage-tags).
- Meetme **Kustutamine**.
- **Veerud** [kuvatavate veergude](work-with-tags-columns.md#customize-columns) kohandamiseks.
- **Filtreerige** siltide [filtreerimiseks](work-with-tags-columns.md#filter-on-tags).
- **Otsige nime**, et otsida mõõdunime järgi.

## <a name="refresh-measures"></a>Meetmete värskendamine

Meetmeid saab värskendada automaatse ajakava alusel või soovi korral käsitsi värskendada. Ühe või mitme mõõdu käsitsi värskendamiseks valige need ja valige **Värskenda**. Automaatse värskendamise ajastamiseks [minge jaotisse](system.md#schedule-tab) Haldussüsteemi **·** > **ajakava** > **.**

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
