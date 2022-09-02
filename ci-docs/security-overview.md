---
title: Turvaseadete konfigureerimine
description: Lisateavet turbesätete kohta leiate jaotisest Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387244"
---
# <a name="configure-security-settings"></a>Turvaseadete konfigureerimine

Hallake API võtmeid, pääsete juurde kliendiandmetele ja seadistage Azure Private Link.

## <a name="manage-api-keys"></a>API võtmete haldamine

Vaadake ja hallake võtmeid, et kasutada [Customer Insightsi API-sid](apis.md) koos teie keskkonnas olevate andmetega.

1. Minge jaotisse **Administraatori turve** > **ja valige** vahekaart API-d **·**.

1. Kui API juurdepääs keskkonnale pole seadistatud, valige **Luba**. Või API juurdepääsu blokeerimiseks keskkonnale valige **Keela** ja kinnita.

1. Hallake esmaseid ja teiseseid API-võtmeid.

   1. Primaarse või teisese API-võtme kuvamiseks **valige sümbol Kuva**.

   1. Primaarse või teisese API-võtme kopeerimiseks valige **sümbol Kopeeri**.

   1. Uute primaarsete või teiseste API-võtmete loomiseks valige **Taasta primaarne** või **Taasta sekundaarne**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Turvaline juurdepääs kliendiandmetele kliendi turvahoidla abil (eelvaade)

Customer Insights kasutab kliendi Power Platform turvahoidla võimalust. Kliendi turvahoidla pakub liidest andmetele juurdepääsu taotluste läbivaatamiseks ja kinnitamiseks (või tagasilükkamiseks). Need päringud tekivad siis, kui tugiteenusejuhtumi lahendamiseks on vaja andmetele juurdepääsu. Selle funktsiooni kasutamiseks peab Customer Insightsil olema olemasolev ühendus teie rentniku keskkonnaga Microsoft Dataverse.

Lisateavet kliendi turvahoidla kohta leiate [kliendi turvahoidla kokkuvõttest](/power-platform/admin/about-lockbox#summary)Power Platform. Artiklis kirjeldatakse [ka töövoogu](/power-platform/admin/about-lockbox#workflow) ja kliendi turvahoidla lubamiseks vajalikku [seadistust](/power-platform/admin/about-lockbox#enable-the-lockbox-policy).

> [!IMPORTANT]
> Üldadministraatorid Power Platform või Power Platform administraatorid saavad kinnitada Customer Insightsi jaoks väljastatud kliendi turvahoidla taotlusi.

## <a name="set-up-an-azure-private-link"></a>Azure Private Linki häälestamine

[Azure Private Link](/azure/private-link/private-link-overview) võimaldab Customer Insightsil luua teie kontoga ühenduse teie Azure Data Lake Storage virtuaalse võrgu privaatse lõpp-punkti kaudu. Salvestuskontol olevate andmete puhul, mis ei ole avatud avalikule internetile, võimaldab Private Link ühenduse selle piiratud võrguga.

> [!IMPORTANT]
> Minimaalne rollinõue Private Linki ühenduse seadistamiseks tehke järgmist.
>
> - Customer Insights: administraator
> - Azure’i sisseehitatud roll: [salvestusruumikonto kaasautor](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Kohandatud Azure’i rolli õigused: [Microsoft.Storage/storageAccounts/read ja Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. Minge Customer Insightsis jaotisse **Administraatori** > **turve** ja valige **vahekaart Privaatsed lingid**.

1. Valige **Lisa privaatne link**.

   **Paanil Lisa privaatne link** loetletakse teie rentniku salvestusruumikontod, mida teil on õigus vaadata.

1. Valige tellimus, ressursigrupp ja salvestusruumikonto.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Valige **Salvesta**.

1. Minge oma Data Lake Storage’i kontole ja avage ekraanil esitatud link.

1. Kinnitage privaatne link.


[!INCLUDE [footer-include](includes/footer-banner.md)]
