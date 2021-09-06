---
title: Customer Insights andmete eksportimine Sendinblue'sse
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: be52554763b57e1c1ef2f960d52bbae79ac9827913c97ac73b429f66bbf4db37
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036050"
---
# <a name="export-segments-to-sendinblue-preview"></a>Segmentide eksportimine Sendinblue (eelversioon)

Kampaaniate loomiseks, e-posti teel turundamiseks ja konkreetsete klientide rühmade kasutamiseks saate eksportida ühtsete kliendiprofiilide segmente Sendinblue.

## <a name="prerequisites-for-connection"></a>Ühenduse eeltingimus

-   Teil on [Sendinblue konto](https://www.sendinblue.com/) ja vastav administraatori mandaat.
-   Sendinblue's on olemas loendid ja vastavad ID-d.
-   Te olete [konfigureerinud segmendid](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 1 miljon profiili Sendinblue'sse eksportimise kohta.
- Sendinblue eksportimine on piiratud segmentidega.
- Kokku 1 miljoni profiiliga segmentide eksportimiseks võib kuluda kuni 90 minutit. 
- Sendinblue'sse eksporditavate profiilide arv sõltub Sendinblue lepingust ja on piiratud.

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

1. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. 

1. Soovi korral saate eksportida **Eesnimi**, **Perekonnanimi** ja **Telefon**, et luua rohkem isikupärastatud e-kirju. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida. 

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights edastada andmeid Sendinlue'le, lubate andmete edastamist väljapoole vastavuse piiri Dynamics 365 Customer Insights jaoks, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste alusel, kuid teie vastutate selle eest, et Sendinblue täidaks kõiki privaatsus- või turvakohustusi, mis teil võivad olla. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
