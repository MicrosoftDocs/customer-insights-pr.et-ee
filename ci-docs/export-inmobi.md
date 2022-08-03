---
title: Customer Insightsi andmete eksportimine InMobisse
description: Vaadake, kuidas konfigureerida ühendust ja eksportida InMobisse.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195883"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Customer Insightsi andmete eksportimine InMobisse (eelvaade)

Eksportige segmentide loendeid või muid andmeid Customer Insightsi eksemplarist [InMobisse](https://www.inmobi.com/).

## <a name="prerequisites"></a>eeltingimused

- [InMobi konto](https://www.inmobi.com/) ja administraatori identimisteave.
- Azure'i [bloobi salvestusruumi konto](/azure/storage/blobs/create-data-lake-storage-account) nimi ja konto võti. Nime ja võtme leidmiseks vaadake teemat [Salvestuskonto sätete haldamine Azure'i portaalis](/azure/storage/common/storage-account-manage).
- [Azure'i bloobimälu konteiner](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) InMobi andmete eksportimiseks.
- InMobi loob otseühenduse teie Blob Storage'iga ja konfigureerib teie andmete automaatse importimise InMobisse. Protsessi algatamiseks võtke ühendust oma InMobi esindajaga.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Azure'i bloobimälu puhul valige standardjõudluse ja esmaklassilise jõudluse taseme [vahel](/azure/storage/blobs/storage-blob-performance-tiers). Kui valite Premium jõudluse järgu, valige [konto tüübiks premium ploki bloobid](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Azure'i bloobimäluga ühenduse loomine

[Häälestage ühendus Azure'i bloobimäluga](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[Ekspordi konfigureerimine](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
