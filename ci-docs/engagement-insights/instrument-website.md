---
title: Oma veebisaidile koodi lisamine
description: Kuidas lisada koodilõigend veebisaidi Dynamics 365 Customer Insights sündmuste jäädvustamiseks.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558841"
---
# <a name="install-the-web-sdk-on-a-website"></a>Veebi-SDK installimine veebisaidile

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Selles artiklis kirjeldatakse, kuidas administraator installib veebisaidile veebitarkvara arendustööriistakomplekti (SDK). Varsti pärast veebisaidi vaatamist saate oma tööruumis sündmusi näha. Lisateavet leiate teemast [Tööruumide ja keskkondade halddamine](manage-environments-workspaces.md). Sündmuste hõlmamiseks mobiilirakendustes vaadake [Arendaja ressursside ülevaade](developer-resources.md).


### <a name="prerequisites"></a>Eeltingimused

* Andmete talletamiseks peavad teil olema tööruumi jaoks administraatoriõigused.
* Tegevuseandmete saatmiseks peab teie veebisait või projekt olema võrgus majutatud. Server ei aktsepteeri kohalikust failist saadetud andmeid.


## <a name="add-web-sdk-to-your-website"></a>Lisage veebi SDK oma veebilehele

Minge **Administreerimis** > **Tööruum** ja valige seejärel **Installijuhend**. Veebi SDK installimiseks on kaks võimalust. Esimene on kasutada allalaadimislinki ja teine on sõlmepaketi halduri (NPM) paketi installimine.

### <a name="option-1-using-the-download-link"></a>Variant 1: Allalaadimislingi kasutamine

1. Valige **Kopeeri kood**, et kopeerida koodilõigend. Vaikimisi on teie tööruumi sisestusvõti manustatud koodijuppi.
  :::image type="content" source="media/copy-code.png" alt-text="Lehe koodilõigendi kuvatõmmis.":::

1. Lisage kopeeritud kood oma veebisaidile lähedal <head> enne mis tahes muid skripte või CSS-silte.
1. Avaldage värskendatud veebisait ja oodake paar minutit sissetuleva veebiliikluse hõivamiseks.
1. Andmete kuvamiseks valige navigeerimispaanil olevast tööruumi vahetajast tööruum. Seejärel valige üks **Avasta** jaotistest.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>2. valik: NPM paketi kasutamine (soovitatav JavaScript -i-põhiste veebirakenduste puhul)

1. Minge meie [NPM veebilehele](https://www.npmjs.com/package/engagementinsights-web) ja järgige veebi SDK NPM paketi installimise ja häälestamise juhiseid.
1. Avaldage värskendatud veebisait ja oodake paar minutit sissetuleva veebiliikluse hõivamiseks.
1. Andmete kuvamiseks valige navigeerimispaanil olevast tööruumi vahetajast tööruum. Seejärel valige üks **Avasta** jaotistest.

## <a name="configuration-options"></a>Konfigureerimissuvandid

Viisardis saate muuta järgmisi koodilõigendi omadusi:

- **sisestusVõti**: Sisestusvõti, mida kasutatakse sündmuste saatmiseks teie tööruumi. Sündmuste saatmiseks teise tööruumi saate muutavalmendusvõtit. Iga tööruumi jaoks on unikaalne valmendusvõti.
- **autoJäädvustus**: määrab, kas lehevaatamised ja suhtlus veebisaidiga on hõivatud. See on kahe valikuga:
    - **vaade**: Sea *tõeks* lehevaadete hõivamiseks. Lehevaated hõivatakse kui *Vaade* [sündmused](glossary.md#event), tüüp [baassündmused](glossary.md#base-event).
    - **klõpsake**: Määra *tõena* et hõivata veebisaidil külastajaga suhtlemist. Lehevaated hõivatakse kui *Tegevus* [sündmused](glossary.md#event), tüüp [baassündmused](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
