---
title: Segmentide nõusolekureeglite aktiveerimine
description: Nõusolekuandmete linkimiseks ja nõusolekukontrollide aktiveerimiseks vaatajaskonna ülevaates järgige neid juhiseid. Administraator võib keelata ka nõusolekukontrollid.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4b55c82229b1a6189c0dd67d145386344286df8a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227488"
---
# <a name="activate-consent-rules"></a>Nõusolekureeglite aktiveerimine

Nõusolekukeskus [(eelvaade)](../consent-management/overview.md) aitab teil ühtlustada eri allikatest pärinevaid nõusolekuandmeid. Nõusoleku vaikekontrollide rakendamiseks kasutage ühtset *nõusoleku* olemit. Pärast nõusolekuandmete importimist nõusolekukeskusesse ja andmete *reeglite konfigureerimist sünkroonitakse olem Nõusoleku* olem automaatselt vaatajaskonna statistikaga.

## <a name="enable-consent-checks"></a>Nõusolekukontrollide lubamine

Nõusolekukeskusesse (eelvaade) imporditud nõusolekuandmete ja seadistatud reeglite abil saate lubada nõusolekukontrolli. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Nõusoleku vahekaart vaatajaskonna ülevaatesätetes koos aktiveeritud nõusolekuandmetega.":::

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Süsteem**.

1. Valige **vahekaart Nõusolek (eelvaade).**

1. **Määrake jaotises Nõusolekukontrollide** lubamine kõigi lubatavate alade tumblernupp **Sees**.

1. **Märkige ruut Luba vaikimisi nõusolekureeglite** alistamine, et eemaldada konkreetsele segmendile jõustatud vaikimisi nõusolekukontrollid. 

1. Valige rippmenüüst, kus soovite alistamise lubada.     

1. **Valige jaotises Kliendiprofiilidega** nõusoleku linkimine atribuut, mida kasutatakse identifikaatorina nõusolekuandmete linkimiseks kliendiandmetega. See on tõenäoliselt telefoninumber või e-posti aadress. 

1. Sätete rakendamiseks valige **Salvesta**.

## <a name="disable-consent-checks"></a>Nõusolekukontrollide keelamine

Nõusolekuandmete kasutamise lõpetamiseks vaatajaskonna statistikas peab administraator süsteemi sätteid vastavalt värskendama.

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Süsteem**.

1. Valige **vahekaart Nõusolek (eelvaade).**

1. Määrake **jaotises Nõusolekukontrollide** lubamine tumblernupp **väljalülitus**.

> [!TIP]
> Nõusolekuhaldusvõime kasutamise lõpetamise kohta leiate teemast [Süsteemisätted nõusolekukeskuses (eelvaade).](../consent-management/system-settings.md)"
