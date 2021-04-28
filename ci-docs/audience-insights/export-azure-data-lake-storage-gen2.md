---
title: Customer Insightsi andmete eksportimine Azure Data Lake Storage Gen2-sse
description: Vaadake, kuidas konfigureerida ühendust Azure Data Lake Storage Gen2-ga.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760046"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a>Ühenduse loomine Azure Data Lake Storage Gen2 (eelversioon)

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Azure Data Lake Gen 2** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma Azure Data Lake Storage Gen2 **Konto nimi**, **Konto võti** ja **Konteiner**.
    - Lisateavet selle kohta, kuidas luua salvestusruumi kontot koos Azure Data Lake Storage Gen2-ga kasutamiseks, leiate teemast [Salvestusruumi konto loomine](/azure/storage/blobs/create-data-lake-storage-account). 
    - Lisateavet Azure Data Lake Gen2 storage konto nime ja konto võtme otsimise kohta leiate [Azure portaalis salvestusruumi konto sätete haldamine](/azure/storage/common/storage-account-manage).

1. Ühenduse loomiseks valige **Salvesta**. 

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus **Azure Data Lake** jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Märgistage lahter iga olemi kõrval, mida soovite antud sihtkohta eksportida.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 

Eksporditud andmed salvestatakse konfigureeritud Azure Data Lake Gen 2 storage konteinerisse. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
