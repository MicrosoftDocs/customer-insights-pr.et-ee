---
title: Süsteemi värskendamise ajastamine
description: Planeerige aeg, millal süsteemi tuleks värskendada
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610323"
---
# <a name="schedule-system-refresh"></a>Süsteemi värskendamise ajastamine

Ajastage kõigi allaneelatud [andmeallikate automaatsed värskendused](data-sources.md). Automaatne värskendamine aitab tagada, et teie andmeallikate värskendused kajastuksid teie kliendi koondprofiilidel.

> [!NOTE]
> Power Query teie hallatavaid andmeallikaid värskendatakse nende enda ajakavade järgi. Nende Power Query andmeallikate värskendamise ajastamiseks konfigureerige selle konkreetse andmeallikas värskendamissätted lehelt **Andmeallikad**. Joondage ajastus ülesvoolu andmete värskendamise ajakavaga, et värskendused ei toimuks korraga.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Andmevoo värskendamise sätted.":::

## <a name="set-system-refresh-schedule"></a>Süsteemi värskendamise ajakava määramine

1. Minge jaotisse **Haldussüsteem** > **ja** valige **vahekaart Ajakava**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Värskendamise ajastamise vahekaart lehelt Süsteem.":::

1. Ajastatud värskendamise vaike-olek on **Väljas**. Ajastatud värskenduste luvamiseks lülitage ekraani ülaosas sisse valik **Sees**.

1. Värskendamisvalikuteks on **Iga nädal** (tavaline) ja **Iga päev**. Kui kavatsete värskendada iga nädal, valige vähemalt üks päev, mil tahate värskendada.

1. Määrake **Ajavöönd** ja seejärel kasutage ripploendit **Aeg** oma värskendamise aja määramiseks. Kui tahate ajastada mitu värskendust ühel päeval, valige **Vali muu kellaaeg**. Saate lisada kuni neli värskendust.

1. Vajutage nuppu **Salvesta**, et muudatused rakendada.

[!INCLUDE [footer-include](includes/footer-banner.md)]
