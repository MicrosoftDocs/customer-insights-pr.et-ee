---
title: Kaasamisülevaadete võimalustega alustamine
description: Ülevaade abiressurssidest kiiresti alustamiseks.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405353"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Alustage Dynamics 365 Customer Insights kaasamisülevaadete võimalustega (avalik eelvaade)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Kaasamisülevaadete võimalus võimaldab teil koguda ja mõõta oma veebisaidil kliendi käitumist. See integreeritakse publiku ülevaadete võimalustega, et näha rikkalikke reaalajalise käitumusliku analüüsi klienditeeninduse aruandeid. Selle artikli lingid aitavad teil kiiresti oma keskkonda konfigureerida ja seadistada.

## <a name="step-1-review-prerequisites"></a>1. samm: vaadake üle eeltingimused

Esmalt peab teil olema aktiivne Microsoft Azure Active Directory kasutajakonto. Seejärel lugege enne kaasamisülevaadete tööruumi seadistamist järgmisi artikleid.

- Vaadake üle ja nõustuge [Teenustingimustega](terms-of-service.md) Microsoftis.  
- Lugege [Halda küpsiseid ja kasutaja nõusolekut](user-consent-storage.md) artiklit. Pärast selle artikli läbivaatamist tuleb hinnata, kas teil on vaja oma kasutaja nõusoleku teatist värskendada. Kui te pole varem "mitte olulisi" küpsiseid kasutanud, peate tõenäoliselt oma saidipoliitikat värskendama.
- Vaadake üle [Põhimõistete](glossary.md) sõnastik kiireks tutvumiseks.

## <a name="step-2-explore-engagement-insights"></a>2. etapp: kaasamisülevaadetega tutvumine

Esmakordsel kaasamisülevaadete külastamisel saate konfigureerida sätteid, vaadata poliitikaid ja uurida toodet.

1. Logige sisse [kaasamisülevaadete võimaluste portaali](https://pi.dynamics.com) kasutades Microsoft Azure Active Directory kasutajakontot. (See võib olla teie kooli või töö konto.)

1. Valige oma piirkond ja märkige ära vastavat ruutu märkides, kas soovite saada värskendusi ja pakkumisi meiliga.

1. Vaadake üle **kaasamisülevaadete (eelvaate) kasutustingimused** ja **Privaatsusavaldus** ning seejärel valige **Tutvuge demoga**, et need aktsepteerida.

1. Tutvuge tootega näidisandmete komplekti abil.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>3. etapp: tööruumi seadistamine ja veebisaidile koodi lisamine

Tööruumis saate vaadata kasutajategevust reaalajas ning talletada ja hallata aruandeid. Lisage veebisaidile kood, et alustada *sündmuste* kogumist, kasutajatelt saadud tegevuste andmeid.

1. [Looge tööruum](create-workspace.md) ja lisage liikmeid.

1. [Lisage kood oma veebisaidile](instrument-website.md) või [mobiilirakendusele](developer-resources.md#capture-events-from-mobile-apps), et näha tegevuse saabumist oma tööruumi.

1. Saate [kuvada reaalajas aruannet](view-reports.md) mis näitab aktiivseid kasutajaid brauseri, seadme, operatsioonisüsteemi, asukoha ja keele järgi. Samuti saate luua [kohandatud aruandeid](custom-reports.md) oma visualiseeringute loomiseks.
    
## <a name="step-4-export-data-to-other-channels"></a>4. etapp: andmete eksportimine muudesse kanalitesse

Saate luua *täpsustatud sündmuseid* (virtuaalse vaate) oma veebianalüütika andmetest. Seejärel filtreerige ja eksportige andmed Azure Data Lake Storage. Saate eksporditud andmed andmeallikana sisse võtta. Lisateavet vt: [Sihtrühma ülevaadete ja kaasamisülevaadete vahelise lingi loomine](integrate-audience-insights-engagement-insights.md).

1. [Luua täpsustatud sündmused](refined-events.md) ekspordiks.

1. [Eksportige andmed](export-events.md) Data Lake Storage'i.

1. Teave isikuandmeid [sisaldavate sündmuseandmete kustutamise ja eksportimise kohta](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>5. etapp: ole ühenduses

Hindame teie aktiivset osalemist ja plaanime tulevaste väljaannete väljatöötamisel arvestada kogu asjakohase tagasisidega. Tagasiside ja probleemidest teatamine on nende kanalite kaudu ühiskasutuses:
- [Kogukond](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Anna tagasisidet](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Tugiteenuse taotlus](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
