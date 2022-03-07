---
title: Teenusepiirangud rakenduses Dynamics 365 Customer Insights
description: Tutvuge piirangutega.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483659"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Teenusepiirangud rakenduse Customer Insights võimalustes

Selles artiklis kirjeldatakse rakendusse Customer Insights sisseehitatud piiranguid, mis on loodud selleks, et tagada teenuse usaldusväärsus ja stabiilsus. Igasugused muudatuste taotlused saate teha [Ideede foorumis](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Sihtrühmaülevaated

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Teenusepiirangud Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioonis

| Ala  | Limiidid  | Märkused |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmendid ja näitajad | 100 segmenti või näitajat. | Aktiivsete [segmentide](audience-insights/segments.md) ja [näitajate](audience-insights/measures.md) koguarv ei tohi ületada 100.  |
| Suhtlused | 20 sügavustaset olemitee seoste puhul. | Luues [segmente](audience-insights/segments.md) või [mõõte](audience-insights/measures.md) kasutades meisterdamisliidest, võib olemiteedel olla kuni 20 seosehüpet alguse- ja lõpuolemi vahel.  |


## <a name="engagement-insights"></a>Kaasamisülevaated

### <a name="workspace-and-event-quotas"></a>Tööruumi ja sündmuse kvoodid

Kaasamisülevaated on äärmiselt skaleeritav rakendus, mis suudab toetada miljoneid sündmusi sekundis. Avaliku eelvaate ajal on sündmustel mahulävi. Organisatsioonis võib olla ka töö tööruumide arvu piirang.

### <a name="engagement-insights-limits"></a>Kaasamisülevaate piirid

- Sündmuse maksimummaht tööruumis = 100 sündmust sekundis

- Tööruumide maksimumarv organisatsioonis = 100

Kui sündmused ületavad läve, võib see põhjustada nimetatud sündmustel põhinevates aruannetes andmete kaotsimineku. Te võite [võtta ühendust toega](https://go.microsoft.com/fwlink/?linkid=2145734), et suurendada mahtu enne piiride ületamist. Töötame koos teiega, et teha kindlaks, kas teie vajadus mahu suurendamiseks ja teie taotluse toetamiseks on vajalik.


[!INCLUDE[footer-include](includes/footer-banner.md)]