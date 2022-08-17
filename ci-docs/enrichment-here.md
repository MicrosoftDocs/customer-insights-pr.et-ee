---
title: Rikasta kliendiprofiile HERE Technologies’iga (eelvaade)
description: Üldine teave ettevõtte HERE Technologies kolmanda osapoole rikastamise kohta.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237853"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Rikasta kliendiprofiile HERE Technologies’iga (eelvaade)

HERE Technologies on asukohaplatvormi ettevõte, mis pakub asukohapõhist teavet ja teenuseid. HERE Technologies’i andmete rikastamise teenused parandavad teie klientide asukohateabe täpsust. See pakub aadressi normaliseerimist, laius- ja pikkuskraadide ekstraheerimist ning palju muud.

## <a name="prerequisites"></a>eeltingimused

- Aktiivne HERE Technologies tellimus. Tellimuse [saamiseks registreeru siin](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) või [võta otse ühendust SIIN Technologies.](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) [Lisateave ettevõtte HERE Technologies asukohapõhise rikastamise kohta.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- HERE [ühenduse](connections.md) konfigureerib [administraator](#configure-the-connection-for-here-technologies).

## <a name="configure-the-connection-for-here-technologies"></a>Konfigureerige ühendus HERE Technologies jaoks

Sa pead olema Customer Insightsis administraator [ja](permissions.md#admin) sul peab olema aktiivne HERE Technologies API võti.

1. Valige **rikastamise konfigureerimisel Lisa ühendus** või minge jaotisse **Administraatori** > **ühendused** ja valige **paanil HERE Technologies käsk Seadista**.

1. Sisestage ühenduse nimi ja kehtiv HERE Technologies API võti.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Valige **konfiguratsiooni valideerimiseks Kinnita** ja seejärel valige **Salvesta**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="HERE technologies ühenduse konfiguratsiooni leht.":::

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **paanilt HERE Technologies paanilt** Rikasta minu andmeid **asukoha** kohta.

   :::image type="content" source="media/HERE-tile.png" alt-text="Paan HERE Technologies.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Valige ühendus. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Tehke valik **Edasi**.

1. **Valige kliendiandmete kogum** ja valige profiil või segment, mida soovite HERE Technologies andmetega rikastada. Kliendi *olem* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

1. Määratlege, millist tüüpi välju oma ühtsetelt profiilidelt vastendamiseks kasutada: esmane ja/või sekundaarne aadress. Mõlemale aadressile saate määrata välja kaardistamise ja mõlema aadressi profiilid eraldi rikastada. Näiteks koduse ja ettevõtte aadressi puhul. Tehke valik **Edasi**.

1. Kaardista oma väljad HERE Technologies andmetega. Valitud esmase ja/või teisese aadressi jaoks on vajalikud väljad **Tänav 1** ja **Sihtnumber**. Suurema vastetäpsuse tagamiseks lisage rohkem välju.

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Sisestage **rikastamise nimi** ja **väljundolemi nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Valige **Käivita**, et alustada rikastamisprotsessi või sulgeda, et naasta **lehele Rikastamised**.

## <a name="view-enrichment-results"></a>Rikastumistulemuste vaatamine

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Põldude **kaupa** rikastatud klientide arv annab iga rikastatud välja katvuse süvitsimineku.

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
