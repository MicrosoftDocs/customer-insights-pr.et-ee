---
title: Customer Insights andmete eksportimine LinkedIn Adsi
description: Lugege, kuidas konfigureerida ühendust ja eksportida LinkedIn Adsi.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 948a7e980df5714034009c92282e78cf2bdcb231
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618286"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmentide eksportimine LinkedIn Adsi (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid LinkedIn Adsi, et luua sobivaid vaatajaskondi. Kasutage sobitatud sihtrühmi ettevõtte sihtimiseks ja kontaktide sihtimiseks.

## <a name="prerequisites"></a>Eeltingimused

-   Teil on [LinkedIn Campaign Manager konto](https://business.linkedin.com/marketing-solutions/ads) ja vastav administraatori sisselogimisandmed.
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide kliendiprofiilid sisaldavad meiliaadressiga välja.

## <a name="known-limitations"></a>Teadaolevad piirangud

- LinkedIn Ads'i saate ekspordi kohta kokku eksportida kuni 100 000 kliendiprofiili.
- Eksportimine LinkedIn Adsi on piiratud segmentidega.
- Kuni 100 000 kliendiprofiili eksportimine LinkedIn Ads'i võib võtta kuni 10 minutit. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Loo LinkedIn Adsi ühendus

1. Avage sihtrühma ülevaadetes **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **LinkedIn Ads** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma [LinkedIn Campaign Manager konto ID](https://www.linkedin.com/help/lms/answer/a424270).

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda** Campaign Monitoriga ühenduse lähtestamiseks.

1. Valige **Autentimine LinkedIn** ja sisestage oma administraatori mandaadid LinkedIn Campaign Manager jaoks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus LinkedIn Ads jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Valige, kas soovite eksportida andmeid, et teha [kontaktide sihtimist](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) või [ettevõtte sihtimist](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) LinkedInis. 

1. Valige jaotises **Andmete sobitamine** kontakti sihtimise jaoks vähemalt üks väli, mis tähistab kliendi meiliaadressi, Apple'i Ad ID-d, Google Ad ID-d, Google Kasutaja ID-d või eesnime ja perekonnanime. Kui valite ettevõtte sihtimise, valige vähemalt üks väli, mis tähistab ettevõtte nime, meilidomeeni, LinkedIni lehe URL-i, aktsiatähist või veebisaiti. Eksportimise täpsemaks määratlemiseks saab valida täiendavaid välju. 

1. Valige segmendid, mille soovite eksportida. LinkedIn Campaign Manager sobitatud sihtrühmad luuakse automaatselt ekspordiks valitud segmentide nimega. Iga segmendi tulemuseks on eraldi sobitatud sihtrühm. 

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate, et Dynamics 365 Customer Insights edastab andmeid LinkedIn Adsi, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed. Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et LinkedIn Ads vastaks teie võimalikele privaatsus- või turvalisuse nõuetele. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insights administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
