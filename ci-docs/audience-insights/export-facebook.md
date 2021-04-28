---
title: Customer Insightsi andmete eksportimine Facebooki reklaamihaldurisse
description: Lugege, kuidas konfigureerida ühendust ja eksportida Facebook Ads Manageri.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906805"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Segmentide loendi eksportimine Facebook Ads Manageri (eelvaade)

Ühtlustatud kliendiprofiilide segmentide eksport Facebooki reklaamikampaaniasse, et luua Facebooki ja Instagrami kampaaniaid.

## <a name="prerequisites-for-connection"></a>Ühenduse eeltingimus

- Teil peab olema [**Facebook Ad konto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), mis sisaldab [**Facebook Business kontot**](https://business.facebook.com/).
- Peate olema [**Facebooki reklaamikonto**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) administraator.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Facebook Ads Manageri saab eksportida korraga kuni 10 miljonit profiili.
- Facebook Ads Manager saab eksportida ainult segmente.
- Looge või värskendage kohandatud vaatajaskondi ainult Facebook *kliendiloendi* tüüpides.
- 10 miljoni profiiliga segmentide eksportimine võib kesta kuni 90 minutit.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Ühenduse loomine Facebook Ads Manageriga

Enne, kui kasutajad saavad luua ekspordi, peab administraator konfigureerima teenusega ühenduse ja lubama kaastöötajatel ühendust kasutada.

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Facebook Ads Manager** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks **Administraatorid**. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autendi Facebook Adsiga: 

   1. Valige **Jätka rakendusega Facebook**, et logida oma Facebooki reklaamikampaaniasse sisse.

   1. Lubage õigus **ads_management** pärast Facebookiga autentimist.

   1. Valige **Facebooki reklaamikonto**, millega soovite töötada.

   1. Valige ripploendist **olemasolev kohandatud sihtrühm** või looge **uus kohandatud sihtrühm**. Lisateavet vt teemast [**Sihtrühmad Facebooki reklaamihalduris**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Selle ekspordiga saate kohandatud vaatajaskondi luua või värskendada teenuses Facebook ainult tüübiga *kliendiloend*. Mõnel juhul näete rippmenüüs erinevat tüüpi kohandatud vaatajaskondi. Kui valite *kliendiloendist* erineva tüübi, toob see kaasa ebaõnnestunud ekspordi. 

1. Vaadake üle **Andmete privaatsus ja vastavaus** ja valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**. 

1. Valige **Ekspordiühendus** väljal ühendus **Facebook Ads Manager** jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Suvandis **Põhiidentifikaatori välja valimine** valige **Meil**, **Nimi ja aadress** või **Telefon**, et saata Facebooki reklaamihaldurile. 

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**.

1. Vastendage vastavad atribuudid valitud põhiidentifikaatori ühtsest kliendiolemist.
   > [NÄPUNÄIDE] Parim võimalus vaste ilmnemiseks on, kui valite põhiidentifikaatoriks **Meil**. Täiendavate identifikaatorite lisamine võib vastendamist parandada.

1. Valige **Lisa atribuut**, et kaardistada rohkem atribuute Facebook Ads Managerile saatmiseks. Facebook Ads Manageri atribuudid kaardistavad järgmisi kasutajasõbralikke nimesid: **FN** = **Eesnimi**, **LN** = **Perekonnanimi**, **FI** = **Esinimetäht**, **PHONE** = **Telefon**, **GEN** = **Sugu**, **DOB** = **Sünnikuupäev**, **ST** = **Osariik**, **CT** = **Linn**, **ZIP** = **Sihtnumber**, **COUNTRY** = **Riik/Regioon**

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Facebooki reklaamihaldurisse andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Facebook Ads täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
