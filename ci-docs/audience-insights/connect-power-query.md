---
title: Andmete valmendamine Power Query konnektori kaudu
description: Power Query-l põhinevate andmeallikate konnektorid.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: b9a1b30e37c3792aa7bdfcfc177da9e8a32c324d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596908"
---
# <a name="connect-to-a-power-query-data-source"></a>Power Query andmeallikaga ühendamine

Power Query pakub andmete valmendamiseks laia komplekti konnektoreid. Enamikku nendest konnektoritest toetab Dynamics 365 Customer Insights. Power Query konnektorite põhjal andmeallikate lisamine järgib üldjoontes järgmises jaotises kirjeldatud juhiseid. Olenevalt kasutatavast konnektorist on siiski vaja erinevat teavet. Lisateavet üksikute konnektorite kohta leiate dokumentatsioonist [Power Query konnektorite viide](/power-query/connectors/).

## <a name="create-a-new-data-source"></a>Loo uus andmeallikas

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige meetod **Andmete importimine** ja valige **Edasi**.

1. Sisestage andmeallikale **Nimi** ja valige andmeallika loomiseks nupp **Edasi**. Nime juhised: 
   - peab algama tähega;
   - kasutage ainult tähti ja numbreid; erimärkide ja tühikute sisestamine pole lubatud;
   - kasutage 3–64 tähemärki.

1. Valige üks [saadaolevatest konnektoritest](#available-power-query-data-sources). Selles näites valime **Teksti/CSV** konnektori.

1. Sisestage valitud konnektorile jaotises **Konnektori sätted** nõutavad üksikasjad ja valige andmete üle vaatamiseks nupp **Edasi**.

1. Valige suvand **Andmete teisendamine**. Selles etapis lisate oma andmeallikale olemid. Olemid on andmekogud. Kui teil on andmebaas, mis sisaldab mitut andmekogumit, on iga andmekomplekt omaette olem.

1. Dialoogiaken **Power Query – päringute redigeerimine** võimaldab andmeid üle vaadata ja täiustada. Olemid, mida süsteemid teie valitud andmeallikas tuvastasid, kuvatakse vasakpoolsel paanil.

   > [!div class="mx-imgBorder"]
   > ![Päringute redigeerimise dialoog](media/data-manager-configure-edit-queries.png "Päringute redigeerimise dialoog")

1. Samuti saate oma andmeid teisendada. Valige redigeeritav või teisendatav olem. Teisenduste rakendamiseks kasutage suvandeid aknas Power Query. Kõik teisendused loetletakse jaotises **Rakendatud etapid**. Power Query pakub arvukalt eelvalmistatud teisendamise võimalusi. Lisateavet leiate teemast [Power Query teisendused](/power-query/power-query-what-is-power-query#transformations).

1. Saate lisada oma andmeallikas täiendavaid olemeid, valides **Hangi andmed** dialoogis **Päringute redigeerimise**.

   Need teisendused on väga soovitatavad.

   - Kui valmendate andmeid CSV-failist, siis esimene rida sisaldab sageli päiseid. Avage **Tabeli teisendamine** ja valige suvand **Kasuta päiseid esimese reana**.
   - Veenduge, et andmetüüp oleks õigesti seadistatud.

1. Teisenduste salvestamiseks valige Power Query akna allosast **Salvesta**. Pärast salvestamist leiate oma andmeallika jaotises **Andmed** > **Andmeallikad**.

1. Lehel **Andmeallikad** märkate, et uus andmeallikas on olekus **Värskendamine**.

## <a name="available-power-query-data-sources"></a>Saadaolevad Power Query andmeallikad

Ajakohase Customer Insightsi imporditavate konnektorite loendi leiate jaotisest [Power Query konnektorite viide](/power-query/connectors/). 

Konnektorid, millel on märgitud veerg **Customer Insights (andmevood)**, on saadaval Power Query põhjal uute andmeallikate loomiseks. Vaadake üle kindla konnektori dokumendid, et saada lisateavet selle eeltingimuste, piirangute ja muude üksikasjade kohta.

## <a name="edit-power-query-data-sources"></a>Power Query andmeallikate redigeerimine

> [!NOTE]
> Ei pruugi olla võimalik muuta andmeallikaid, mis on samaaegselt kasutusel mõnes rakenduse protsessis (nt *segmentimine*, *vaste* või *ühinemine*). 
>
> Lehe **Sätted** abil saate jälgida iga aktiivse protsessi kulgu. Protsessi lõpuleviimisel saate naasta **Andmeallikate** lehele ja teha soovitud muudatused.

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2. Valige muudetava andmeallika kõrval asuv vertikaalne kolmikpunkt ja valige rippmenüüst suvand **Redigeeri**.

   > [!div class="mx-imgBorder"]
   > ![Redigeerimise suvand](media/edit-option-data-sources.png "Redigeerimise suvand")

3. Rakendage muudatused ja teisendused dialoogiaknas **Power Query – päringute redigeerimine**, nii nagu on kirjeldatud jaotises [Uue andmeallika loomine](#create-a-new-data-source).

4. Valige pärast redigeerimist muudatuste salvestamiseks Power Querys **Salvesta**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]