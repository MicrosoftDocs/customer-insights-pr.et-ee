---
title: Customer Insightsi andmete eksportimine DotDigitali
description: Lugege, kuidas konfigureerida ühendust ja eksportida DotDigitali.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f63a0f5f5f93e96681a88fd758381c012a404f43
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642454"
---
# <a name="export-segments-to-dotdigital-preview"></a>Segmentide eksportimine DotDigitali (eelversioon)

Eksportige koondatud kliendiprofiilid DotDigitali aadressiraamatutesse ning kasutage neid kampaaniate ja e-turunduse jaoks ning DotDigitali abil kliendisegmentide loomiseks. 

## <a name="prerequisites-for-a-connection"></a>Ühenduse eeltingimus

-   Teil on [DotDigital'i konto](https://dotdigital.com/) ja olete loonud [API-kasutaja](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Ühenduse loomiseks on vaja API kasutaja mandaati
-   DotDigitalis on olemas aadressiraamatud ja asjakohased ID-d. ID leiate URL-ist, kui valite ja avate aadressiraamatu. Lisateavet leiate teemast [DotDigitali aadressiraamatud](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Olete [konfigureerinud segmendid](segments.md) Customer Insightsis.
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni miljoni kliendiprofiili DotDigitali ekspordi kohta.
- DotDigitali saab eksportida ainult segmente.
- Miljoni kliendiprofiiliga segmentide eksportimiseks võib teenusepakkujapoolsete piirangute tõttu kuluda kuni 3 tundi. 
- Kliendiprofiilide arv, mida saate DotDigital'i eksportida, sõltub ja on piiratud vastavalt teie DotDigital lepingule.

## <a name="set-up-connection-to-dotdigital"></a>Ühenduse loomine DotDigitaliga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **DotDigital** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma **DotDigitali API kasutajanimi ja parool**. 

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


1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Korrake samu juhiseid muude valikuliste väljade puhul, nagu **Eesnimi**, **Perekonnanimi**, **Täisnimi**, **Sugu** ja **Sihtnumber**.

1. Valige segmendid, mille soovite eksportida. DotDigitali saate eksportida kuni miljon kliendiprofiili.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 
 
DotDigitalis leiate nüüd oma segmendid [DotDigitali aadressiraamatutest](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil DotDigitali andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et DotDigital täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE [footer-include](includes/footer-banner.md)]
