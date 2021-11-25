---
title: Teenuse limiidid Dynamics 365 Customer Insights
description: Tutvuge piirangutega.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791976"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Teenusepiirangud rakenduse Customer Insights võimalustes

Selles artiklis kirjeldatakse rakendusse Customer Insights sisseehitatud piiranguid, mis on loodud selleks, et tagada teenuse usaldusväärsus ja stabiilsus. Igasugused muudatuste taotlused saate teha [Ideede foorumis](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Sihtrühmaülevaated

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Teenuselimiidid Dynamics 365 Customer Insights vaatajaskonna ülevaate võimekuses

| Ala  | Limiidid  | Märkused |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmendid, mõõdud ja prognoosid | 300  | [Segmentide, mõõtude ja prognooside koguarv](audience-insights/segments.md) kokku ei tohi [...](audience-insights/measures.md)[...](audience-insights/predictions.md) ületada 300.  |
| Suhtlused | 20 sügavustaset olemitee seoste puhul. | Luues [segmente](audience-insights/segments.md) või [mõõte](audience-insights/measures.md) kasutades meisterdamisliidest, võib olemiteedel olla kuni 20 seosehüpet alguse- ja lõpuolemi vahel.  |


## <a name="engagement-insights"></a>Kaasamisülevaated

### <a name="workspace-and-event-quotas"></a>Tööruumi ja sündmuse kvoodid

Kaasamisülevaated on äärmiselt skaleeritav rakendus, mis suudab toetada miljoneid sündmusi sekundis. Avaliku eelvaate ajal on sündmustel mahulävi. Organisatsioonis võib olla ka töö tööruumide arvu piirang.

### <a name="engagement-insights-limits"></a>Kaasamisülevaate piirid

- Sündmuse maksimummaht tööruumis = 100 sündmust sekundis

- Tööruumide maksimumarv organisatsioonis = 100

Kui sündmused ületavad läve, võib see põhjustada nimetatud sündmustel põhinevates aruannetes andmete kaotsimineku. Te võite [võtta ühendust toega](https://go.microsoft.com/fwlink/?linkid=2145734), et suurendada mahtu enne piiride ületamist. Töötame koos teiega, et teha kindlaks, kas teie vajadus mahu suurendamiseks ja teie taotluse toetamiseks on vajalik.


[!INCLUDE[footer-include](includes/footer-banner.md)]
