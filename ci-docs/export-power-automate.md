---
title: Power Automate konnektori (eelvaate) | Microsofti dokumendid
description: Looge voogusid Microsoft Power Automate'is Dynamics 365 Customer Insightsist
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196113"
---
# <a name="power-automate-connector-preview"></a>Power Automate’i konnektor (eelvaade)

Käivitage konkreetsed sündmused, mis ilmnevad automaatselt andmete muutmisel ja hallake keerulisemaid vooge otse [Microsoft Power Automate](https://flow.microsoft.com/)'is.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Maksimaalselt 100 kõnet 60 sekundi jooksul. Kasutage [parameetrit](/connectors/customerinsights/#get-items-from-an-entity) $skip API lõpp-punktile mitu korda helistamiseks.

## <a name="power-automate-triggers"></a>Power Automate'i päästikud

Saate kasutada päästikuid pilvevoogude loomiseks ja korduvate ülesannete (nt teatiste ja keerukamate toimingute) automatiseerimiseks. Kasutage päästikuid, kui:

- Andmeallikas värskendamine nurjub.
- Andmeallikas värskendamine õnnestub.
- Segmendil ületatakse künnis. Päästiku piiranguks on läve ületamine.
- Ettevõtlusmeetme puhul ületatakse künnis. Toetatakse ainult ilma dimensioonita ärinäitajad. Päästiku piiranguks on läve ületamine.
- Täielik plaanitud värskendamine on lõpule viidud. See päästik ei tööta käsitsi käivitatud värskenduste puhul.
- Ühendamisprotsessi värskendamine on lõpule viidud.

[Päästikute konfigureerimine Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Power Automate'i toimingud

Power Automate'i konnektor pakub saadaolevatest päästikutest erinevaid toiminguid. Lisateavet leiate juhendist [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Power Automate'i voo loomine

1. Minge **Administraator** > **Ühendused**.

1. Valige **Power Automate'i** paanil suvand **Seadista**.

1. Avaneb Power Automate'i Customer Insightsi konnektor (eelversioon). **Logige sisse** rakendusse Power Automate.

1. Valige üks võimalikest päästikutest ja lisage oma uuele voole veel etappe. Lisateavet leiate teemast [Pilvevoo loomine Power Automate'is](/power-automate/get-started-logic-flow).

Näited voogude kasutamise kohta: 
- Sõnumi postitamine Microsoft Teamsi kanalisse juhul, kui andmeallika värskendamine nurjub. 
- Meili saatmine andmete omanikele segmendi läve ületamisel.

[!INCLUDE [footer-include](includes/footer-banner.md)]
