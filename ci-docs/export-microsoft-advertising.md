---
title: Segmentide eksportimine Microsoft Advertisingusse (eelvaade)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Microsoft Advertisingusse.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca37159ec6473ad5c331a0ce1aa8424d277529ff
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082803"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Segmentide eksportimine Microsoft Advertisingusse (eelvaade)

Customer Insights segmentide eksportimine Microsoft Advertisingusse, et luua kliendisobivuse sihtrühmad. Kasutage neid vaatajaskondi oma reklaamikampaaniate jaoks.

## <a name="prerequisites"></a>Eeltingimused

-   [Microsoft Advertising konto](https://ads.microsoft.com/) ja vastav administraatori mandaat.
-   Olete aktsepteerinud kliendi sobitamise kasutustingimused. 
-   [Konfigureeritud segmendid](segments.md) Customer Insightsis.
-   Eksporditud segmentide ühildatud kliendiprofiilid sisaldavad meiliaadressiga välja.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Microsoft Advertisingusse saate ekspordi kohta kokku eksportida kuni 500 000 kliendiprofiili.
- Eksportimine Microsoft Advertisingusse on piiratud segmentidega.
- Kuni 500 000 kliendiprofiili eksportimine Microsoft Advertisingusse võib võtta kuni 10 minutit. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Ühenduse loomine Microsoft Advertisinguga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Microsoft Advertising** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda** Microsoft Advertisinguga ühenduse lähtestamiseks.

1. Valige **Autentimine Microsoft Advertisinguga** ja sisestage oma administraatori mandaadid Microsoft Advertisingu jaoks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus Microsoft Advertisingu jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Valige eksportimiseks segmendid. Microsoft Advertisingi kliendisobituse sihtrühmad luuakse automaatselt ekspordiks valitud segmentide nimega. Iga segmendi tulemuseks on eraldi kliendisobitatud sihtrühm. 

1. Sisestage oma **Microsofti Advertising Customer ID ja Account ID**. Microsoft Advertisingi sisselogimise korral leiate URL-i parameetritest kliendi ID (`cid`) ja konto ID (`aid`).

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, kliendi meiliaadressiga väli. Segmentide eksportimine Microsoft Advertisingusse on vajalik.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate, et Dynamics 365 Customer Insights edastab andmeid Microsoft Advertisingusse, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed. Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et Microsoft Advertising vastaks teie võimalikele privaatsus- või turvalisuse nõuetele. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insights administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
