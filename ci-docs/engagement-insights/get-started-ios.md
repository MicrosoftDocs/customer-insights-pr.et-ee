---
title: iOS SDK kasutamise alustamine
description: Teave iOS SDK isikupärastamise ja käitamise kohta
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036868"
---
# <a name="get-started-with-the-ios-sdk"></a>iOS SDK kasutamise alustamine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

See õpetus juhendab teid oma iOS seadme seadistamisel Dynamics 365 Customer Insights kaasamise ülevaatel SDK. Te saate portaalis sündmusi näha viie minuti pärast või varem.

## <a name="configuration-options"></a>Konfigureerimissuvandid

Järgmised seadistusvõimalused saab SDK-le edastada pakutava faili `EIConfig.plist` kaudu:

- **ingestionKey**: Edastusvõti saatis sündmused teie projekti.
- **autoctionlectAction**: Boolean väärtus toimingusündmuse automaatseks lubamiseks või keelamiseks.
- **autocollectView**: Boolean väärtus toimingusündmuse automaatseks lubamiseks või keelamiseks.
- **endpointUrl**: lõpp-punkti URL, kuhu sündmused suunatakse.

## <a name="prerequisites"></a>Eeltingimused

- Xcode versioon 9+
- iOS versioon 8.2+
- Edastusvõti (hankimiseks vaadake allolevaid juhiseid)

## <a name="integrate-the-sdk-into-your-application"></a>SDK integreerimine rakendusega

Alustage protsessi, valides töötamiseks tööala, valides iOS mobiiliplatvormi ja laadides alla SDK.

- Valige oma tööruum vasakpoolsel navigeerimispaanil tööruumi vahetaja abil.

- Kui teil pole olemasolevat tööruumi, valige  **Uus tööruum** ja järgige [uue tööruumi](create-workspace.md) loomise juhiseid.

## <a name="configure-the-sdk"></a>Konfigureeri SDK

Kui olete SDK alla laadinud, saate sellega sündmuste lubamiseks ja määratlemiseks töötada Xcode-is.

1. Pärast tööruumi loomist minge **Administraator** > **Tööruum** ja seejärel valige **Installijuhend**.

1. Laadige alla [kaasamisülevaated iOS-i SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip)ja paigutage `EIObjC.xcframework` fail `Frameworks` kausta.

1. Kui `Frameworks` kausta pole olemas, looge see projektikaustas.

## <a name="enable-auto-instrumentation"></a>Luba automaatne instrumentatsioon
 
Automaatse instrumentatsiooni saab hõlpsasti lubada ilma kodeerimiseta. Projekti käitamisel jälgib see automaatselt `view` ja `action` sündmusi, kasutades konfigureeritud edastusvõtit. 

1. Värskendage ja lisage esitatud `EIConfig.plist` fail oma projektikausta järgmistel väljadel:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = JAH
    - autocollectAction = JAH

2. Seejärel lisage fail `EIConfig.plist` oma projekti Xcode'iga. 



Automaatse instrumentatsiooni keelamiseks uuendage lisatud `EIConfig.plist` failis oma projektikausta järgmisi välju. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Rakendage kohandatud sündmusi

1. Avage Xcode-is on projekt ja liikuge **Üldine** seaded. 
1. Lisage `EIObjC.xcframework` projekti jaotisse "Raamistikud, teegid ja manustatud sisu".

1. Importige raamistiku päisefail üksuses AppDelegate.m koos järgmise koodilõiguga:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Initsialiseerige rakenduse seotusteabe SDK: didFinishLaunchingWithOptions.
1. Kopeerige XML-lõigend **Installijuhendist**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Sündmuse jälgimine:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Määrake oma sündmuse kasutaja üksikasjad

SDK võimaldab määratleda kasutajateavet, mida saab saata iga sündmusega. Kasutajateabe määramiseks helistage `setUser:(nonnull EIUser *)user` SDK API.

Kasutaja üksikasjade määramine tasemel `Analytics` tähendab, et see teave on kõigil telemeetriatele. Kui aga määrate sündmuse taseme, helistades `setUser:(nonnull EIUser *)user` API-le EIEvent objektil, sisaldab see teave ainult seda konkreetset sündmust.

Andmeklass `EIUser` sisaldab järgmisi NSString atribuute:

- **kohalikId**: kasutaja kohalik ID.
- **autenditudId**: autenditud kasutaja ID.
- **autenditudTüüp**: autentimistüüp, mida kasutati autenditud kasutaja ID saamiseks.
- **nimi**: Kasutaja nimi.
- **ekiri**: Saatja ekirja aadress.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
