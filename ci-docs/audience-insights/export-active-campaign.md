---
title: Customer Insights andmete eksportimine ActiveCampaigni
description: Vaadake, kuidas konfigureerida ühendust ja eksportida ActiveCampaigni.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 089b9b0d76437e695f797f941ed384734d8f772e
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227804"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmentide eksportimine ActiveCampaigni (eelversioon)

Eksportige ühtsete kliendiprofiilide segmendid ActiveCampaigni ja kasutage neid turundustegevusteks.

## <a name="prerequisites"></a>Eeltingimused

-   Teil on [ActiveCampaign konto](https://www.activecampaign.com/) ja vastav administraatori mandaat.
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide ühildatud kliendiprofiilid sisaldavad meiliaadressiga välja.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Ühe ekspordi kohta saate eksportida kuni miljon kliendiprofiili ActiveCampaign'i ja see võib võtta kuni 90 minutit.
- ActiveCampaign eksportimine on piiratud segmentidega.
- Kliendiprofiilide arv, mida saate ActiveCampaign'i eksportida, sõltub teie ActiveCampaign lepingust.

## <a name="set-up-connection-to-activecampaign"></a>Saate häälestada ActiveCampaign ühendust

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **ActiveCampaign** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma [ActiveCampaign API võti ja REST lõpp-punkti hostinimi](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). REST lõpp-punkti hostinimi on ainult hostinimi ilma https://. 

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. **Ühenda** ActiveCampaign ühenduse lähtestamiseks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ühendus ekspordiks** väljal soovitud ühendus ActiveCampaign jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Sisestage oma [**ActiveCampaigni loendi ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Segmentide ActiveCampaign eksportimine on vajalik. Soovi korral saate isikupärastatud meilide loomiseks eksportida eesnime, perekonnanime ja telefoni. Nende väljade vastendamiseks valige Lisa atribuut.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights edastada andmeid ActiveCampaign'i, lubate andmete edastamist väljapoole vastavuse piiri Dynamics 365 Customer Insights jaoks, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste alusel, kuid teie vastutate selle eest, et ActiveCampaign täidaks kõiki privaatsus- või turvakohustusi, mis teil võivad olla. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
