---
title: LiveRamp identiteediandmete rikastamine
description: Rikastage kliendiprofiile LiveRampi andmetega.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373061"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Kliendiprofiilide rikastamine LiveRampi identiteediandmetega (eelvaade) 

LiveRamp pakub deterministlikku võrguühenduseta identiteedi eraldusvõimet ja kliendiandmete konsolideerimist. Kliendiandmetes identifikaatorid saate vastendada AbiliTeci identiteedigraafikuga ja saada AbiliTec ID-d. Seejärel saate neid ID-sid kasutada oma kliendiandmete paremaks ühendamiseks. 

## <a name="prerequisites"></a>eeltingimused 

Rikastamise konfigureerimiseks peavad olema täidetud järgmised eeltingimused. 

- Teil on aktiivne LiveRampi tellimus. Tellimuse saamiseks pöörduge oma LiveRampi konto meeskonna poole või lisateabe saamiseks [dynamics@liveramp.com](mailto:dynamics@liveramp.com).   

- Aktiivne AbiliTeci tellimus koos kliendi ID-ga ja API-le juurdepääs. Lisateavet leiate teemast [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Toetatud riigid/piirkonnad 

Praegu toetame kliendiprofiilide rikastamist LiveRampi andmetega ainult Ameerika Ühendriikides. 

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine 

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**. 

1. Valige paanil Identiteet suvand **Rikasta minu andmeid**.**·** 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identivaan rikastamise ülevaate lehel.":::

1. Valige [ühendus](connections.md) ripploendist. Kui ühendusi pole saadaval, pöörduge administraatori poole. Kui olete administraator, saate luua ühenduse, valides **Lisa ühendus**. Valige **ripploendist LiveRamp**. 

1. Valige **Edasi** ja valige kliendi andmekogum, **mida** soovite LiveRampi identiteediandmetega rikastada. Saate valida *olemi Klient*, et rikastada kõiki oma kliendiprofiile, või valida *segmendiolemi*, et rikastada ainult selles segmendis sisalduvaid kliendiprofiile. 

1. Valige **Edasi** ja määratlege, millist tüüpi välju teie ühtsetest profiilidest tuleks kasutada LiveRampi sobivate identiteediandmete otsimiseks. Nõutav on vähemalt üks väljadest **Nimi ja aadress**, **Telefon** või **E-post**. 

   > [!TIP]
   > Mida rohkem põhiidentifikaatoreid ja välju vastendate, seda suurem on tõenäosus, et vaste määr on suurem 

1. Vastendage oma ühendatud *kliendiolemi* väljad, mida kasutatakse LiveRampi AbiliTec ID graafikuga sobitamiseks. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRampi rikastamise andmete kaardistamise valikud.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine. 

1. Sisestage **rikastamise ja** väljundolemi **nimi**. 

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist. 

## <a name="configure-the-connection-for-liveramp"></a>LiveRampi ühenduse konfigureerimine 

Ühenduste [konfigureerimiseks](connections.md) peate olema administraator. Valige **Rikastamise konfigureerimisel Lisa ühendus** või avage **AdminConnections** > **ja** valige **Häälestage** paanil **LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Konfiguratsioonipaan ühenduse seadistamiseks LiveRamp AbiliTec teenusega.":::

1. Kuva nime **jaoks** sisestage ühenduse nimi. 

1. Esitage kehtiv LiveRamp kliendi ID ja saladus. 

1. Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**. 

1. Valige **Kontrolli** konfiguratsiooni valideerimiseks. 

1. Ühenduse lõpuleviimiseks valige **Salvesta**. 

## <a name="enrichment-results"></a>Rikastamise tulemused 

Rikastamisprotsessi alustamiseks valige käsuribalt Käsk Käivita. Samuti saate lasta süsteemil rikastumise automaatselt käivitada [ajastatud värskendamise osana](system.md#schedule-tab). Töötlemisaeg sõltub teie kliendiandmete mahust. 

Kui rikastamisprotsess on lõpule jõudnud, saate vaadata äsja rikastatud kliendiprofiilide andmed jaotises **Minu rikastamised**. Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu. 

Igale rikastatud profiilile üksikasjalikule vaatele pääsete juurde, validesVaatega **rikastatud** andmed. 

## <a name="next-steps"></a>Järgmised toimingud

Rikastatud kliendiandmetele toetumine. AbiliTeci ID-dega saate konsolideerida kliendiprofiilid isikupõhisesse vaatesse. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus 

Kui lubate Dynamics 365 Customer Insights edastada andmeid LiveRampile, lubate andmete edastamist väljaspool vastavuspiiri Dynamics 365 Customer Insights, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhendamisel, kuid teie vastutate selle eest, et LiveRamp täidaks teie privaatsus- või turvakohustusi. Lisateabe saamiseks vaadake Microsofti [privaatsusavaldust](https://go.microsoft.com/fwlink/?linkid=396732). Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
