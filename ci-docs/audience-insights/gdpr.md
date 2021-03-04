---
title: Andmesubjekti õigused (DSR) vastavalt GDPR-ile | Microsoft Docs
description: Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsiooni andmesubjekti taotlustele vastamine.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268681"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Andmesubjekti õigused (DSR) vastavalt GDPR-ile

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsiooni GDPR-i andmesubjekti kustutamistaotlustele vastamine

Õigus isikuandmete eemaldamiseks ettevõtte kliendiandmetest on isikuandmete kaitse üldmääruse (GDPR-i) põhikaitse. Isikuandmete eemaldamine hõlmab kogi isiklike andmete ja süsteemi loodud logide eemaldamist, va auditi logi teabe.

### <a name="manage-data-subject-delete-requests"></a>Andmete kustutamise taotluste haldamine

Sihtrühmaülevaadete funktsioon pakub järgmisi tootega seotud kogemusi, et kustutada teatud kliendi või kasutaja isikuandmed.

- **Kliendiandmete kustutamise taotluste haldamine**: kliendi andmed Customer Insightsis on sisestatud algsest andmeallikast, mis on Customer Insightsi väline. Kõik GDPR-i kustutamise taotlused tuleb teha algses andmeallikas.
- **Customer Insightsi kliendiandmete kustutamise taotluste haldamine**: kasutajate andmeid loob Customer Insights. Kõik GDPR-i kustutamise taotlused tuleb teha Customer Insightsis.

#### <a name="manage-delete-requests-for-customer-data"></a>Kliendiandmete kustutamise taotluste haldamine

Customer Insightsi administraator saab nende etappide abil eemaldada kliendiandmeid, mis kustutati andmeallikas.

1. Logige sisse rakendusse Dynamics 365 Customer Insights.
2. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**
3. Tehke iga loendis oleva andmeallikaga, mis sisaldab kustutatud kliendiandmeid, järgmist.
   1. Valige (...) ja seejärel valige nupp **Värskenda**.
   2. Kontrollige andmeallikas olekut **Oleku** all. Märge tähendab, et värskendamine õnnestus. Ohukolmnurk tähendab, et midagi läks valesti. Kui kuvatakse ohukolmnurk, võtke ühendust aadressil D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Kliendiandmete GDPR-i kustutamise taotluste käsitlemine](media/gdpr-data-sources.png "Kliendiandmete GDPR-i kustutamise taotluste käsitlemine")

#### <a name="manage-delete-requests-for-user-data"></a>Kasutajaandmete kustutamise taotluste haldamine

Customer Insightsi administraator saab Customer Insightsi kasutaja andmete kustutamiseks toimida järgmiselt.

1. Logige sisse rakendusse Dynamics 365 Customer Insights.
2. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Õigused**.
3. Valige märkeruutude abil kasutaja, kelle soovite kustutada.
4. Valige **Eemalda**.

> [!div class="mx-imgBorder"]
> ![Kasutajaandmete GDPR-i põhiste kustutamistaotluste haldamine](media/gdpr-permissions.png "Kasutajaandmete GDPR-i põhiste kustutamistaotluste haldamine")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR-i andmesubjekti eksportimistaotlustele vastamine

Osana meie pühendumusest saatmaks teid teekonnal isikuandmete kaitse üldmääruseni (GDPR) oleme välja töötanud dokumendid, mis aitavad teil valmistuda. Selles dokumentatsioonis kirjeldatakse toiminguid, mida saate kohe teha, et toetada GDPR-i täitmist sihtrühmaülevaadete kasutamisel.

### <a name="manage-export-and-view-requests"></a>Ekspordi ja vaate taotluste haldamine

Andmete teisaldamise õigus võimaldab andmesubjektil taotleda oma isikuandmete koopiat elektrooniliselt (määratletakse kui „struktureeritud, tavaliselt kasutatav, masinloetav ja koostalitlusvõimeline vorming“), mida võib edastada teisele andmetöötlejale.

#### <a name="export-customer-data-tenant-admin"></a>Kliendiandmete eksportimine (rentniku administraator)

Rentniku administraator võib järgida andmete eksportimisel järgmisi etappe.

1. Saatke meili aadressile D365CI@microsoft.com, et määrata taotluses kliendi meiliaadress. Customer Insightsi meeskond saadab registreeritud rentniku administraatori meiliaadressile meili, paludes kinnitust andmete eksportimiseks.
2. Kinnitage taotletud kliendile andmete eksportimise luba.
3. Saage eksporditud andmed rentniku administraatori meiliaadressi kaudu.

#### <a name="export-user-data-tenant-admin"></a>Kasutajaandmete eksportimine (rentniku administraator)

1. Saatke meil aadressile D365CI@microsoft.com, et määrata taotluses kasutaja meiliaadress. Customer Insightsi meeskond saadab registreeritud rentniku administraatori meiliaadressile meili, paludes kinnitust andmete eksportimiseks.
2. Kinnitage taotletud kasutajale andmete eksportimise luba.
3. Saage eksporditud andmed rentniku administraatori meiliaadressi kaudu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]