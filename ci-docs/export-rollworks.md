---
title: Customer Insights andmete eksportimine RollWorksi
description: Lugege, kuidas konfigureerida ühendust ja eksportida RollWorksi.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ba63f9146b17ebf6daf5b0a9f39c0d6bc32a1bfa
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642823"
---
# <a name="export-segments-to-rollworks-preview"></a>Segmentide eksportimine RollWorksi (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente RollWorksi ja kasutada neid turundustegevuste jaoks. 

## <a name="prerequisites-for-a-connection"></a>Ühenduse eeltingimus

-   Teil on [RollWorks konto](https://www.rollworks.com/) ja vastav administraatori mandaat.
-   Olete [konfigureerinud segmendid](segments.md) Customer Insightsis.
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- RollWorks'i saate ekspordi kohta kokku eksportida kuni 250 000 kliendiprofiili.
- Vähem kui 100 kliendiprofiiliga segmente ei saa RollWorks'i eksportida. 
- Eksportimine RollWorksi on piiratud segmentidega.
- Kuni 250 000 kliendiprofiili eksportimine RollWorks'i võib võtta kuni 10 minutit. 
- Kliendiprofiilide arv, mida saate RollWorks'i eksportida, sõltub ja on piiratud vastavalt teie RollWorks lepingule.

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

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Segmentide eksportimine RollWorksi on vajalik.

1. Valige segmendid, mille soovite eksportida. Valige vähemalt 100 liikmega segment. Väiksemaid segmente ei saa eksportida. Lisaks on eksporditava segmendi maksimummaht 250 000 liiget ekspordi kohta. 

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate, et Dynamics 365 Customer Insights edastab andmeid RollWorksile, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed. Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et RollWorks vastaks teie võimalikele privaatsus- või turvalisuse nõuetele. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
