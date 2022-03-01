---
title: Power BI konnektor
description: Õppige kasutama konnektorit Dynamics 365 Customer Insights Power BI-s.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405527"
---
# <a name="connector-for-power-bi-preview"></a>Power BI’i konnektor (eelvaade)

Visualiseerige oma andmeid rakendusega Power BI Desktop. Oma ühendatud kliendiandmetega täiendavate ülevaadete ja aruannete loomine.

## <a name="prerequisites"></a>Eeltingimused

- Teil on koondatud kliendiprofiilid.
- Teie arvutisse on installitud rakenduse [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) uusim versioon. [Lisateave: Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konnektori konfigureerimine Power BI jaoks

1. Valige rakenduses Power BI Desktop **Fail** > **Too andmed**.

1. Valige **Kuva veel** ja otsige rakendust **Dynamics 365 Customer Insights**

1. Valige tulem ja valige **Ühenda**.

1. **Logige sisse** samale organisatsiooni kontole, mida kasutate Customer Insightsi jaoks, ja valige **Ühenda**.
   > [!NOTE]
   > Selles etapis osutavat kontot kasutatakse Customer Insightsist andmete toomiseks ja see ei pea olema sama, mille abil olete Power BI-sse sisse logitud. Andmete toomiseks kasutatava konto lähtestamiseks avage Power BI ja minge jaotisse **Fail** > **Suvandid** > **Sätted** > **Andmeallika sätted**. Valige andmeallikate loendist **Dynamics 365 Customer Insightsi sisselogimine** ja seejärel suvand **Tühista õigused**.  

1. Dialoogiboksis **Navigaator**. näete kõigi keskkondade loendit, millele teil on juurdepääs. Laiendage keskkond ja avage mis tahes kaust (olemid, näitajad, segmendid, rikastamised). Näiteks avage kaust **Olemid**, et näha kõiki olemeid, mida saate importida.

   ![Power BI konnektori navigaator](media/power-bi-navigator.png "Power BI konnektori navigaator")

1. Valige kaasatavate olemite kõrval olevad märkeruudud ja vajutage **Laadi**. Saate valida mitu olemit erinevatest keskkondadest.

1. Olemite laadimisel näete laadivat dialoogiboksi. Kui kõik teie valitud olemid on laaditud, saate Power BI funktsioone kasutada andmete visualiseerimiseks.

## <a name="large-data-sets"></a>Suured andmekogumid

Customer Insightsi Power BI konnektor on loodud töötama andmekogumitega, mis sisaldavad kuni 1 miljon kliendiprofiili. Suurte andmekogumite importimine võib toimida, kuid see võtab kaua aega. Lisaks võib protsess Power BI piirangute tõttu aeguda. Lisateavet vaadake teemast [Power BI: soovitused mahukate andmekogumite jaoks](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Andmete alamhulgaga töötamine

Kaaluge andmete alamhulgaga töötamist. Näiteks saate luua [segmente](segments.md), selle asemel et eksportida kõik kliendikirjed Power BI-sse.
