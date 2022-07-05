---
title: Kliendiprofiilide rikastamine LiveRampi identiteediandmetega (eelvaade)
description: Kliendiprofiilide rikastamine LiveRampi andmetega.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 334440493c50448005ec90d0cfac11358d677b73
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082194"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Kliendiprofiilide rikastamine LiveRampi identiteediandmetega (eelvaade)

LiveRamp pakub deterministlikku võrguühenduseta identiteedilahendust ja kliendiandmete konsolideerimist. Saate vastendada kliendiandmetes olevad isikuidentifikaatorid AbiliTeci identiteedigraafikuga ja saada AbiliTeci ID-d. Seejärel saate neid ID-sid kasutada oma kliendiandmete paremaks ühendamiseks.

## <a name="supported-countriesregions"></a>Toetatud riigid/piirkonnad

Praegu toetame kliendiprofiilide rikastamist LiveRampi andmetega ainult Ameerika Ühendriikides.

## <a name="prerequisites"></a>eeltingimused

- Aktiivne LiveRampi tellimus. Tellimuse saamiseks võtke ühendust oma LiveRampi konto meeskonnaga või [dynamics@liveramp.com](mailto:dynamics@liveramp.com) lisateabe saamiseks.

- Aktiivne AbiliTeci tellimus, millel on kliendi ID ja salajane API-le juurdepääsemiseks. Lisateavet leiate teemast [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/).

- LiveRamp-ühenduse [konfigureerib](connections.md) [administraator](#configure-the-connection-for-liveramp).

## <a name="configure-the-connection-for-liveramp"></a>LiveRampi ühenduse konfigureerimine

Peate olema Customer Insightsi administraator [ja teil peab olema](permissions.md#admin) aktiivne LiveRamp kliendi ID ja saladus.

1. Valige **rikastamise konfigureerimisel Lisa ühendus** või avage **administraatoriühendused** > **ja** valige **paanil LiveRamp käsk Häälesta**.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Konfiguratsioonipaan ühenduse häälestamiseks Teenusega LiveRamp AbiliTec.":::

1. Sisestage ühenduse nimi ja kehtiv LiveRamp kliendi ID ja saladus.

1. Vaadake üle ja esitage oma nõusolek [Andmete privaatsuse ja nõuetele vastavus](#data-privacy-and-compliance) kohta, valides suvandi **Nõustun**.

1. Konfiguratsiooni kinnitamiseks valige **Kinnita** ja seejärel valige **Salvesta**.

### <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights andmeid LiveRampile edastada, lubate andmete edastamise väljaspool nõuetele vastavuse piiri Dynamics 365 Customer Insights, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste kohaselt, kuid teie vastutate selle eest, et LiveRamp täidaks kõik teie privaatsus- või turbekohustused. Lisateabe saamiseks vaadake Microsofti [privaatsusavaldust](https://go.microsoft.com/fwlink/?linkid=396732). Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **Kopeeri minu andmed** **paanil LiveRamp identiteet**.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identiteedipaan rikastamise ülevaate lehel.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Valige ühendus. Võtke ühendust administraatoriga, kui see pole saadaval.

1. Tehke valik **Edasi**.

1. **Valige kliendi andmestik** ja valige profiil või segment, mida soovite LiveRampi identiteediandmetega rikastada. Olem *Klient* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

1. Määratlege, millist tüüpi välju oma ühtsetest profiilidest kasutada LiveRampi identiteediandmete sobitamiseks. Nõutav on vähemalt üks väljadest **Nimi ja aadress**, **E-post** või **Telefon**. Suurema vaste täpsuse tagamiseks lisage teised väljad. Tehke valik **Edasi**.

1. Vastendage oma väljad LiveRampi ID-andmetega.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRampi rikastamise andmete vastendamise suvandid.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Sisestage **rikastamise nimi** ja väljundolemi **nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Rikastamisprotsessi alustamiseks või lehele Rikastamine naasmise **lähedal** valige **Käivita**.

## <a name="view-enrichment-results"></a>Rikastamise tulemuste kuvamine

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Põlluga **rikastatud** klientide arv tagab iga rikastatud välja katvuse süvitsimise.

## <a name="next-steps"></a>Järgmised toimingud

Rikastatud kliendiandmetele toetumine. AbiliTeci ID-de abil saate kliendiprofiilid isikupõhiseks vaateks konsolideerida.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
