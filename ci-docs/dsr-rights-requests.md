---
title: Andmesubjekti õigused (DSR) vastavalt GDPR-ile | Microsoft Docs
description: Dynamics 365 Customer Insightsi andmesubjekti taotlustele vastamine.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: af2583295627f98e980adbca4f216b9c34c3cad8
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808541"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Andmesubjekti õigused (DSR) vastavalt GDPR-ile

Euroopa Liidu General Data Protection Regulation (GDPR) on kehtiv alates 25. maist 2018. See annab üksikisikutele nende andmetega seoses märkimisväärselt õigusi. GDPR on üksikisikute privaatsusõiguste kaitse ja lubamise kohta. Rohkem teavet Microsofti enda õiguste ja turvalisuse kohta saate lugeda [Microsofti usalduskeskusest](https://www.microsoft.com/trust-center).

Oleme pühendunud sellele, et aitame klientidel täita GDPR-i nõudeid. See hõlmab õigust kustutada ja eksportida andmeid, mis sisaldavad isikuandmeid, nagu kasutaja ID-d, telefoninumbrid ja meiliaadressid. Administraatorid saavad juurutada kasutajataotlusi isiklike andmete kustutamiseks või eksportimiseks.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insightsi GDPR-i andmesubjekti kustutamise taotlustele vastamine

Õigus isikuandmete eemaldamiseks ettevõtte kliendiandmetest on isikuandmete kaitse üldmääruse (GDPR-i) põhikaitse. Isikuandmete eemaldamine hõlmab kogi isiklike andmete ja süsteemi loodud logide eemaldamist, va auditi logi teabe.

#### <a name="manage-data-subject-delete-requests"></a>Andmete kustutamise taotluste haldamine

Customer Insights pakub konkreetse kliendi või kasutaja isikuandmete kustutamiseks järgmisi tootesiseseid kogemusi.

- **Kliendiandmete kustutamise taotluste haldamine**: kliendi andmed Customer Insightsis on sisestatud algsest andmeallikast, mis on Customer Insightsi väline. Kõik GDPR-i kustutamise taotlused tuleb teha algses andmeallikas.
- **Customer Insightsi kliendiandmete kustutamise taotluste haldamine**: kasutajate andmeid loob Customer Insights. Kõik GDPR-i kustutamise taotlused tuleb teha Customer Insightsis.

##### <a name="manage-requests-to-delete-customer-data"></a>Kliendiandmete kustutamise taotluste haldamine

Customer Insightsi administraator saab nende etappide abil eemaldada kliendiandmeid, mis kustutati andmeallikas.

1. Logige sisse rakendusse Dynamics 365 Customer Insights.
2. Andmeallikate **·** > **avamine**
3. Tehke iga loendis oleva andmeallikaga, mis sisaldab kustutatud kliendiandmeid, järgmist.
   1. Valige vertikaalne kolmikpunkt (&vellip;) ja seejärel valige **Värskenda**.
   2. Kontrollige andmeallikas olekut **Oleku** all. Märge tähendab, et värskendamine õnnestus. Ohukolmnurk tähendab, et midagi läks valesti. Kui kuvatakse ohukolmnurk, võtke ühendust aadressil D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Kliendiandmete GDPR-i kustutamise taotluste käsitlemine.](media/gdpr-data-sources.png "Kliendiandmete GDPR-i kustutamise taotluste käsitlemine")

##### <a name="manage-delete-requests-for-user-data"></a>Kasutajaandmete kustutamise taotluste haldamine

Customer Insightsi administraator saab Customer Insightsi kasutaja andmete kustutamiseks toimida järgmiselt.

1. Logige sisse rakendusse Dynamics 365 Customer Insights.
2. **Avage administraatori** > **turbeõigused** > **·**.
3. Valige märkeruutude abil kasutaja, kelle soovite kustutada.
4. Valige **Eemalda**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR-i andmesubjekti eksportimistaotlustele vastamine

Osana meie kohustusest teha teiega koostööd teie teekonnal isikuandmete kaitse üldmääruse (GDPR) juurde, oleme välja töötanud dokumendid, mis aitavad teil vastata andmesubjektide taotlustele.

#### <a name="manage-export-and-view-requests"></a>Ekspordi ja vaate taotluste haldamine

Andmete teisaldamise õigus võimaldab andmesubjektil taotleda oma isikuandmete koopiat elektrooniliselt (määratletakse kui „struktureeritud, tavaliselt kasutatav, masinloetav ja koostalitlusvõimeline vorming“), mida võib edastada teisele andmetöötlejale.

##### <a name="export-customer-data-tenant-admin"></a>Kliendiandmete eksportimine (rentniku administraator)

Rentniku administraator võib järgida andmete eksportimisel järgmisi etappe.

1. Saatke meili aadressile D365CI@microsoft.com, et määrata taotluses kliendi meiliaadress. Customer Insightsi meeskond saadab registreeritud rentniku administraatori meiliaadressile meili, paludes kinnitust andmete eksportimiseks.
2. Kinnitage taotletud kliendile andmete eksportimise luba.
3. Saage eksporditud andmed rentniku administraatori meiliaadressi kaudu.

##### <a name="export-user-data-tenant-admin"></a>Kasutajaandmete eksportimine (rentniku administraator)

1. Saatke meil aadressile D365CI@microsoft.com, et määrata taotluses kasutaja meiliaadress. Customer Insightsi meeskond saadab registreeritud rentniku administraatori meiliaadressile meili, paludes kinnitust andmete eksportimiseks.
2. Kinnitage taotletud kasutajale andmete eksportimise luba.
3. Saage eksporditud andmed rentniku administraatori meiliaadressi kaudu.

## <a name="consent-management-preview"></a>Nõusoleku haldamine (eelvaade)

Nõusolekuhalduse võimalus ei kogu otseselt kasutajaandmeid. See impordib ja töötleb nõusolekuandmeid, mida kasutajad esitavad teistes rakendustes.

Nõusolekuandmete eemaldamiseks konkreetsete kasutajate kohta eemaldage need nõusoleku haldamise võimele allaneelatud andmeallikatest. Pärast andmeallikas värskendamist kustutatakse eemaldatud andmed ka nõusolekukeskuses. Nõusolekuolemit kasutavad rakendused kustutavad ka andmed, mis eemaldati allikast pärast [värskendamist](system.md#refresh-processes). Soovitame värskendada andmeallikaid kiiresti pärast andmesubjekti päringule vastamist, et eemaldada kasutaja andmed kõigist muudest protsessidest ja rakendustest.

[!INCLUDE [footer-include](includes/footer-banner.md)]