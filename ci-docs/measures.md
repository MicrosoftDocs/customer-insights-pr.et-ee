---
title: Meetmete ülevaade
description: Vaadake, kuidas meetmed aitavad analüüsida ja kajastada teie ettevõtte tulemuslikkust.
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
ms.openlocfilehash: 880c06bffcfa269151d96cb4c597eed4832fc61b
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083118"
---
# <a name="measures-overview"></a>Meetmete ülevaade

See aitab teil paremini mõista kliendi käitumist ja äritegevust. Nad vaatavad asjakohaseid [ühendatud profilide](data-unification.md) väärtusi. Näiteks soovib ettevõte näha, kui palju on *kogukulud kliendi kohta*, et mõista üksikkliendi ostuajalugu või mõõta *ettevõtte kogumüüki*, et aru saada kogu ettevõtte kogutaseme tuludest.  

Meetmed luuakse [mõõtekoosturi](measure-builder.md), erinevate operaatoritega andmepäringu platvormi ja lihtsate kaardistamisvõimaluste abil. See võimaldab filtreerida andmeid, rühmitada tulemusi, tuvastada [olemite seoseteid](relationships.md) ja kuvada väljundi eelvaadet. Tavaliselt kasutatavate meetmete tõhusaks konfigureerimiseks saate [kasutada eelmääratletud malle](measure-templates.md).

Kasutage äritegevuste plaanimiseks näitaja ehitajat, pärides kliendiandmeid ja väljastades ülevaateid. Näiteks *kogukulu ühe kliendi kohta* ja *kogutulu ühe kliendi kohta* loomine aitab tuvastada suure kulutamise, kuid suure tootlusega klientide rühm. [Saate luua nende meetmete põhjal segmendi](segments.md), et juhtida parimaid toiminguid.

## <a name="manage-your-measures"></a>Meetmete haldamine

Meetmete loendi leiate lehelt **Meetmed**.

Leiate teavet näidiku tüübi, autori, loomise kuupäeva, staatuse ja oleku kohta. Kui valite loendist soovitud näitaja, saate vaadata väljundi eelversiooni ja laadida alla CSV-faili.

:::image type="content" source="media/measures-actions.png" alt-text="Toimingud üksikute näitajate haldamiseks."lightbox="media/measures-actions.png":::

Mõõdu valimisel on saadaval järgmised toimingud.

- Meetme konfiguratsiooni **Redigeerimine**.
- **Duplikaat** mõõt. Saate selle atribuute kohe redigeerida või lihtsalt duplikaadi salvestada.
- **Värskendage** näitajat, võttes aluseks värskeimad andmed. Kõigi meetmete samaaegseks värskendamiseks valige kõik mõõdud ja **värskendage**.
- Meetme **Ümbernimetamine**.
- **Aktiveeri** või **Inaktiveeri**. Passiivseid näitajad ei värskendata [kavandatud värskenduse](system.md#schedule-tab) ajal.
- **Silt** [segmendi siltide](work-with-tags-columns.md#manage-tags) haldamiseks.
- Meetme **Kustutamine**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Järgmine etapp

Olemasolevate näitajate abil saate luua [kliendisegmendi](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
