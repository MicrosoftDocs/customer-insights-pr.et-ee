---
title: Customer Insights andmete eksportimine Campaign Monitori
description: Lugege, kuidas konfigureerida ühendust ja eksportida Campaign Monitori.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: be9c92a087ab4664077d18fe8585bf96715c1535
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228148"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Segmentide eksportimine Campaign Monitori (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente Campaign Monitori ja kasutada neid turundustegevuste jaoks.

## <a name="prerequisites"></a>Eeltingimused

-   Teil on [Campaign Monitori konto](https://www.campaignmonitor.com/) ja vastav administraatori volikiri.
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kampaania jälgimisse saate eksportida kuni miljoni kliendiprofiili ekspordi kohta.
- Eksportimine Campaign Monitori on piiratud segmentidega.
- Kuni miljoni kliendiprofiili eksportimine Kampaania Jälgimisse võib võtta kuni 20 minutit. 
- Kliendiprofiilide arv, mida saate Kampaania Jälgimisse eksportida, sõltub ja on piiratud vastavalt teie Kampaania Jälgimise lepingule.

## <a name="set-up-connection-to-campaign-monitor"></a>Campaign Monitoriga ühenduse loomine

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Campaign Monitor** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda** Campaign Monitoriga ühenduse lähtestamiseks.

1. Valige **Autentimine Campaign Monitoriga** ja sisestage oma administraatori mandaadid Campaign Monitori jaoks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus Campaign Monitori jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Sisestage [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Looge API-võti](https://www.campaignmonitor.com/api/getting-started/) esmalt Campaign Monitori **Konto sätted** sätetest, et vaadata API-loendi ID-d.  

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Segmentide eksportimine Campaign Monitori on vajalik.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate, et Dynamics 365 Customer Insights edastab andmeid Campaign Monitorile, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed. Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et Campaign Monitor vastaks teie võimalikele privaatsus- või turvalisuse nõuetele. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
