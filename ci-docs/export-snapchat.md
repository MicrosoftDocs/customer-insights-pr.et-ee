---
title: Customer Insights andmete eksportimine Snapchati
description: Lugege, kuidas konfigureerida ühendust ja eksportida Snapchati.
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d64b482c322af8632e29ec41d6e34c390c5e646c
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947271"
---
# <a name="export-segments-to-snapchat-preview"></a>Segmentide eksportimine Snapchati (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente Snapchati ja kasutada neid turundustegevuste jaoks. 

## <a name="prerequisites-for-a-connection"></a>Ühenduse eeltingimus

-   Teil on [Snapchat Business account](https://business.snapchat.com/), [Snapchat Ads account](https://ads.snapchat.com/) ja vastavad administraatori mandaadid. YOu peab olema vähemalt organisatsioonikonto liige ja konkreetse reklaamikonto andmehaldur. 
-   Teil on snapchati vaatajaskonna halduris vähemalt üks vaatajaskond, kelle tüüp on SAM (Snap Audience Match). 
-   Olete [konfigureerinud segmendid](segments.md) Customer Insightsis.
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Eksportimine Snapchati on piiratud segmentidega.
- Kuni miljoni kliendiprofiili eksportimine Snapchat'i võib võtta kuni 15 minutit. 

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

1. Sisestage [**Snapchati segmendi/vaatajaskonna ID**](https://businesshelp.snapchat.com/s/article/custom-audiences). Vaatajaskonna ID-d leiate URL-ist pärast publiku valimist Snapchati vaatajaskonna halduris. 

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Segmentide eksportimine Snapchati on vajalik.

1. Valige segmendid, mille soovite eksportida. 

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate, et Dynamics 365 Customer Insights edastab andmeid Snapchatile, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed. Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et Snapchat vastaks teie võimalikele privaatsus- või turvalisuse nõuetele. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
