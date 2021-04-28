---
title: Segmendid põhinevad prognoosväljundil
description: Segmentide loomine ärimudeli väljundolemi prognoos põhjal.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741424"
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

1. Valige ülevaatamiseks soovitud mudeli kõrval vertikaalsed valipsed ja valige **vaade**.

1. Klõpsake tulemustelehel käsku **Loo segment**. Tulemuste lehe kohta lisateabe saamiseks vaadake üle mudeli kohta käiv artikkel.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Prognooside tulemuste kuvatõmmis, koos esiletõstmisega toimingus Loo segment.":::

1. Looge uus segment valitud mudeli väljundüksuse põhjal. Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).