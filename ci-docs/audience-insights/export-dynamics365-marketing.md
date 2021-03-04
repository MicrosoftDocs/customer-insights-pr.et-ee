---
title: Customer Insightsi andmete eksportimine rakendusse Dynamics 365 Marketing
description: Vaadake, kuidas konfigureerida ühendust rakendusega Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269049"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Ühendus rakendusega Dynamics 365 Marketing (eelvaateversioon)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Kasutage lahenduses Dynamics 365 Marketing kampaaniate loomiseks ja konkreetsete kliendirühmadega ühenduse võtmiseks [segmente](segments.md). Lisateavet leiate teemast [Dynamics 365 Customer Insightsi segmentide kasutamine Dynamics 365 Marketingiga](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Eeltingimus

- Enne segmendi eksportimist Customer Insightsist Marketingi, peavad kontaktikirjed olema olemas rakenduses Dynamics 365 Marketing. Lugege lisateavet selle kohta, kuidas valmendada kontakte [Dynamics 365 Marketingis Common Data Servicesi abil](connect-power-query.md).

  > [!NOTE]
  > Segmentide eksportimine sihtrühmaülevaadetest Marketingi ei loo uusi kontaktikirjeid Marketingi eksemplaris. Marketingi kontaktikirjed peavad olema valmendatud sihtrühmaülevaadetes ja neid tuleb kasutada andmeallikana. Need tuleb lisada ka ühendatud kliendi olemisse, et vastendada kliendi ID-d ja kontakti ID-deks, enne kui segmente saab eksportida.

## <a name="configure-the-connector-for-marketing"></a>Konnektori konfigureerimine Marketingi jaoks

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.

1. Jaotises **Dynamics 365 Marketing** valige suvand **Häälestamine**.

1. Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.

1. Sisestage väljale **Serveri aadress** oma organisatsiooni Marketingi URL.

1. Jaotises **Serveri administraatorikonto** valige suvand **Logi sisse** ja valige rakenduse Dynamics 365 Marketing konto.

1. Vastendage kliendi ID väli Dynamics 365 kontakti ID-ga.

1. Tehke valik **Edasi**.

1. Valige üks või mitu segmenti.

1. Valige **Salvesta**.

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]