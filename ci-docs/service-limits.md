---
title: Teenuselimiidid Customer Insightsis
description: Mõista piiranguid ja piiranguid Customer Insights SaaS teenuses.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940663"
---
# <a name="service-limits-in-customer-insights"></a>Teenuselimiidid Customer Insightsis

Selles artiklis kirjeldatakse rakendusse Customer Insights sisseehitatud piiranguid, mis on loodud selleks, et tagada teenuse usaldusväärsus ja stabiilsus. Igasugused muudatuste taotlused saate teha [Ideede foorumis](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Kihtdiagramm  | Limiidid  | Märked |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmendid, mõõdud ja ennustused | 300  | Segmentide [...](segments.md), [mõõtude](measures.md) ja [prognooside](predictions.md) koguarv kokku ei tohi ületada 300.  |
| Suhtlused | 20 sügavustaset olemitee seoste puhul. | Luues [segmente](segments.md) või [mõõte](measures.md) kasutades meisterdamisliidest, võib olemiteedel olla kuni 20 seosehüpet alguse- ja lõpuolemi vahel.  |

## <a name="fair-scheduling-of-jobs"></a>Tööde õiglane planeerimine

Customer Insights on SaaS-teenus, mis kasutab Jagatud Azure'i ressursse. Klientidel on tavaliselt muutuva intensiivsusega töökoormus ja erinevad sõiduplaanid. Et tagada õiglane juurdepääs aluseks olevatele ressurssidele, tagame, et süsteemiprotsessid viiakse läbi õiglases korras. Süsteemiprotsesside näited on andmete ühendamise, segmentide värskenduste või mõõtarvutusega seotud tööd. Õiglane planeerimine kaitseb teid ressursside järjekorras seismise eest, kui taotletud töökohti on palju. Samal ajal ei garanteeri Customer Insights, et kõik teie järjekorras olevad tööd töödeldakse paralleelselt.

[!INCLUDE [footer-include](includes/footer-banner.md)]
