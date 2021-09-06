---
title: Customer Insights andmete eksportimine Campaign Monitori
description: Lugege, kuidas konfigureerida ühendust ja eksportida Campaign Monitori.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d2cc3ec944faa1d77ffb44e8abb422d753c5625d0ccef75cbb7efb14cb7c3741
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031882"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Segmentide eksportimine Campaign Monitori (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente Campaign Monitori ja kasutada neid turundustegevuste jaoks.

## <a name="prerequisites"></a>Eeltingimused

-   Teil on [Campaign Monitori konto](https://www.campaignmonitor.com/) ja vastav administraatori volikiri.
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Campaign Monitori saate eksportida kuni 1 miljoni profiili ekspordi kohta.
- Eksportimine Campaign Monitori on piiratud segmentidega.
- Kuni 1 miljoni profiili eksportimine Campaign Monitori võib võtta kuni 20 minutit lõpuleviimiseks. 
- Campaign Monitori eksporditavate profiilide arv sõltub ja on piiratud teie lepinguga Campaign Monitoriga.

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

3. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. Segmentide eksportimine Campaign Monitori on vajalik.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate, et Dynamics 365 Customer Insights edastab andmeid Campaign Monitorile, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed. Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et Campaign Monitor vastaks teie võimalikele privaatsus- või turvalisuse nõuetele. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
