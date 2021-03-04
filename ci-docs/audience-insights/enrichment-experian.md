---
title: Rikastamine kolmanda osapoole rikastamisteenusega Experianilt
description: Üldine teave Experiani kolmanda osapoole rikastamise kohta.
ms.date: 12/10/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: baf3cc58a233b70c48fb94ac4a543d162f91bdd1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269555"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Kliendi profiilide rikastamine Experiani demograafiliste andmetega (eelvaade)

Experian on üleilmne liider tarbijate ja ärikrediidi aruandluse ning turundusega seotud teenuste valdkonnas. Experiani andmete rikastamise teenustega saate oma klientidest luua põhjalikuma ülevaate, rikastades klientide profiile selliste demograafiliste andmetega nagu leibkonna suurus, sissetulek ja palju muud.

## <a name="prerequisites"></a>Eeltingimused

Experiani konfigureerimiseks peavad olema täidetud järgmised eeltingimused.

- Teil on olemas aktiivne Experiani kordustellimus. Kordustellimuse saamiseks [võtke otse ühendust Experianiga](https://www.experian.com/marketing-services/contact). [vaadake lisateavet Experiani andmete rikastamise kohta](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Teil on olemas kasutaja ID, poole ID ja mudeli number SSH-toega teenuse Secure Transport (ST) konto jaoks, mille Experian teie jaoks lõi.
- Omate sihtrühmaülevaadetes [administraatori](permissions.md#administrator) õigusi.

## <a name="configuration"></a>Konfiguratsioon

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige Experiani paanilt suvand **Rikasta minu andmeid**.

   > [!div class="mx-imgBorder"]
   > ![Experiani paan](media/experian-tile.png "Experiani paan")

1. Valige suvand **Alusta** ja sisestage oma Experian Secure Transporti konto kasutaja ID, poole ID ja mudeli number. Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**. Kinnitage kogu sisestatud teave, valides suvandi **Rakenda**.

## <a name="map-your-fields"></a>Väljade vastendamine

1.  Valige **Lisa andmed** ja valige **Kliendiandmete kogum**, mida soovite Experiani demograafiliste andmetega rikastada. Saate valida olemi **Klient**, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.

1. Valige oma peamised identifikaatorid üksusest **Nimi ja aadress**, **E-post** või **Telefon**, et saata need Experiani identiteedi lahenduseks.

   > [!TIP]
   > Rohkemate võtmeidentifikaatori atribuutide saatmine Experianile annab tõenäoliselt suurema vastavuse määra.

1. Valige suvand **Edasi** ja vastendage oma koondatud kliendiolemi asjakohased atribuudid valitud võtmeidentifikaatori väljade jaoks.

1. Valige suvand **Lisa atribuut**, et vastendada mis tahes täiendavaid atribuute, mida soovite Experianile saata.

1.  Väljavastenduse lõpule viimiseks valige **Salvesta**.

    > [!div class="mx-imgBorder"]
    > ![Experiani väljade vastendamine](media/experian-field-mapping.png "Experiani väljade vastendamine")

## <a name="enrichment-results"></a>Rikastamise tulemused

Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**. Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab). Töötlemisaeg sõltub teie kliendiandmete mahust ja rikastamistoimingutest, mille Experian on teie konto jaoks seadistanud.

Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt. Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.

Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.

## <a name="next-steps"></a>Järgmised etapid

Rikastatud kliendiandmetele toetumine. Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [Ekspordi andmed](export-destinations.md).

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Experiani andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Experian täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]