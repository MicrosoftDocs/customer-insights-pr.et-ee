---
title: Andmete allaneelamine konnektori kaudu Power Query (sisaldab videot)
description: Andmeallikate konnektorid, mis põhinevad rakendusel Power Query.
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
ms.openlocfilehash: 50258365c3134c588aa79ec72c66d0de329e0ff1
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642664"
---
# <a name="connect-to-a-power-query-data-source"></a>Andmeallikas ühenduse loomine Power Query

Power Query pakub laias valikus konnektoreid andmete allaneelamiseks. Enamikku nendest konnektoritest toetab Dynamics 365 Customer Insights. 

Andmeallikate lisamine konnektorite põhjal Power Query järgib tavaliselt selles jaotises kirjeldatud juhiseid. Olenevalt kasutatavast konnektorist on siiski vaja erinevat teavet. Lisateavet leiate konnektoriviite üksikute konnektorite dokumentatsioonist [Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Loo uus andmeallikas

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige suvand **Microsofti Power Query**.

1. Sisestage andmeallikale **Nimi** ja valige andmeallika loomiseks nupp **Edasi**.

1. Valige üks [saadaolevatest konnektoritest](#available-power-query-data-sources). Selles näites valime **teksti/CSV** konnektori.

1. Sisestage valitud konnektorile jaotises **Konnektori sätted** nõutavad üksikasjad ja valige andmete üle vaatamiseks nupp **Edasi**.

1. Valige suvand **Andmete teisendamine**. Selles etapis lisate oma andmeallikale olemid. Olemid on andmekogud. Kui teil on andmebaas, mis sisaldab mitut andmekogumit, on iga andmekomplekt omaette olem.

1. Dialoogiboks **Power Query – päringute** redigeerimine võimaldab teil andmeid üle vaadata ja täpsustada. Olemid, mida süsteemid teie valitud andmeallikas tuvastasid, kuvatakse vasakpoolsel paanil.

   > [!div class="mx-imgBorder"]
   > ![Päringute redigeerimise dialoog.](media/data-manager-configure-edit-queries.png "Päringute redigeerimise dialoog")

1. Samuti saate oma andmeid teisendada. Valige redigeeritav või teisendatav olem. Teisenduste Power Query rakendamiseks kasutage aknas olevaid suvandeid. Kõik teisendused loetletakse jaotises **Rakendatud etapid**. Power Query pakub arvukalt eelnevalt ehitatud transformatsioonivõimalusi. Lisateavet vt teemast [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).

   Soovitame kasutada järgmisi teisendusi.

   - Kui valmendate andmeid CSV-failist, siis esimene rida sisaldab sageli päiseid. **Valige Teisendamine** ja valige **Kasuta esimest rida päistena**.
   - Veenduge, et andmetüüp oleks õigesti seadistatud. Näiteks kuupäevaväljade puhul valige kuupäevatüüp.

1. Dialoogiboksis **Päringute** redigeerimine andmeallikas täiendavate olemite lisamiseks avage **Avaleht** ja valige Too **andmed**.

1. Teisenduste salvestamiseks valige **akna allosas Salvesta**.Power Query Pärast salvestamist leiate oma andmeallika jaotises **Andmed** > **Andmeallikad**.

1. Lehel **Andmeallikad** märkate, et uus andmeallikas on olekus **Värskendamine**.

## <a name="available-power-query-data-sources"></a>Saadaolevad Power Query andmeallikad

Vaadake konnektori [Power Query viidet](/power-query/connectors/) konnektorite loendi kohta, mida saate kasutada andmete importimiseks Customer Insightsi. 

Veerus **Customer Insights (Dataflows)** märkega konnektorid on saadaval uute andmeallikate loomiseks rakenduse põhjal Power Query. Vaadake üle kindla konnektori dokumendid, et saada lisateavet selle eeltingimuste, piirangute ja muude üksikasjade kohta.

## <a name="edit-power-query-data-sources"></a>Andmeallikate redigeerimine Power Query

> [!NOTE]
> Ei pruugi olla võimalik muuta andmeallikaid, mis on samaaegselt kasutusel mõnes rakenduse protsessis (nt *segmentimine*, *vaste* või *ühinemine*). 
>
> **Lehel Sätted** saate jälgida iga aktiivse protsessi edenemist. Protsessi lõpuleviimisel saate naasta **Andmeallikate** lehele ja teha soovitud muudatused.

1. Avage suvandid **Andmed** > **Andmeallikad**.

2. Valige muudetava andmeallika kõrval vertikaalne ellips ja valige rippmenüüst **Muuda**.

   > [!div class="mx-imgBorder"]
   > ![Redigeerimise suvand.](media/edit-option-data-sources.png "Redigeerimise suvand")

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]
   
3. Rakendage oma muudatused ja teisendused dialoogiboksis **Power Query Päringute** redigeerimine, nagu on kirjeldatud [jaotises Uue andmeallikas](#create-a-new-data-source) loomine.

4. Muudatuste salvestamiseks valige **pärast muudatuste lõpuleviimist nupp Salvesta** sisse Power Query.


[!INCLUDE [footer-include](includes/footer-banner.md)]
