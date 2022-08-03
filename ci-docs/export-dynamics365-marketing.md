---
title: Segmentide eksportimine rakendusse Dynamics 365 Marketing (eelvaade)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196619"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>Segmentide eksportimine rakendusse Dynamics 365 Marketing (eelvaade)

Kasutage [segmente](segments.md) kampaaniate loomiseks ja konkreetsete kliendirühmadega ühenduse võtmiseks rakendusega [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Kui kasutate Dynamics 365 Marketing'i uusi võimalusi reaalajas klienditeekonna korraldamiseks Dataverse organisatsioonis, ei pea te Dynamics 365 Marketingisse standardekspordi looma. Customer Insightsi kontaktid ja segmendid on saadaval otse rakenduses Dynamics 365 Marketing pärast rakenduse Marketing ja Customer Insights ühendamist. Enne olemasolevate ekspordite kustutamist vaadake üle dokumentatsioon [, kuidas ühendada Customer Insights ja Dynamics 365 Marketing klienditeekond orkestreerimisega](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>Eeltingimus

Enne segmendi eksportimist Customer Insightsist Marketingi, peavad kontaktikirjed olema olemas rakenduses Dynamics 365 Marketing. Lugege lisateavet selle kohta, kuidas valmendada kontakte [Dynamics 365 Marketingis Microsoft Dataversei abil](connect-dataverse-managed-lake.md).

> [!NOTE]
> Segmentide eksportimine Customer Insightsist rakendusse Marketing ei loo turunduseksemplarides uusi kontaktikirjeid. Rakenduse Marketing kontaktikirjed tuleb alla neelata Customer Insightsis ja neid tuleb kasutada andmeallikas. Need tuleb lisada ka ühendatud kliendi olemisse, et vastendada kliendi ID-d ja kontakti ID-deks, enne kui segmente saab eksportida.

## <a name="set-up-connection-to-marketing"></a>Ühenduse loomine Marketingiga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Dynamics 365 Marketing**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage väljale **Serveri aadress** oma organisatsiooni Marketingi URL.

1. Jaotises **Serveri administraatorikonto** valige suvand **Logi sisse** ja valige rakenduse Dynamics 365 Marketing konto.

1. Vastendage kliendi olemi kontakti ID väli Dynamics 365 kontakti ID-ga.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus Dynamics 365 Marketing jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige kliendi olemis väli Kontakti ID, mis vastab Dynamics 365-i kontakti ID-le.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
