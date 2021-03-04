---
title: Customer Insightsi andmete eksportimine SFTP hostidesse
description: Teave selle kohta, kuidas konfigureerida ühendust SFTP hostiga.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267993"
---
# <a name="connector-for-sftp-preview"></a>SFTP konnektor (eelversioon)

Kasutage oma kliendiandmeid kolmanda osapoole rakendustes, eksportides need turvalise failiedastuse protokolli (SFTP) hosti.

## <a name="prerequisites"></a>Eeltingimused

- SFTP-hosti saadavus ja vastav identimisteave.

## <a name="connect-to-sftp"></a>Ühenduse loomine SFTP-ga

1. Avage **Haldus** > **Ekspordi sihtkohad**.

1. Valige jaotises **SFTP** suvand **Seadistamine**.

1. Sisestage väljale **Kuvatav nimi** oma sihtkoha äratuntav nimi.

1. Sisestage oma SFTP konto jaoks **Kasutajanimi**, **Parool**, **Hostinimi** ja **Ekspordikaust**.

1. Valige ühenduse testimiseks **Kinnita**.

1. Pärast edukat kontrollimist valige, kas soovite eksportida oma andmed **GZIP-iks tihendatud** või **Tihendamata** kujul ja valige eksporditud failidele **väljaeraldaja**.

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Ekspordi konfigureerimise alustamiseks valige **Edasi**.

## <a name="configure-the-export"></a>Ekspordi konfigureerimine

1. Valige olemid, nt segmendid, mida soovite eksportida.

   > [!NOTE]
   > Igal valitud olemil on eksportimisel kuni viis väljundfaili. 

1. Valige **Salvesta**.

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).

## <a name="known-limitations"></a>Teadaolevad piirangud

- Ekspordi käitusaeg sõltub teie süsteemi jõudlusest. Soovitame teie serveri minimaalseks konfiguratsiooniks kahte protsessori tuuma ja 1 GB mälu. 
- Kuni 100 miljoni kliendiprofiiliga olemite eksportimiseks võib kuluda 90 minutit, kui kasutate soovitatud minimaalset kahe protsessori tuuma ja 1 GB mäluga konfiguratsiooni. 

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil SFTP kaudu andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et ekspordisihtkohad täidavad kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]