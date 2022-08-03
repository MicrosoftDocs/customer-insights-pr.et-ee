---
title: Andmete eksportimine Salesforce Marketing Cloudi (eelvaade)
description: Vaadake, kuidas konfigureerida ühendust ja eksportida Salesforce Marketing Cloud'i.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197033"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Andmete eksportimine Salesforce Marketing Cloudi (eelvaade)

Kasutage kliendiandmeid Salesforce Marketing Cloud'is, eksportides need turvalise failiedastuse protokolli (SFTP) asukoha kaudu.

## <a name="prerequisites"></a>eeltingimused

- [SFTP host Salesforce Marketing Cloudi](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) jaoks ja vastavad administraatori mandaadid.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Ühenduse seadistamine Salesforce Marketing Cloudiga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Salesforce Marketing Cloud**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma SFTP konto jaoks **Kasutajanimi**, **Parool**, **Hostinimi** ja **Ekspordikaust**.

1. Valige ühenduse testimiseks **Kinnita**.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus SFTP jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige, kas soovite eksportida oma andmed **Gzipped** või **Unzipped** ja **väljaeraldaja** eksporditavate failide jaoks.

1. Valige olemid (nt segmendid), mida soovite eksportida.

   > [!NOTE]
   > Iga valitud olem jagatakse eksportimisel maksimaalselt viieks väljundfailiks.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Customer Insights andmete importimine Salesforce Marketing Cloud'i SFTP asukohast

1. Looge [andmelaiendid Salesforce Marketing Cloud'is](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5), et importida Customer Insights andmefail SFTP asukohast.

2. [Importige andmed SFTP asukohast](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) Salesforce Marketing Cloud andmelaiendisse.

3. Seadistage automatiseerimine andmete importimiseks andmelaienditele. Lisateave [failide kukutamise automaatika ja ajastatud automaatika](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Määratle [faili kukutamise automaatika](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) või [ajastatud automaatika](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Siin on näide [automatiseerimine SFTP-ga](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
