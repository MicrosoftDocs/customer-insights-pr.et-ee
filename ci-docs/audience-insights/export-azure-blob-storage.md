---
title: Customer Insights andmete eksportimine Azure Blob Storage'isse
description: Lugege, kuidas konfigureerida ühendust ja eksportida Blob storage'isse.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 294feff2f77c3756fbadb36c90aab430454f5967
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760184"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Segmendiloendi ja muude andmete eksportimine Azure'i Blob Storage'isse (eelversioon)

Saate salvestada oma Customer Insights andmed bloobimällu või kasutada seda oma andmete edastamiseks teistesse rakendustesse.

## <a name="set-up-the-connection-to-blob-storage"></a>Loo Azure Bloobimälu ühendus

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Azure Blob Storage** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage **Konto nimi**, **Konto võti** ja **Konteiner** bloobimälu konto jaoks.
    - Lisateavet bloobimälu konto nime ja konto võtme otsimise kohta leiate [Azure portaalis salvestusruumi konto sätete haldamine](/azure/storage/common/storage-account-manage).
    - Lisateavet konteineri loomise kohta leiate teemast [Konteineri loomine](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Ühenduse loomiseks valige **Salvesta**. 

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus Azure Blob Storage jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Märgistage lahter iga olemi kõrval, mida soovite antud sihtkohta eksportida.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab).     
Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 

Eksporditud andmed salvestatakse konfigureeritud bloobimälukonteinerisse. Konteineris luuakse automaatselt järgmised kaustateed.

- Lähteolemite ja süsteemi loodud olemite jaoks: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Näide: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- Model.json eksporditud olemitele on %ExportDestinationName% tasemel
  - Näide: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
