---
title: Segmentide eksportimine Klaviyosse (eelvaade)
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e45ca5827afa29d97a746bd1a474c2346cc32d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196757"
---
# <a name="export-segments-to-klaviyo-preview"></a>Segmentide eksportimine Klaviyosse (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid Klaviyo ja kasutage neid turundustegevusteks.

## <a name="prerequisites"></a>eeltingimused

- [Klaviyo konto](https://www.klaviyo.com/) ja vastavad administraatori mandaadid.
- [Klaviyo API võti](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- [Klaviyo nimekirja ID](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Klaviyosse eksportimise kohta kuni 1 miljon kliendiprofiili, mille lõpuleviimiseks võib kuluda kuni 20 minutit. Kliendiprofiilide arv, mida saate Klaviyosse eksportida, sõltub teie lepingust Klaviyoga.
- Ainult segmendid.

## <a name="set-up-connection-to-klaviyo"></a>Klaviyo ühenduse häälestamine

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Klaviyo**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage sisselogimise jätkamiseks oma Klaviyo API-võti.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Autentimiseks Klaviyoga** ja andke oma haldurile identimisteabe Klaviyo jaoks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ühendus ekspordiks** väljal soovitud ühendus Klaviyo jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Sisestage oma **Klaviyo loendi ID**.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
