---
title: Customer Insights andmete eksportimine Omnisendi
description: Lugege, kuidas konfigureerida ühendust ja eksportida Omnisendi.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 15fc6fc2426ad3958268e5bcc200b8eb2b0fd13a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226757"
---
# <a name="export-segments-to-omnisend-preview"></a>Segmentide eksportimine Omnisendi (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente Omnisendi ja kasutada neid turundustegevuste jaoks.

## <a name="prerequisites"></a>Eeltingimused

-   Teil on [Omnisend konto](https://www.omnisend.com/) ja vastav administraatori mandaat.
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Ühe ekspordi kohta saate eksportida kuni miljon kliendiprofiili Omnisend'i ja see võib võtta kuni 4 tundi.
- Eksportimine Omnisendi on piiratud segmentidega.
- Kliendiprofiilide arv, mida saate Omnisend'i eksportida, sõltub teie Omnisend lepingust.

## <a name="set-up-connection-to-omnisend"></a>Ühenduse loomine Omnisendiga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Omnisend** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma [Omnisend API võti](https://support.omnisend.com/en/articles/1061890-generating-api-key).

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda** Omnisend ühenduse lähtestamiseks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus Omnisend jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Segmentide eksportimine Omnisendi on vajalik. Soovi korral saate eksportida Eesnimi, Perekonnanimi, Aadress, Riik/regioon, Osariik, Linn ja Postiindeks isikupärastatud meilide loomiseks. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate, et Dynamics 365 Customer Insights edastab andmeid Omnisendile, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed. Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et Omnisend vastaks teie võimalikele privaatsus- või turvalisuse nõuetele. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
