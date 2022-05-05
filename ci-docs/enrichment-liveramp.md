---
title: LiveRamp identiteediandmete rikastamine
description: Kliendiprofiilide rikastamine LiveRampi andmetega.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0727818f6df565d9a031966a68d521ae7167e484
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642565"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Kliendiprofiilide rikastamine LiveRampi identiteediandmetega (Eelvaade) 

LiveRamp pakub deterministlikku võrguühenduseta identiteedilahendust ja kliendiandmete konsolideerimist. Saate vastendada kliendiandmetes olevad isikuidentifikaatorid AbiliTeci identiteedigraafikuga ja saada AbiliTeci ID-d. Seejärel saate neid ID-sid kasutada oma kliendiandmete paremaks ühendamiseks. 

## <a name="prerequisites"></a>eeltingimused 

Rikastamise konfigureerimiseks peavad olema täidetud järgmised eeltingimused. 

- Teil on aktiivne LiveRampi tellimus. Tellimuse saamiseks võtke ühendust oma LiveRampi konto meeskonnaga või [dynamics@liveramp.com](mailto:dynamics@liveramp.com) lisateabe saamiseks.   

- Aktiivne AbiliTeci tellimus, millel on kliendi ID ja salajane API-le juurdepääsemiseks. Lisateavet leiate teemast [AbiliTec API Developer Hub](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Toetatud riigid/piirkonnad 

Praegu toetame kliendiprofiilide rikastamist LiveRampi andmetega ainult Ameerika Ühendriikides. 

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine 

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**. 

1. Valige **Paanil** Identiteet **käsk Rikasta minu andmeid**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Identiteedipaan rikastamise ülevaate lehel.":::

1. Valige [ühendus](connections.md) ripploendist. Kui ühendusi pole saadaval, pöörduge administraatori poole. Kui olete administraator, saate ühenduse luua, valides suvandi **Lisa ühendus**. Valige **ripploendist LiveRamp**. 

1. Valige **Edasi** ja valige **Kliendi andmestik**, mida soovite LiveRampi identiteediandmetega rikastada. Saate valida *olemi Klient*, et rikastada kõiki oma kliendiprofiile, või valida *segmendiolemi*, et rikastada ainult selles segmendis sisalduvaid kliendiprofiile. 

1. Valige **Edasi** ja määratlege, millist tüüpi välju ühtsetest profiilidest tuleks kasutada LiveRampist sobivate identiteediandmete otsimiseks. Nõutav on vähemalt üks väljadest **Nimi ja aadress**, **Telefon** või **E-post**. 

   > [!TIP]
   > Mida rohkem võtmeidentifikaatoreid ja välju vastendate, seda suurem on tõenäosus, et mängumäär on suurem 

1. Vastendage oma ühtse *kliendiolemi* väljad, mida kasutatakse LiveRamp'i AbiliTec ID graafikuga sobitamiseks. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="LiveRampi rikastamise andmete vastendamise suvandid.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine. 

1. **Sisestage rikastamise ja** olemi **Väljund nimi**. 

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist. 

## <a name="configure-the-connection-for-liveramp"></a>LiveRampi ühenduse konfigureerimine 

Ühenduste [konfigureerimiseks](connections.md) peate olema administraator. Valige **rikastamise konfigureerimisel Lisa ühendus** või minge valikule **AdminConnections** > **ja** valige paanil **LiveRamp** käsk **Häälesta**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Konfiguratsioonipaan ühenduse häälestamiseks Teenusega LiveRamp AbiliTec.":::

1. Sisestage **kuvamisnime** kuvamiseks ühenduse nimi. 

1. Esitage kehtiv LiveRamp kliendi ID ja saladus. 

1. Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**. 

1. Valige **Kontrolli** konfiguratsiooni valideerimiseks. 

1. Ühenduse lõpuleviimiseks valige **Salvesta**. 

## <a name="enrichment-results"></a>Rikastamise tulemused 

Rikastamisprotsessi alustamiseks valige käsuribalt Käsk Käivita. Samuti saate lasta süsteemil rikastamist ajastatud värskendamise [osana automaatselt käivitada](system.md#schedule-tab). Töötlemisaeg sõltub teie kliendiandmete mahust. 

Kui rikastamisprotsess on lõpule viidud, saate vaadata äsja rikastatud kliendiprofiilide andmeid jaotises **Minu rikastamised**. Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu. 

Igale rikastatud profiilile pääsete juurde üksikasjalikule vaatele, valides **suvandi Vaata rikastatud** andmeid. 

## <a name="next-steps"></a>Järgmised toimingud

Rikastatud kliendiandmetele toetumine. AbiliTeci ID-de abil saate kliendiprofiilid isikupõhiseks vaateks konsolideerida. 
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus 

Kui lubate Dynamics 365 Customer Insights andmeid LiveRampile edastada, lubate andmete edastamise väljaspool nõuetele vastavuse piiri Dynamics 365 Customer Insights, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste kohaselt, kuid teie vastutate selle eest, et LiveRamp täidaks kõik teie privaatsus- või turbekohustused. Lisateabe saamiseks vaadake Microsofti [privaatsusavaldust](https://go.microsoft.com/fwlink/?linkid=396732). Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine. 


[!INCLUDE [footer-include](includes/footer-banner.md)]
