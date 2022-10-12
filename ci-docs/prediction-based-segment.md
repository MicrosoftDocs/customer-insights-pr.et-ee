---
title: Prognoos mudelil põhineva segmendi loomine
description: Segmentide loomine ärimudeli väljundolemi prognoos põhjal.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610415"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Segmendi loomine prognoosmudelil (eelvaade)

Prognoosi tulemused rakenduvad mõnikord ainult teie klientide alamhulgale. Suurendage soovituste isikupärastamist, luues prognoosmudelite tulemustest segmendid. Näiteks võite anda konkreetseid soovitusi klientidele, kes eelistavad teatud tüüpi teenuseid.

## <a name="prerequisites"></a>Eeltingimused

- Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.

- Tootesoovitus, tehinguvoolavus, tellimusvoolavus või kliendi eluea väärtuse mudel, mis on konfigureeritud jaotises Customer Insights. Vaadake läbi erinevate mudelite häälestamise nõuded:

  - [Tootesoovitusmudel](predict-product-recommendation.md)
  - [Tellimusvoolavuse mudel](predict-subscription-churn.md)
  - [Tehinguvoolavuse mudel](predict-transactional-churn.md)
  - [Kliendi eluea väärtuse mudel](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Prognooside põhjal kliendisegmendi loomine

1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.

1. Valige mudel, mida soovite läbi vaadata, ja valige **Vaade**.

1. Klõpsake tulemustelehel käsku **Loo segment**. Tulemuste lehe kohta lisateabe saamiseks vaadake üle mudeli kohta käiv artikkel.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Prognooside tulemuste kuvatõmmis, koos esiletõstmisega toimingus Loo segment.":::

1. Looge uus segment, kasutades valitud mudeli väljundolemi atribuute. Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).

> [!TIP]
> Samuti saate luua segmendi prognoos mudeli jaoks lehelt Segmendid, valides **Suvandi Uus** ja käsk **Loo luureandmetest** **.** > **·** Lisateavet leiate teemast [Kiirsegmentidega](segment-quick.md) uue segmendi loomine.

[!INCLUDE [footer-include](includes/footer-banner.md)]
