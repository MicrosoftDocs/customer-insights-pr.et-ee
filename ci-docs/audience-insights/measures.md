---
title: Meetmete mõistmine ja haldamine
description: Vaadake, kuidas meetmed aitavad teie ettevõtte jõudlust analüüsida ja kajastada.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: c46fcc3baba1d6c92c2c0fe459a62277343cc0e4
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359768"
---
# <a name="measures-overview"></a>Mõõdude ülevaade

See aitab teil paremini mõista kliendi käitumist ja äritegevust. Nad vaatavad asjakohaseid [ühendatud profilide](data-unification.md) väärtusi. Näiteks soovib ettevõte näha, kui palju on *kogukulud kliendi kohta*, et mõista üksikkliendi ostuajalugu või mõõta *ettevõtte kogumüüki*, et aru saada kogu ettevõtte kogutaseme tuludest.  

Meetmed luuakse [mõõdu koostaja](measure-builder.md), erinevate operaatoritega andmepäringu platvormi ja lihtsate kaardistamisvõimaluste abil. See võimaldab filtreerida andmeid, rühmitada tulemusi, tuvastada [olemite seoseteid](relationships.md) ja kuvada väljundi eelvaadet. Eelmääratletud malle [saate](measure-templates.md) kasutada tavaliselt kasutatavate mõõdukondade tõhusaks konfigureerimiseks.

Kasutage äritegevuste plaanimiseks näitaja ehitajat, pärides kliendiandmeid ja väljastades ülevaateid. Näiteks *kogukulu ühe kliendi kohta* ja *kogutulu ühe kliendi kohta* loomine aitab tuvastada suure kulutamise, kuid suure tootlusega klientide rühm. Nende mõõdu põhjal saate [luua segmendi](segments.md), et juhtida järgmiseid parimaid toiminguid. 

## <a name="manage-your-measures"></a>Meetmete haldamine

Meetmete loendi leiate lehelt **Meetmed**.

Leiate teavet näidiku tüübi, autori, loomise kuupäeva, staatuse ja oleku kohta. Kui valite loendist soovitud näitaja, saate vaadata väljundi eelversiooni ja laadida alla CSV-faili.

Kõigi oma meetmete korraga värskendamiseks valige **Värskenda kõik** ilma kindlat meedet valimata.

:::image type="content" source="media/measure-actions.png" alt-text="Toimingud üksikute näitajate haldamiseks.":::

Valige loendist soovitud näitaja järgmiste suvandite jaoks.

- Valige meetme nimi, et näha selle üksikasju.
- Meetme konfiguratsiooni **Redigeerimine**.
- **Värskendage** näitajat, võttes aluseks värskeimad andmed.
- Meetme **Ümbernimetamine**.
- Meetme **Kustutamine**.
- **Aktiveeri** või **Inaktiveeri**. Passiivseid näitajad ei värskendata [kavandatud värskenduse](system.md#schedule-tab) ajal.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="next-step"></a>Järgmine etapp

Olemasolevate näitajate abil saate luua [kliendisegmendi](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
