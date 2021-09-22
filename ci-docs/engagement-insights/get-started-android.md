---
title: Android SDK kasutamise alustamine
description: Teave Android SDK isikupärastamise ja käitamise kohta
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036913"
---
# <a name="get-started-with-the-android-sdk"></a>Hakake kasutama rakendust Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

See juhend juhatab teid Android rakenduse intrumentimise protsessist läbi Dynamics 365 Customer Insights kaasamisülevaadete SDK abil. Te saate portaalis sündmusi näha viie minuti pärast või varem.

## <a name="configuration-options"></a>Konfigureerimissuvandid
Järgmised seadistusvõimalused saab SDK-le edastada:

- **ingestionKey**: Edastusvõti saadab sündmused teie tööruumi.

## <a name="prerequisites"></a>Eeltingimused

- Android Studio

- Miinimum Android API tase: 16 (Jelly Bean)

- Edastusvõti (hankimiseks vaadake allolevaid juhiseid)

## <a name="step-1-integrate-the-sdk-into-your-application"></a>1. etapp. SDK integreerimine rakendusega
Alustage protsessi, valides töötamiseks tööruumi, valides Android mobiiliplatvormi ja laadides alla Android SDK.

- Valige oma tööruum vasakpoolsel navigeerimispaanil tööruumi vahetaja abil.

- Kui teil pole olemasolevat tööruumi, valige  **Uus tööruum** ja järgige [uue tööruumi](create-workspace.md) loomise juhiseid.

## <a name="step-2-configure-the-sdk"></a>2. etapp. Konfigureeri SDK

1. Pärast tööruumi loomist minge **Administraator** > **Tööruum** ja seejärel valige  **Installijuhend**. 

1. Laadige alla [kaasamisülevaated Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) ja paigutage `eiandroidsdk-debug.aar` fail `libs` kausta.

1. Avage oma projekti taseme `build.gradle` fail ja lisage järgmised lõigendid:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Saate seadistada kaasamisülevaadete SDK konfiguratsiooni läbi `AndroidManifest.xml` faili, mis asub `manifests` kaustas. 
1. Kopeerige XML-lõigend **Installijuhendist**. `Your-Ingestion-Key` peaks asustama automaatselt.

   > [!NOTE]
   > Te ei pea jaotist `${applicationId}` asendama. See asustatakse automaatselt.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Saate lubada või keelata `View` sündmuste automaathõivet, määrates ülaltoodud `autoCapture` välja väärtuseks `true` või `false`.

1. (valikuline) Muud konfiguratsioonid hõlmavad lõpp-punkti kogumiga URL seadmist. Need saab lisada edastusvõtme `AndroidManifest.xml` metaandmete alla:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>3. etapp. Lähtesta SDK üksusest MainActivity 

Pärast SDK initsialiseerimist saate keskkonnas MainActivity töötada sündmuste ja nende atribuutidega.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Sea atribuut kõigile sündmustele (valikuline)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Kontekstisündmuse atribuutide puhul toetatakse järgmisi tüüpe.
- String
- Kuupäev
- Topelttäpsusega
- Pikk
- Loogiline
- UUID

### <a name="track-an-event"></a>Sündmuse jälgimine

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

### <a name="set-user-details-for-your-event-optional"></a>Määrake oma sündmuse kasutaja üksikasjad (valikuline)

SDK võimaldab määratleda kasutajateavet, mida saab saata iga sündmusega. Kasutajateabe määramiseks helistage `setUser(user: User)` API `Analytics` tasemel.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

Andmeklass `User` sisaldab järgmisi stringi atribuute:

- **kohalikId**: kasutaja kohalik ID.
- **autenditudId**: autenditud kasutaja ID.
- **authType** autentimistüüp, mida kasutati autenditud kasutaja ID saamiseks.
- **nimi**: Kasutaja nimi.
- **ekiri**: Saatja ekirja aadress.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
