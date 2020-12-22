---
title: Power Automate konnektor | Microsoft Docs
description: Looge Microsoft Power Automate’i vooge Dynamics 365 Customer Insightsi kaudu.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405522"
---
# <a name="power-automate-connector-preview"></a>Power Automate’i konnektor (eelvaade)

Käivitage konkreetsed sündmused, mis ilmnevad automaatselt andmete muutmisel ja hallake keerulisemaid vooge otse [Power Automate](https://flow.microsoft.com/)'is.

## <a name="power-automate-triggers"></a>Power Automate'i päästikud

Saate kasutada erinevaid päästikuid, mis võimaldavad teil luua voogusid korduvate tööülesannete automatiseerimiseks (nt teatised või täpsemaid toiminguid). 

- Käivitub, kui andmeallika värskendamine nurjub. 
- Käivitub, kui andmeallika värskendamine õnnestub.
- Käivitub, kui segmendi lävi ületatakse. Päästiku piiranguks on läve ületamine.
- Käivitub, kui ärimeetme lävi ületatakse. Päästiku piiranguks on läve ületamine.
- Käivitub, kui lõpule on viidud (andmeallikate, segmentide, näitajate, ...) täielik värskendamine.
- Käivitub, kui ühendamisprotsess (kaardistamine, vastendamine, liitmine) on lõpule viidud.

[Päästikute konfigureerimine Power Automate'is](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Power Automate'i toimingud
Power Automate'i konnektor pakub saadaolevatest päästikutest erinevaid toiminguid. Lisateavet leiate juhendist [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Power Automate'i voo loomine sihtrühmaülevaadetes

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Süsteem**.

1. Valige lehel **Süsteem** vahekaart **Olek**.

1. Valige jaotises **Andmeallikad** suvand **Vood** ja valige ripploendist **Voo loomine**.
   > [!div class="mx-imgBorder"]
   > ![Power Automate’i konnektor, mis näitab voo loomise toimingut](media/power-automate-connector-create-flow.png "Voo loomise toimingut näitav rakenduse Power Automate konnektor")

1. Valige Power Automate'is eelistatud voo loomiseks üks saadaolevatest päästikutest. Esimest korda voogu luues peate end esmalt rakenduse Power Automate konnektori jaoks autentima.
