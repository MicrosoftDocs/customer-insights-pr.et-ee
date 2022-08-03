---
title: Segmentide eksportimine Facebook Ads Manageri (eelvaade) (sisaldab videot)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Facebook Ads Manageri.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195009"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Segmentide eksportimine Facebook Ads Manageri (eelvaade)

Ühtlustatud kliendiprofiilide segmentide eksport Facebooki reklaamikampaaniasse, et luua Facebooki ja Instagrami kampaaniaid.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>eeltingimused

- [Facebook Reklaamikonto](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account), mis sisaldab ärikontot [Facebook](https://business.facebook.com/).
- Administraatori õigused Reklaamikontol [Facebook](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 10 miljonit kliendiprofiili reklaamihaldurisse Facebook eksportimise kohta, mis võib võtta kuni 90 minutit.
- Ainult segmendid.
- Facebook *kliendiloendi* tüüp ainult kohandatud [vaatajaskondades](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > Mõnel juhul võite ripploendis näha eri tüüpi kohandatud vaatajaskondi. Kui valite kliendiloendist *erineva* tüübi, siis eksportimine nurjub.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Ühenduse loomine Facebook Ads Manageriga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Facebook Ads Manager**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. [Lubage kaasautoritel kasutada ühendust ekspordiks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autendi Facebook Adsiga:

   1. Valige **Jätka Facebook**, et logida sisse oma Facebook Ads kontole.

   1. Lubage õigus **ads_management** pärast Facebookiga autentimist.

   1. Valige **Facebooki reklaamikonto**, millega soovite töötada.

   1. Valige rippmenüüst **Olemasolev kohandatud vaatajaskond** või looge **Uus kohandatud vaatajaskond**.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Väljal **Ühendus ekspordiks** valige ühendus jaotisest Facebook Ads Manager. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Väljal **Ühenda andmed** valige **E-post**, **Nimi ja aadress** või **Telefon**, et saata Ads Managerile Facebook.

1. Vastendage vastavad atribuudid valitud põhiidentifikaatori ühtsest kliendiolemist.
   > [!TIP]
   > Parim võimalus vaste ilmnemiseks on, kui valite põhiidentifikaatoriks **E-kiri**. Täiendavate identifikaatorite lisamine võib vastendamist parandada.

1. Valige **Lisa atribuut**, et kaardistada rohkem atribuute Facebook Ads Managerile saatmiseks. Facebook Ads Manageri atribuudid kaardistavad järgmisi kasutajasõbralikke nimesid: **FN** = **Eesnimi**, **LN** = **Perekonnanimi**, **FI** = **Esinimetäht**, **PHONE** = **Telefon**, **GEN** = **Sugu**, **DOB** = **Sünnikuupäev**, **ST** = **Osariik**, **CT** = **Linn**, **ZIP** = **Sihtnumber**, **COUNTRY** = **Riik/Regioon**

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
