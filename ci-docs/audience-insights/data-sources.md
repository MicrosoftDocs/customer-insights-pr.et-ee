---
title: Andmeallikate kasutamine andmete valmendamiseks
description: Vaadake, kuidas eri allikatest andmeid importida.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643948"
---
# <a name="overview-about-data-sources"></a>Andmeallikate ülevaade

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioon ühendub andmetega, mis on pärit paljudest allikatest. Andmeallikaga ühendamist nimetatakse sageli *andmete sisestamiseks*. Pärast andmete sisestamist saate need [ühendada](data-unification.md) ja nendega toiminguid teha.

## <a name="add-a-data-source"></a>Lisa andmeallikas

Vaadake üksikasjalikke artikleid selle kohta, kuidas andmeallikat lisada, olenevalt sellest, millise suvandi te valite.

Saate andmeallikat lisada kolmel peamisel viisil.

- [Kümnete Power Query konnektorite kaudu](connect-power-query.md)
- [Common Data Modeli kaustast](connect-common-data-model.md)
- [Enda Common Data Service’i andmejärvest](connect-common-data-service-lake.md)

> [!NOTE]
> Asutusesisestest andmeallikatest ei saa veel andmeid lisada.

## <a name="review-ingested-data"></a>Sisestatud andmete läbivaatus

Näete iga sisestatud andmeallika nime, selle olekut ja viimast korda, kui neid andmeid selle allika jaoks värskendati. Saate andmeallikate loendit iga veeru järgi sortida.

> [!div class="mx-imgBorder"]
> ![Andmeallikas lisatud](media/configure-data-datasource-added.png "Andmeallikas lisatud")

|Olek  |Kirjeldus  |
|---------|---------|
|Õnnestunud   |Andmeallikas valmendati edukalt juhul, kui veerus **Värskendatud** on toodud aeg.
|Pole käivitatud   |Andmeallikas pole valmendatud andmeid või see on ikka mustandirežiimis.         |
|Värskendamine    |Andmete sisestamine on pooleli. Selle toimingu tühistamiseks valige **Peata värskendamine** **Toimingute** veerus. Andmeallika värskendamise peatamine ennistab selle viimase värskendamise olekusse.       |
|Ebaõnnestus     |Andmete sisestamisel ilmnesid tõrked.         |

Valige **Värskenda olekut**, et vaadata üle värskendamise oleku üksikasjad, sh tõrke üksikasjad ja allavooluprotsesside värskendused.

Andmete laadimine võib veidi aega võtta. Pärast edukat värskendamist saab lisatud andmeid vaadata lehel **Olemid**. Lisateavet vt jaotisest [Olemid](entities.md).

## <a name="refresh-a-data-source"></a>Andmeallika värskendamine

Andmeallikaid saab värskendada automaatse ajakava järgi või soovi korral käsitsi. 

Minge jaotisse **Haldus** > **Süsteem** > [**Ajastamine**](system.md#schedule-tab), et konfigureerida kõigi valmendatud andmeallikate ajastatud värskendamine.

Andmeallika värskendamiseks mis tahes ajal toimige järgmiselt.

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**

2. Valige värskendamist vajava andmeallika kõrvalt vertikaalne kolmikpunkt ja valige ripploendist **Värskenda**.

3. Andmeallika jaoks käivitatakse nüüd käsitsivärskendamine. Andmeallika värskendamisel värskendatakse nii olemiskeem kui ka kõigi andmeallikas määratletud olemite andmed.

4. Kui soovite olemasoleva värskendamise tühistada, klõpsake **Lõpeta värskendamine** ja andmeallikas taastatakse viimase värskendamise olekusse.

## <a name="delete-a-data-source"></a>Andmeallika kustutamine

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2. Valige eemaldatava andmeallika kõrval asuv vertikaalne kolmikpunkt ja valige rippmenüüst suvand **Kustuta**.

3. Kinnitage, et soovite kustutada.
