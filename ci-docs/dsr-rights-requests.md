---
title: Andmesubjekti õigused (DSR) vastavalt GDPR-ile | Microsoft Docs
description: Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsiooni andmesubjekti taotlustele vastamine.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350264"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Andmesubjekti õigused (DSR) vastavalt GDPR-ile

Euroopa Liidu General Data Protection Regulation (GDPR) on kehtiv alates 25. maist 2018. See annab üksikisikutele nende andmetega seoses märkimisväärselt õigusi. GDPR on üksikisikute privaatsusõiguste kaitse ja lubamise kohta. Rohkem teavet Microsofti enda õiguste ja turvalisuse kohta saate lugeda [Microsofti usalduskeskusest](https://www.microsoft.com/trust-center).

Oleme pühendunud sellele, et aitame klientidel täita GDPR-i nõudeid. See hõlmab õigust kustutada ja eksportida andmeid, mis sisaldavad isikuandmeid, nagu kasutaja ID-d, telefoninumbrid ja meiliaadressid. Administraatorid saavad juurutada kasutajataotlusi isiklike andmete kustutamiseks või eksportimiseks.

## <a name="audience-insights"></a>Sihtrühmaülevaated

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsiooni GDPR-i andmesubjekti kustutamistaotlustele vastamine

Õigus isikuandmete eemaldamiseks ettevõtte kliendiandmetest on isikuandmete kaitse üldmääruse (GDPR-i) põhikaitse. Isikuandmete eemaldamine hõlmab kogi isiklike andmete ja süsteemi loodud logide eemaldamist, va auditi logi teabe.

#### <a name="manage-data-subject-delete-requests"></a>Andmete kustutamise taotluste haldamine

Sihtrühmaülevaadete funktsioon pakub järgmisi tootega seotud kogemusi, et kustutada teatud kliendi või kasutaja isikuandmed.

- **Kliendiandmete kustutamise taotluste haldamine**: kliendi andmed Customer Insightsis on sisestatud algsest andmeallikast, mis on Customer Insightsi väline. Kõik GDPR-i kustutamise taotlused tuleb teha algses andmeallikas.
- **Customer Insightsi kliendiandmete kustutamise taotluste haldamine**: kasutajate andmeid loob Customer Insights. Kõik GDPR-i kustutamise taotlused tuleb teha Customer Insightsis.

##### <a name="manage-requests-to-delete-customer-data"></a>Kliendiandmete kustutamise taotluste haldamine

Customer Insightsi administraator saab nende etappide abil eemaldada kliendiandmeid, mis kustutati andmeallikas.

1. Logige sisse rakendusse Dynamics 365 Customer Insights.
2. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**
3. Tehke iga loendis oleva andmeallikaga, mis sisaldab kustutatud kliendiandmeid, järgmist.
   1. Valige (...) ja seejärel valige nupp **Värskenda**.
   2. Kontrollige andmeallikas olekut **Oleku** all. Märge tähendab, et värskendamine õnnestus. Ohukolmnurk tähendab, et midagi läks valesti. Kui kuvatakse ohukolmnurk, võtke ühendust aadressil D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Kliendiandmete GDPR-i kustutamise taotluste käsitlemine.](audience-insights/media/gdpr-data-sources.png "Kliendiandmete GDPR-i kustutamise taotluste käsitlemine")

##### <a name="manage-delete-requests-for-user-data"></a>Kasutajaandmete kustutamise taotluste haldamine

Customer Insightsi administraator saab Customer Insightsi kasutaja andmete kustutamiseks toimida järgmiselt.

1. Logige sisse rakendusse Dynamics 365 Customer Insights.
2. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Õigused**.
3. Valige märkeruutude abil kasutaja, kelle soovite kustutada.
4. Valige **Eemalda**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>GDPR-i andmesubjekti eksportimistaotlustele vastamine

Osana meie pühendumusest saatmaks teid teekonnal isikuandmete kaitse üldmääruseni (GDPR) oleme välja töötanud dokumendid, mis aitavad teil valmistuda. Selles dokumentatsioonis kirjeldatakse toiminguid, mida saate kohe teha, et toetada GDPR-i täitmist sihtrühmaülevaadete kasutamisel.

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

## <a name="consent-management-preview"></a>Nõusolekuhaldus (eelvaade)

Nõusoleku haldamise võimalus ei kogu kasutajaandmeid otse. See impordib ja töötleb ainult nõusolekuandmeid, mida kasutajad pakuvad teistes rakendustes.

Konkreetsete kasutajate nõusolekuandmete eemaldamiseks eemaldage need nõusoleku haldamise võimesse neelatud andmeallikatest. Pärast andmeallikas värskendamist kustutatakse eemaldatud andmed ka nõusolekukeskuses. Nõusoleku olemit kasutavad rakendused kustutavad ka andmed, mis eemaldati allikast pärast [värskendamist](audience-insights/system.md#refresh-processes). Soovitame värskendada andmeallikaid kiiresti pärast andmesubjektitaotlusele vastamist, et eemaldada kasutaja andmed kõigist muudest protsessidest ja rakendustest.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]