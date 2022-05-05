---
title: Turbesätted rakenduses Dynamics 365 Customer Insights
description: Siit leiate teavet rakenduse turbesätete kohta Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653789"
---
# <a name="security-overview-page"></a>Turbeülevaate leht

Lehel **Turvalisus** on loetletud suvandid kasutajaõiguste ja -funktsioonide konfigureerimiseks, mis aitavad turvalisemaks muuta Dynamics 365 Customer Insights. Sellele lehele pääsevad juurde ainult administraatorid. 

Sätete konfigureerimiseks avage **AdminSecurity** > **·**.

Leht **Turvalisus** sisaldab järgmisi vahekaarte.
- [Kasutajad](#users-tab)
- [APId](#apis-tab)
- [Võtmehoidla](#key-vault-tab)

## <a name="users-tab"></a>Vahekaart Kasutajad

Juurdepääs Customer Insightsile on piiratud teie asutuse kasutajatega, kelle administraator on rakendusse lisanud. Vahekaart **Kasutajad** võimaldab hallata kasutaja juurdepääsu ja nende õigusi. Lisateavet leiate teemast [Kasutajaõigused](permissions.md).

## <a name="apis-tab"></a>Vahekaart API-d

Vaadake ja hallake customer Insights API-de [kasutamise](apis.md) võtmeid oma keskkonna andmetega.

Saate luua uusi primaar- ja sekundaarvõtmeid, valides suvandi **Taasta primaar-** või **Regenerate sekundaarne**. 

API-le juurdepääsu blokeerimiseks keskkonnale valige **Keela**. Kui API-d on keelatud, saate uuesti juurdepääsu andmiseks valida **Luba**.

## <a name="key-vault-tab"></a>Vahekaart Võtmehoidla

Vahekaart **Võtmehoidla** võimaldab teil linkida ja hallata oma [Azure'i võtmehoidlat](/azure/key-vault/general/basic-concepts) keskkonnaga.
Sihtotstarbelise võtmehoidla abil saab etappe luua ja kasutada saladusi organisatsiooni vastavuse piirides. Customer Insights saab kasutada Azure Key Vault'i saladusi, et [luua ühendusi](connections.md) kolmandate osapoolte süsteemidega.

Lisateavet leiate jaotisest [Enda Azure'i võtmehoidla loomine](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
