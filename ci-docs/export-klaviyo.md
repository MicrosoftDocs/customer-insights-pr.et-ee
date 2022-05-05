---
title: Customer Insights andmete eksportimine Klaviyo'sse
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Klaviyo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: aa6d43884e5e57af4627b7d5a857d3043abcd026
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642852"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Segmendiloendite eksportimine Klaviyosse (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid Klaviyo ja kasutage neid turundustegevusteks.

## <a name="prerequisites"></a>Eeltingimused

-   Teil on [Klaviyo konto](https://www.klaviyo.com/) ja vastav administraatori mandaat.
-   Olete [konfigureerinud segmendid](segments.md) Customer Insightsis.
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Klaviyo'sse saate ekspordi kohta kokku eksportida kuni 100 000 kliendiprofiili.
- Klaviyo eksportimine on piiratud segmentidega.
- Kuni miljoni kliendiprofiili eksportimine Klaviyo'sse võib võtta kuni 20 minutit. 
- Kliendiprofiilide arv, mida saate Klaviyo'sse eksportida, sõltub ja on piiratud vastavalt teie Klaviyo lepingule.

## <a name="set-up-connection-to-klaviyo"></a>Klaviyo ühenduse häälestamine

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Klaviyo** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage sisselogimise jätkamiseks oma [Klaviyo API-võti](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys). 

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. **Ühenda** Klaviyo ühenduse lähtestamiseks.

1. Valige **Autentimiseks Klaviyoga** ja andke oma haldurile identimisteabe Klaviyo jaoks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ühendus ekspordiks** väljal soovitud ühendus Klaviyo jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Sisestage oma [**Klaviyo loendi ID**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Segmentide Klaviyo eksportimine on vajalik.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights edastada andmeid Klaviyo'le, lubate andmete edastamist väljapoole vastavuse piiri Dynamics 365 Customer Insights jaoks, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste alusel, kuid teie vastutate selle eest, et Klaviyo täidaks kõiki privaatsus- või turvakohustusi, mis teil võivad olla. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
