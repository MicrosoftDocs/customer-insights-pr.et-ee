---
title: Android SDK kasutamise alustamine
description: Teave Android SDK isikupärastamise ja käitamise kohta
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 71ec4841303bd17d3f605547be8d6032c58a7b21
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977508"
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

## <a name="integrate-the-sdk-into-your-application"></a>SDK integreerimine rakendusega
Alustage protsessi, valides töötamiseks tööruumi, valides Android mobiiliplatvormi ja laadides alla Android SDK.

- Valige oma tööruum vasakpoolsel navigeerimispaanil tööruumi vahetaja abil.

- Kui teil pole olemasolevat tööruumi, valige  **Uus tööruum** ja järgige [uue tööruumi](create-workspace.md) loomise juhiseid.

- Pärast tööruumi loomist minge **Administraator** > **Tööruum** ja seejärel valige  **Installijuhend**.

## <a name="configure-the-sdk"></a>Konfigureeri SDK

Kui olete SDK alla laadinud, saate sellega sündmuste lubamiseks ja määratlemiseks töötada Android Studios. Selle tegemiseks on kaks võimalust.
### <a name="option-1-use-jitpack-recommended"></a>1. võimalus: kasutage JitPacki (soovitatav)
1. Lisa JitPack repositooriumisse `build.gradle` juur:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Lisage sõltuvus.
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>2. võimalus: kasutage allalaadimislinki
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

## <a name="enable-auto-instrumentation"></a>Luba automaatne instrumentatsioon

1. Lisage oma `manifests` kausta faili `AndroidManifest.xml` võrgu- ja Interneti-juurdepääsu õigused.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. Saate seadistada kaasamisülevaadete SDK konfiguratsiooni läbi `AndroidManifest.xml` faili.

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

   >[!NOTE]
   >`Action` Sündmused tuleb lisada käsitsi.

1. (valikuline) Muud konfiguratsioonid hõlmavad lõpp-punkti kogumiga URL seadmist. Neid saab lisada allaneelamise võtme metaandmete alla `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>Rakendage kohandatud sündmusi

Pärast SDK initsialiseerimist saate keskkonnas `MainActivity` töötada sündmuste ja nende atribuutidega.


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

## <a name="set-user-details-for-your-event-optional"></a>Määrake oma sündmuse kasutaja üksikasjad (valikuline)

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
