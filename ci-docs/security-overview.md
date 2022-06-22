---
title: Customer Insightsi turbesätted
description: Siit leiate teavet rakenduse turbesätete kohta Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947410"
---
# <a name="security-settings-in-customer-insights"></a>Customer Insightsi turbesätted

Lehel **Turvalisus** on loetletud suvandid kasutajaõiguste ja -funktsioonide konfigureerimiseks, mis aitavad turvalisemaks muuta Dynamics 365 Customer Insights. Sellele lehele pääsevad juurde ainult administraatorid.

Sätete konfigureerimiseks avage **administraatori** > **turvalisus**.

Leht **Turvalisus** sisaldab järgmisi vahekaarte.

- [Kasutajad](#users-tab)
- [APId](#apis-tab)
- [Privaatsed lingid](#private-links-tab)
- [Võtmehoidla](#key-vault-tab)
- [Kliendi andmetele pääsete turvaliselt juurde kliendi lukustuskausta kaudu (eelvaade)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Vahekaart Kasutajad

Juurdepääs Customer Insightsile on piiratud teie asutuse kasutajatega, kelle administraator on rakendusse lisanud. Vahekaart **Kasutajad** võimaldab hallata kasutaja juurdepääsu ja nende õigusi. Lisateavet leiate teemast [Kasutajaõigused](permissions.md).

## <a name="apis-tab"></a>Vahekaart API-d

Vaadake ja hallake customer Insights API-de [kasutamise](apis.md) võtmeid oma keskkonna andmetega.

Saate luua uusi primaar- ja sekundaarvõtmeid, valides suvandi **Taasta primaar-** või **Regenerate sekundaarne**. 

API-le juurdepääsu blokeerimiseks keskkonnale valige **Keela**. Kui API-d on keelatud, saate uuesti juurdepääsu andmiseks valida **Luba**.

## <a name="private-links-tab"></a>Vahekaart Privaatsed lingid

[Azure Private Link](/azure/private-link/private-link-overview) võimaldab Customer Insightsil luua teie Azure Data Lake Storage kontoga ühenduse teie virtuaalse võrgu privaatse lõpp-punkti kaudu. Salvestuskontol olevate andmete puhul, mis ei ole avatud avalikule internetile, võimaldab Privaatlink ühendust selle piiratud võrguga.

> [!IMPORTANT]
> Minimaalne rollinõue privaatlingi ühenduse seadistamiseks.
>
> - Customer Insights: administraator
> - Azure'i sisseehitatud roll: [Storage Account Contributor](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Kohandatud Azure'i rolli õigused: [Microsoft.Storage/storageAccounts/read ja Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

Privaatse lingi seadistamine Customer Insightsis on kaheastmeline protsess. Esmalt algatate privaatse lingi **loomise Customer Insightsi administraatori** > **turbe** > **eralinkidest**. Privaatse **lingi** lisaminepaanil on loetletud rentniku salvestusruumikontod, mida teil on õigused vaadata. Valige salvestuskonto ja andke nõusolek eralingi loomiseks.

Seejärel peate kinnitama privaatlingi Data Lake Storage konto poolel. Uue privaatlingi kinnitamiseks avage ekraanil esitatud link.

## <a name="key-vault-tab"></a>Vahekaart Võtmehoidla

Vahekaart **Võtmehoidla** võimaldab teil linkida ja hallata oma [Azure'i võtmehoidlat](/azure/key-vault/general/basic-concepts) keskkonnaga.
Sihtotstarbelise võtmehoidla abil saab etappe luua ja kasutada saladusi organisatsiooni vastavuse piirides. Customer Insights saab kasutada Azure Key Vault'i saladusi, et [luua ühendusi](connections.md) kolmandate osapoolte süsteemidega.

Lisateavet leiate jaotisest [Enda Azure'i võtmehoidla loomine](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Kliendi andmetele pääsete turvaliselt juurde kliendi lukustuskausta kaudu (eelvaade)

Customer Insights kasutab Power Platform kliendiluku funktsiooni. Kliendilukuboks pakub liidest andmetele juurdepääsu taotluste ülevaatamiseks ja kinnitamiseks (või tagasilükkamiseks). Need taotlused tekivad siis, kui tugijuhtumi lahendamiseks on vaja andmetele juurdepääsu kliendiandmetele. Selle funktsiooni kasutamiseks peab Customer Insightsil olema olemasolev ühendus rentniku keskkonnaga Microsoft Dataverse.

Lisateavet kliendi lukustuskausta kohta leiate [kliendilukustu kokkuvõttest](/power-platform/admin/about-lockbox#summary)Power Platform. Artiklis kirjeldatakse [ka töövoogu](/power-platform/admin/about-lockbox#workflow) ja nõutavat [seadistust](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) kliendiluku lubamiseks.

> [!IMPORTANT]
> Customer Insightsi jaoks Power Platform Power Platform väljastatud kliendiluku või administraatorite globaalsed administraatorid saavad kinnitada customer lockboxi taotlused.

[!INCLUDE [footer-include](includes/footer-banner.md)]
