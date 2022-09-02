---
title: Andmesubjekti õigused (DSR) vastavalt GDPR-ile | Microsoft Docs
description: Dynamics 365 Customer Insightsi andmesubjekti taotlustele vastamine.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387106"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Andmesubjekti õigused (DSR) vastavalt GDPR-ile

Euroopa Liidu General Data Protection Regulation (GDPR) on kehtiv alates 25. maist 2018. See annab üksikisikutele nende andmetega seoses märkimisväärselt õigusi. GDPR on üksikisikute privaatsusõiguste kaitse ja lubamise kohta. Lisateavet Microsofti pühendumuse kohta turvalisusele ja nõuetele vastavusele leiate Microsofti [usalduskeskusest](https://www.microsoft.com/trust-center).

Oleme pühendunud sellele, et aitame klientidel täita GDPR-i nõudeid. See hõlmab õigust kustutada või eksportida andmeid, mis sisaldavad isikuandmeid, nagu kasutaja ID-d, telefoninumbrid ja e-posti aadressid. Administraatorid saavad juurutada kasutajataotlusi isiklike andmete kustutamiseks või eksportimiseks.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>GDPR-i andmesubjektile Customer Insightsi kustutamistaotlustele vastamine

Õigus isikuandmete eemaldamiseks ettevõtte kliendiandmetest on isikuandmete kaitse üldmääruse (GDPR-i) põhikaitse. Isikuandmete eemaldamine hõlmab kogi isiklike andmete ja süsteemi loodud logide eemaldamist, va auditi logi teabe.

### <a name="manage-data-subject-delete-requests"></a>Andmete kustutamise taotluste haldamine

Customer Insights pakub konkreetse kliendi või kasutaja isikuandmete kustutamiseks järgmisi tootesiseseid funktsioone.

- **Kliendiandmete kustutamise taotluste haldamine**: kliendi andmed Customer Insightsis on sisestatud algsest andmeallikast, mis on Customer Insightsi väline. Esmalt tehke GDPR-i kustutamistaotlused algses andmeallikas.
- **Customer Insightsi kliendiandmete kustutamise taotluste haldamine**: kasutajate andmeid loob Customer Insights. Tehke kõik GDPR-i kustutamistaotlused Customer Insightsis.

#### <a name="manage-requests-to-delete-customer-data"></a>Kliendiandmete kustutamise taotluste haldamine

Eemaldage Customer Insightsi administraatorina Customer Insightsi kliendiandmed, mis kustutati andmeallikas. Veenduge, et GDPR-i kustutamistaotlused tehti algses andmeallikas.

1. Logige sisse rakendusse Dynamics 365 Customer Insights.

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Tehke iga loendis oleva andmeallikaga, mis sisaldab kustutatud kliendiandmeid, järgmist.
   1. Valige andmeallikas ja seejärel valige **Värskenda**.
   1. Kontrollige andmeallikas olekut **Oleku** all. Märge tähendab, et värskendamine õnnestus. Ohukolmnurk tähendab, et midagi läks valesti. Kui kuvatakse ohukolmnurk, võtke ühendust aadressil D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Kliendiandmete GDPR-i kustutamise taotluste käsitlemine.":::

1. Pärast edukat andmeallikate värskendamist käivitage ka allavoolu värskendused. Eriti kui teil pole plaanis Customer Insightsi korduvat täielikku värskendamist.

   > [!IMPORTANT]
   > Staatilisi segmente ei kaasata täielikku värskendamisse ega pärast kustutamistaotlust allavoolu toimuvatesse värskendamistesse. Tagamaks, et kliendiandmed eemaldatakse ka staatilistest segmentidest, looge staatilised segmendid värskendatud lähteandmetega uuesti.

#### <a name="manage-delete-requests-for-user-data"></a>Kasutajaandmete kustutamise taotluste haldamine

Kustutage Customer Insightsi administraatorina Customer Insightsi kasutajaandmed.

1. Logige sisse rakendusse Dynamics 365 Customer Insights.

1. Avage **jaotis Administraatori** > **turbe** > ja valige **vahekaart Kasutajad** .

1. Märkige nende kasutajate ruut, kelle soovite kustutada.

1. Valige **Eemalda**.

1. Kinnitage kustutamine.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR-i andmesubjekti eksportimistaotlustele vastamine

Andmete teisaldamise õigus võimaldab andmesubjektil taotleda oma isikuandmete koopiat elektrooniliselt (määratletakse kui „struktureeritud, tavaliselt kasutatav, masinloetav ja koostalitlusvõimeline vorming“), mida võib edastada teisele andmetöötlejale.

### <a name="manage-export-and-view-requests"></a>Ekspordi ja vaate taotluste haldamine

Hallake kliendi- või kasutajaandmete eksportimise taotlusi.

#### <a name="export-customer-data-tenant-admin"></a>Kliendiandmete eksportimine (rentniku administraator)

Rentnikuadministraatorina eksportige kliendiandmeid.

1. Saatke meili aadressile D365CI@microsoft.com, et määrata taotluses kliendi meiliaadress. Customer Insightsi meeskond saadab registreeritud rentniku administraatori meiliaadressile meili, paludes kinnitust andmete eksportimiseks.
2. Kinnitage taotletud kliendile andmete eksportimise luba.
3. Saage eksporditud andmed rentniku administraatori meiliaadressi kaudu.

#### <a name="export-user-data-tenant-admin"></a>Kasutajaandmete eksportimine (rentniku administraator)

Rentnikuadministraatorina eksportige kasutajaandmeid.

1. Saatke meil aadressile D365CI@microsoft.com, et määrata taotluses kasutaja meiliaadress. Customer Insightsi meeskond saadab registreeritud rentnikuadministraatori meiliaadressile meilisõnumi, milles palub andmete eksportimiseks kinnitust.
1. Kinnitage taotletud kasutajale andmete eksportimise luba.
1. Saage eksporditud andmed rentniku administraatori meiliaadressi kaudu.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Andmete kustutamise käsitlemine Dynamics 365 Customer Insights

Andmed kustutatakse (andmesektsioonid ja andmete hetktõmmised), kui andmesektsioonid ja andmete hetktõmmised on passiivsed rohkem kui 30 päeva, mis tähendab, et need on asendatud uue andmesektsiooni ja hetktõmmisega andmeallikate värskendamise kaudu.

Kõiki andmeid ja hetktõmmiseid ei kustutata. Kõige värskem andmesektsioon ja andmete hetktõmmis on aktiivsed, kuna neid kasutatakse Customer Insightsis. Uusimate andmete puhul pole oluline, kas andmeallikaid pole viimase 30 päeva jooksul värskendatud.

[!INCLUDE [footer-include](includes/footer-banner.md)]
