---
title: Kliendiprofiilide rikastamine LiveRampi identiteediandmetega (eelvaade)
description: Rikastage kliendiprofiile LiveRamp andmetega.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196343"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Kliendiprofiilide rikastamine LiveRampi identiteediandmetega (eelvaade)

LiveRamp pakub deterministlikku võrguühenduseta identiteedilahendust ja kliendiandmete konsolideerimist. Saate vastendada oma kliendiandmetes olevaid isiklikke identifikaatoreid AbiliTeci identiteedigraafikuga ja saada AbiliTeci ID-sid. Seejärel saate neid ID-sid kasutada oma kliendiandmete paremaks ühendamiseks.

## <a name="supported-countriesregions"></a>Toetatud riigid/piirkonnad

Praegu toetame kliendiprofiilide rikastamist LiveRamp andmetega ainult Ameerika Ühendriikides.

## <a name="prerequisites"></a>eeltingimused

- Aktiivne LiveRamp tellimus. Tellimuse saamiseks võtke ühendust oma LiveRampi konto meeskonnaga [dynamics@liveramp.com](mailto:dynamics@liveramp.com) või lisateabe saamiseks.

- Aktiivne AbiliTeci tellimus koos kliendi ID-ga ja salajane juurdepääs API-le. Lisateavet vaadake [jaotisest AbiliTec API developer hub](https://developers.liveramp.com/abilitec-api/).

- LiveRamp-ühenduse [...](connections.md)[konfigureerib](#configure-the-connection-for-liveramp) administraator.

## <a name="configure-the-connection-for-liveramp"></a>LiveRampi ühenduse konfigureerimine

Peate olema Customer Insightsi administraator [ning](permissions.md#admin) teil peab olema aktiivne LiveRamp kliendi ID ja salajane.

1. Rikastamise konfigureerimisel valige **Lisa ühendus** või minge jaotisse **Administraatori** > **ühendused** ja valige **LiveRamp-paanil käsk Seadista**.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfiguratsioonipaan teenusega LiveRamp AbiliTec ühenduse loomiseks.":::

1. Sisestage ühenduse nimi ja kehtiv LiveRamp kliendi ID ning saladus.

1. Vaadake üle ja esitage oma nõusolek [Andmete privaatsuse ja nõuetele vastavus](#data-privacy-and-compliance) kohta, valides suvandi **Nõustun**.

1. Valige **konfiguratsiooni valideerimiseks Kinnita** ja seejärel valige **Salvesta**.

### <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights andmete edastamise LiveRampi, lubate edastada andmeid väljaspool nõuetele vastavuse piiri, sealhulgas potentsiaalselt tundlike andmete, näiteks isikuandmete puhul Dynamics 365 Customer Insights. Microsoft edastab need andmed teie korraldusel, kuid teie vastutate selle eest, et LiveRamp täidaks kõiki teie privaatsus- või turbekohustusi. Lisateabe saamiseks vaadake Microsofti [privaatsusavaldust](https://go.microsoft.com/fwlink/?linkid=396732). Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **Rikasta minu andmeid** **paanilt LiveRamp**.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identiteedipaan rikastamise ülevaate lehel.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Valige ühendus. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Tehke valik **Edasi**.

1. **Valige kliendiandmete kogum** ja valige profiil või segment, mida soovite LiveRampist identiteediandmetega rikastada. Kliendi *olem* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

1. Määratlege, millist tüüpi välju oma ühendatud profiilidest kasutada LiveRamp'i identiteediandmete sobitamiseks. Nõutav on vähemalt üks väljadest **Nimi ja aadress**, **E-post** või **Telefon**. Suurema vastetäpsuse tagamiseks lisage teisi välju. Tehke valik **Edasi**.

1. Vastendage oma väljad LiveRampi identifitseerimisandmetega.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Andmete kaardistamise võimalused LiveRamp rikastamiseks.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Sisestage **rikastamise nimi** ja **väljundolemi nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Valige **Käivita**, et alustada rikastamisprotsessi või sulgeda, et naasta **lehele Rikastamised**.

## <a name="view-enrichment-results"></a>Rikastumistulemuste vaatamine

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Põldude **kaupa** rikastatud klientide arv annab iga rikastatud välja katvuse süvitsimineku.

## <a name="next-steps"></a>Järgmised toimingud

Rikastatud kliendiandmetele toetumine. AbiliTeci ID-de kasutamine kliendiprofiilide konsolideerimiseks isikupõhisesse vaatesse.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
