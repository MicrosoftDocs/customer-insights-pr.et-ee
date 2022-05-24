---
title: Customer Insightsi andmete eksportimine Marketosse
description: Lugege, kuidas konfigureerida ühendust ja eksportida platvormile Marketo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7354b0aeafbe95e60d172b16c26d83c5dc25fb96
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642942"
---
# <a name="export-segments-to-marketo-preview"></a>Segmentide eksportimine platvormile Marketo (eelversioon)

Eksportige Marketo abil koondatud kliendiprofiilide segmente kampaaniate loomiseks, meiliturunduse pakkumiseks ja konkreetsete kliendirühmade kasutamiseks.

## <a name="prerequisites-for-connection"></a>Ühenduse eeltingimus

-   Teil on [Marketo konto](https://login.marketo.com/) ja asjakohane administraatori identimisteave.
-   Marketos on olemas loendid ja asjakohased ID-d. Lisateavet leiate artiklist [Marketo loendid](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Te olete [konfigureerinud segmendid](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni miljoni kliendiprofiili Marketo ekspordi kohta.
- Marketosse saab eksportida ainult segmente.
- Miljoni kliendiprofiiliga segmentide eksportimiseks võib aega võtta kuni kolm tundi. 
- Kliendiprofiilide arv, mida saate Marketo'sse eksportida, sõltub ja on piiratud vastavalt teie Marketo lepingule.

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

1. **Valige jaotises Andmete sobitamine** vähemalt üks väli, mis tähistab kliendi meiliaadressi või kliendi Marketo ID-d. 

1. Soovi korral saate eksportida **Eesnimi**, **Perekonnanimi**, **Linn**, **Osariik** ja **Riik/regioon**  isikupärastatud meilide loomiseks. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida. Marketosse saate eksportida kuni miljon kliendiprofiili.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). Marketos leiate nüüd oma segmendid jaotisest [Marketo loendid](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Marketosse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Marketo täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE [footer-include](includes/footer-banner.md)]