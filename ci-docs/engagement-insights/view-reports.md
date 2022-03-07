---
title: Kuva andmearuanded
description: Kasutage saadaolevaid aruandeid oma saidil reaalajas tegevuse koostamiseks.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 03b0b4bab0d5d9c2ae641c85aac8174ec1668d45
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229735"
---
# <a name="view-reports"></a>Kuva aruanded

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Aruanne on andmete visualiseeringute kogum, mis kasutab SDK kaudu kogutud andmeid, mis aitavad teil kasutaja käitumist mõõta ja mõista. Dynamics 365 Customer Insights kaasamisülevaated sisaldavad veebi- ja mobiiliprojektide out-of-box (OOB) aruandeid.  

## <a name="web-reports"></a>Veebiaruanded

Veebiaruannetele pääsete juurde jaotises **Avasta** vasakpoolsel navigeerimispaanil.

:::image type="content" source="media/report-menu.png" alt-text="Navigeerimine, mis näitab saadaolevate aruannete loendit.":::

### <a name="real-time-usage-report"></a>Reaalaja kasutuse aruanne

**Reaalajaline kasutus** aruanne annab ülevaate teie saidi praegusest tegevusest, mida värskendatakse iga hetk automaatselt. Juurutage reaalajas kasutamist, et jälgida turunduskampaaniate, pressisündmuste ja muude stsenaariumide mõju saidi liiklusele.

### <a name="key-metrics-reports"></a>Võtmemõõdikute aruanded

- **Lehevaated** loetleb üksikute lehtede lehevaatamised koos kogu valitud ajavahemiku kogu vaatamiste arvuga.

- **Külastused** näitavad teavet külastuste arvu ja külastusaja kestuse kohta.

- **Külastajad** teavitavad teid uutest ja tagastatud kordumatutest külastajadest teie saidile.

### <a name="content-reports"></a>Sisuaruanded

- **Lingid** kuvavad teavet klikkide arvu ja tüübi kohta.

- **Sulgege lehed**, loetleb lingid, mida külastajad saidilt väljumiseks klikkisid.

### <a name="traffic-sources-reports"></a>Liiklusaruanded

- **Viitajad** loetlevad domeenid ja URL-id, mis juhtisid külastajad teie lehele.

- **Jälgimiskoodid** pakuvad teavet nende linkide jälgimiskoodide kohta, mis juhivad külastajaid teie lehele.

### <a name="visitor-profiles-reports"></a>Külastajaprofiilide aruanded

- **Seadmed** loetlevad füüsilised seadmed, mida kasutati teie saidile juurdepääsuks.

- **OS ja brauserid** pakuvad ülevaateid operatsioonisüsteemidest ja brauseritest, mida kasutati teie lehele liikumisel.

- **Asukohad** kuvatakse teave külastaja kohta riigi, piirkonna ja linna järgi.

- **Keeled** loendi lehevaatamised külastaja eelistatud keelte kaupa.

## <a name="mobile-reports"></a>Mobiilsed aruanded

Mobiiliaruanded on rühmitatud reaalajas kasutuse, rakenduse ja kasutaja kategooriatesse. Mobiiliaruannetele pääsete juurde jaotises **Avasta** vasakpoolsel navigeerimispaanil.   

:::image type="content" source="media/mobile-reports.png" alt-text="Kaasamisülevaadete kasutajaliides, mis näitab reaalajas kasutusaruannet, mis renderdab andmeid diagrammides ja loendites.":::   

### <a name="real-time-usage"></a>Reaalajas kasutus

**Reaalajas kasutamine** annab ülevaate mobiilirakenduse praegusest tegevusest, mida värskendatakse automaatselt iga minut. Kasutage reaalajas kasutamist, et jälgida rakenduses praegu aktiivsete kasutajate ja seansside arvu ning ülakuva vaateid.

### <a name="app-reports"></a>Rakenduse aruanded

- **Kuvavaated** kuvatakse rakenduse üksikkuvade kuvavaated ja valitud ajavahemiku jooksul kuvavaadete koguarv. Kuvavaateid saate vaadata ekraani nime või kuva pealkirja alusel.

- **Seansid** näitavad teavet seansside arvu ja seansside kestuse kohta.

- **Tagasipöördumise sagedus** rühmaseanss loetakse päevade arvu järgi viimasest seansist.

- **Kasutajad** kuvavad mobiilirakenduses uusi ja tagasipöördunud kasutajaid.

- **Sündmused** loetleb kõik teie rakenduses kogutud sündmused, millele lisatakse iga sündmuse koguarv.

### <a name="user-reports"></a>Kasutajaaruanded

- **Rakenduse versioonid** loetleb teie mobiilirakenduse versioonid, mida teie kasutajabaas kasutab.

- **Seadmed ja operatsioonisüsteemi versioonid** annab ülevaateid, millistes seadmetes ja operatsioonisüsteemides teie mobiilirakendust käitatakse.

- **Asukohad** kuvab teave rakendsuse külastaja kohta riigi, piirkonna ja linna järgi.

## <a name="filter-by-time-or-date-range"></a>Filtreerige kellaaja või kuupäeva vahemiku alusel.

Veebi- või mobiiliaruandes saate valida ajavahemiku või kuupäeva vahemiku, et keskenduda väärtusele või ajaperioodile. 

- Ajapaneeli valimiseks valige aruandevaate parempoolses ülanurgas aruande ripploendist soovitud väärtus. Saate valida ka väärtuse **Fikseeritud kuupäeva vahemik**. 

  :::image type="content" source="media/filter-by-time.png" alt-text="Filtreerige kellaaja või kuupäeva vahemiku alusel.":::   

- Enamike aruannete korral valige aruande filtreerimiseks diagrammis või loendis soovitud väärtus.

> [!NOTE]
> Ajavahemiku valimine on reaalajaaruandes keelatud; reaalaja aruande ajavahemik on "praegu."


[!INCLUDE[footer-include](../includes/footer-banner.md)]
