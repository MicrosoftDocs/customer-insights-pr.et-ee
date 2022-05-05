---
title: Segmentide nõusolekureeglite aktiveerimine
description: Järgige neid juhiseid nõusolekuandmete linkimiseks ja nõusolekukontrollide aktiveerimiseks rakenduses Dynamics 365 Customer Insights. Administraator saab keelata ka nõusolekukontrollid.
ms.date: 11/12/2021
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bfa03f4b7b56b300a74ebd04721cd64b893879f1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642525"
---
# <a name="activate-consent-rules"></a>Nõusolekureeglite aktiveerimine

Nõusolekukeskus [(eelvaade)](consent-management/overview.md) aitab teil ühtlustada erinevatest allikatest pärinevaid nõusolekuandmeid. Nõusoleku vaikekontrollide rakendamiseks kasutage ühtset *nõusolekuolemit*. Pärast nõusolekuandmete importimist nõusolekukeskusesse ja andmete *reeglite konfigureerimist sünkroonitakse olem Nõusolek* automaatselt rakendusega Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Nõusolekukontrollide lubamine

Nõusolekukeskusesse imporditud nõusolekuandmete (eelvaade) ja seadistatud reeglite abil saate lubada nõusolekukontrolli. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Customer Insightsi sätete vahekaart Nõusolek aktiveeritud nõusolekuandmetega.":::

1. Avage **Administraator** > **Süsteem** lahenduses Customer Insights.

1. **Valige vahekaart Nõusolek (eelvaade).**

1. **Seadke jaotises Nõusolekukontrollide** lubamine tumblernupp väärtuseks **Sees** kõigi nende alade puhul, mida soovite lubada.

1. **Märkige ruut Luba nõusoleku vaikereeglite** alistamine, et eemaldada kindlas segmendis jõustatud vaikeloa kontrollid. 

1. Valige rippmenüüst koht, kus soovite tühistamisi lubada.     

1. **Valige jaotises Kliendiprofiilidega** nõusoleku linkimine atribuut, mida kasutatakse identifikaatorina nõusolekuandmete linkimiseks kliendiandmetega. See on tõenäoliselt telefoninumber või e-posti aadress. 

1. Sätete rakendamiseks valige **Salvesta**.

## <a name="disable-consent-checks"></a>Nõusolekukontrollide keelamine

Nõusolekuandmete kasutamise lõpetamiseks Customer Insightsis peab administraator süsteemi sätteid vastavalt värskendama.

1. Avage **Administraator** > **Süsteem** lahenduses Customer Insights.

1. **Valige vahekaart Nõusolek (eelvaade).**

1. **Seadke jaotises Nõusolekukontrollide** lubamine tumblernupp väärtuseks **Väljas**.

> [!TIP]
> Nõusolekuhalduse võimaluse kasutamise lõpetamiseks lugege teemat [Nõusolekukeskuse süsteemisätted (eelvaade)](consent-management/system-settings.md).
