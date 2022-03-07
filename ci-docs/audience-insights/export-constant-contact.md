---
title: Customer Insights andmete eksportimine Constant Contacti
description: Lugege, kuidas konfigureerida ühendust ja eksportida Constant Contacti.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8841945814397ffa70c56638a8bed25499c1a06f
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226398"
---
# <a name="export-segments-to-constant-contact-preview"></a>Segmentide eksportimine Constant Contacti (eelversioon)

Saate eksportida ühendatud kliendiprofiilide segmente Constant Contacti ja kasutada neid turundustegevuste jaoks. 

## <a name="prerequisites-for-a-connection"></a>Ühenduse eeltingimus

-   Teil on [Constant Contact konto](https://www.constantcontact.com/account-home) ja vastav administraatori mandaat.
-   Olete sihtrühmaülevaadetes [segmendid konfigureerinud](segments.md).
-   Eksporditud segmentide koondatud kliendiprofiilid sisaldavad välja, mis tähistab meiliaadressi.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Pidevasse Kontakti saate eksportida kuni miljoni kliendiprofiili ekspordi kohta.
- Eksportimine Constant Contacti on piiratud segmentidega.
- Kuni miljoni kliendiprofiili eksportimine Pidevasse Kontakti võib võtta kuni üks tund. 
- Kliendiprofiilide arv, mida saate Pidevasse Kontakti eksportida, sõltub ja on piiratud vastavalt teie Pideva Kontakti lepingule.

## <a name="set-up-connection-to-constant-contact"></a>Ühenduse loomine Constant Contactiga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Constant Contact** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Valige **Ühenda** Constant Contactiga ühenduse lähtestamiseks.

1. Valige **Autentimiseks Konstantse Kontaktiga** ja andke oma haldurile identimisteabe Konstantse Kontakti jaoks. 

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus Constant Contacti jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Sisestage oma [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists). Et leida URL-ist loendi ID, avage loend Constant Contactis.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Segmentide eksportimine Constant Contacti on vajalik.

1. Soovi korral saate isikupärastatud meilide loomiseks täiendavalt eksportida väljad Eesnimi ja Perekonnanimi. Nende väljade vastendamiseks valige **Lisa atribuut**.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate, et Dynamics 365 Customer Insights edastab andmeid Constant Contactile, lubate, et andmed edastatakse väljaspoole vastavuse piiri Dynamics 365 Customer Insights, sealhulgas võimalikud tundliku iseloomuga andmed nagu isikuandmed. Microsoft kannab sellised andmed üle teie juhiste järgi, kuid teie vastutate selle eest, et Constant Contact vastaks teie võimalikele privaatsus- või turvalisuse nõuetele. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).

Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
