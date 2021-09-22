---
title: Käivita iOS SDK näidis
description: Näidis projekt iOS SDK kohta teabe saamiseks
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036823"
---
# <a name="run-the-ios-sdk-sample"></a>Käivita iOS SDK näidis

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

See iOS näidisprojekt aitab teil mõista, kuidas SDK rakenduses töötab. Te ei pea koodi kirjutama. Lisage lihtsalt oma edastusvõti ja näete oma tööruumis kohe sündmusi.

## <a name="prerequisites"></a>Eeltingimused

- [Xcode versioon 9+](https://developer.apple.com/xcode/downloads/)
- [Edastusvõti](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Laadi alla iOS SDK näidis

1. [Laadige alla kaasamisülevaated iOS SDK näidis](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Saate tihendatud faili lahti pakkida `ei-ios-sample.zip`.
1. Avage näidisrakenduse projekt Xcode.
1. Asendage failis `EIConfig.plist` string `“YOUR-INGESTION-KEY”` väljale `ingestionKey` oma tööruumi edastusvõtmega töövõteandmetest jaotises **Administraator** > **Tööruum** > **Paigaldusjuhend**.
1. Näidisprojekti käivitamiseks valige **Käivita**.
1. Kuvage sündmused oma tööruumis.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
