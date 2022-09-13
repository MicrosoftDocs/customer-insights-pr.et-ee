---
title: Teenuse limiidid Customer Insightsis
description: Mõistke piiranguid ja piiranguid Customer Insights SaaS-teenuses.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f38b7d9985368fc38107f1f360f0603a7fcc8e6
ms.sourcegitcommit: 3c7cdfc8bd83ca236e4777240e08a541dc955d34
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 09/07/2022
ms.locfileid: "9411735"
---
# <a name="service-limits-in-customer-insights"></a>Teenuse limiidid Customer Insightsis

 Customer Insightsil on sisseehitatud limiidid, mis on loodud teenuse töökindluse ja stabiilsuse tagamiseks. Igasugused muudatuste taotlused saate teha [Ideede foorumis](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Kihtdiagramm  | Limiidid  | Märked |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmendid, mõõdud ja ennustused | 300  | Segmentide, [mõõtmiste](segments.md)[ja](measures.md) [prognooside](predictions-overview.md) koguarv ei tohi ületada 300.  |
| Suhtlused | 20 sügavustaset olemitee seoste puhul. | Luues [segmente](segments.md) või [mõõte](measures.md) kasutades meisterdamisliidest, võib olemiteedel olla kuni 20 seosehüpet alguse- ja lõpuolemi vahel.  |

## <a name="fair-scheduling-of-jobs"></a>Tööde õiglane ajastamine

Customer Insights on SaaS-teenus, mis kasutab jagatud Azure’i ressursse. Klientidel on tavaliselt muutuva intensiivsusega töökoormused ja erinevad ajakavad. Selleks et tagada õiglane juurdepääs alusressurssidele, tagame, et süsteemiprotsesse teostatakse õiglases korras. Süsteemiprotsesside näited on tööd, mis on seotud andmete ühendamise, segmendivärskenduste või arvutamise mõõtmisega. Õiglane ajakava kaitseb teid ressursside järjekorras seismise eest, kui soovitud töökohti on palju. Samal ajal ei garanteeri Customer Insights, et kõiki teie järjekorda pandud töid töödeldakse paralleelselt.

[!INCLUDE [footer-include](includes/footer-banner.md)]
