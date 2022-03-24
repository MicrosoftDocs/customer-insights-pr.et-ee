---
title: Rikastamine kolmanda osapoole rikastamisega HERE Technologies
description: Üldine teave ettevõtte HERE Technologies kolmanda osapoole rikastamise kohta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 1cbbad9bfe559bcb15b23894fc7475507aae8add
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376275"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Kliendiprofiilide rikastamine ettevõtte HERE Technologies teenuste abil (eelversioon)

HERE Technologies on asukohaplatvormi ettevõte, mis pakub asukohapõhist teavet ja teenuseid. Ettevõtte HERE Technologies andmete rikastamise teenuste abil saate luua täpsema ülevaate oma klientide asukohast aadressi normaliseerimise, laius- ja pikkuskraadide ekstraktimise ning palju muu kaudu.

## <a name="prerequisites"></a>Eeltingimused

Ettevõtte HERE Technologies rikastamisteenuse konfigureerimiseks peavad olema täidetud järgmised eeltingimused.

- Teil peab olema aktiivne ettevõtte HERE Technologies tellimus. Tellimuseks saate [registreeruda siin](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) või [kontakteeruda ettevõttega HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) otse. [Lisateave ettevõtte HERE Technologies asukohapõhise rikastamise kohta.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [ühendus](connections.md) on saadaval *või* teil on [administraatori](permissions.md#admin) õigused ja HERE Technologies API võti.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage **Andmed** > **Rikastamine**. 

1. Valige **Mu andmete rikastamine** HERE Technologies paanil ja valige **Alustamine**.

   > [!div class="mx-imgBorder"]
   > ![Paan HERE Technologies.](media/HERE-tile.png "Paan „HERE Technologies“")

1. Valige [ühendus](connections.md) ripploendist. Kui ühendus pole saadaval, pöörduge administraatori poole. Kui olete administraator, saate ühenduse luua, kui valite suvandi **Lisa ühendus**. Valige **HERE Technologies** ripploendist. 

1. Valige **Ühenda HERE Technologies**, et kinnitada valik.

1.  Valige **Edasi** ja valige **Kliendi andmekomplekt**, mida soovite HERE Technologies asukoha andmetega rikastada. Saate valida olemi **Klient**, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendiandmete kogumi valimisel.":::

1. Valige, kas soovite vastendada väljad esmase ja/või teisese aadressiga. Mõlemale aadressile saate määrata välja kaardistamise ja mõlema aadressi profiilid eraldi rikastada. Näiteks kui olemas on kodu- ja äriaadress. Tehke valik **Edasi**.

1. Määratlege, milliseid teie koondatud profiilide välju tuleks kasutada, et otsida ettevõtte HERE Technologies teenuse kaudu ühtivaid asukohaandmeid. Valitud esmase ja/või teisese aadressi jaoks on vajalikud väljad **Tänav 1** ja **Sihtnumber**. Selleks et vasted oleksid täpsemad, saab lisada rohkem välju.

   > [!div class="mx-imgBorder"]
   > ![HERE Technologiese rikastamise konfigureerimise leht.](media/enrichment-HERE-configuration.png "HERE Technologiese rikastamise konfigureerimise leht")

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Peate rikastamise jaoks sisestama nime. 

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

## <a name="configure-the-connection-for-here-technologies"></a>Konfigureerige ühendus HERE Technologies jaoks 

Ühenduste konfigureerimiseks peate olema administraator. Valige **Lisa ühendus** rikastamise konfigureerimisel *või* minge **Administraator** > **Ühendused** ja valige **Seadista** HERE Technologies paanil.

1. Sisestage ühenduse nimi **Kuvatav nimi** väljale.

1. Sisestage sobiv HERE Technologies API võti.

1. Vaadake üle ja esitage oma nõusolek **Andmete privaatsuse ja nõuetele vastavus** kohta, valides suvandi **Nõustun**.

1. Valige **Kontrolli** konfiguratsiooni valideerimiseks.

1. Pärast kontrollimise lõpuleviimist valige **Salvesta**.

   > [!div class="mx-imgBorder"]
   > ![HERE technologies ühenduse konfiguratsiooni leht.](media/enrichment-HERE-connection.png "HERE technologies ühenduse konfiguratsiooni leht")

## <a name="enrichment-results"></a>Rikastamise tulemused

Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**. Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab). Töötlemise aeg sõltub teie kliendiandmete mahust ja ettevõtte HERE Technologies API vastuseaegadest.

Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt. Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.

Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.

## <a name="next-steps"></a>Järgmised etapid

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil ettevõttesse HERE Technologies andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et HERE Technologies täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insights administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
