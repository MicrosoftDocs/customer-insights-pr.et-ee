---
title: Täpsemad veebi SDK stsenaariumid
description: Täpsemad stsenaariumid, mida oma veebisaidi SDK-ga seadistamisel arvesse võtta.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 4c6646ecadbb604000d6c95b685cf6e420969a6d
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558697"
---
# <a name="advanced-web-sdk-instrumentation"></a>Veebi SDK täpsem dokumentatsioon

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

See artikkel juhendab teid keerukate stsenaariumide abil, mida tuleb arvestada kui [lisate oma veebisaidi](instrument-website.md) rakendusega Dynamics 365 Customer Insights kaasamisülevaadete võimalusega SDK- le.

## <a name="setting-user-details-for-your-event"></a>Sündmuse kasutaja üksikasjade seadmine

SDK võimaldab määratleda kasutajateavet, mida saab saata iga sündmusega. Saate määrata kasutaja `user` üksikasjad (atribuudis, mida nimetatakse `IUser` objektiks), mis on sarnane atribuudi `src`, `name` ja `cfg` koodilõigend konfiguratsioonis.

Objekt `IUser` sisaldab järgmisi stringi atribuute:

- **kohalikId**: kasutaja kohalik ID.
- **autenditudId**: autenditud kasutaja ID.
- **autenditudTüüp**: autentimistüüp, mida kasutati autenditud kasutaja ID saamiseks.
- **nimi**: Kasutaja nimi.
- **ekiri**: Saatja ekirja aadress.

Järgmises näites on toodud näiteks koodilõigend teabe saatmine. Kui näete funktsioone, mille eel on tärnitähis *, asendage funktsioon oma kohandatud rakendamisega.

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Kasutajateavet saate määrata ka`setUser(user: IUser)` API-le helistades. Telemeetria, mis saadetakse pärast `setUser` API -le helistamist, sisaldab kasutajateavet.

## <a name="adding-custom-properties-for-each-event"></a>Iga sündmuse jaoks kohandatud atribuutide lisamine

SDK võimaldab määratleda kasutajateavet, mida saab saata iga sündmusega. Saate määrata kohandatud atribuudid objektina, mis sisaldab võtmeväärtuse paare (väärtus võib olla tüüpidest `string | number | boolean`). Saate lisada objekti atribuudile nimega `props`, mis on sarnane `src`,`name`ja `cfg` -iga koodilõigendi konfiguratsioonis.

Järgmine näide näitab koodilõiku, mis saadab kohandatud atribuute:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Kohandatud atribuute saate määrata ka individuaalselt, helistades `setProperty(name: string, value: string | number | boolean)` API -le.

## <a name="sending-custom-events"></a>Kohandatud sündmuste saatmine

SDK-d saab kasutada kohandatud sündmuste saatmiseks. Peate sündmusega koos saadetava sündmuse ja atribuutide jaoks määrama nime.

Järgmine näide näitab koodilõiku, mis saadab kohandatud atribuute. Väärtus "NIMI" on koodilõigu konfiguratsioonis võtmes `name` olev väärtus. Samuti on see muutuja nimi akna objektis, kus SDK laaditakse.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
