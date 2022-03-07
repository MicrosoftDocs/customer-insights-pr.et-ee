---
title: Segmentide nõusoleku vaikereeglite haldamine
description: Nõusoleku haldamise võimaluse abil saate nõusoleku vaikereeglid keelata või muuta, kui alistamine on lubatud.
ms.date: 12/01/2021
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4eae4da67fd4c6e70800f495ba30366d4fc9a0dd
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228934"
---
# <a name="disable-or-change-default-consent-rules"></a>Nõusoleku vaikereeglite keelamine või muutmine

Kui teie organisatsioonid kasutavad [nõusolekuhalduse võimalust](../consent-management/overview.md) koos vaatajaskonna statistikaga, [saavad administraatorid jõustada segmentide nõusolekureegleid](activate-consent.md). 

Segmendipiirkonna jõustatud nõusolekureeglitega teavitab iga segment nõusolekukontrolli ja reeglite seisu. Kui alistamine on lubatud, lülitatakse konkreetsete segmentide puhul vaikeloa reeglid välja. Iga segmendi looja saab segmendile vaikereeglite peale lisada rohkem nõusolekureegleid. 

## <a name="for-administrators"></a>Administraatoritele

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Segmendi koostaja nõusolekureegli suvanditega.":::

**Nõusoleku vaikereeglite desaktiveerimiseks**

1. **Valige nõusolekureeglite** teatises **Kuva üksikasjad**. 

1. **Määrake tumblernupu vaikesuhitsetuse reeglid** väärtuseks **Väljas**.

**Nõusolekureeglite lisamiseks**

1. **Valige nõusolekureeglite** teatises **Kuva üksikasjad**. 

1. Valige **Lisa nõusolekureeglid** ja valige nõusolekureegel ripploendist **Valige nõusoleku andmetüüp**.

1. Uue reegli rakendamiseks segmendile valige **Salvesta**.

## <a name="for-contributors"></a>Toetajatele

Segmendi loomiseks ilma jõustatud nõusolekureegliteta peate tegema koostööd oma administraatoriga, et need oma segmendis keelata. Siiski saate lisada oma nõusolekureeglid segmentidele, mida omate ja haldate.

See on kolmeastmeline protsess: 
1. [Looge segment](segments.md) vaatajaskonna ülevaates ja salvestage see. 

1. Jagage segmendi nime oma administraatoriga ja paluge neil [lubada teie segmendi](activate-consent.md) alistamine. 

1. Avage oma segmendid uuesti. **Valige nõusolekureeglite** teatises Kuva üksikasjad **ja lisage nõusolekureeglid,** mida soovite rakendada. **Seejärel salvestage** ja **käivitage** oma segment.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
