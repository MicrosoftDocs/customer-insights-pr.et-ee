---
title: Power Automate konnektor | Microsoft Docs
description: Looge Microsoft Power Automate’i vooge Dynamics 365 Customer Insightsi kaudu.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268819"
---
# <a name="power-automate-connector-preview"></a>Power Automate’i konnektor (eelvaade)

Käivitage konkreetsed sündmused, mis ilmnevad automaatselt andmete muutmisel ja hallake keerulisemaid vooge otse [Power Automate](https://flow.microsoft.com/)'is.

## <a name="power-automate-triggers"></a>Power Automate'i päästikud

Saate kasutada päästikuid pilvevoogude loomiseks ja korduvate ülesannete (nt teatiste ja keerukamate toimingute) automatiseerimiseks. 

- Käivitub, kui andmeallika värskendamine nurjub. 
- Käivitub, kui andmeallika värskendamine õnnestub.
- Käivitub, kui segmendi lävi ületatakse. Päästiku piiranguks on läve ületamine.
- Käivitub, kui ärimeetme lävi ületatakse. Päästiku piiranguks on läve ületamine.
- Käivitub, kui lõpule on viidud (andmeallikate, segmentide, näitajate, ...) täielik värskendamine.
- Käivitub, kui ühendamisprotsess (kaardistamine, vastendamine, liitmine) on lõpule viidud.

[Päästikute konfigureerimine Power Automate'is](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate'i toimingud
Power Automate'i konnektor pakub saadaolevatest päästikutest erinevaid toiminguid. Lisateavet leiate juhendist [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automate'i voo loomine

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.

1. Valige **Power Automate'i** paanil suvand **Seadista**.

1. Avaneb Power Automate'i Customer Insightsi konnektor (eelversioon). **Logige sisse** rakendusse Power Automate.

1. Valige üks võimalikest päästikutest ja lisage oma uuele voole veel etappe. Lisateavet leiate teemast [Pilvevoo loomine Power Automate'is](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Näited voogude kasutamise kohta. 
- Sõnumi postitamine Microsoft Teamsi kanalisse juhul, kui andmeallika värskendamine nurjub. 
- Meili saatmine andmete omanikele segmendi läve ületamisel.



[!INCLUDE[footer-include](../includes/footer-banner.md)]