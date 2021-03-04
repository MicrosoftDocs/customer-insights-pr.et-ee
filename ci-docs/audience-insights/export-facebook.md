---
title: Customer Insightsi andmete eksportimine Facebooki reklaamihaldurisse
description: Teave selle kohta, kuidas konfigureerida ühendust Facebooki reklaamihalduriga.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269969"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Facebooki reklaamihalduri konnektor (eelversioon)

Ühtlustatud kliendiprofiilide segmentide eksport Facebooki reklaamikampaaniasse, et luua Facebooki ja Instagrami kampaaniaid.

## <a name="prerequisites"></a>Eeltingimused

- Vajate [**Facebooki reklaamikontot**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), mis hõlmab [**Facebooki ärikontot**](https://business.facebook.com/).
- Peate olema [**Facebooki reklaamikonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) administraator.

## <a name="connect-to-facebook-ads-manager"></a>Facebooki reklaamihalduriga ühenduse loomine

1. Avage **Haldus** > **Ekspordi sihtkohad**.

1. Valige jaotises **Facebooki reklaamihaldur** suvand **Seadistus**.

1. Sisestage väljale **Kuvatav nimi** oma ekspordi sihtkoha äratuntav nimi.

1. Valige **Jätka rakendusega Facebook**, et logida oma Facebooki reklaamikampaaniasse sisse.

1. Lubage õigus **ads_management** pärast Facebookiga autentimist.

1. Valige **Facebooki reklaamikonto**, millega soovite töötada.

1. Valige ripploendist **olemasolev kohandatud sihtrühm** või looge **uus kohandatud sihtrühm**. Lisateavet vt teemast [**Sihtrühmad Facebooki reklaamihalduris**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Ekspordi konfigureerimiseks valige **Edasi**.

## <a name="configure-the-connector"></a>Konnektori konfigureerimine

1. Suvandis **Põhiidentifikaatori välja valimine** valige **Meil**, **Nimi ja aadress** või **Telefon**, et saata Facebooki reklaamihaldurile.

1. Vastendage vastavad atribuudid valitud põhiidentifikaatori ühtsest kliendiolemist.
   > [NÄPUNÄIDE] Parim võimalus vaste ilmnemiseks on, kui valite põhiidentifikaatoriks **Meil**. Täiendavate identifikaatorite lisamine võib vastendamist parandada.

1. Valige **Lisa atribuut**, et vastendada täiendavaid atribuute, mida Facebooki reklaamihaldurile saata. Facebooki reklaamihalduri atribuudid vastendavad järgmisi kasutajasõbralikke nimesid: **FN** = **eesnimi**, **LN** = **perekonnanimi**, **FI** = **esinimetäht**, **PHONE** = **telefon**, **GEN** = **sugu**, **DOB** = **sünnikuupäev**, **ST** = **osariik**, **CT** = **linn**, **ZIP** = **sihtnumber**, **COUNTRY** = **riik/regioon**

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).

## <a name="known-limitations"></a>Teadaolevad piirangud

- Facebooki reklaamihaldurisse saab eksportida korraga kuni kümme miljonit profiili. 
- Facebooki reklaamihaldurisse saab eksportida ainult segmente
- Kümne miljoni profiiliga segmentide eksportimine võib kesta kuni 90 minutit.

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Facebooki reklaamihaldurisse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Facebook Ads täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]