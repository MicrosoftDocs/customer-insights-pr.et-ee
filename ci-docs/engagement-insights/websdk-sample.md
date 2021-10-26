---
title: Veebi-SDK näite käitamine
description: Siit leiate teavet SDK veebinäidise isikupärastamise ja käitamise kohta.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606201"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Kaasamisülevaadete võimaluse jaoks veebi SDK Dynamics 365 Customer Insights näite käitamine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Kaasamisülevaadete võimaluse veebi SDK teek on JavaScript teek näidiskoodiga, mida saate oma veebisaidil kasutada.

## <a name="prerequisites"></a>Eeltingimused

- Installi [Visual Studio kood](https://code.visualstudio.com/).
- [Installige Live Serveri laiend](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) rakenduses Visual Studio Code ja tutvuge Live Serveri käitustega.
- Teil peab olema [kaasamise ülevaadete tööruum](create-workspace.md).

## <a name="run-sample"></a>Käivita näide

1. [Laadige alla SDK veebinäidis](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Saate tihendatud faili lahti pakkida `ei_websdk_sample.zip`.

1. Avage lahti pakitud kaust Visual Studio Code.

1. Minge oma tööruumi kaasamise ülevaadete portaali. Valige **Administraator** > **Tööruum** ja seejärel **Installijuhend**. JavaScripti koodilõigendi kopeerimiseks järgige esimest varianti ja valige **Kopeeri kood**.

1. Kleepige äsja kopeeritud koodilõik faili `ei_websdk_sample.html` selle rea alla:

   - <-- KLEEBI SELLE REA ALLA JAVASCRIPTI KOODILÕIGEND, MIS ON PÄRIT KAASAMISE ÜLEVAADETE PORTAALIST -->

1. Avage `ei_websdk_sample.html` fail, kasutades Live Server rakendust Visual Studio Code valides **Mine Live`i** olekuribalt.

1. Lehe avamisel tuleks vaatesündmus automaatselt saata. Lehel mis tahes nupul klõpsates saadetakse toimingusündmused. Nupp **Jälita sündmusi** saadab ka kohandatud sündmusi. Nupu **Mine Bing`i** valimine saadab enne Bingi veebisaidile navigeerimist tegevussündmuse.

1. Vaadake tööruumi liikumisel vooga sündmusi. See tööruum seostatakse 4. etapis sisestatud sisseelamisvõtmega.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
