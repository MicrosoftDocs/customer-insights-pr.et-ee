---
title: Power Automate konnektor | Microsoft Docs
description: Looge voogusid Microsoft Power Automate'is Dynamics 365 Customer Insightsist
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976083"
---
# <a name="power-automate-connector-preview"></a>Power Automate’i konnektor (eelvaade)

Käivitage konkreetsed sündmused, mis ilmnevad automaatselt andmete muutmisel ja hallake keerulisemaid vooge otse [Power Automate](https://flow.microsoft.com/)'is.

## <a name="power-automate-triggers"></a>Power Automate'i päästikud

Saate kasutada päästikuid pilvevoogude loomiseks ja korduvate ülesannete (nt teatiste ja keerukamate toimingute) automatiseerimiseks. 

- Käivitub, kui andmeallika värskendamine nurjub. 
- Käivitub, kui andmeallika värskendamine õnnestub.
- Käivitub, kui segmendi lävi ületatakse. Päästiku piiranguks on läve ületamine.
- Käivitub, kui ärimeetme lävi ületatakse. Toetatakse ainult ilma dimensioonita ärinäitajad. Päästiku piiranguks on läve ületamine.
- Käivitub, kui lõpule on viidud (andmeallikate, segmentide, näitajate, ...) täielik värskendamine.
- Käivitub, kui ühendamisprotsess (kaardistamine, vastendamine, liitmine) on lõpule viidud.

[Päästikute konfigureerimine Power Automate'is](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate'i toimingud
Power Automate'i konnektor pakub saadaolevatest päästikutest erinevaid toiminguid. Lisateavet leiate juhendist [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automate'i voo loomine

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.

1. Valige **Power Automate'i** paanil suvand **Seadista**.

1. Avaneb Power Automate'i Customer Insightsi konnektor (eelversioon). **Logige sisse** rakendusse Power Automate.

1. Valige üks võimalikest päästikutest ja lisage oma uuele voole veel etappe. Lisateavet leiate teemast [Pilvevoo loomine Power Automate'is](/power-automate/get-started-logic-flow).

Näited voogude kasutamise kohta. 
- Sõnumi postitamine Microsoft Teamsi kanalisse juhul, kui andmeallika värskendamine nurjub. 
- Meili saatmine andmete omanikele segmendi läve ületamisel.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
