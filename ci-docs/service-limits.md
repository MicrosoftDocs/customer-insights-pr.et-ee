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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350402"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Teenusepiirangud rakenduse Customer Insights võimalustes

Selles artiklis kirjeldatakse rakendusse Customer Insights sisseehitatud piiranguid, mis on loodud selleks, et tagada teenuse usaldusväärsus ja stabiilsus. Igasugused muudatuste taotlused saate teha [Ideede foorumis](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Sihtrühmaülevaated

| Kihtdiagramm  | Limiidid  | Märked |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmendid, meetmed ja ennustused | 300  | Segmentide [...](audience-insights/segments.md), [mõõtude](audience-insights/measures.md) ja [ennustuste](audience-insights/predictions.md) koguarv kokku ei tohi ületada 300.  |
| Suhtlused | 20 sügavustaset olemitee seoste puhul. | Luues [segmente](audience-insights/segments.md) või [mõõte](audience-insights/measures.md) kasutades meisterdamisliidest, võib olemiteedel olla kuni 20 seosehüpet alguse- ja lõpuolemi vahel.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
