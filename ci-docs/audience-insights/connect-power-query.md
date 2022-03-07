---
title: Andmete sissemaksmine konnektori Power Query kaudu (sisaldab videot)
description: Andmeallikate konnektorid, mis põhinevad Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 4c12933a0684094702843be309525dd6d5d9b6f4
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355516"
---
# <a name="connect-to-a-power-query-data-source"></a>Andmeallikas-ga Power Query ühenduse loomine

Power Query pakub andmete neelamiseks laia konnektorite komplekti. Enamikku nendest konnektoritest toetab Dynamics 365 Customer Insights. 

Konnektoritel Power Query põhinevate andmeallikate lisamine järgib tavaliselt selles jaotises kirjeldatud juhiseid. Olenevalt kasutatavast konnektorist on siiski vaja erinevat teavet. Lisateavet leiate konnektori viite üksikute konnektorite dokumentatsioonist [Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Loo uus andmeallikas

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige suvand **Microsofti Power Query**.

1. Sisestage andmeallikale **Nimi** ja valige andmeallika loomiseks nupp **Edasi**.

1. Valige üks [saadaolevatest konnektoritest](#available-power-query-data-sources). Selles näites **valime teksti/CSV** konnektori.

1. Sisestage valitud konnektorile jaotises **Konnektori sätted** nõutavad üksikasjad ja valige andmete üle vaatamiseks nupp **Edasi**.

1. Valige suvand **Andmete teisendamine**. Selles etapis lisate oma andmeallikale olemid. Olemid on andmekogud. Kui teil on andmebaas, mis sisaldab mitut andmekogumit, on iga andmekomplekt omaette olem.

1. Dialoogiboks **Power Query – päringute** redigeerimine võimaldab andmeid üle vaadata ja täpsustada. Olemid, mida süsteemid teie valitud andmeallikas tuvastasid, kuvatakse vasakpoolsel paanil.

   > [!div class="mx-imgBorder"]
   > ![Päringute redigeerimise dialoog.](media/data-manager-configure-edit-queries.png "Päringute redigeerimise dialoog")

1. Samuti saate oma andmeid teisendada. Valige redigeeritav või teisendatav olem. Kasutage aknas Power Query suvandeid teisenduste rakendamiseks. Kõik teisendused loetletakse jaotises **Rakendatud etapid**. Power Query pakub mitmeid eelnevalt ehitatud transformatsioonivõimalusi. Lisateavet vt [Power Query teemast Transformations](/power-query/power-query-what-is-power-query#transformations).

   Soovitame kasutada järgmisi teisendusi.

   - Kui valmendate andmeid CSV-failist, siis esimene rida sisaldab sageli päiseid. **Valige Teisendamine** ja valige **Kasuta esimest rida päistena**.
   - Veenduge, et andmetüüp oleks õigesti seadistatud. Näiteks kuupäevaväljade puhul valige kuupäeva tüüp.

1. Dialoogiboksis Päringute redigeerimine andmeallikas **täiendavate olemite** lisamiseks **minge avalehte** ja valige **Hankige andmed**.

1. Teisenduste salvestamiseks valige **akna allservas** Salvesta Power Query. Pärast salvestamist leiate oma andmeallika jaotises **Andmed** > **Andmeallikad**.

1. Lehel **Andmeallikad** märkate, et uus andmeallikas on olekus **Värskendamine**.

## <a name="available-power-query-data-sources"></a>Saadaolevad Power Query andmeallikad

[Power Query Vaadake konnektorite loendit](/power-query/connectors/), mida saate kasutada andmete importimiseks Customer Insightsi. 

Veerus **Customer Insights (Dataflows)** märgitud konnektorid on saadaval uute andmeallikate Power Query loomiseks. Vaadake üle kindla konnektori dokumendid, et saada lisateavet selle eeltingimuste, piirangute ja muude üksikasjade kohta.

## <a name="edit-power-query-data-sources"></a>Andmeallikate redigeerimine Power Query

> [!NOTE]
> Ei pruugi olla võimalik muuta andmeallikaid, mis on samaaegselt kasutusel mõnes rakenduse protsessis (nt *segmentimine*, *vaste* või *ühinemine*). 
>
> **Lehel Sätted** saate jälgida iga aktiivse protsessi edenemist. Protsessi lõpuleviimisel saate naasta **Andmeallikate** lehele ja teha soovitud muudatused.

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2. Valige muudetava andmeallika kõrval vertikaalne ellips ja valige rippmenüüst **Muuda**.

   > [!div class="mx-imgBorder"]
   > ![Redigeerimise suvand.](media/edit-option-data-sources.png "Redigeerimise suvand")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Rakendage muudatused ja teisendused dialoogiboksis **Power Query – Päringute** redigeerimine, nagu on kirjeldatud [jaotises Uue andmeallikas](#create-a-new-data-source) loomine.

4. Muudatuste salvestamiseks valige **Salvesta** Power Query pärast muudatuste lõpuleviimist.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
