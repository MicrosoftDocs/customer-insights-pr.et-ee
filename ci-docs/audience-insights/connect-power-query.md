---
title: Andmete sissemaksmine Power Query-liidese kaudu (Video)
description: Power Query-l põhinevate andmeallikate konnektorid.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 38c447d80a25feca087ca9f110278b8401423018
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903835"
---
# <a name="connect-to-a-power-query-data-source"></a>Power Query andmeallikaga ühendamine

Power Query pakub andmete valmendamiseks laia komplekti konnektoreid. Enamikku nendest konnektoritest toetab Dynamics 365 Customer Insights. 

Andmeallikate lisamine Power Query konnektorite põhjal järgib tavaliselt selles jaotises kirjeldatud juhiseid. Olenevalt kasutatavast konnektorist on siiski vaja erinevat teavet. Lisateavet leiate Power Query konnektori viite üksikute konnektorite [dokumentatsioonist](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Loo uus andmeallikas

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige **Microsoft Power Query, seejärel valige** **Edasi**.

1. Sisestage andmeallikale **Nimi** ja valige andmeallika loomiseks nupp **Edasi**.

1. Valige üks [saadaolevatest konnektoritest](#available-power-query-data-sources). Selles näites valime **teksti/CSV** konnektori.

1. Sisestage valitud konnektorile jaotises **Konnektori sätted** nõutavad üksikasjad ja valige andmete üle vaatamiseks nupp **Edasi**.

1. Valige suvand **Andmete teisendamine**. Selles etapis lisate oma andmeallikale olemid. Olemid on andmekogud. Kui teil on andmebaas, mis sisaldab mitut andmekogumit, on iga andmekomplekt omaette olem.

1. Dialoogiaken **Power Query – päringute redigeerimine** võimaldab andmeid üle vaadata ja täiustada. Olemid, mida süsteemid teie valitud andmeallikas tuvastasid, kuvatakse vasakpoolsel paanil.

   > [!div class="mx-imgBorder"]
   > ![Päringute redigeerimise dialoog.](media/data-manager-configure-edit-queries.png "Päringute redigeerimise dialoog")

1. Samuti saate oma andmeid teisendada. Valige redigeeritav või teisendatav olem. Teisenduste rakendamiseks kasutage suvandeid aknas Power Query. Kõik teisendused loetletakse jaotises **Rakendatud etapid**. Power Query pakub arvukalt eelvalmistatud teisendamise võimalusi. Lisateavet leiate teemast [Power Query teisendused](/power-query/power-query-what-is-power-query#transformations).

1. Saate lisada oma andmeallikas täiendavaid olemeid, valides **Hangi andmed** dialoogis **Päringute redigeerimise**.

   Soovitame kasutada järgmisi teisendusi.

   - Kui valmendate andmeid CSV-failist, siis esimene rida sisaldab sageli päiseid. Avage **Tabeli teisendamine** ja valige suvand **Kasuta päiseid esimese reana**.
   - Veenduge, et andmetüüp oleks õigesti seadistatud.

1. Teisenduste salvestamiseks valige Power Query akna allosast **Salvesta**. Pärast salvestamist leiate oma andmeallika jaotises **Andmed** > **Andmeallikad**.

1. Lehel **Andmeallikad** märkate, et uus andmeallikas on olekus **Värskendamine**.

## <a name="available-power-query-data-sources"></a>Saadaolevad Power Query andmeallikad

Vaadake [Power Query konnektorite](/power-query/connectors/) loendit, mida saate kasutada andmete importimiseks Customer Insightsi. 

Konnektorid, millel on märgitud veerg **Customer Insights (andmevood)**, on saadaval Power Query põhjal uute andmeallikate loomiseks. Vaadake üle kindla konnektori dokumendid, et saada lisateavet selle eeltingimuste, piirangute ja muude üksikasjade kohta.

## <a name="edit-power-query-data-sources"></a>Power Query andmeallikate redigeerimine

> [!NOTE]
> Ei pruugi olla võimalik muuta andmeallikaid, mis on samaaegselt kasutusel mõnes rakenduse protsessis (nt *segmentimine*, *vaste* või *ühinemine*). 
>
> Lehel **Sätted** saate jälgida iga aktiivse protsessi edenemist. Protsessi lõpuleviimisel saate naasta **Andmeallikate** lehele ja teha soovitud muudatused.

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2. Valige muudetava andmeallika kõrval vertikaalne ellips ja valige rippmenüüst **Muuda**.

   > [!div class="mx-imgBorder"]
   > ![Redigeerimise suvand.](media/edit-option-data-sources.png "Redigeerimise suvand")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Rakendage muudatused ja teisendused dialoogiaknas **Power Query – päringute redigeerimine**, nii nagu on kirjeldatud jaotises [Uue andmeallika loomine](#create-a-new-data-source).

4. Valige pärast redigeerimist muudatuste salvestamiseks Power Querys **Salvesta**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
