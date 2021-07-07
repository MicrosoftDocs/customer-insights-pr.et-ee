---
title: Customer Insights andmete eksportimine Salesforce Marketing Cloud'i
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Salesforce Marketing Cloud'i.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314600"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>Segmentide ja muude andmete eksportimine Salesforce Marketing Cloud'i (eelversioon)

Kasutage kliendiandmeid Salesforce Marketing Cloud'is, eksportides need turvalise failiedastuse protokolli (SFTP) asukoha kaudu.

## <a name="prerequisites-for-connection"></a>Ühenduse eeltingimus

- SFTP-hosti saadavus ja vastav administraatori mandaat. [SFTP-asukohtade seadistamine Salesforce Marketing Cloud'is](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a>Teadaolevad piirangud

- Ekspordi käitusaeg sõltub teie süsteemi jõudlusest. Soovitame teie serveri minimaalseks konfiguratsiooniks kahte protsessori tuuma ja 1 GB mälu. 
- Kuni 100 miljoni kliendiprofiiliga olemite eksportimiseks, kasutades soovitatavat minimaalset konfiguratsiooni, võib minna 90 minutit. 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Ühenduse loomine Salesforce Marketing Cloud'iga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Salesforce Marketing Cloud** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma SFTP konto jaoks **Kasutajanimi**, **Parool**, **Hostinimi** ja **Ekspordikaust**.

1. Valige ühenduse testimiseks **Kinnita**.

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus SFTP jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Valige, kas soovite eksportida oma andmed **Gzipped** või **Unzipped** ja **väljaeraldaja** eksporditavate failide jaoks.

1. Valige olemid, nt segmendid, mida soovite eksportida.

   > [!NOTE]
   > Iga valitud olem tükeldatakse eksportimisel kuni viieks väljundfailiks. 

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Customer Insights andmete importimine Salesforce Marketing Cloud'i SFTP asukohast

1. Looge [andmelaiendid Salesforce Marketing Cloud'is](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), et importida Customer Insights andmefail SFTP asukohast.

2. [Importige andmed SFTP asukohast](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) Salesforce Marketing Cloud andmelaiendisse. 

3. Seadistage automatiseerimine andmete importimiseks andmelaienditele. Lisateave [failide kukutamise automaatika ja ajastatud automaatika](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Määratle [faili kukutamise automaatika](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) või [ajastatud automaatika](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Siin on näide [automatiseerimine SFTP-ga](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil SFTP kaudu andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et ekspordisihtkohad täidavad kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
