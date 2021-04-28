---
title: Customer Insights andmete eksportimine RollWorksi
description: Lugege, kuidas konfigureerida ühendust ja eksportida RollWorksi.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760513"
---
# <a name="export-segment-lists-to-rollworks-preview"></a>Segmendiloendite eksportimine RollWorksi (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente RollWorksi ja kasutada neid turundustegevuste jaoks. 

## <a name="prerequisites-for-a-connection"></a>Ühenduse eeltingimus

-   Teil on [RollWorks konto](https://www.rollworks.com/) ja vastav administraatori mandaat.
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- RollWorksi saate eksportida kuni 250 000 profiili ekspordi kohta.
- Vähem kui 100 profiiliga segmente ei saa RollWorksi eksportida. 
- Eksportimine RollWorksi on piiratud segmentidega.
- Kuni 250'000 profiili eksportimine RollWorksi võib võtta kuni 10 minutit lõpuleviimiseks. 
- RollWorksi eksporditavate profiilide arv sõltub ja on piiratud teie lepinguga RollWorksiga.

## <a name="set-up-connection-to-rollworks"></a>Ühenduse loomine RollWorksiga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **RollWorks** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda** RollWorks ühenduse lähtestamiseks.

1. Valige **Autentimine RollWorksiga** ja sisestage oma administraatori mandaadid RollWorksi jaoks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus RollWorks jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Sisestage oma **RollWorks Advertiser ID** [ID RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. Segmentide eksportimine RollWorksi on vajalik.

1. Valige segmendid, mille soovite eksportida. Valige vähemalt 100 liikmega segment. Väiksemaid segmente ei saa eksportida. Lisaks on eksporditava segmendi maksimummaht 250 000 liiget ekspordi kohta. 

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate, et Dynamics 365 Customer Insights edastab andmeid RollWorksile, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed. Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et RollWorks vastaks teie võimalikele privaatsus- või turvalisuse nõuetele. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
