---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755539"
---
Pärast andmete allaneelamist alustage andmete ühendamise protsessi, et luua ühtne kliendiprofiil. Lisateavet leiate teemast [Andmete koondamine](../data-unification.md).

### <a name="select-source-fields"></a>Lähteväljade valimine

1. Pärast andmete valmendamist vastendage e-kaubanduse ja lojaalsusandmete kontaktid harilike andmetüüpidega. **Avage jaotisSe Andmete** > **ühendamine**.

1. Valige olemid, mis esindavad kliendiprofiili: **eCommerceContacts** ja **loyCustomers**.

   ![E-kaubanduse ja lojaalsuse andmeallikad vahekaardil „Koondamine“.](../media/unify-ecommerce-loyalty.png)

1. Valige andmeallika **eCommerceContacts** peamiseks võtmeks **ContactId** ja andmeallika **loyCustomers** peamiseks võtmeks **LoyaltyID**.

1. Tehke valik **Edasi**. Jätke duplikaatkirjed vahele ja valige **Edasi**.

### <a name="match-conditions"></a>Sobitamise tingimused

1. Valige **eCommerceContacts: peamise olemina e-kaubandus** ja kaasake kõik kirjed.

1. Valige **loyCustomers: LoyaltyScheme** ja lisage kõik kirjed.

1. Lisage reegel.
   - Valige **FullName** nii eCommerceContacts'i kui ka loyCustomersi jaoks.
   - Normaliseerimise jaoks valige **tüüp (telefon, nimi, aadress jne**).**·**
   - Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.
   - Sisestage **nime jaoks FullName, Email**.

1. Lisage meiliaadressile teine tingimus.
   - Valige **e-post** nii e-kaubanduse kontaktidele kui ka loyCustomersile.
   - Jätke suvand „Normaliseerimine“ tühjaks.
   - Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.

   ![Reegli vastavusseviimine nime ja meili korral vahekaardil „Koondamine“.](../media/unify-match-rule.png)

1. Valige nupp **Valmis**.

1. Tehke valik **Edasi**.

### <a name="unify-fields"></a>Väljade ühendamine

1. Nimetage **olem ContactId ümber üksusele** ContactIdLOYALTY **·** **,** et eristada seda teistest allaneelatud ID-dest.

1. Läbivaatuseks valige **Edasi** ja seejärel valige **Loo kliendiprofiilid**.
