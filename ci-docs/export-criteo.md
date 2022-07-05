---
title: Segmentide eksportimine Criteosse (eelvaade)
description: Vaadake, kuidas ühendust konfigureerida ja Criteosse eksportida.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082782"
---
# <a name="export-segments-to-criteo-preview"></a>Segmentide eksportimine Criteosse (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid kampaaniate loomiseks, e-posti turunduse pakkumiseks ja konkreetsete kliendirühmade kasutamiseks Criteoga.

## <a name="prerequisites-for-connection"></a>Ühenduse eeltingimus

-   Teil on [Criteo Dynamicsi sihtimise konto](https://www.criteo.com/login/) ja vastavad administraatori identimisteave.
-   Te olete [konfigureerinud segmendid](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 1 miljon kliendiprofiili Criteo ekspordi kohta.
- Eksportimine Criteosse piirdub segmentidega.
- 1 miljoni kliendiprofiiliga segmentide eksportimine võib võtta kuni 30 minutit. 
- Kliendiprofiilide arv, mida saate Criteosse eksportida, sõltub ja piirab teie lepingut Criteoga.

## <a name="set-up-connection-to-criteo"></a>Ühenduse häälestamine Criteoga

1. Minge **Administraator** > **Ühendused**.

1. Ühenduse konfigureerimiseks valige **Lisa ühendus** ja valige **Criteo**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valige **Nõustun** andmete privaatsuse ja nõuetele vastavuse **kinnitamisega** ning valige **Ühenda**, et lähtestada ühendus Criteoga.

1. Valige **Criteoga** autentsus ja esitage Criteo jaoks oma administraatori kasutajanimi ja mandaat. 

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige väljal **Ekspordiühendus** ühendus jaotisest Criteo ühendus. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval. 

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. 

1. Soovi korral saate eksportida **reklaamija ID** ja **nime**

1. Valige segmendid, mille soovite eksportida. 

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights andmeid Criteole edastada, lubate andmete edastamise väljaspool nõuetele vastavuse piiri Dynamics 365 Customer Insights, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste kohaselt, kuid teie vastutate selle eest, et Criteo täidaks kõik privaatsus- või turbekohustused, mis teil võivad olla. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](includes/footer-banner.md)]
