---
title: Android SDK näidis
description: Näidis projekt Android SDK kohta teabe saamiseks
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229913"
---
# <a name="run-the-android-sdk-sample"></a>Käivita Android SDK näidis

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

See Android näidisprojekt aitab teil mõista, kuidas SDK rakenduses töötab. Te ei pea koodi kirjutama. Lisage lihtsalt oma edastusvõti ja näete oma tööruumis kohe sündmusi.

## <a name="prerequisites"></a>Eeltingimused

- [Android Studio](https://developer.android.com/studio)
- [Edastusvõti](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Laadi alla Android SDK näidis

1. [Laadige alla kaasamisülevaated Android SDK näidis](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Saate tihendatud faili lahti pakkida `ei-android-sample.zip`.
1. Avage pakkimata kaust Android Studio.
1. Asendage failis `AndroidManifest.xml` string `"Your-Ingestion-Key"` oma tööruumi sisestusvõtmega töövõteandmetest jaotises **Administraator** > **Tööruum** > **Paigaldusjuhend**, 

   > [!NOTE]
   > Te ei pea jaotist `${applicationId}` asendama. See asustatakse automaatselt.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Näidisprojekti käivitamiseks valige **Käivita**.
1. Kuvage sündmused oma tööruumis.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
