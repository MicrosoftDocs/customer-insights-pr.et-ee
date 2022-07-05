---
title: Kliendiprofiilide rikastamine HERE Technologiesiga (eelvaade)
description: Üldine teave ettevõtte HERE Technologies kolmanda osapoole rikastamise kohta.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052046"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Kliendiprofiilide rikastamine HERE Technologiesiga (eelvaade)

HERE Technologies on asukohaplatvormi ettevõte, mis pakub asukohapõhist teavet ja teenuseid. HERE Technologies'i andmete rikastamise teenused parandavad teie klientide asukohateabe täpsust. See pakub aadressi normaliseerimist, laiuskraadide ja pikkuskraadide ekstraheerimist ning palju muud.

## <a name="prerequisites"></a>eeltingimused

- Aktiivne HERE Technologies tellimus. Tellimuse [saamiseks registreeruge siin](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) või [võtke otse ühendust HERE Technologiesiga](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you). [Lisateave ettevõtte HERE Technologies asukohapõhise rikastamise kohta.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE-ühenduse [konfigureerib](connections.md) [administraator](#configure-the-connection-for-here-technologies).

## <a name="configure-the-connection-for-here-technologies"></a>Konfigureerige ühendus HERE Technologies jaoks

Peate olema Customer Insightsi administraator [ja teil peab olema](permissions.md#admin) aktiivne HERE Technologies API võti.

1. Valige **rikastamise konfigureerimisel Lisa ühendus** või avage **administraatoriühendused** > **ja** valige **paanil HERE Technologies käsk Häälesta**.

1. Sisestage ühenduse nimi ja kehtiv HERE Technologies API võti.

1. Vaadake üle ja esitage oma nõusolek [Andmete privaatsuse ja nõuetele vastavus](#data-privacy-and-compliance) kohta, valides suvandi **Nõustun**.

1. Konfiguratsiooni kinnitamiseks valige **Kinnita** ja seejärel valige **Salvesta**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="HERE technologies ühenduse konfiguratsiooni leht.":::

### <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil ettevõttesse HERE Technologies andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et HERE Technologies täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insights administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **Rikasta minu andmed** asukoha **kohta** paanilt HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Paan HERE Technologies.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Valige ühendus. Võtke ühendust administraatoriga, kui see pole saadaval.

1. Tehke valik **Edasi**.

1. **Valige Kliendi andmekogum** ja valige profiil või segment, mida soovite rikastada HERE Technologies andmetega. Olem *Klient* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

1. Määratlege, millist tüüpi välju ühtsetest profiilidest sobitamiseks kasutada: esmane ja/või sekundaarne aadress. Mõlemale aadressile saate määrata välja kaardistamise ja mõlema aadressi profiilid eraldi rikastada. Näiteks kodune aadress ja ettevõtte aadress. Tehke valik **Edasi**.

1. Vastendage oma väljad HERE Technologies andmetega. Valitud esmase ja/või teisese aadressi jaoks on vajalikud väljad **Tänav 1** ja **Sihtnumber**. Suurema vaste täpsuse tagamiseks lisage veel välju.

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Sisestage **rikastamise nimi** ja väljundolemi **nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Rikastamisprotsessi alustamiseks või lehele Rikastamine naasmise **lähedal** valige **Käivita**.

## <a name="view-enrichment-results"></a>Rikastamise tulemuste kuvamine

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Põlluga **rikastatud** klientide arv tagab iga rikastatud välja katvuse süvitsimise.

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
