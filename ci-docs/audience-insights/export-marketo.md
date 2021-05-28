---
title: Customer Insightsi andmete eksportimine Marketosse
description: Lugege, kuidas konfigureerida ühendust ja eksportida platvormile Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059311"
---
# <a name="export-segments-to-marketo-preview"></a>Segmentide eksportimine platvormile Marketo (eelversioon)

Eksportige Marketo abil koondatud kliendiprofiilide segmente kampaaniate loomiseks, meiliturunduse pakkumiseks ja konkreetsete kliendirühmade kasutamiseks.

## <a name="prerequisites-for-connection"></a>Ühenduse eeltingimus

-   Teil on [Marketo konto](https://login.marketo.com/) ja asjakohane administraatori identimisteave.
-   Marketos on olemas loendid ja asjakohased ID-d. Lisateavet leiate artiklist [Marketo loendid](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Te olete [konfigureerinud segmendid](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Marketosse saab eksportida korraga kuni miljon profiili.
- Marketosse saab eksportida ainult segmente.
- Miljoni profiiliga segmentide eksportimine võib kesta kuni kolm tundi. 
- Marketosse eksporditavate profiilide arv sõltub Marketoga sõlmitud lepingust.

## <a name="set-up-connection-to-marketo"></a>Ühenduse loomine platvormiga Marketo

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Marketo** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma **[Marketo kliendi-ID, Client secret ja REST Endpoint hostinimi](https://developers.marketo.com/rest-api/authentication/)**. REST lõpp-punkti hostinimi on ainult hostinimi ilma `https://`. Näide: `xyz-abc-123.mktorest.com`. 

1. Valige **Nõustun**, et nõustuda jaotise **Andmete privaatsus ja nõuetele vastavus** tingimustega ja valige **Ühenda**, et Marketoga ühenduda.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus Marketo jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Sisestage oma **[Marketo loendi ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. Loendi ID on lihtsalt arvväärtus. Kui teie Marketo loendi ID on näiteks ST12345A7, eemaldage märk enne ja pärast numbreid ning sisestage `12345`. 

1. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. 

1. Soovi korral saate eksportida **Eesnimi**, **Perekonnanimi**, **Linn**, **Osariik** ja **Riik/regioon**  isikupärastatud meilide loomiseks. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida. Marketosse saate eksportida kuni miljon kliendiprofiili.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). Marketos leiate nüüd oma segmendid jaotisest [Marketo loendid](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Marketosse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Marketo täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
