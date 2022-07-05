---
title: Segmentide eksportimine Ads Manageri Facebook (eelvaade) (sisaldab videot)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Facebook Ads Manageri.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 782abd7d69166b9c81ac25c4d7e191bdeb03a887
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082971"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Segmentide eksportimine Facebook Ads Manageri (eelvaade)

Ühtlustatud kliendiprofiilide segmentide eksport Facebooki reklaamikampaaniasse, et luua Facebooki ja Instagrami kampaaniaid.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Ühenduse eeltingimus

- Teil peab olema [**Facebook Ads konto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), mis sisaldab [**Facebook Business Account**](https://business.facebook.com/).
- Te peate olema [**Facebook Ads konto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) administraator.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 10 miljoni kliendiprofiili Facebook Ads Manager'i eksportimise kohta.
- Facebook Ads Manager saab eksportida ainult segmente.
- Looge või värskendage kohandatud vaatajaskondi ainult Facebook *kliendiloendi* tüüpides.
- Kuni 10 miljoni kliendiprofiiliga segmendi eksportimine võib võtta kuni 90 minutit.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Ühenduse loomine Facebook Ads Manageriga

Enne, kui kasutajad saavad luua ekspordi, peab administraator konfigureerima teenusega ühenduse ja lubama kaastöötajatel ühendust kasutada.

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Facebook Ads Manager** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autendi Facebook Adsiga: 

   1. Valige **Jätka Facebook**, et logida sisse oma Facebook Ads kontole.

   1. Lubage õigus **ads_management** pärast Facebookiga autentimist.

   1. Valige **Facebooki reklaamikonto**, millega soovite töötada.

   1. Valige rippmenüüst **Olemasolev kohandatud vaatajaskond** või looge **Uus kohandatud vaatajaskond**. Lisateavet vt teemast [**Sihtrühmad Facebooki reklaamihalduris**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Selle ekspordiga saate kohandatud vaatajaskondi luua või värskendada teenuses Facebook ainult tüübiga *kliendiloend*. Mõnel juhul näete rippmenüüs erinevat tüüpi kohandatud vaatajaskondi. Kui valite *kliendiloendist* erineva tüübi, toob see kaasa ebaõnnestunud ekspordi. 

1. Vaadake üle **Andmete privaatsus ja vastavaus** ja valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**. 

1. Valige **Ekspordiühendus** väljal ühendus **Facebook Ads Manager** jaotisest. Kui te seda jaotise nime ei näe, pole seda tüüpi ühendused teile saadaval.

1. Suvandis **Põhiidentifikaatori välja valimine** valige **Meil**, **Nimi ja aadress** või **Telefon**, et saata Facebooki reklaamihaldurile. 

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.

1. Vastendage vastavad atribuudid valitud põhiidentifikaatori ühtsest kliendiolemist.
   > [!TIP]
   > Parim võimalus vaste ilmnemiseks on, kui valite põhiidentifikaatoriks **E-kiri**. Täiendavate identifikaatorite lisamine võib vastendamist parandada.

1. Valige **Lisa atribuut**, et kaardistada rohkem atribuute Facebook Ads Managerile saatmiseks. Facebook Ads Manageri atribuudid kaardistavad järgmisi kasutajasõbralikke nimesid: **FN** = **Eesnimi**, **LN** = **Perekonnanimi**, **FI** = **Esinimetäht**, **PHONE** = **Telefon**, **GEN** = **Sugu**, **DOB** = **Sünnikuupäev**, **ST** = **Osariik**, **CT** = **Linn**, **ZIP** = **Sihtnumber**, **COUNTRY** = **Riik/Regioon**

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). 

Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Facebooki reklaamihaldurisse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Facebook Ads täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE [footer-include](includes/footer-banner.md)]
