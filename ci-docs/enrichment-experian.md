---
title: Kliendiprofiilide rikastamine demograafiaga Experian (eelversioon)
description: Üldine teave Experian kolmanda osapoole rikastamise kohta.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237991"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Kliendiprofiilide rikastamine demograafiaga Experian (eelversioon)

Experian on tarbija- ja ärikrediidi aruandluse ja turundusteenuste ülemaailmne liider. Andmete rikastamise teenuste Experian abil saate oma kliente sügavamalt mõista, rikastades oma kliendiprofiile demograafiliste andmetega, nagu leibkonna suurus, sissetulek ja palju muud.

## <a name="supported-countriesregions"></a>Toetatud riigid/piirkonnad

Praegu toetame kliendiprofiilide rikastamist ainult Ameerika Ühendriikides.

## <a name="prerequisites"></a>eeltingimused

- Aktiivne Experian tellimus. Kordustellimuse saamiseks [võtke Experian](https://www.experian.com/marketing-services/contact) otse ühendust. [Lugege lisateavet Experian andmerikastamine](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Ühenduse Experian [konfigureerib](connections.md) [administraator](#configure-the-connection-for-experian).

- Experian Teie jaoks loodud SSH-toega turvalise transpordi (ST) konto Experian kasutaja ID, osapoole ID ja mudelinumber.

## <a name="configure-the-connection-for-experian"></a>Konfigureerige Experian ühendus

Peate olema Customer Insightsi administraator [ning](permissions.md#admin) teil peab Experian olema kasutaja ID, osapoole ID ja mudelinumber.

1. Valige **Rikastamise konfigureerimisel Lisa ühendus** või minge jaotisse **Administraatori** > **ühendused** ja valige **paanil käsk Häälesta** Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian ühenduse konfiguratsiooni paan.":::

1. Sisestage ühenduse nimi ning turvalise transpordi konto kehtiv kasutaja ID, osapoole ID ja mudelinumber Experian.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Valige **konfiguratsiooni valideerimiseks Kinnita** ja seejärel valige **Salvesta**.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **Rikasta minu andmeid** paanilt **Demograafiline teave** Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian paani rikastamise ülevaate lehel.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Valige ühendus. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Tehke valik **Edasi**.

1. **Valige kliendiandmete kogum** ja valige profiil või segment, millelt Experian soovite demograafiliste andmetega rikastada. Kliendi *olem* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendiandmete kogumi valimisel.":::

1. Määratlege, millist tüüpi välju oma ühtsetest profiilidest kasutada demograafiliste andmete vastendamiseks allikast Experian. Vähemalt üks väljadest **Nimi ja aadress**, **Telefon** või **E-post** on nõutav. Suurema vastetäpsuse tagamiseks lisage teisi välju. Tehke valik **Edasi**.

1. Vastendage oma väljad demograafiliste andmetega alates Experian.

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
