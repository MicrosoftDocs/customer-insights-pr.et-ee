---
title: Segmentide eksportimine DotDigitali (eelversioon)
description: Lugege, kuidas konfigureerida ühendust ja eksportida DotDigitali.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196067"
---
# <a name="export-segments-to-dotdigital-preview"></a>Segmentide eksportimine DotDigitali (eelversioon)

Eksportige koondatud kliendiprofiilid DotDigitali aadressiraamatutesse ning kasutage neid kampaaniate ja e-turunduse jaoks ning DotDigitali abil kliendisegmentide loomiseks.

## <a name="prerequisites"></a>eeltingimused

- [DotDigitali konto](https://dotdigital.com/) ja [API kasutaja](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- DotDigitali ID uuest [või olemasolevast aadressiraamatust](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) DotDigitalis. ID leiate URL-ist, kui valite ja avate aadressiraamatu.
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 1 miljon kliendiprofiili ekspordi kohta DotDigitali, mille täitmine võib pakkujapoolsete piirangute tõttu võtta kuni kolm tundi. Kliendiprofiilide arv, mida saate DotDigitali eksportida, sõltub teie lepingust DotDigitaliga.
- Ainult segmendid.

## <a name="set-up-connection-to-dotdigital"></a>Ühenduse loomine DotDigitaliga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **DotDigital**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma **DotDigitali API kasutajanimi ja parool**.

1. Sisestage oma **DotDigitali aadressiraamatu ID**.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus DotDigital jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi.

1. Soovi korral eksportige **eesnimi**, **perekonnanimi**, **täisnimi**, **sugu** ja **sihtnumber**.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Leidke DotDigitalis oma segmendid [DotDigitali aadressiraamatutest](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
