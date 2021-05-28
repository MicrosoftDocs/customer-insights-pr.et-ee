---
title: Customer Insightsi andmete eksportimine DotDigitali
description: Lugege, kuidas konfigureerida ühendust ja eksportida DotDigitali.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d08504856e1c673ef32433b83bf491d7f4e8cee4
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976841"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a>Segmendiloendite eksportimine DotDigitali (eelversioon)

Eksportige koondatud kliendiprofiilid DotDigitali aadressiraamatutesse ning kasutage neid kampaaniate ja e-turunduse jaoks ning DotDigitali abil kliendisegmentide loomiseks. 

## <a name="prerequisites-for-a-connection"></a>Ühenduse eeltingimus

-   Teil on [DotDigitali konto](https://dotdigital.com/) ja asjakohane administraatori identimisteave.
-   DotDigitalis on olemas aadressiraamatud ja asjakohased ID-d. ID leiate URL-ist, kui valite ja avate aadressiraamatu. Lisateavet leiate teemast [DotDigitali aadressiraamatud](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- DotDigitali saab eksportida korraga kuni miljon profiili.
- DotDigitali saab eksportida ainult segmente.
- Miljoni profiiliga segmentide eksportimiseks võib teenusepakkuja tõttu kuluda kuni kolm tundi. 
- DotDigitali eksporditavate profiilide arv sõltub DotDigitaliga sõlmitud lepingust.

## <a name="set-up-connection-to-dotdigital"></a>Ühenduse loomine DotDigitaliga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **DotDigital** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma **DotDigitali kasutajanimi ja parool**.

1. Sisestage oma **[DotDigitali aadressiraamatu ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda**, et käivitada ühendus DotDigitaliga.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**. 

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus DotDigital jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.


1. Valige jaotise **Andmete vastavusseviimine** väljal **Meil** oma koondatud kliendiprofiili väli, mis tähistab kliendi meiliaadressi. Korrake samu juhiseid muude valikuliste väljade puhul, nagu **Eesnimi**, **Perekonnanimi**, **Täisnimi**, **Sugu** ja **Sihtnumber**.

1. Valige segmendid, mille soovite eksportida. DotDigitali saate eksportida kuni miljon kliendiprofiili.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 
 
DotDigitalis leiate nüüd oma segmendid [DotDigitali aadressiraamatutest](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil DotDigitali andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et DotDigital täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
