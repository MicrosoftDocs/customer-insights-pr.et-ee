---
title: Sihtrühma ülevaadete segmentide kasutamine kaasamisülevaadete aruannete filtreerimiseks
description: Kasutage vaatajaskonna statistika segmente kliendi veebisaidil kaasamisstatistika abil kogutud käitumisandmete interaktiivses analüüsis.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230481"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Sihtrühma ülevaadete segmentide kasutamine kaasamisülevaadete aruannete filtreerimiseks

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Kaasamisstatistika abil saate vaatajaskonna statistika segmente kasutada oma veebisaitide kaasamisstatistika kogutud käitumisandmete interaktiivses analüüsis.

## <a name="prerequisite"></a>Eeltingimus

- Kaasamisülevaadete keskkond, kus teil on sihtrühma ülevaadete segmentide andmed lingitud vaatajaskonna statistika keskkonnaga, kus segmendid ja kliendiprofiilid luuakse. Lisateave: [Sihtrühma ülevaadete ja kaasamisülevaadete vahelise lingi loomine](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Sihtrühma ülevaadete segmentide loomine 

> [!IMPORTANT]
> Selleks, et sihtrühma ülevaated kuvaksid kaasamisülevaadetes, peate esmalt [käitama kooste- ja järgmised protsessid](../audience-insights/merge-entities.md). Järgmised protsessid on olulised, kuna need loovad ainulaadse tabeli, mis valmistab vaatajaskonna statistika segmendid ette kaasamisstatistikaga jagamiseks. (Süsteemivärskenduse ajasmisel kaasatakse need automaatselt ka järgnevad protsessid.)

Kaasamisülevaadetes või loodud kohandatud aruannetes saate kasutada sihtrühma ülevaadete segmente. Lisateavet leiate [valmisprofiili aruannetest](profile-reports.md) ning [kohandatud aruannete loomisest ja redigeerimisest](custom-reports.md).

**Sihtrühma ülevaadete segmentide kasutamiseks kaasamisülevaadete aruannetes**

1. Valige oma **Tööruumi** lehel **Andmed** ja seejärel vahekaart **Segmendid**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Valige Segmentide vahekaart.":::

   >[!NOTE]
   > Sihtrühma ülevaadete segmendi valimine viib teid sihtrühma ülevaadeteni, kust saate teada, kuidas see segment reeglite ja loogika järgi loodi. Lisateavet sihtrühma kaasamise segmentide kohta leiate teemast [Segmentide kuvamine ja loomine](../audience-insights/segments.md).

2. Valige kasutusvalmis aruanne või [looge kohandatud aruanne](custom-reports.md) ja seejärel valige **Lisa tingimus**. (Selle näite puhul valisime **Lehevaated** aruanne.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Tingimuse lisamine.":::

3. Valige **Filtreeri segmentide järgi**, laiendage loendit **Segmendi tüüp** ja seejärel valige **Demograafia**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Valige demograafilise segmendi tüüp.":::

4. Laiendage loendit **Segmendi nimi** ja seejärel valige sihtrühma ülevaadete segment.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Valige segment.":::

5. Saate rakendada ühte või mitut segmenti, sealhulgas käitumuslikud (kaasamisstatistika) ja demograafilised (sihtrühma statistika) segmendid. 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Lehevaadete aruanne on piiratud USA klientide ja avalehe segmentidega.":::

Eelneval pildil on valitud **USA kliendid** ja **Avalehe** segmendid, mis piirab aruande **Lehevaated** kuvamist ainult nende kahe segmendi kuvamiseks. 


>[!NOTE]
> Saate kasutada sihtrühma statistika segmente, et filtreerida kaasamisstatistika esmaseid aruandeid, kohandatud aruandeid ja lehtreid. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]