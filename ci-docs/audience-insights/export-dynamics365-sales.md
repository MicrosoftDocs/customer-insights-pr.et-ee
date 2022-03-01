---
title: Customer Insightsi andmete eksportimine rakendusse Dynamics 365 Sales
description: Vaadake, kuidas konfigureerida ühendust rakendusega Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643813"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>Ühendus rakendusega Dynamics 365 for Sales (eelvaateversioon)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Kasutage kliendiandmeid turundusloendite loomiseks, töövoogude järeltegevusteks ja kampaaniate saatmiseks Dynamics 365 Salesi abil.

## <a name="prerequisite"></a>Eeltingimus

Kontaktikirjed [rakendusest Dynamics 365 Sales on valmendatud Common Data Service'i abil](connect-power-query.md).

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
