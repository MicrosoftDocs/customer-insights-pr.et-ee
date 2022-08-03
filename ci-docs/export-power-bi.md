---
title: Power BI’i konnektor (eelvaade)
description: Õppige kasutama konnektorit Dynamics 365 Customer Insights Power BI-s.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196665"
---
# <a name="power-bi-connector-preview"></a>Power BI’i konnektor (eelvaade)

Looge töölaua abil Microsoft Power BI oma andmete jaoks visualiseeringuid. Oma ühendatud kliendiandmetega täiendavate ülevaadete ja aruannete loomine.

## <a name="prerequisites"></a>eeltingimused

- Ühtsed kliendiprofiilid.
- Teie arvutisse on installitud [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) uusim versioon. [Lisateave: Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konnektori konfigureerimine Power BI jaoks

1. Valige rakenduses Power BI Desktop **Fail** > **Too andmed**.

1. Valige **Kuva veel** ja otsige rakendust **Dynamics 365 Customer Insights**

1. Valige käsk **Ühenda**.

1. **Logige sisse** samale organisatsiooni kontole, mida kasutate Customer Insightsi jaoks, ja valige **Ühenda**.
   > [!NOTE]
   > Selles etapis osutavat kontot kasutatakse Customer Insightsist andmete toomiseks ja see ei pea olema sama, mille abil olete Power BI-sse sisse logitud. Andmete toomiseks kasutatava konto lähtestamiseks avage Power BI ja minge jaotisse **Fail** > **Suvandid** > **Sätted** > **Andmeallika sätted**. Valige andmeallikate loendist **Dynamics 365 Customer Insightsi sisselogimine** ja seejärel suvand **Tühista õigused**.  

1. **Dialoogiboksis Navigaator** saate vaadata kõigi keskkondade loendit, millele teil on juurdepääs. Laiendage keskkond ja avage mis tahes kaust (olemid, näitajad, segmendid, rikastamised). Näiteks avage kaust **Olemid**, et näha kõiki olemeid, mida saate importida.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Power BI Konnektori Navigaator.":::

1. Valige kaasatavate olemite kõrval olevad märkeruudud ja vajutage **Laadi**. Saate valida mitu olemit erinevatest keskkondadest.

   Laadimise dialoogiboks kuvatakse olemite laadimise ajal. Kui kõik valitud olemid on laaditud, kasutage andmete visualiseerimise võimalusi Power BI.

## <a name="large-data-sets"></a>Suured andmekogumid

Customer Insightsi Power BI konnektor on loodud töötama andmekogumitega, mis sisaldavad kuni 1 miljon kliendiprofiili. Suuremate andmekogumite importimine võib toimida, kuid võtab kaua aega ja võib piirangute tõttu Power BI aeguda. Lisateavet vaadake teemast [Power BI: soovitused mahukate andmekogumite jaoks](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Andmete alamhulgaga töötamine

Kaaluge andmete alamhulgaga töötamist. Näiteks looge [segmente](segments.md), selle asemel et eksportida kõik kliendikirjed Power BI.

## <a name="troubleshooting"></a>Tõrkeotsing

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insightsi keskkonda ei kuvata Power BI-s

Keskkonnad, millel on Customer Insightsis kahe identse olemi vahel määratletud rohkem kui üks [seos](relationships.md), pole konnektoris Power BI saadaval.

Tuvastage dubleeritud seosed ja eemaldage need.

1. Avage **andmeseosed** > **keskkonnas**, kus te puudute Power BI.
1. Topeltseoste tuvastamiseks tehke järgmist.
   - Kontrollige, kas kahe sama olemi vahel on määratletud mitu seost.
   - Kontrollige, kas kahe koondamisprotsessi kaasatud olemi vahel on loodud seos. Kõigi koondamisprotsessi kaasatud olemite vahel on määratletud varjatud seos.
1. Eemaldage tuvastatud topeltseosed.

Pärast topeltseoste eemaldamist proovige Power BI konnektor uuesti konfigureerida.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Tõrked kuupäevaväljadel olemite laadimisel Power BI Desktop -ile

Kui laadite olemeid, mis sisaldavad väljasid kuupäevavorminguga (nt KK/PP/AAAA), võite sobimatute lokaadivormingute tõttu ilmneda tõrkeid. See mittevastavus ilmneb siis, kui teie Power BI Desktop faili väärtuseks on määratud mõni muu lokaat kui inglise keeles (Ameerika Ühendriigid), kuna Customer Insightsi kuupäevaväljad salvestatakse USA-vormingus.

Failil Power BI Desktop -il on ükskohasäte, mis rakendatakse andmete toomisel. Kuupäevavigade [parandamiseks määrake . BPI-fail](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) inglise keelde (Ameerika Ühendriigid).

[!INCLUDE [footer-include](includes/footer-banner.md)]
