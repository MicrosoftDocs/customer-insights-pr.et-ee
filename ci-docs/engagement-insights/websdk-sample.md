---
title: Veebi-SDK näite käitamine
description: Siit leiate teavet SDK veebinäidise isikupärastamise ja käitamise kohta.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036598"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Kaasamisülevaadete võimaluse jaoks veebi SDK Dynamics 365 Customer Insights näite käitamine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Kaasamisülevaadete võimaluse veebi SDK teek on JavaScript teek näidiskoodiga, mida saate oma veebisaidil kasutada.

## <a name="prerequisites"></a>Eeltingimused

- Installi [Visual Studio kood](https://code.visualstudio.com/).
- [Installige Live Serveri laiend](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) rakenduses Visual Studio Code ja tutvuge Live Serveri käitustega.
- Teil peab olema [sisestamisvõti](instrument-website.md).

## <a name="run-sample"></a>Käivita näide

1. [Laadige alla SDK veebinäidis](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Saate tihendatud faili lahti pakkida `ei_websdk_sample.zip`.

1. Avage lahti pakitud kaust Visual Studio Code.

1. Failis `ei_websdk_sample.html` asendage string "INGESTION_KEY" teie kaasamisülevaadete võimaluste portaali vihjevõtmega ja stringi "NIMI" globaalse nimega, millega soovite SDK-d installeerida. Veenduge, et asendate kõik juhtumid.

1. Avage `ei_websdk_sample.html` fail, kasutades Live Server rakendust Visual Studio Code valides **Mine Live`i** olekuribalt.

1. Lehe avamisel tuleks vaatesündmus automaatselt saata. Lehel mis tahes nupul klõpsates saadetakse toimingusündmused. Nupp **Jälita sündmusi** saadab ka kohandatud sündmusi. Nupu **Mine Bing`i** valimine saadab enne Bingi veebisaidile navigeerimist tegevussündmuse.

1. Vaadake tööruumi liikumisel vooga sündmusi. See tööruum seostatakse 4. etapis sisestatud sisseelamisvõtmega.


[!INCLUDE[footer-include](../includes/footer-banner.md)]