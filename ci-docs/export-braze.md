---
title: Segmentide eksportimine braze'i (eelvaade)
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Braze'i.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082677"
---
# <a name="export-segments-to-braze-preview"></a>Segmentide eksportimine braze'i (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid Braze'i ja kasutage neid turundustegevustes.

## <a name="prerequisites"></a>eeltingimused

- Braze'i [konto](https://www.braze.com/) ja vastavad administraatori identimisteave.
- Olemasolevad [segmendid Braze'is](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide ühtsed kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi ja Braze'i kliendi ID-d.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Braze'i eksportimine on piiratud segmentidega.
- Kuni 1 miljoni kliendiprofiili eksportimine Braze'i võib võtta kuni 40 minutit.
- Braze'i eksporditavate kliendiprofiilide arv sõltub braze'iga sõlmitud lepingust ja on piiratud.

## <a name="set-up-connection-to-braze"></a>Ühenduse häälestamine Braze'iga

1. Minge **Administraator** > **Ühendused**.

1. Ühenduse konfigureerimiseks valige **Lisa ühendus** ja valige **Braze**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisselogimise jätkamiseks esitage oma [Braze API-võti](https://www.braze.com/docs/api/basics/).

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Ühenduse avamiseks Braze'iga valige **Ühenda**.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige väljal **Ekspordi** ühendus jaotisest Braze ühendus. Kui te seda jaotist ei näe, pole teile seda tüüpi ühendusi saadaval.  

1. **Lisage ekspordile kuvatav nimi**.

1. Lisage väljale Braze Segmendi API identifikaator, kuhu soovite eksportida, väljale **Braze Segment API identifikaator**. Identifikaatori leiate Braze'i platvormi segmendi üksikasjadest.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Valige väljal **Kliendi ID** väli, mis tähistab kliendi Braze ID-d. See on vajalik segmentide eksportimiseks Braze'i. Soovi korral saate valida rohkem välju.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights andmeid Braze'ile edastada, lubate andmete edastamise väljaspool nõuetele vastavuse piiri Dynamics 365 Customer Insights, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste kohaselt, kuid teie vastutate selle eest, et Braze täidaks kõik teie privaatsus- või turbekohustused. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
