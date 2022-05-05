---
title: Customer Insightsi andmete eksportimine Autopilotisse
description: Lugege, kuidas konfigureerida ühendust ja eksportida Autopilot'isse.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01fb04cd1f0acfee1fcc9243269f967942580891
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642705"
---
# <a name="export-segments-to-autopilot-preview"></a>Segmentide eksportimine Autopilot'isse (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente Autopiloti kontaktiloenditesse ja kasutada neid Autopilotis kampaaniate ja meiliturunduste jaoks. 

## <a name="prerequisites-for-a-connection"></a>Ühenduse eeltingimus

-   Teil on [Autopiloti konto](https://www.autopilothq.com/) ja asjakohane administraatori identimisteave.
-   Olete [konfigureerinud segmendid](segments.md) Customer Insightsis.
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Autopilotisse saate kokku eksportida kuni 100 000 kliendiprofiili.
- Autopilotisse saab eksportida ainult segmente.
- Kuni 100 000 kliendiprofiili eksportimine Autopilot'i võib võtta paar tundi. 
- Kliendiprofiilide arv, mida saate Autopilot'i eksportida, sõltub ja on piiratud vastavalt teie Autopilot lepingule.

## <a name="set-up-connection-to-autopilot"></a>Ühenduse loomine Autopilot'iga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Autopilot** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma [Autopiloti API võti](https://autopilot.docs.apiary.io/#).

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda**, et käivitada ühendus Autopilotiga.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus Autopilot jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Korrake samu juhiseid muude valikuliste väljade puhul, nagu **Eesnimi** ja **Perekonnanimi**.

1. Valige segmendid, mille soovite eksportida. Soovitame **tungivalt mitte eksportida kokku üle 100 000 kliendiprofiili** Autopilotisse. 

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Autopilotisse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Autopilot täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE [footer-include](includes/footer-banner.md)]
