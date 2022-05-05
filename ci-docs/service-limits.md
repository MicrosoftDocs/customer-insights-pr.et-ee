---
title: Teenusepiirangud rakenduses Dynamics 365 Customer Insights
description: Tutvuge piirangutega.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641757"
---
# <a name="service-limits-in-customer-insights"></a>Teenuselimiidid Customer Insightsis

Selles artiklis kirjeldatakse rakendusse Customer Insights sisseehitatud piiranguid, mis on loodud selleks, et tagada teenuse usaldusväärsus ja stabiilsus. Igasugused muudatuste taotlused saate teha [Ideede foorumis](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Kihtdiagramm  | Limiidid  | Märked |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmendid, mõõdud ja ennustused | 300  | Segmentide [...](segments.md), [mõõtude](measures.md) ja [prognooside](predictions.md) koguarv kokku ei tohi ületada 300.  |
| Suhtlused | 20 sügavustaset olemitee seoste puhul. | Luues [segmente](segments.md) või [mõõte](measures.md) kasutades meisterdamisliidest, võib olemiteedel olla kuni 20 seosehüpet alguse- ja lõpuolemi vahel.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
