---
title: Power BI konnektor
description: Õppige kasutama konnektorit Dynamics 365 Customer Insights Power BI-s.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e901114703a43b4b4e751e0a93eb4876d7636c00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642792"
---
# <a name="connector-for-power-bi-preview"></a>Power BI’i konnektor (eelvaade)

Visualiseerige oma andmeid rakendusega Power BI Desktop. Oma ühendatud kliendiandmetega täiendavate ülevaadete ja aruannete loomine.

## <a name="prerequisites"></a>Eeltingimused

- Teil on koondatud kliendiprofiilid.
- Teie arvutisse on installitud [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) uusim versioon. [Lisateave: Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Konnektori konfigureerimine Power BI jaoks

1. Valige rakenduses Power BI Desktop **Fail** > **Too andmed**.

1. Valige **Kuva veel** ja otsige rakendust **Dynamics 365 Customer Insights**

1. Valige käsk **Ühenda**.

1. **Logige sisse** samale organisatsiooni kontole, mida kasutate Customer Insightsi jaoks, ja valige **Ühenda**.
   > [!NOTE]
   > Selles etapis osutavat kontot kasutatakse Customer Insightsist andmete toomiseks ja see ei pea olema sama, mille abil olete Power BI-sse sisse logitud. Andmete toomiseks kasutatava konto lähtestamiseks avage Power BI ja minge jaotisse **Fail** > **Suvandid** > **Sätted** > **Andmeallika sätted**. Valige andmeallikate loendist **Dynamics 365 Customer Insightsi sisselogimine** ja seejärel suvand **Tühista õigused**.  

1. Dialoogiboksis **Navigaator**. näete kõigi keskkondade loendit, millele teil on juurdepääs. Laiendage keskkond ja avage mis tahes kaust (olemid, näitajad, segmendid, rikastamised). Näiteks avage kaust **Olemid**, et näha kõiki olemeid, mida saate importida.

   ![Power BI Konnektori Navigaator.](media/power-bi-navigator.png "Power BI konnektori navigaator")

1. Valige kaasatavate olemite kõrval olevad märkeruudud ja vajutage **Laadi**. Saate valida mitu olemit erinevatest keskkondadest.

1. Olemite laadimisel näete laadivat dialoogiboksi. Kui kõik teie valitud olemid on laaditud, saate Power BI funktsioone kasutada andmete visualiseerimiseks.

## <a name="large-data-sets"></a>Suured andmekogumid

Customer Insightsi Power BI konnektor on loodud töötama andmekogumitega, mis sisaldavad kuni 1 miljon kliendiprofiili. Suurte andmekogumite importimine võib toimida, kuid see võtab kaua aega. Lisaks võib protsess Power BI piirangute tõttu aeguda. Lisateavet vaadake teemast [Power BI: soovitused mahukate andmekogumite jaoks](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Andmete alamhulgaga töötamine

Kaaluge andmete alamhulgaga töötamist. Näiteks saate luua [segmente](segments.md), selle asemel et eksportida kõik kliendikirjed Power BI-sse.

## <a name="troubleshooting"></a>Tõrkeotsing

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>Customer Insightsi keskkonda ei kuvata Power BI-s

Keskkonnad, millel on Customer Insightsis kahe identse olemi vahel määratletud rohkem kui üks [seos](relationships.md), pole konnektoris Power BI saadaval.

Saate topeltseoseid tuvastada ja eemaldada.

1. Avage **jaotis Andmeseosed** > **keskkonna** kohta, kus te puudute Power BI.
2. Topeltseoste tuvastamiseks tehke järgmist.
   - Kontrollige, kas kahe sama olemi vahel on määratletud mitu seost.
   - Kontrollige, kas kahe koondamisprotsessi kaasatud olemi vahel on loodud seos. Kõigi koondamisprotsessi kaasatud olemite vahel on määratletud varjatud seos.
3. Eemaldage tuvastatud topeltseosed.

Pärast topeltseoste eemaldamist proovige Power BI konnektor uuesti konfigureerida. Keskkond peaks olema nüüd saadaval.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Tõrked kuupäevaväljadel olemite laadimisel Power BI Desktop -ile

Kuupäevavorminguga nagu KUU/PÄEV/AASTA, välju sisaldavate olemite laadimisel võivad lokaadivormingute mitteühildumisel ilmneda tõrked. See mittevastavus juhtub siis, kui teie Power BI Desktop fail on seatud teisele lokaadile kui inglise keel (Ameerika Ühendriigid), kuna Customer Insightsi kuupäevaväljad salvestatakse USA vormingus.

Failil Power BI Desktop -il on ükskohasäte, mis rakendatakse andmete toomisel. Kui soovite, et need kuupäevaväljad sadetakse õigesti, määrake selle kohaks . BPI-fail inglise keelde (USA). [Siit saate teada, kuidas muuta Power BI desktop fail](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) kohta.

[!INCLUDE [footer-include](includes/footer-banner.md)]
