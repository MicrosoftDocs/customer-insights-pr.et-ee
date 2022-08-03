---
title: Andmete eksportimine Azure'i bloobimällu (eelvaade)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Blob storage'isse.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195699"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>Andmete eksportimine Azure'i bloobimällu (eelvaade)

Saate salvestada oma Customer Insights andmed bloobimällu või kasutada seda oma andmete edastamiseks teistesse rakendustesse.

## <a name="prerequisites"></a>eeltingimused

- Azure'i [bloobi salvestusruumi konto](/azure/storage/blobs/create-data-lake-storage-account) nimi ja konto võti. Nime ja võtme leidmiseks vaadake teemat [Salvestuskonto sätete haldamine Azure'i portaalis](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Teadaolevad piirangud

- Azure'i bloobimälu puhul valige standardjõudluse ja esmaklassilise jõudluse taseme [vahel](/azure/storage/blobs/storage-blob-performance-tiers). Kui valite Premium jõudluse järgu, valige [konto tüübiks premium ploki bloobid](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>Blob Storage'iga ühenduse loomine

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Azure'i bloobimälu**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage **Konto nimi**, **Konto võti** ja **Konteiner** bloobimälu konto jaoks.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Selle ekspordi konfigureerimiseks peab teil [olema selle ühenduse tüübi jaoks õigus](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Kui lülitasite sisse Azure'i [bloobimälu konto pehme kustutamise sätte](/azure/storage/blobs/soft-delete-blob-enable), siis eksportimine nurjub. Andmete bloobidele eksportimiseks lülitage ajutine kustutamine välja.

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus Azure Blob Storage jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Sisestage Bloobimälu kausta nimi.

1. Märgistage lahter iga olemi kõrval, mida soovite antud sihtkohta eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Eksporditud andmed salvestatakse konfigureeritud bloobimälukonteinerisse. Konteineris luuakse automaatselt järgmised kaustateed.

- Lähteolemite ja süsteemi loodud olemite jaoks:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  Näide: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > Suurt hulka andmeid sisaldavate olemite eksportimine võib viia iga ekspordi puhul mitme CSV-failini samas kaustas. Ekspordi tükeldamine toimub jõudlusega seotud põhjustel, et minimeerida ekspordi lõpuleviimiseks kuluvat aega.

- Eksporditud üksuste mudel.json asub *%ExportDestinationName%* tasemel.  
  
  Näide: Dynamics365CustomerInsights/CustomerInsights_ abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
