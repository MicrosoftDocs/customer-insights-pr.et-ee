---
title: Customer Insightsi andmete eksportimine Azure Data Lake Storage Gen2-sse
description: Vaadake, kuidas konfigureerida ühendust Azure Data Lake Storage Gen2-ga.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477174"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Azure Data Lake Storage Gen2 konnektor (eelversioon)

Saate salvestada oma Customer Insightsi andmed Azure Data Lake Storage Gen2-sse või kasutada seda oma andmete edastamiseks teistesse rakendustesse.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage Gen2 konnektori konfigureerimine

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.

1. Tehke jaotises **Azure Data Lake Storage Gen2** valik **Seadista**.

1. Sisestage väljale **Kuvatav nimi** oma sihtkoha äratuntav nimi.

1. Sisestage oma Azure Data Lake Storage Gen2 **Konto nimi**, **Konto võti** ja **Konteiner**.
    - Lisateavet selle kohta, kuidas luua salvestusruumi kontot koos Azure Data Lake Storage Gen2-ga kasutamiseks, leiate teemast [Salvestusruumi konto loomine](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - Lisateavet Azure Data Lake Gen2 salvestusruumi konto nime ja konto võtme otsimise kohta leiate teemast [Salvestusruumi konto sätete haldamine Azure'i portaalis](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. Tehke valik **Edasi**.

1. Märgistage lahter iga olemi kõrval, mida soovite antud sihtkohta eksportida.

1. Valige **Salvesta**.

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md#export-data-on-demand). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).
