---
title: Segmentide eksportimine rakendusse ActiveCampaign
description: Vaadake, kuidas konfigureerida ühendust ja eksportida ActiveCampaigni.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725395"
---
# <a name="export-segments-to-activecampaign-preview"></a>Segmentide eksportimine ActiveCampaigni (eelversioon)

Eksportige ühtsete kliendiprofiilide segmendid ActiveCampaigni ja kasutage neid turundustegevusteks.

## <a name="prerequisites"></a>eeltingimused

- ActiveCampaigni [konto](https://www.activecampaign.com/) ja vastavad administraatori identimisteabed.
- ActiveCampaigni [loendi ID](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- [ActiveCampaign API-võti](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) ja REST-lõpp-punkti hostinimi.
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Privaatset linki koos teenusega Bring your own storage (BYOS) ei toetata.
- Kuni 1 miljon kliendiprofiili ActiveCampaigni eksportimise kohta, mille täitmiseks võib kuluda kuni 90 minutit. Kliendiprofiilide arv, mida saate ActiveCampaign'i eksportida, sõltub teie ActiveCampaign lepingust.
- Ainult segmendid.

## <a name="set-up-connection-to-activecampaign"></a>Saate häälestada ActiveCampaign ühendust

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **ActiveCampaign**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma ActiveCampaign API võti ja REST lõpp-punkti hostinimi. REST lõpp-punkti hostinimi on ainult hostinimi ilma https://.

1. [Vaadake üle andmete privaatsus ja nõuetele vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport.**

1. Valige **Ühendus ekspordiks** väljal soovitud ühendus ActiveCampaign jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Sisestage oma **ActiveCampaigni loendi ID**.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi.

1. Soovi korral eksportige **eesnimi**, **perekonnanimi** ja **telefon**, et luua isikupärasemaid meilisõnumeid. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
