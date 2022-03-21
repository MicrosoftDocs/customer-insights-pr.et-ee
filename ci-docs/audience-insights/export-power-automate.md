---
title: Power Automate konnektor | Microsoft Docs
description: Looge voogusid Microsoft Power Automate'is Dynamics 365 Customer Insightsist
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dc9bbe22b7f10cf92f06cae18fbece9808b87dce
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226709"
---
# <a name="power-automate-connector-preview"></a>Power Automate’i konnektor (eelvaade)

Käivitage konkreetsed sündmused, mis ilmnevad automaatselt andmete muutmisel ja hallake keerulisemaid vooge otse [Power Automate](https://flow.microsoft.com/)'is.

## <a name="power-automate-triggers"></a>Power Automate'i päästikud

Saate kasutada päästikuid pilvevoogude loomiseks ja korduvate ülesannete (nt teatiste ja keerukamate toimingute) automatiseerimiseks. 

- Käivitub, kui andmeallika värskendamine nurjub. 
- Käivitub, kui andmeallika värskendamine õnnestub.
- Käivitub, kui segmendi lävi ületatakse. Päästiku piiranguks on läve ületamine.
- Käivitub, kui ärimeetme lävi ületatakse. Toetatakse ainult ilma dimensioonita ärinäitajad. Päästiku piiranguks on läve ületamine.
- Käivitatakse, kui (andmeallikad, segmendid, mõõdud jne) täielik värskendamine on lõpule viidud.
- Käivitub, kui ühendamisprotsess (kaardistamine, vastendamine, liitmine) on lõpule viidud.

[Päästikute konfigureerimine Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate'i toimingud

Power Automate'i konnektor pakub saadaolevatest päästikutest erinevaid toiminguid. Lisateavet leiate juhendist [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automate'i voo loomine

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.

1. Valige **Power Automate'i** paanil suvand **Seadista**.

1. Avaneb Power Automate'i Customer Insightsi konnektor (eelversioon). **Logige sisse** rakendusse Power Automate.

1. Valige üks võimalikest päästikutest ja lisage oma uuele voole veel etappe. Lisateavet leiate teemast [Pilvevoo loomine Power Automate'is](/power-automate/get-started-logic-flow).

Näited voogude kasutamise kohta: 
- Sõnumi postitamine Microsoft Teamsi kanalisse juhul, kui andmeallika värskendamine nurjub. 
- Meili saatmine andmete omanikele segmendi läve ületamisel.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
