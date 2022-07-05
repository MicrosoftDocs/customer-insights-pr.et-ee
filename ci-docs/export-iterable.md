---
title: Segmentide eksportimine iterable'i (eelvaade)
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Iterable'i.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 98d5aeab6b0e932d291213053d509ec72da82e47
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052230"
---
# <a name="export-segments-to-iterable-preview"></a>Segmentide eksportimine iterable'i (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid Iterable'i ja kasutage neid turundustegevuseks.

## <a name="prerequisites"></a>eeltingimused

-   Teil on Iterable'i [konto](https://iterable.com/) ja vastav administraatori identimisteave.
-   Olete [konfigureerinud segmendid](segments.md) Customer Insightsis.
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Iterable'i eksportimine piirdub segmentidega.
- Kuni 1 miljoni kliendiprofiili eksportimine Iterable'i võib võtta kuni 30 minutit. 
- Iterable'i eksportitavate kliendiprofiilide arv sõltub ja on piiratud teie lepingust Iterable'iga.

## <a name="set-up-connection-to-iterable"></a>Ühenduse häälestamine Iterable'iga

1. Minge **Administraator** > **Ühendused**.

1. Ühenduse konfigureerimiseks valige **Lisa ühendus** ja valige **Iterable**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage sisselogimise jätkamiseks oma [Iterable API-võti](https://support.iterable.com/hc/en-us/articles/360043464871). 

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Iterable'iga ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige väljal **Ekspordiühendus** ühendus ühendus jaotisest Iterable. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

3. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Segmentide eksportimine iterable'i on vajalik.Iterable'is loodud loend saab täpselt sama nime kui teie segmendi nimi rakenduses Dynamics 365 Customer Insights.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights andmeid Iterable'ile edastada, lubate andmete edastamist väljaspool nõuetele vastavuse piiri Dynamics 365 Customer Insights, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste kohaselt, kuid teie vastutate selle eest, et Iterable täidaks kõik teie privaatsus- või turbekohustused. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
