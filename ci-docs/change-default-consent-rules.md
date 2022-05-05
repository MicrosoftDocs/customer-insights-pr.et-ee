---
title: Segmentide nõusoleku vaikereeglite haldamine
description: Nõusoleku haldamise võimaluse korral saate nõusoleku vaikereeglid keelata või muuta, kui tühistamine on lubatud.
ms.date: 12/01/2021
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 43f03ea97765e112a8ea2a7da97cc548c8c84dfc
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642575"
---
# <a name="disable-or-change-default-consent-rules"></a>Nõusoleku vaikereeglite keelamine või muutmine

Kui teie organisatsioonid kasutavad [rakenduses nõusolekuhalduse võimalust](consent-management/overview.md)Dynamics 365 Customer Insights, [saavad administraatorid jõustada segmentide nõusolekureegleid](activate-consent.md). 

Segmendi piirkonnas jõustatud nõusolekureeglitega teavitab iga segment nõusolekukontrolli olekust ja reeglitest. Kui tühistamine on lubatud, lülitatakse kindlate segmentide puhul nõusoleku vaikereeglid välja. Iga segmendi looja saab lisada segmendi vaikereeglitele lisaks rohkem nõusolekureegleid. 

## <a name="for-administrators"></a>Administraatoritele

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="Segmendi koostaja nõusolekureegli suvanditega.":::

**Vaikimisi nõusolekureeglite desaktiveerimiseks tehke järgmist.**

1. **Valige nõusolekureeglite** teatises Kuva **üksikasjad**. 

1. Määrake **nõusoleku vaikereeglid** olekusse **Väljas**.

**Nõusolekureeglite lisamiseks tehke järgmist.**

1. **Valige nõusolekureeglite** teatises Kuva **üksikasjad**. 

1. Valige **Lisa nõusolekureeglid** ja valige ripploendist **Nõusoleku valimine nõusoleku** reegel.

1. Uue reegli rakendamiseks segmendile valige **Salvesta**.

## <a name="for-contributors"></a>Toetajatele

Segmendi loomiseks ilma jõustatud nõusolekureegliteta peate tegema koostööd oma administraatoriga, et need oma segmendis keelata. Siiski saate lisada oma nõusolekureeglid segmentidele, mida omate ja haldate.

See on kolmeastmeline protsess: 
1. [Looge segment](segments.md) Customer Insightsis ja salvestage see. 

1. Jagage segmendi nime oma administraatoriga ja paluge neil lubada [segmendi](activate-consent.md) alistamised. 

1. Avage oma segmendid uuesti. Valige nõusolekureeglite teatises **Kuva üksikasjad** ja lisage nõusolekureeglid, **mida soovite** rakendada. **Seejärel salvestage** ja **käivitage** segment.



[!INCLUDE [footer-include](includes/footer-banner.md)] 
