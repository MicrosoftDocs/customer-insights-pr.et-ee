---
title: Andmete sissemaksmine Power Query konnektori kaudu (sisaldab videot)
description: Andmeallikate konnektorid, mis põhinevad Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: aae49be4364676ecc7a307e60eeca13859f1662a
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934973"
---
# <a name="connect-to-a-power-query-data-source"></a>Andmeallikas-ga ühenduse loomine Power Query

Power Query pakub andmete neelamiseks laia konnektorite komplekti. Enamikku nendest konnektoritest toetab Dynamics 365 Customer Insights. 

Power Query Konnektoritel põhinevate andmeallikate lisamine järgib tavaliselt selles jaotises kirjeldatud juhiseid. Olenevalt kasutatavast konnektorist on siiski vaja erinevat teavet. Lisateavet leiate konnektori viite üksikute konnektorite [Power Query dokumentatsioonist](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Loo uus andmeallikas

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige **Microsoft, seejärel valige Edasi Power Query** **·**.

1. Sisestage andmeallikale **Nimi** ja valige andmeallika loomiseks nupp **Edasi**.

1. Valige üks [saadaolevatest konnektoritest](#available-power-query-data-sources). Selles näites valime **teksti/CSV** konnektori.

1. Sisestage valitud konnektorile jaotises **Konnektori sätted** nõutavad üksikasjad ja valige andmete üle vaatamiseks nupp **Edasi**.

1. Valige suvand **Andmete teisendamine**. Selles etapis lisate oma andmeallikale olemid. Olemid on andmekogud. Kui teil on andmebaas, mis sisaldab mitut andmekogumit, on iga andmekomplekt omaette olem.

1. **Power Query Dialoogiboks – päringute redigeerimine** võimaldab andmeid üle vaadata ja täpsustada. Olemid, mida süsteemid teie valitud andmeallikas tuvastasid, kuvatakse vasakpoolsel paanil.

   > [!div class="mx-imgBorder"]
   > ![Päringute redigeerimise dialoog.](media/data-manager-configure-edit-queries.png "Päringute redigeerimise dialoog")

1. Samuti saate oma andmeid teisendada. Valige redigeeritav või teisendatav olem. Kasutage aknas suvandeid Power Query teisenduste rakendamiseks. Kõik teisendused loetletakse jaotises **Rakendatud etapid**. Power Query pakub mitmeid eelnevalt ehitatud transformatsioonivõimalusi. Lisateavet vt [Power Query teemast Transformations](/power-query/power-query-what-is-power-query#transformations).

1. Saate lisada oma andmeallikas täiendavaid olemeid, valides **Hangi andmed** dialoogis **Päringute redigeerimise**.

   Soovitame kasutada järgmisi teisendusi.

   - Kui valmendate andmeid CSV-failist, siis esimene rida sisaldab sageli päiseid. Avage **Tabeli teisendamine** ja valige suvand **Kasuta päiseid esimese reana**.
   - Veenduge, et andmetüüp oleks õigesti seadistatud.

1. **·** Power Query Teisenduste salvestamiseks valige akna allservas Salvesta. Pärast salvestamist leiate oma andmeallika jaotises **Andmed** > **Andmeallikad**.

1. Lehel **Andmeallikad** märkate, et uus andmeallikas on olekus **Värskendamine**.

## <a name="available-power-query-data-sources"></a>Saadaolevad Power Query andmeallikad

Vaadake [Power Query konnektorite](/power-query/connectors/) loendit, mida saate kasutada andmete importimiseks Customer Insightsi. 

**Veerus Customer Insights (Dataflows) märgitud konnektorid** on saadaval uute andmeallikate Power Query loomiseks. Vaadake üle kindla konnektori dokumendid, et saada lisateavet selle eeltingimuste, piirangute ja muude üksikasjade kohta.

## <a name="edit-power-query-data-sources"></a>Andmeallikate redigeerimine Power Query

> [!NOTE]
> Ei pruugi olla võimalik muuta andmeallikaid, mis on samaaegselt kasutusel mõnes rakenduse protsessis (nt *segmentimine*, *vaste* või *ühinemine*). 
>
> Lehel **Sätted** saate jälgida iga aktiivse protsessi edenemist. Protsessi lõpuleviimisel saate naasta **Andmeallikate** lehele ja teha soovitud muudatused.

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2. Valige muudetava andmeallika kõrval vertikaalne ellips ja valige rippmenüüst **Muuda**.

   > [!div class="mx-imgBorder"]
   > ![Redigeerimise suvand.](media/edit-option-data-sources.png "Redigeerimise suvand")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Rakendage muudatused ja teisendused **Power Query dialoogiboksis – Päringute** redigeerimine, nagu on kirjeldatud jaotises Uue andmeallikas [loomine](#create-a-new-data-source).

4. Muudatuste salvestamiseks valige **Salvesta pärast muudatuste** Power Query lõpuleviimist.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
