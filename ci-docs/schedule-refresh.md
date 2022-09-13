---
title: Süsteemi värskendamise ajastamine
description: Planeerige aeg, millal süsteemi tuleks värskendada
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 949ea071ca41127b0c45488d5d7af3f6aa4e1c35
ms.sourcegitcommit: d7054a900f8c316804b6751e855e0fba4364914b
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/02/2022
ms.locfileid: "9395951"
---
# <a name="schedule-system-refresh"></a>Süsteemi värskendamise ajastamine

Ajastage kõigi allaneelatud [andmeallikate automaatsed värskendused](data-sources.md). Automaatne värskendamine aitab tagada, et teie andmeallikate värskendused kajastuksid teie kliendi koondprofiilidel.

> [!NOTE]
> Power Query teie hallatavaid andmeallikaid värskendatakse nende enda ajakavade järgi. Nende Power Query andmeallikate värskendamise ajastamiseks konfigureerige selle konkreetse andmeallikas värskendamissätted lehelt **Andmeallikad**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Andmevoo värskendamise sätted.":::

## <a name="set-system-refresh-schedule"></a>Süsteemi värskendamise ajakava määramine

1. Minge jaotisse **Haldussüsteem** > **ja** valige **vahekaart Ajakava**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Värskendamise ajastamise vahekaart lehelt Süsteem.":::

1. Ajastatud värskendamise vaike-olek on **Väljas**. Ajastatud värskenduste luvamiseks lülitage ekraani ülaosas sisse valik **Sees**.

1. Värskendamisvalikuteks on **Iga nädal** (tavaline) ja **Iga päev**. Kui kavatsete värskendada iga nädal, valige vähemalt üks päev, mil tahate värskendada.

1. Määrake **Ajavöönd** ja seejärel kasutage ripploendit **Aeg** oma värskendamise aja määramiseks. Kui tahate ajastada mitu värskendust ühel päeval, valige **Vali muu kellaaeg**. Saate lisada kuni neli värskendust.

1. Vajutage nuppu **Salvesta**, et muudatused rakendada.

[!INCLUDE [footer-include](includes/footer-banner.md)]
