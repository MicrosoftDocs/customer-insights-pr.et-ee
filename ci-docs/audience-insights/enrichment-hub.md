---
title: Koondatud kliendiprofiilide rikastamine
description: Kasutage võimalusi kliendiandmete rikastamiseks.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667089"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Kliendiprofiilide rikastamine (eelvaade)

Kliendiandmete rikastamiseks saate kasutada andmeid allikatest, nagu Microsoft ja teised partnerid.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Rikastamisekeskuse leht":::

Minge sihtrühmaülevaadetes jaotisse **Andmed** > **Rikastamine**, et töötada rikastamissuvanditega.    
Rikastamiste loomiseks või redigeerimiseks peavad teil olema kaasautori või administraatori õigused. Lisateavet vt teemast [Õigused](permissions.md).

Vahekaardilt **Avastamine** leiate järgmised rikastamised.

- [Tootemarke](enrichment-microsoft-graph.md) esitab Microsoft Graph
- [Huvisid](enrichment-microsoft-graph.md) esitab Microsoft Graph
- [Ettevõtte andmeid](enrichment-leadspace.md) esitab Leadspace
- [Demograafilisi andmeid](enrichment-experian.md) esitab Experian
- [Asukohaandmeid](enrichment-here.md) esitab HERE Technologies
- [Kohandatud andmed](enrichment-SFTP-custom-import.md) turvalise failiedastuse protokolli (SFTP) kaudu

Saate kuvada oma konfigureeritud rikastamisi ja redigeerida nende atribuute vahekaardil **Minu rikastamised**.

## <a name="manage-existing-enrichments"></a>Olemasolevate rikastamiste haldamine

Avage **Minu rikastamised**, et näha kõiki konfigureeritud rikastamisi. Iga rikastamine on esindatud reana, mis sisaldab täiendavat teavet rikastamise kohta.

Saadaolevate suvandite kuvamiseks valige rikastamine. Samuti saate suvandite kuvamiseks valida loendiüksuse kolmikpunkti (...).

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Rikastamiste haldamise suvandid rikastamiste loendis":::

- Rikastamise üksikasjade **Vaade** koos rikastatud kliendiprofiilide arvuga.
- Rikastamise konfiguratsiooni **Redigeerimine**.
- Rikastamise **käivitamine**, et värskendada kliendiprofiile uusimate andmetega.
- Olemasoleva rikastamise **Desaktiveerimine**, et peatada selle automaatne värskendamine iga ajastatud värskendamisega. Viimasest edukast värskendamisest pärinevad andmed jäävad jätkuvalt kättesaadavaks. Passiivse rikastamise **Aktiveerimine**, et taaskäivitada automaatne värskendamine iga ajastatud värskendamisega.
- Rikastamise **kustutamine**.

Saate korraga käivitada või desaktiveerida mitu rikastamist, valides need loendist. Vaatamise ja redigeerimise suvandid ei ole saadaval hulgitoiminguna ja töötavad korraga ainult ühe rikastamisega.
