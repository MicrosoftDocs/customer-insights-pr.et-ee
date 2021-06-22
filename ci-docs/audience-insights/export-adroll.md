---
title: Customer Insightsi andmete eksportimine AdRolli
description: Lugege, kuidas konfigureerida ühendust ja eksportida AdRoll-i.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124360"
---
# <a name="export-segments-to-adroll-preview"></a>Segmentide eksportimine AdRoll-i (eelversioon)

Eksportige kliendi koondprofiili segmendid AdRolli ja kasutage neid reklaamimiseks. 

## <a name="prerequisites-for-a-connection"></a>Ühenduse eeltingimus

-   Teil on [AdRolli konto](https://www.adroll.com/) ja asjakohane administraatori identimisteave.
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- AdRolli saate ühe ekspordi kohta eksportida kuni 250 000 profiili.
- Vähem kui 100 profiiliga segmente ei saa AdRolli eksportida. 
- AdRolli saab eksportida ainult segmente.
- Kuni 250 000 profiili eksportimiseks AdRolli võib kuluda kuni 10 minutit. 
- AdRolli eksporditavate profiilide arv sõltub AdRollga sõlmitud lepingust ja on sellega piiratud.

## <a name="set-up-connection-to-adroll"></a>Ühenduse loomine AdRoll'iga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **AdRoll** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda**, et käivitada ühendus AdRolliga.

1. Valige **Autentimine AdRolliga** ja sisestage oma AdRolli administraatori identimisteave. 

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus AdRoll jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Sisestage oma **AdRoll Advertiser ID** Lisateavet leiate teemast [AdRoll Advertiser profiilid](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. See on vajalik segmentide eksportimiseks AdRolli.

1. Valige segmendid, mille soovite eksportida. Valige vähemalt 100 liikmega segment. Väiksemaid segmente ei saa eksportida. Lisaks on eksporditava segmendi maksimummaht 250 000 liiget ekspordi kohta. 

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil AdRolli andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et AdRoll täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
