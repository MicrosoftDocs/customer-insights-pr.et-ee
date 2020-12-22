---
title: Rikastamine kolmanda osapoole rikastamisteenusega ettevõttelt HERE Technologies
description: Üldine teave ettevõtte HERE Technologies kolmanda osapoole rikastamise kohta.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668673"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Kliendiprofiilide rikastamine ettevõtte HERE Technologies teenuste abil (eelversioon)

HERE Technologies on asukohaplatvormi ettevõte, mis pakub asukohapõhist teavet ja teenuseid. Ettevõtte HERE Technologies andmete rikastamise teenuste abil saate luua täpsema ülevaate oma klientide asukohast aadressi normaliseerimise, laius- ja pikkuskraadide ekstraktimise ning palju muu kaudu.

## <a name="prerequisites"></a>Eeltingimused

Ettevõtte HERE Technologies rikastamisteenuse konfigureerimiseks peavad olema täidetud järgmised eeltingimused.

- Teil peab olema aktiivne ettevõtte HERE Technologies tellimus. Tellimuseks saate [registreeruda siin](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) või võtta otse [ühendust ettevõttega HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Lisateave ettevõtte HERE Technologies asukohapõhise rikastamise kohta.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Teil on ettevõtte HERE Technologies API võti.

- Teil on [administraatori](permissions.md#administrator) õigused.

## <a name="configuration"></a>Konfiguratsioon

1. Avage **Andmed** > **Rikastamine**.

1. Valige paanilt HERE Technologies **Rikasta mu andmeid**.

   > [!div class="mx-imgBorder"]
   > ![Paan „HERE Technologies“](media/HERE-tile.png "Paan „HERE Technologies“")

1. Sisestage aktiivne **HERE Technologiese API võti**. Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**. 

1. Kinnitage mõlemad sisendid, valides **Loo ühendus HERE-ga**.

1. Valige **Lisa andmed** ja valige, kas soovite vastendada väljad esmase ja/või teisese aadressiga. Saate määrata väljavastendused mõlema aadressi jaoks (nt kodu- ja ettevõtte aadress) ning rikastada mõlema aadressi profiile eraldi. Tehke valik **Edasi**.

1. Määratlege, milliseid teie koondatud profiilide välju tuleks kasutada, et otsida ettevõtte HERE Technologies teenuse kaudu ühtivaid asukohaandmeid. Valitud esmase ja/või teisese aadressi jaoks on vajalikud väljad **Tänav 1** ja **Sihtnumber**. Selleks et vasted oleksid täpsemad, saab lisada rohkem välju.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologiese rikastamise konfigureerimise leht](media/enrichment-HERE-configuration.png "HERE Technologiese rikastamise konfigureerimise leht")

1. Valige **Rakenda**, et lõpetada väljade vastendamine.

## <a name="enrichment-results"></a>Rikastamise tulemused

Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**. Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab). Töötlemise aeg sõltub teie kliendiandmete mahust ja ettevõtte HERE Technologies API vastuseaegadest.

Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt. Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.

Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.

## <a name="next-steps"></a>Järgmised etapid

Rikastatud kliendiandmetele toetumine. Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [Ekspordi andmed](export-destinations.md).

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil ettevõttesse HERE Technologies andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et HERE Technologies täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
