---
title: Customer Insightsi andmete eksportimine SendGridi
description: Vaadake, kuidas konfigureerida ühendust SendGridiga.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268727"
---
# <a name="connector-for-sendgrid-preview"></a>SendGridi konnektor (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente SendGridi kontaktiloenditesse ja kasutada neid SendGridis kampaaniate ja meiliturunduste jaoks. 

## <a name="prerequisites"></a>Eeltingimused

-   Teil on [SendGridi konto](https://sendgrid.com/) ja asjakohane administraatori identimisteave.
-   SendGridis on olemas kontaktiloendid ja asjakohased ID-d. Lisateavet leiate teemast [SendGrid – kontaktide haldamine](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="connect-to-sendgrid"></a>Ühenda SendGrid

1. Avage **Haldus** > **Ekspordi sihtkohad**.

1. Tehke jaotises **SendGrid** valik **Seadista**.

1. Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="SendGridi ekspordi konfiguratsioonipaan.":::

1. Sisestage oma **SendGridi API võti** [SendGridi API võti](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Sisestage oma **[SendGridi loendi ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda**, et käivitada ühendus SendGridiga.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ekspordi konfigureerimiseks valige **Edasi**.

## <a name="configure-the-connector"></a>Konnektori konfigureerimine

1. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. Korrake samu juhiseid muude valikuliste väljade puhul, nagu **Eesnimi**, **Perekonnanimi**, **Riik/piirkond**, **Maakond**, **Linn** ja **Sihtnumber**.

1. Valige segmendid, mille soovite eksportida. Soovitame **tungivalt mitte eksportida kokku üle 100 000 kliendiprofiili** SendGridi. 

1. Valige **Salvesta**.

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kokku kuni 100 000 profiili SendGridi.
- SendGridi saab eksportida ainult segmente.
- Kuni 100 000 profiili eksportimiseks SendGridi võib kuluda paar tundi. 
- SendGridi eksporditavate profiilide arv sõltub SendGridiga sõlmitud lepingust.

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil SendGridi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et SendGrid täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]