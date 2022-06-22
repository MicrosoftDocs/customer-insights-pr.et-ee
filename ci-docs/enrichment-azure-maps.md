---
title: Kliendiprofiilide rikastamine Azure Mapsi asukohaandmetega
description: Üldine teave Azure Maps esimese osapoole rikastamise kohta.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a806b2d0c791972c967c90694527608b4def9f3f
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953623"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Kliendiprofiilide rikastamine Azure Mapsi abil (eelvaade)

Azure Maps pakub asukohakeskseid andmeid ja teenuseid georuumilistel andmetel põhinevate kogemuste pakkumiseks sisseehitatud asukohateabe abil. Azure Mapsi andmete rikastamise teenused täiustavad teie klientide asukohateabe täpsust. See toob võimalusi, nagu näiteks normaliseerimine ning laius- ja pikkuskraadide eraldamise rakendusele Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>eeltingimused

- Aktiivne Azure Mapsi tellimus. Tellimuse [saamiseks registreeruge või saate tasuta prooviversiooni](https://azure.microsoft.com/services/azure-maps/).

- Azure Mapsi [ühenduse](connections.md) konfigureerib [administraator](#configure-the-connection-for-azure-maps).

## <a name="configure-the-connection-for-azure-maps"></a>Konfigureerige ühendus Azure Mapsi jaoks

Peate olema Customer Insightsi administraator [ja teil peab olema](permissions.md#admin) aktiivne Azure Mapsi API-võti.

1. Valige rikastamise konfigureerimisel **Lisa ühendus** või minge **Administraator** > **Ühendused** ja valige **Seadista** Azure Mapsi paanil.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Mapsi ühenduse konfigureerimise leht.":::

1. Sisestage ühenduse nimi ja kehtiv Azure Mapsi API-võti.

1. Vaadake üle ja esitage oma nõusolek [Andmete privaatsuse ja nõuetele vastavus](#data-privacy-and-compliance) kohta, valides suvandi **Nõustun**.

1. Konfiguratsiooni kinnitamiseks valige **Kinnita** ja seejärel valige **Salvesta**.

### <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights edastada andmeid Azure Mapsi, lubate andmete edastamist väljapoole vastavuse piiri Dynamics 365 Customer Insights jaoks, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab need andmed teie juhiste kohaselt, kuid vastutate selle eest, et Azure Maps täidaks kõik teie privaatsus- või turbekohustused. Lisateavet leiate jaotisest [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **Suvand Rikasta minu andmeid** paanil Asukoht **paanil** Microsoft Azure Maps.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Mapsi paan.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Valige ühendus. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Tehke valik **Edasi**.

1. **Valige kliendi andmestik** ja valige profiil või segment, mida soovite Microsofti andmetega rikastada. Olem *Klient* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

1. Määratlege, millist tüüpi välju ühtsetest profiilidest sobitamiseks kasutada: esmane ja/või sekundaarne aadress. Mõlemale aadressile saate määrata välja kaardistamise ja mõlema aadressi profiilid eraldi rikastada. Näiteks kodune aadress ja ettevõtte aadress. Tehke valik **Edasi**.

1. Vastendage väljad Azure Mapsi asukohaandmetega. Valitud esmase ja/või teisese aadressi jaoks on vajalikud väljad **Tänav 1** ja **Sihtnumber**. Suurema vaste täpsuse tagamiseks lisage rohkem välju.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Azure Mapsi atribuudi vastendamine.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Vaadake üle **täpsemad sätted**, mis pakuvad täpsemate kasutusjuhtumite käsitlemisel maksimaalset paindlikkust. Järgmisi vaikeväärtusi ei ole tavaliselt vaja muuta.

   - **Aadressitüüp**: parim aadressivaste tagastab isegi siis, kui see pole täielik. Ainult täielike aadresside (nt aadresside, mis sisaldavad majanumbrit) toomine tühjendage kõik märkeruudud peale **punktiaadresside**.
   - **Keel**: aadressid naasevad aadressipiirkonnal põhinevas keeles. Standardiseeritud aadressikeele rakendamiseks valige ripploendist soovitud keel. Näiteks valides inglise **tagastab** **Kopenhaagen, Taani** asemel **København, Danmark**.
   - **Maksimaalne tulemuste** arv: tulemuste arv aadressi kohta.

1. Tehke valik **Edasi**.

1. Sisestage **rikastamise nimi** ja väljundolemi **nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Rikastamisprotsessi alustamiseks või lehele Rikastamine naasmise **lähedal** valige **Käivita**.

## <a name="enrichment-results"></a>Rikastamise tulemused

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Põlluga **rikastatud** klientide arv tagab iga rikastatud välja katvuse süvitsimise.

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
