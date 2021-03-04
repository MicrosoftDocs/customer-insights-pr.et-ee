---
title: Customer Insightsi andmete eksportimine Azure'i bloobimällu
description: Vaadake, kuidas konfigureerida Azure’i bloobimälu ühendus.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269187"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Azure’i bloobimälu konnektor (eelvaade)

Salvestage oma Customer Insightsi andmed Azure'i bloobimällu või kasutage seda oma andmete edastamiseks teistesse rakendustesse.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Azure’i bloobimälu konnektori konfigureerimine

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.

1. Jaotises **Azure’i bloobimälu** valige suvand **Seadista**.

1. Sisestage Azure’i bloobimälu kontole **Konto nimi**, **Konto võti** ja **Konteiner**.
    - Lisateavet Azure'i bloobimälu konto nime ja kontovõtme kohta vaadake teemast [Salvestuskonto sätete haldamine Azure'i portaalis](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - Lisateavet konteineri loomise kohta leiate teemast [Konteineri loomine](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Sisestage väljale **Kuvatav nimi** oma sihtkoha äratuntav nimi.

1. Tehke valik **Edasi**.

1. Märgistage lahter iga olemi kõrval, mida soovite antud sihtkohta eksportida.

1. Valige **Salvesta**.

Eksporditud andmed salvestatakse teie konfigureeritud Azure’i bloobimälu konteinerisse. Konteineris luuakse automaatselt järgmised kaustateed.

- Lähteolemite ja süsteemi loodud olemite jaoks: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Näide: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Eksporditud olemite model.json hakkab olema %ExportDestinationName%-i tasemel
  - Näide: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md#export-data-on-demand). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]