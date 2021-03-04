---
title: Customer Insightsi andmete eksportimine rakendusse Dynamics 365 Sales
description: Vaadake, kuidas konfigureerida ühendust rakendusega Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269003"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Ühendus rakendusega Dynamics 365 for Sales (eelvaateversioon)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Kasutage kliendiandmeid turundusloendite loomiseks, töövoogude järeltegevusteks ja kampaaniate saatmiseks Dynamics 365 Salesi abil.

## <a name="prerequisite"></a>Eeltingimus

1. Enne segmendi eksportimist Customer Insightsist Salesi, peavad kontaktikirjed olema olemas rakenduses Dynamics 365 Sales. Lugege lisateavet selle kohta, kuidas valmendada kontakte [Dynamics 365 Salesis Common Data Servicesi abil](connect-power-query.md).

   > [!NOTE]
   > Segmentide eksportimine sihtrühmaülevaadetest Salesi ei loo uusi kontaktikirjeid Salesi eksemplaris. Salesi kontaktikirjed peavad olema valmendatud sihtrühmaülevaadetes ja neid tuleb kasutada andmeallikana. Need tuleb lisada ka ühendatud kliendi olemisse, et vastendada kliendi ID-d ja kontakti ID-deks, enne kui segmente saab eksportida.

## <a name="configure-the-connector-for-sales"></a>Konnektori konfigureerimine Salesi jaoks

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.

1. Jaotises **Dynamics 365 Sales** valige suvand **Häälestamine**.

1. Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.

1. Sisestage väljale **Serveri aadress** oma organisatsiooni Salesi URL.

1. Jaotises **Serveri administraatorikonto** valige suvand **Logi sisse** ja valige rakenduse Dynamics 365 Sales konto.

1. Vastendage kliendi ID väli Dynamics 365 kontakti ID-ga.

1. Tehke valik **Edasi**.

1. Valige üks või mitu segmenti.

1. Valige **Salvesta**.

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]