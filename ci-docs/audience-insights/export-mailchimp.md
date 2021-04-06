---
title: Customer Insightsi andmete eksportimine Mailchimpi
description: Vaadake, kuidas konfigureerida ühendust Mailchimpiga.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598196"
---
# <a name="connector-for-mailchimp-preview"></a>Mailchimpi konnektor (eelversioon)

Eksportige koondatud kliendiprofiilide segmendid MailChimpi, et luua teabelehti ja meilikampaaniad.

## <a name="prerequisites"></a>Eeltingimused

-   Teil on [Mailchimpi konto](https://mailchimp.com/) ja asjakohane administraatori identimisteave.
-   Mailchimpis on olemas sihtrühmad ja asjakohased ID-d. Lisateavet leiate teemast [Mailchimpi sihtrühmad](https://mailchimp.com/help/create-audience/).
-   Te olete [konfigureerinud segmendid](segments.md)
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="connect-to-mailchimp"></a>Loo ühendus Mailchimpiga

1. Avage **Haldus** > **Ekspordi sihtkohad**.

1. Tehke jaotises **Mailchimp** valik **Seadista**.

1. Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Sisestage oma **[Mailchimpi sihtrühma ID](https://mailchimp.com/help/find-audience-id/)** ja valige **Ühenda**, et käivitada ühendus Mailchimpiga.

1. Valige **Autentimine Mailchimpiga** ja sisestage oma Mailchimpi identimisteave.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Mailchimpi ühenduse ekspordi kuvatõmmis":::

1. Ekspordi konfigureerimiseks valige **Edasi**.

## <a name="configure-the-connector"></a>Konnektori konfigureerimine

1. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. 

1. Soovi korral saate isikupärastatud meilide loomiseks täiendavalt eksportida väljad **Eesnimi** ja **Perekonnanimi**. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida. Mailchimpi saate eksportida kuni miljon kliendiprofiili.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Väljade ja segmentide valimine Mailchimpi eksportimiseks":::

1. Valige **Salvesta**.

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab). Mailchimpis leiate nüüd oma segmendid jaotisest [Mailchimpi sihtrühmad](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Teadaolevad piirangud

- Mailchimpi saab eksportida korraga kuni miljon profiili.
- Mailchimpi saab eksportida ainult segmente.
- Miljoni profiiliga segmentide eksportimiseks võib teenusepakkuja tõttu kuluda kuni kolm tundi. 
- Mailchimpi eksporditavate profiilide arv sõltub Mailchimpiga sõlmitud lepingust.

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Mailchimpi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Mailchimp täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]