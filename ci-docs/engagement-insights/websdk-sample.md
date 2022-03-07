---
title: Veebi-SDK näite käitamine
description: Siit leiate teavet SDK veebinäidise isikupärastamise ja käitamise kohta.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a50a10db784ec7c1943c94e74000713309787e5c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225326"
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
