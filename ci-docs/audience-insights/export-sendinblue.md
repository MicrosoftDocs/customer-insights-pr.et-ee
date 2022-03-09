---
title: Customer Insights andmete eksportimine Sendinblue'sse
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8d870ff31ce2d441e619ac18899c4d1b6c69ca41
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231414"
---
# <a name="export-segments-to-sendinblue-preview"></a>Segmentide eksportimine Sendinblue (eelversioon)

Kampaaniate loomiseks, e-posti teel turundamiseks ja konkreetsete klientide rühmade kasutamiseks saate eksportida ühtsete kliendiprofiilide segmente Sendinblue.

## <a name="prerequisites-for-connection"></a>Ühenduse eeltingimus

-   Teil on [Sendinblue konto](https://www.sendinblue.com/) ja vastav administraatori mandaat.
-   Sendinblue's on olemas loendid ja vastavad ID-d.
-   Te olete [konfigureerinud segmendid](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni miljoni kliendiprofiili Sendinblue ekspordi kohta.
- Sendinblue eksportimine on piiratud segmentidega.
- Miljoni kliendiprofiiliga segmentide eksportimine võib aega võtta 90 minutit. 
- Kliendiprofiilide arv, mida saate Sendinblue'sse eksportida, sõltub ja on piiratud vastavalt teie Sendinblue lepingule.

## <a name="set-up-connection-to-sendinblue"></a>Sendinblue ühenduse häälestamine

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Sendinblue** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage **[SendinBlue API-võti](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Valige **Nõustun**, et kinnitada **Andmete privaatsus ja nõuetele vastavus** ning valige **Ühenda** Sendinblue ühenduse lähtestamiseks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ühendus ekspordiks** väljal soovitud ühendus Sendinblue jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Sisestage oma **Sendinblue loendi ID** 

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. 

1. Soovi korral saate eksportida **Eesnimi**, **Perekonnanimi** ja **Telefon**, et luua rohkem isikupärastatud e-kirju. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida. 

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights edastada andmeid Sendinlue'le, lubate andmete edastamist väljapoole vastavuse piiri Dynamics 365 Customer Insights jaoks, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste alusel, kuid teie vastutate selle eest, et Sendinblue täidaks kõiki privaatsus- või turvakohustusi, mis teil võivad olla. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
