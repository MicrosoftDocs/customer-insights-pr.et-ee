---
title: Customer Insightsi andmete eksportimine Braze'i
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Braze'i.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bfc9b34506dc3385b5edf12b31e74d05f2d20655
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642545"
---
# <a name="export-segment-lists-to-braze-preview"></a>Segmendiloendite eksportimine braze'i (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid Braze'i ja kasutage neid turundustegevustes.

## <a name="prerequisites"></a>eeltingimused

-   Teil on Braze'i [konto](https://www.braze.com/) ja vastav administraatori identimisteave.
-   Olete [konfigureerinud segmendid](segments.md) Customer Insightsis.
-   Eksporditud segmentide ühtsed kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi ja Braze'i kliendi ID-d. 

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

1. Valige väljal **Ekspordi** ühendus jaotisest Braze ühendus. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.  

3. **Valige jaotise** Andmete sobitamine **väljal Meil** väli, mis tähistab kliendi meiliaadressi, väljal "Kliendi ID" väli, mis tähistab kliendi Braze ID-d. See on vajalik segmentide eksportimiseks Braze'i. Braze'i segmendid luuakse segmendi sama nimega kui rakenduses Dynamics 365 Customer Insights. Andmete sobitamiseks saate valida täiendavaid valikulisi välju. 

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights andmeid Braze'ile edastada, lubate andmete edastamise väljaspool nõuetele vastavuse piiri Dynamics 365 Customer Insights, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab selliseid andmeid teie juhiste kohaselt, kuid teie vastutate selle eest, et Braze täidaks kõik teie privaatsus- või turbekohustused. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
