---
title: Segmentide eksportimine RollWorksi (eelversioon)
description: Lugege, kuidas konfigureerida ühendust ja eksportida RollWorksi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e13aeca4ee5309f85e7de2986cd1a2ba5d2992fb
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195607"
---
# <a name="export-segments-to-rollworks-preview"></a>Segmentide eksportimine RollWorksi (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente RollWorksi ja kasutada neid turundustegevuste jaoks.

## <a name="prerequisites"></a>eeltingimused

- [RollWorksi konto](https://www.rollworks.com/) ja vastavad administraatori mandaadid.
- [RollWorksi reklaamija ID](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 250 000 kliendiprofiili ühe ekspordi kohta RollWorksi, mille lõpuleviimiseks võib kuluda kuni 10 minutit. Kliendiprofiilide arv, mida saate RollWorksi eksportida, sõltub teie lepingust RollWorksiga.
- Ainult segmendid.

## <a name="set-up-connection-to-rollworks"></a>Ühenduse loomine RollWorksiga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **RollWorks**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada.  Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Autentimine RollWorksiga** ja sisestage oma administraatori mandaadid RollWorksi jaoks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus RollWorks jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Sisestage oma **RollWorksi reklaamija ID**.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
