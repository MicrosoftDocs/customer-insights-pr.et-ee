---
title: Customer Insights andmete eksportimine Snapchati
description: Lugege, kuidas konfigureerida ühendust ja eksportida Snapchati.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 421dcd5ba5421597cf9dea71a9f9f25c7972a4f26fb49d4b042f8667a317ab5d
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033396"
---
# <a name="export-segments-to-snapchat-preview"></a>Segmentide eksportimine Snapchati (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente Snapchati ja kasutada neid turundustegevuste jaoks. 

## <a name="prerequisites-for-a-connection"></a>Ühenduse eeltingimus

-   Teil on [Snapchat Business account](https://business.snapchat.com/), [Snapchat Ads account](https://ads.snapchat.com/) ja vastavad administraatori mandaadid.
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Eksportimine Snapchati on piiratud segmentidega.
- Kuni 1 miljoni profiili eksportimine Snapchati võib võtta kuni 15 minutit lõpuleviimiseks. 

## <a name="set-up-connection-to-snapchat"></a>Ühenduse loomine Snapchatiga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Snapchat** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda** Snapchat ühenduse lähtestamiseks.

1. Valige **Autentimine Snapchatiga** ja sisestage oma administraatori mandaadid Snapchati jaoks. 

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus Snapchat jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Sisestage [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).

1. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. Segmentide eksportimine Snapchati on vajalik.

1. Valige segmendid, mille soovite eksportida. 

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate, et Dynamics 365 Customer Insights edastab andmeid Snapchatile, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed. Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et Snapchat vastaks teie võimalikele privaatsus- või turvalisuse nõuetele. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.