---
title: Customer Insightsi andmete eksportimine SFTP hostidesse
description: Lugege, kuidas konfigureerida ühendust ja eksportida SFTP asukohta.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b19ca6b8085846785682046f83d0ed4758269e5b98303692c703d995407ca7dd
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035456"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Segmentide ja muude andmete eksportimine SFTPsse (eelversioon)

Kliendiandmete kasutamiseks muude tootjate rakendustes eksportige need turvalise failiedastuse protokolli (SFTP) asukohta.

## <a name="prerequisites-for-connection"></a>Ühenduse eeltingimus

- SFTP-hosti saadavus ja vastav identimisteave.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Ekspordi käitusaeg sõltub teie süsteemi jõudlusest. Soovitame teie serveri minimaalseks konfiguratsiooniks kahte protsessori tuuma ja 1 GB mälu. 
- Kuni 100 miljoni kliendiprofiiliga olemite eksportimiseks võib kuluda 90 minutit, kui kasutate soovitatud minimaalset kahe protsessori tuuma ja 1 GB mäluga konfiguratsiooni. 

## <a name="set-up-connection-to-sftp"></a>SFTP ühenduse loomine

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **SFTP** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma SFTP konto jaoks **Kasutajanimi**, **Parool**, **Hostinimi** ja **Ekspordikaust**.

1. Valige ühenduse testimiseks **Kinnita**.

1. Valige, kas soovite eksportida oma andmed **Gzipped** või **Unzipped** ja **väljaeraldaja** eksporditavate failide jaoks.

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus SFTP jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Valige olemid, nt segmendid, mida soovite eksportida.

   > [!NOTE]
   > Iga valitud olem tükeldatakse eksportimisel kuni viieks väljundfailiks. 

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil SFTP kaudu andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et ekspordisihtkohad täidavad kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
