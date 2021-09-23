---
title: Kaasamisülevaadete võimalustega alustamine
description: Ülevaade abiressurssidest kiiresti alustamiseks.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494589"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Alustage Dynamics 365 Customer Insights kaasamisülevaadete võimalustega (avalik eelvaade)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Kaasamisülevaadete võimalus võimaldab teil koguda ja mõõta oma veebisaidil kliendi käitumist. See integreeritakse publiku ülevaadete võimalustega, et näha rikkalikke reaalajalise käitumusliku analüüsi klienditeeninduse aruandeid. Selle artikli lingid aitavad teil kiiresti oma keskkonda konfigureerida ja seadistada.

## <a name="step-1-review-prerequisites"></a>1. samm: vaadake üle eeltingimused

Esmalt peab teil olema aktiivne Microsoft Azure Active Directory (AAD) kasutajakonto. Seejärel lugege enne kaasamisülevaadete tööruumi seadistamist järgmisi artikleid.

- Vaadake üle ja nõustuge [Teenustingimustega](terms-of-service.md) Microsoftis.  
- Lugege [Halda küpsiseid ja kasutaja nõusolekut](user-consent-storage.md) artiklit. Kontrollige, kas teil on vaja oma kasutaja nõusoleku teatist värskendada. Kui te pole varem "mitte olulisi" küpsiseid kasutanud, peate tõenäoliselt oma saidipoliitikat värskendama.
- Vaadake üle [Põhimõistete](glossary.md) sõnastik kiireks tutvumiseks.

## <a name="step-2-explore-engagement-insights"></a>2. etapp: kaasamisülevaadetega tutvumine

Esmakordsel sihtrühma ülevaate külastamisel saate konfigureerida sätteid, vaadata üle poliitikad ja võimalustega tutvuda.

1. Sisse logida [kaasamisülevaadete võimaluste portaali](https://home.ci.ai.dynamics.com/app/engagement-insights), kasutades oma Microsoft AAD kasutaja (kooli või töö) kontot.

1. Valige oma piirkond ja märkige ruut, kui soovite saada meilivärskendusi ja -pakkumisi.

1. Vaadake üle **kaasamisülevaated (eelvaate) kasutustingimused** ja **privaatsusavalduse** ning seejärel valige nende sätete aktsepteerimiseks valik **Tutvuge demoga**.

1. Tutvuge tootega näidisandmete komplekti abil.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>3. etapp: tööruumi seadistamine ja veebisaidile koodi lisamine

Tööruumis saate vaadata kasutajategevust reaalajas ning talletada ja hallata aruandeid. Lisage veebisaidile kood, et alustada *sündmuste* kogumist, kasutajatelt saadud tegevuste andmeid.

1. [Looge tööruum](create-workspace.md) ja lisage liikmeid.

1. [Lisage kood oma veebisaidile](instrument-website.md) või [mobiilirakendusele](developer-resources.md#capture-events-from-mobile-apps), et näha tegevuse saabumist oma tööruumi.

1. Saate kuvada [reaalajas aruannet](view-reports.md), kus aktiivsed kasutajad kuvatakse brauseri, seadme, operatsioonisüsteemi, asukoha ja keele järgi. Samuti saate luua [kohandatud aruandeid](custom-reports.md) oma visualiseeringute loomiseks.
    
## <a name="step-4-export-data-to-other-channels"></a>4. etapp: andmete eksportimine muudesse kanalitesse

Saate luua *täpsustatud sündmuseid* (virtuaalse vaate) oma veebianalüütika andmetest. Seejärel filtreerige ja eksportige andmed Azure Data Lake Storage. Saate eksporditud andmed andmeallikana sisse võtta. Lisateavet vt: [Sihtrühma ülevaadete ja kaasamisülevaadete vahelise lingi loomine](integrate-audience-insights-engagement-insights.md).

1. [Luua täpsustatud sündmused](refined-events.md) ekspordiks.

1. [Eksportige andmed](export-events.md) Data Lake Storage'i.

1. [Looge link sihtrühma ülevaadete ja kaasamisülevaadete vahel](integrate-audience-insights-engagement-insights.md), et jagada andmeid kahe võimaluse vahel.

1. Teave isikuandmeid [sisaldavate sündmuseandmete kustutamise ja eksportimise kohta](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>5. etapp: ole ühenduses

Oleme tänulikud teie aktiivse osalemise eest ja võtame tulevaste väljaannete väljatöötamisel arvesse kogu asjakohast tagasisidet. Tagasiside ja probleemidest teatamine on nende kanalite kaudu ühiskasutuses:
- [Kogukond](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Anna tagasisidet](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Tugiteenuse taotlus](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
