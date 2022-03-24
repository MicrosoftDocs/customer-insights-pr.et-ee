---
title: Customer Insightsi andmete eksportimine rakendusse Dynamics 365 Marketing
description: Lugege, kuidas konfigureerida ühendust ja eksportida Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 0bd2bfa7402ed19cb92ff1f35208b150cfec48c3
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455810"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Kasutage segmente rakendusega Dynamics 365 Marketing (eelversioon)



Kasutage lahenduses Dynamics 365 Marketing kampaaniate loomiseks ja konkreetsete kliendirühmadega ühenduse võtmiseks [segmente](segments.md). Lisateavet leiate teemast [Dynamics 365 Customer Insightsi segmentide kasutamine Dynamics 365 Marketingiga](/dynamics365/marketing/customer-insights-segments).

Kui kasutate Dynamics 365 Marketing'i uusi võimalusi reaalajas klienditeekonna korraldamiseks Dataverse organisatsioonis, ei pea te Dynamics 365 Marketingisse standardekspordi looma. Sihtrühma ülevaadete kontaktid ja segmendid on pärast Marketing ja Customer Insightsi ühendamist saadaval otse rakenduses Dynamics 365 Marketing. Enne olemasoleva ekspordi kustutamist vaadake üle dokumentatsioon [sihtrühma ülevaadete ja Dynamics 365 Marketing klienditeekonna ühendamiseks](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Ühenduse eeltingimus

- Enne segmendi eksportimist Customer Insightsist Marketingi, peavad kontaktikirjed olema olemas rakenduses Dynamics 365 Marketing. Lugege lisateavet selle kohta, kuidas valmendada kontakte [Dynamics 365 Marketingis Microsoft Dataversei abil](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > Segmentide eksportimine sihtrühmaülevaadetest Marketingi ei loo uusi kontaktikirjeid Marketingi eksemplaris. Marketingi kontaktikirjed peavad olema valmendatud sihtrühmaülevaadetes ja neid tuleb kasutada andmeallikana. Need tuleb lisada ka ühendatud kliendi olemisse, et vastendada kliendi ID-d ja kontakti ID-deks, enne kui segmente saab eksportida.

## <a name="set-up-connection-to-marketing"></a>Ühenduse loomine Marketingiga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Dynamics 365 Marketing** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage väljale **Serveri aadress** oma organisatsiooni Marketingi URL.

1. Jaotises **Serveri administraatorikonto** valige suvand **Logi sisse** ja valige rakenduse Dynamics 365 Marketing konto.

1. Vastendage olemi Kliendi väli Kontakti ID Dynamics 365 kontakti ID-ga.

1. Ühenduse loomiseks valige **Salvesta**. 

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus Dynamics 365 Marketing jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Valige üks või mitu segmenti.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
