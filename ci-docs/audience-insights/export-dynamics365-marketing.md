---
title: Customer Insightsi andmete eksportimine rakendusse Dynamics 365 Marketing
description: Vaadake, kuidas konfigureerida ühendust rakendusega Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643768"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Ühendus rakendusega Dynamics 365 Marketing (eelvaateversioon)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Kasutage lahenduses Dynamics 365 Marketing kampaaniate loomiseks ja konkreetsete kliendirühmadega ühenduse võtmiseks [segmente](segments.md). Lisateavet leiate teemast [Dynamics 365 Customer Insightsi segmentide kasutamine Dynamics 365 Marketingiga](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Eeltingimus

Kontaktikirjed [rakendusest Dynamics 365 Marketing on valmendatud Common Data Service'is](connect-power-query.md).

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
