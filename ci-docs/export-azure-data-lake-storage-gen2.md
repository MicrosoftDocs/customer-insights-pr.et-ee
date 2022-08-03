---
title: Andmete eksportimine Gen2-sse Azure Data Lake Storage (eelvaade)
description: Vaadake, kuidas konfigureerida ühendust Azure Data Lake Storage Gen2-ga.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196435"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Andmete eksportimine Gen2-sse Azure Data Lake Storage (eelvaade)

Salvestage oma Customer Insightsi andmed Azure Data Lake Storage Gen2 kontole või kasutage seda oma andmete edastamiseks teistesse rakendustesse.

## <a name="prerequisites"></a>eeltingimused

- [Salvestuskonto, mida kasutada Azure Data Lake Gen2-ga](/azure/storage/blobs/create-data-lake-storage-account). Salvestusruumikonto nime ja võtme leidmiseks vaadake teemat [Salvestuskonto sätete haldamine Azure'i portaalis](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Teadaolevad piirangud

- Gen2 puhul Azure Data Lake Storage valige standardjõudluse ja esmaklassilise jõudluse taseme [vahel](/azure/storage/blobs/create-data-lake-storage-account). Kui valite Premium jõudluse järgu, valige [konto tüübiks premium ploki bloobid](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Gen2-ühenduse seadistamine Azure Data Lake Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Azure Data Lake Gen 2**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma Azure Data Lake Storage Gen2 **Konto nimi**, **Konto võti** ja **Konteiner**.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige väljal **Ühendus ekspordiks** ühendus jaotisest Azure Data Lake. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Sisestage Kausta nimi Gen2 salvestusruumi jaoks Azure Data Lake Storage.

1. Märgistage lahter iga olemi kõrval, mida soovite antud sihtkohta eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Eksporditud andmed salvestatakse konfigureeritud Azure Data Lake Gen 2 storage konteinerisse.

> [!TIP]
> Suurt hulka andmeid sisaldavate olemite eksportimine võib viia iga ekspordi puhul mitme CSV-failini samas kaustas. Ekspordi tükeldamine toimub jõudlusega seotud põhjustel, et minimeerida ekspordi lõpuleviimiseks kuluvat aega.

[!INCLUDE [footer-include](includes/footer-banner.md)]
