---
title: Customer Insightsi andmete eksportimine InObisse
description: Siit saate teada, kuidas konfigureerida ühendus ja eksportida InMobisse.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9059607"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Segmendiloendi ja muude andmete eksportimine Rakendusse InMobi (eelvaade)

Eksportige segmendiloendid või muud andmed Customer Insightsi eksemplarist [InObisse](https://www.inmobi.com/).

## <a name="prerequisites"></a>eeltingimused

1. Teil on [InMobi konto](https://www.inmobi.com/) ja administraatori identimisteave.
1. Teil on Azure Blobi salvestusruumi konto nimi ja vastav kontovõti. Lisateavet leiate teemast [Salvestusruumikonto sätete haldamine Azure'i portaalis](/azure/storage/common/storage-account-manage). Salvestuskontol on konteiner, kuhu inMobi andmeid eksportida. Lisateavet leiate teemast [Konteineri loomine](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi loob otseühenduse teie Bloobi salvestusruumiga ja konfigureerib teie andmete automaatse impordi InObisse. Protsessi alustamiseks võtke ühendust oma InMobi esindajaga.

## <a name="known-limitations"></a>Teadaolevad piirangud

1. Azure Blob Storage'i puhul saate valida standardse jõudluse ja Premium-jõudluse taseme [vahel](/azure/storage/blobs/storage-blob-performance-tiers). Kui valite Premium jõudluse järgu, valige [konto tüübiks premium ploki bloobid](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Azure Blob Storage'iga ühenduse häälestamine ja ekspordi konfigureerimine

1. Järgige juhiseid ühenduse häälestamiseks [Azure Blob Storage'iga](export-azure-blob-storage.md).
2. Ekspordi [konfigureerimiseks](export-azure-blob-storage.md#configure-an-export) järgige juhiseid.

[!INCLUDE [footer-include](includes/footer-banner.md)]
