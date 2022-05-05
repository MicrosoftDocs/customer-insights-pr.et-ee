---
title: Rikastamine kolmanda osapoole rikastamisega Experian
description: Üldine teave Experian kolmanda osapoole rikastamise kohta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f5aa45316b9e0e99c7ba4389353063e9d3ce06c
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642455"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Kliendiprofiilide rikastamine demograafiaga Experian (eelversioon)

Experian on tarbija- ja ärikrediidi aruandluse ja turundusteenuste ülemaailmne liider. Andmete rikastamise teenuste Experian abil saate oma kliente sügavamalt mõista, rikastades oma kliendiprofiile demograafiliste andmetega, nagu leibkonna suurus, sissetulek ja palju muud.

## <a name="prerequisites"></a>Eeltingimused

Experian konfigureerimiseks peavad olema täidetud järgmised eeltingimused:

- Teil peab olema aktiivne rakenduse Experian kordustellimus. Kordustellimuse saamiseks [võtke Experian](https://www.experian.com/marketing-services/contact) otse ühendust. [Lugege lisateavet Experian andmerikastamine](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Administraator on Experian ühenduse juba konfigureerinud *või* teil on [administraatori](permissions.md#admin) õigused. Teil on vaja ka kasutaja ID-d, osapoole ID-d ja mudelinumbrit SSH-toega turvalise transpordi (ST) konto jaoks, mille lõi teile Experian.

## <a name="supported-countriesregions"></a>Toetatud riigid/piirkonnad

Praegu toetame kliendiprofiilide rikastamist ainult Ameerika Ühendriikides.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **Rikasta minu andmed** Experian paanil.

   > [!div class="mx-imgBorder"]
   > ![Experian paan.](media/experian-tile.png "Experian tile")
   > 

1. Valige [ühendus](connections.md) ripploendist. Kui ühendusi pole saadaval, pöörduge administraatori poole. Kui olete administraator, saate ühenduse luua, valides **Lisa ühendus** käsu ja valides ripploendist Experian. 

1. Valige **Ühenda Experian**, et kinnitada ühenduse valik.

1.  Valige **Edasi** ja valige **Kliendi andmekomplekt**, mille andmeid soovite Experian demograafiliste andmetega rikastada. Saate valida olemi **Klient**, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendiandmete kogumi valimisel.":::

1. Valige **Edasi** ja määrake, millist tüüpi välju teie ühendatud profiilidest tuleks kasutada Experian andmetest demograafiliste andmete sobitamiseks. Vähemalt üks väljadest **Nimi ja aadress**, **Telefon** või **E-post** on nõutav. Suurema sobivuse täpsuse saavutamiseks saab lisada kuni kaks muud välja. See valik mõjutab kaardistamisvälju, millele teil on järgmises etapis juurdepääs.

    > [!TIP]
    > Rohkem võtmeidentifikaatori atribuute, mis Experian-ile saadetakse, tõenäoliselt annab suurema vaste määra.

1. Valige **Edasi**, et alustada väljade kaardistamist.

1. Määratlege, milliseid väljad teie ühendatud profiilidest tuleks kasutada Experian sobivate demograafiliste andmete otsimiseks. Nõutud väljad on vastavalt tähistatud.

1. Sisestage rikastamise nimi ja väljundolemi nimi.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

## <a name="configure-the-connection-for-experian"></a>Konfigureerige Experian ühendus 

Ühenduste konfigureerimiseks peate olema administraator. Valige rikastamise konfigureerimisel **Lisa ühendus** *või* minge **Administraator** > **Ühendused** ja valige **Seadista** Experian paanil.

1. Seejärel valige suvand **Alustamine**.

1. Sisestage ühenduse nimi **Kuvatav nimi** väljale.

1. Sisestage oma Experian turvalise transpordi konto kehtiv kasutaja ID, osapoole ID ja mudeli number.

1. Vaadake üle ja esitage oma nõusolek **Andmete privaatsuse ja nõuetele vastavus** kohta, valides suvandi **Nõustun**.

1. Valige **Kontrolli** konfiguratsiooni valideerimiseks.

1. Pärast kontrollimise lõpuleviimist valige **Salvesta**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian ühenduse konfiguratsiooni paan.":::

## <a name="enrichment-results"></a>Rikastamise tulemused

Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**. Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab). Töötlemisaeg sõltub teie kliendiandmete suurusest ja teie Experian konto jaoks seadistatud rikastamisprotsessidest.

Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt. Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.

Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.

## <a name="next-steps"></a>Järgmised etapid

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights edastada andmeid Experian-ile, lubate andmete edastamist väljapoole vastavuse piiri Dynamics 365 Customer Insights jaoks, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste alusel, kuid teie vastutate selle eest, et Experian täidaks kõiki privaatsus- või turvakohustusi, mis teil võivad olla. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insights administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE [footer-include](includes/footer-banner.md)]
