---
title: Kliendiprofiilide rikastamine Azure Mapsi asukohaandmetega (eelvaade)
description: Üldine teave Azure Maps esimese osapoole rikastamise kohta.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238037"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Kliendiprofiilide rikastamine Azure Mapsi asukohaandmetega (eelvaade)

Azure Maps pakub asukohakeskseid andmeid ja teenuseid, et pakkuda georuumilistel andmetel põhinevaid funktsioone sisseehitatud asukohaanalüüsiga. Azure Mapsi andmete rikastamise teenused täiustavad teie klientide asukohateabe täpsust. See toob võimalusi, nagu näiteks normaliseerimine ning laius- ja pikkuskraadide eraldamise rakendusele Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>eeltingimused

- Aktiivne Azure Mapsi tellimus. Tellimuse [saamiseks registreeruge või hankige tasuta prooviperiood](https://azure.microsoft.com/services/azure-maps/).

- Azure Mapsi [ühenduse](connections.md) konfigureerib [administraator](#configure-the-connection-for-azure-maps).

## <a name="configure-the-connection-for-azure-maps"></a>Konfigureerige ühendus Azure Mapsi jaoks

Peate olema Customer Insightsi administraator [ja](permissions.md#admin) teil peab olema aktiivne Azure Mapsi API võti.

1. Valige rikastamise konfigureerimisel **Lisa ühendus** või minge **Administraator** > **Ühendused** ja valige **Seadista** Azure Mapsi paanil.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Mapsi ühenduse konfigureerimise leht.":::

1. Sisestage ühenduse nimi ja kehtiv Azure Maps API võti.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Valige **konfiguratsiooni valideerimiseks Kinnita** ja seejärel valige **Salvesta**.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **paanil Asukoht** kaartidelt **suvand Rikasta minu andmeid** Microsoft Azure.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Mapsi paan.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Valige ühendus. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Tehke valik **Edasi**.

1. Valige **kliendiandmete kogum** ja profiil või segment, mida soovite Microsofti andmetega rikastada. Kliendi *olem* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

1. Määratlege, millist tüüpi välju oma ühtsetelt profiilidelt vastendamiseks kasutada: esmane ja/või sekundaarne aadress. Mõlemale aadressile saate määrata välja kaardistamise ja mõlema aadressi profiilid eraldi rikastada. Näiteks koduse ja ettevõtte aadressi puhul. Tehke valik **Edasi**.

1. Vastendage oma väljad Azure Mapsi asukohaandmetega. Valitud esmase ja/või teisese aadressi jaoks on vajalikud väljad **Tänav 1** ja **Sihtnumber**. Suurema vastetäpsuse tagamiseks lisage rohkem välju.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Mapsi atribuutide vastendamine.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Vaadake üle **täpsemad sätted**, mis pakuvad täpsemate kasutusjuhtumite käsitlemiseks maksimaalset paindlikkust. Järgmisi vaikeväärtusi pole aga tavaliselt vaja muuta.

   - **Aadresside** tüüp: tagastab parima aadressi vaste isegi siis, kui see pole täielik. Ainult täielike aadresside (nt aadresside, mis sisaldavad majanumbrit) toomine tühjendage kõik märkeruudud peale **punktiaadresside**.
   - **Keel**: aadressid tagastatakse keeles aadressipiirkonna alusel. Standardiseeritud aadressikeele rakendamiseks valige ripploendist soovitud keel. Näiteks valides **inglise keele**, naaseb **Kopenhaagen, Taani**, mitte **København, Danmark**.
   - **Maksimaalne tulemuste** arv: tulemuste arv aadressi kohta.

1. Tehke valik **Edasi**.

1. Sisestage **rikastamise nimi** ja **väljundolemi nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Valige **Käivita**, et alustada rikastamisprotsessi või sulgeda, et naasta **lehele Rikastamised**.

## <a name="view-enrichment-results"></a>Rikastumistulemuste vaatamine

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Põldude **kaupa** rikastatud klientide arv annab iga rikastatud välja katvuse süvitsimineku.

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
