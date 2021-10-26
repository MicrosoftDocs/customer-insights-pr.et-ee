---
title: Customer Insightsi andmete eksportimine Mailchimpi
description: Lugege, kuidas konfigureerida ühendust ja eksportida Mailchimpi.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 94a9fead56ce8c40b35d4eb41ebdc0d672798dce
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618608"
---
# <a name="export-segments-to-mailchimp-preview"></a>Segmentide eksportimine Mailchimpi (eelversioon)

Eksportige koondatud kliendiprofiilide segmendid MailChimpi, et luua teabelehti ja meilikampaaniad.

## <a name="prerequisites-for-connection"></a>Ühenduse eeltingimus

-   Teil on [Mailchimpi konto](https://mailchimp.com/) ja asjakohane administraatori identimisteave.
-   Mailchimpis on olemas sihtrühmad ja asjakohased ID-d. Lisateavet leiate teemast [Mailchimpi sihtrühmad](https://mailchimp.com/help/create-audience/).
-   Te olete [konfigureerinud segmendid](segments.md)
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni miljoni kliendiprofiili Mailchimp ekspordi kohta.
- Mailchimpi saab eksportida ainult segmente.
- Miljoni kliendiprofiiliga segmentide eksportimiseks võib aega võtta kuni kolm tundi. 
- Kliendiprofiilide arv, mida saate Mailchimp'i eksportida, sõltub ja on piiratud vastavalt teie Mailchimp lepingule.

## <a name="set-up-connection-to-mailchimp"></a>Ühenduse loomine Mailchimpiga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Mailchimp** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda** Mailchimp ühenduse lähtestamiseks.

1. Valige **Autentimine Mailchimpiga** ja sisestage oma Mailchimpi identimisteave.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**. 

## <a name="configure-the-connector"></a>Konnektori konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed**> **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus Mailchimp jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Sisestage oma **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. 

1. Soovi korral saate eksportida **Eesnimi** ja **Perekonnanimi** isikupärastatud meilide loomiseks. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida. Mailchimpi saate eksportida kuni miljon kliendiprofiili.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Mailchimpi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Mailchimp täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
