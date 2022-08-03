---
title: Ekspordi segmendid MoEngage'i
description: Siit saate teada, kuidas konfigureerida ühendust ja eksportida MoEngage'i.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199187"
---
# <a name="export-segments-to-moengage-preview"></a>Segmentide eksportimine MoEngage'i (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid MoEngage'i ja kasutage neid MoEngage'is e-posti turunduseks.

## <a name="prerequisites-for-a-connection"></a>Ühenduse eeltingimus

- [MoEngage'i konto](https://www.moengage.com/) ja vastavad administraatori mandaadid.
- MoEngage'i API võti moEngage'i seadetest > API-st.
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 100 000 kliendiprofiili ekspordi kohta MoEngage'i, mis võib võtta kuni 15 minutit. Kliendiprofiilide arv, mida saate MoEngage'i eksportida, sõltub teie lepingust MoEngage'iga.
- Ainult segmendid.

## <a name="set-up-connection-to-moengage"></a>Ühenduse seadistamine MoEngage'iga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **ühenduse konfigureerimiseks MoEngage**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma [MoEngage Data API ID ja API võti](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Valige **Ühenda**, et lähtestada ühendus MoEngage'iga.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa eksport**.

1. Valige väljal **Ekspordiühendus** jaotisest MoEngage ühendus. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Korrake samu samme ka teiste valikuliste väljade puhul.

1. Valige segmendid, mille soovite eksportida. Loome ühe või mitu segmenti, millel on sama nimi kui MoEngage'is jaotises **Segmentide kohandatud segmendid** > **valitud segmendid**.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
