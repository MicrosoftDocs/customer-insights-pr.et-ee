---
title: Segmentide eksportimine Constant Contacti (eelversioon)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Constant Contacti.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c0affd3ed45f462696850813bd50331061dde780
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724496"
---
# <a name="export-segments-to-constant-contact-preview"></a>Segmentide eksportimine Constant Contacti (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente Constant Contacti ja kasutada neid turundustegevuste jaoks.

## <a name="prerequisites"></a>eeltingimused

- Pideva [kontakti konto](https://www.constantcontact.com/account-home) ja vastavad administraatori identimisteabed.
- Pideva [kontaktiloendi ID](https://app.constantcontact.com/pages/contacts/ui#lists). Et leida URL-ist loendi ID, avage loend Constant Contactis.
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.
- Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Privaatset linki koos teenusega Bring your own storage (BYOS) ei toetata.
- Kuni 1 miljon kliendiprofiili püsikontakti eksportimise kohta, mille täitmiseks võib kuluda kuni üks tund. Pidevasse kontakti eksportitavate kliendiprofiilide arv sõltub teie lepingust püsikontaktiga.
- Ainult segmendid.

## <a name="set-up-connection-to-constant-contact"></a>Ühenduse loomine Constant Contactiga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Pidev kontakt**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. [Vaadake üle andmete privaatsus ja nõuetele vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse lähtestamiseks valige **Ühenda**.

1. Valige **Autentimiseks Konstantse Kontaktiga** ja andke oma haldurile identimisteabe Konstantse Kontakti jaoks.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport.**

1. Valige **Ekspordiühendus** väljal ühendus Constant Contacti jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Sisestage oma **pidevate kontaktide loendi ID**.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi.

1. Soovi korral eksportige **eesnimi** ja **perekonnanimi** lisaväljadena, et luua isikupärasemaid e-kirju. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
