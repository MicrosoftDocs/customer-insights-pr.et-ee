---
title: Oma veebisaidile koodi lisamine
description: Kuidas lisada koodilõigend veebisaidi sündmuste jäädvustamiseks.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035089"
---
# <a name="install-the-code-snippet-on-a-website"></a>Koodilõigendi installimine veebisaidile

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Selles artiklis kirjeldatakse, kuidas administraator koodilõigendi veebisaidile installib. Varsti pärast skripti lisamist veebisaidile saate oma tööruumis sündmusi näha. Lisateavet leiate teemast [Tööruumide ja keskkondade halddamine](manage-environments-workspaces.md). Sündmuste hõlmamiseks mobiilirakendustes vaadake [Arendaja ressursside ülevaade](developer-resources.md).


### <a name="prerequisites"></a>Eeltingimused

* Andmete talletamiseks peavad teil olema tööruumi jaoks administraatoriõigused.
* Tegevuseandmete saatmiseks peab teie veebisait või projekt olema võrgus majutatud. Server ei aktsepteeri kohalikust failist saadetud andmeid.


## <a name="add-code-to-your-website"></a>Oma veebisaidile koodi lisamine
1.  Minge **Administreerimis** > **Tööruum** ja valige seejärel **Installijuhend**.
1. Valige **Kopeeri kood**, et kopeerida koodilõigend. Vaikimisi on teie tööruumi sisestusvõti manustatud koodijuppi.
:::image type="content" source="media/copy-code.png" alt-text="Lehe koodilõigendi kuvatõmmis.":::
3. Lisage kopeeritud koodilõigend veebisaidile <head> enne mis tahes muid skripte või CSS-silte.
4.  Avaldage värskendatud veebisait ja oodake paar minutit sissetuleva veebiliikluse hõivamiseks.
5.  Andmete kuvamiseks valige navigeerimispaanil olevast tööruumi vahetajast tööruum. Seejärel valige üks **Avasta** jaotistest.

## <a name="configuration-options"></a>Konfigureerimissuvandid

Viisardis saate muuta järgmisi koodilõigendi omadusi:

- **sisestusVõti**: Sisestusvõti, mida kasutatakse sündmuste saatmiseks teie tööruumi. Sündmuste saatmiseks teise tööruumi saate muutavalmendusvõtit. Iga tööruumi jaoks on unikaalne valmendusvõti. 
- **autoJäädvustus**: määrab, kas lehevaatamised ja suhtlus veebisaidiga on hõivatud. See on kahe valikuga:
    - **vaade**: Sea *tõeks* lehevaadete hõivamiseks. Lehevaated hõivatakse kui *Vaade* [sündmused](glossary.md#event), tüüp [baassündmused](glossary.md#base-event).
    - **klõpsake**: Määra *tõena* et hõivata veebisaidil külastajaga suhtlemist. Lehevaated hõivatakse kui *Tegevus* [sündmused](glossary.md#event), tüüp [baassündmused](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
