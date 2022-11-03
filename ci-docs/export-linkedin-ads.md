---
title: Segmentide eksportimine LinkedIn Adsi (eelvaade)
description: Lugege, kuidas konfigureerida ühendust ja eksportida LinkedIn Adsi.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 06eb915e352ad545f95e96e6108be0f81f43a451
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725303"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Segmentide eksportimine LinkedIn Adsi (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid LinkedIn Adsi, et luua sobivaid vaatajaskondi. Kasutage sobitatud sihtrühmi ettevõtte sihtimiseks ja kontaktide sihtimiseks.

## <a name="prerequisites"></a>eeltingimused

- Konto [LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) ja vastava administraatori identimisteave.
- Konto [LinkedIn Campaign Manager ID](https://www.linkedin.com/help/lms/answer/a424270).
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmendid vajavad vähemalt ühte konkreetset välja sõltuvalt sellest, kas valite [kontaktide sihtimise või](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ettevõtte sihtimise [LinkedInis](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). Võimalikud väljad on loetletud ekspordi **konfigureerimisel** andmete vastendamise [etapis](#configure-an-export).

## <a name="known-limitations"></a>Teadaolevad piirangud

- Privaatset linki koos teenusega Bring your own storage (BYOS) ei toetata.
- Kuni 100 000 kliendiprofiili LinkedIn Adsi eksportimise kohta, mille täitmine võib võtta kuni 10 minutit.
- Ainult segmendid. Segment peab sisaldama vähemalt 300 kordumatut profiili.

## <a name="set-up-connection-to-linkedin-ads"></a>Ühenduse loomine LinkedIn Adsiga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **LinkedIn Ads**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Esitage oma LinkedIn Campaign Manager konto ID.

1. [Vaadake üle andmete privaatsus ja nõuetele vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Autentimine LinkedIn** ja sisestage oma administraatori mandaadid LinkedIn Campaign Manager jaoks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport.**

1. Valige **Ekspordiühendus** väljal ühendus LinkedIn Ads jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige, kas soovite eksportida andmeid, et teha [kontaktide sihtimist](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) või [ettevõtte sihtimist](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) LinkedInis.

1. Valige jaotises **Andmete sobitamine** kontakti sihtimise jaoks vähemalt üks väli, mis tähistab kliendi meiliaadressi, Apple'i Ad ID-d, Google Ad ID-d, Google Kasutaja ID-d või eesnime ja perekonnanime. Kui valite ettevõtte sihtimise, valige vähemalt üks väli, mis tähistab ettevõtte nime, meilidomeeni, LinkedIni lehe URL-i, aktsiatähist või veebisaiti.

1. Soovi korral lisage ekspordi täpsemaks määratlemiseks väljad. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida. LinkedIn Campaign Manager sobitatud sihtrühmad luuakse automaatselt ekspordiks valitud segmentide nimega. Iga segmendi tulemuseks on eraldi sobitatud sihtrühm.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
