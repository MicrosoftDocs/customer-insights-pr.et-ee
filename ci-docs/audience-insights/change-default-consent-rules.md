---
title: Segmentide nõusoleku vaikereeglite haldamine
description: Nõusoleku haldamise võimaluse abil saate nõusoleku vaikereeglid keelata või muuta, kui alistamine on lubatud.
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884165"
---
# <a name="disable-or-change-default-consent-rules"></a>Nõusoleku vaikereeglite keelamine või muutmine

Kui teie organisatsioonid kasutavad [nõusolekuhalduse võimalust](../consent-management/overview.md) koos vaatajaskonna statistikaga, [saavad administraatorid](activate-consent.md) jõustada segmentide nõusolekureegleid. 

Segmendipiirkonna jõustatud nõusolekureeglitega teavitab iga segment nõusolekukontrolli ja reeglite seisu. Kui alistamine on lubatud, lülitatakse konkreetsete segmentide puhul vaikeloa reeglid välja. Iga segmendi looja saab segmendile vaikereeglite peale lisada rohkem nõusolekureegleid. 

## <a name="for-administrators"></a>Administraatoritele

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Segmendi koostaja nõusolekureegli suvanditega.":::

**Nõusoleku vaikereeglite desaktiveerimiseks**

1. Valige **nõusolekureeglite** teatises **Vaata üksikasju**. 

1. Määrake **tumblernupud** Vaikimisi nõusolekureeglid väärtuseks **Väljas**.

**Nõusolekureeglite lisamiseks**

1. Valige **nõusolekureeglite** teatises **Vaata üksikasju**. 

1. Valige **Lisa nõusolekureeglid** ja valige nõusolekureegel **ripploendist Valige nõusoleku** andmetüüp.

1. Uue reegli rakendamiseks segmendile valige **Salvesta**.

## <a name="for-contributors"></a>Toetajatele

Segmendi loomiseks ilma jõustatud nõusolekureegliteta peate tegema koostööd oma administraatoriga, et need oma segmendis keelata. Siiski saate lisada oma nõusolekureeglid segmentidele, mida omate ja haldate.

See on kolmeastmeline protsess: 
1. [Looge segment](segments.md) vaatajaskonna ülevaates ja salvestage see. 

1. Jagage segmendi nime oma administraatoriga ja paluge neil [lubada teie segmendi alistamine](activate-consent.md). 

1. Avage oma segmendid uuesti. Valige **nõusolekureeglite** teatises **Kuva üksikasjad ja** lisage nõusolekureeglid, mida soovite rakendada. Seejärel **salvestage** ja **käivitage** oma segment.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
