---
title: Kliendiprofiilide rikastamine demograafiaga Experian (eelversioon)
description: Üldine teave Experian kolmanda osapoole rikastamise kohta.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: a30e98b06ed07590ab95cae1d8db8023e49ff7f9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053016"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Kliendiprofiilide rikastamine demograafiaga Experian (eelversioon)

Experian on tarbija- ja ärikrediidi aruandluse ja turundusteenuste ülemaailmne liider. Andmete rikastamise teenuste Experian abil saate oma kliente sügavamalt mõista, rikastades oma kliendiprofiile demograafiliste andmetega, nagu leibkonna suurus, sissetulek ja palju muud.

## <a name="supported-countriesregions"></a>Toetatud riigid/piirkonnad

Praegu toetame kliendiprofiilide rikastamist ainult Ameerika Ühendriikides.

## <a name="prerequisites"></a>eeltingimused

- Aktiivne Experian tellimus. Kordustellimuse saamiseks [võtke Experian](https://www.experian.com/marketing-services/contact) otse ühendust. [Lugege lisateavet Experian andmerikastamine](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Ühenduse Experian [konfigureerib](connections.md) [administraator](#configure-the-connection-for-experian).

- Experian Teie jaoks loodud SSH-toega turvalise transpordi (ST) konto Experian kasutaja ID, osapoole ID ja mudeli number.

## <a name="configure-the-connection-for-experian"></a>Konfigureerige Experian ühendus

Peate olema Customer Insightsi administraator [ja teil peab](permissions.md#admin) olema Experian kasutaja ID, osapoole ID ja mudeli number.

1. Valige **rikastamise konfigureerimisel Lisa ühendus** või avage **administraatoriühendused** > **ja** valige paanil **Käsk** Häälesta Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian ühenduse konfiguratsiooni paan.":::

1. Sisestage oma turvalise transpordi konto jaoks ühenduse nimi ning kehtiv kasutaja ID, osapoole ID ja mudelinumber Experian.

1. Vaadake üle ja esitage oma nõusolek [Andmete privaatsuse ja nõuetele vastavus](#data-privacy-and-compliance) kohta, valides suvandi **Nõustun**.

1. Konfiguratsiooni kinnitamiseks valige **Kinnita** ja seejärel valige **Salvesta**.

### <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights edastada andmeid Experian-ile, lubate andmete edastamist väljapoole vastavuse piiri Dynamics 365 Customer Insights jaoks, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste alusel, kuid teie vastutate selle eest, et Experian täidaks kõiki privaatsus- või turvakohustusi, mis teil võivad olla. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732). Teie Dynamics 365 Customer Insights administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. **Valige** **Paanilt** Demograafiliste andmete rikastamine Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Experian paani rikastamise ülevaate lehel.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Valige ühendus. Võtke ühendust administraatoriga, kui see pole saadaval.

1. Tehke valik **Edasi**.

1. **Valige kliendi andmestik** ja valige profiil või segment, mida soovite rikastada rakenduse demograafiliste andmetega Experian. Olem *Klient* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendiandmete kogumi valimisel.":::

1. Määratlege, millist tüüpi välju oma ühtsetest profiilidest kasutada demograafia andmete sobitamiseks rakendusest Experian. Vähemalt üks väljadest **Nimi ja aadress**, **Telefon** või **E-post** on nõutav. Suurema vaste täpsuse tagamiseks lisage teised väljad. Tehke valik **Edasi**.

1. Vastendage oma väljad rakenduse demograafiliste andmetega Experian.

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
