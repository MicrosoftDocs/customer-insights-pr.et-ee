---
title: Ühtsete profiilide kasutamine rakenduses Dynamics 365 Marketing
description: Siit saate teada, kuidas integreerida ühtsed profiilid ja segmendid Dynamics 365 Marketingiga.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 45c59465771e4ad25ed36d5da1568e67b94cf994
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653790"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Ühtsete kliendiprofiilidega töötamine rakenduses Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) tõstab klientide kogemusi, võimaldades teil korraldada isikupärastatud reise kõigis puutepunktides, et tugevdada suhteid ja teenida lojaalsust. Rakendus Dynamics 365 Marketing töötab sujuvalt Dynamics 365 Salesi, Dynamics 365 Customer Insights, ja Microsoft Teams muude toodetega ning võimaldab teil teha kiiremaid ja paremaid otsuseid, kasutades andmete ja tehisintellekti võimsust.

Ühendades Customer Insightsi andmed turundusega, saate teha järgmist.

- Sihtige ühtseid kliendiprofiile ja segmente. See võimaldab teil kaasata iga klienti, olenemata kliendi andmete asukohast.
- Põhidünaamiline sisu (nt isikupärastatud märgid) meilisõnumites, SMS-is ja tõuketeatistes selliste meetmete kohta nagu püsikliendi olek, tellimuse uuendamise kuupäev, peamine konto või mis tahes muu meede, mille olete jäädvustanud ühtses Customer Insightsi profiilis.
- Laadige turunduse andmed Customer Insightsi ja kombineerige need muudest allikatest pärinevate kliendiandmetega.
- Rakendage Customer Insightsi andmete puhastamise, rikastamise ja häguseid sobitamisvahendeid.


## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Rikkalike kliendiprofiilide kasutamine reaalajas turunduses

Reaalajas turundus võimaldab teil luua [kohandatud päästikuid](/dynamics365/marketing/real-time-marketing-custom-triggers), mis käivitavad kliendi teekonnad mis tahes klienditegevuse põhjal. Mida isikupärastatud on teie andmed, seda asjakohasemad ja isikupärastatumad on teie reisid. See muudab turunduse ja customer insightsi ühendamise nii võimsaks. Saate [ühendada andmeid](data-unification.md) mis tahes allikast ja seejärel kasutada neid hüper-isikupärastatud kliendireiside toitmiseks.

Lisateave: [Customer Insightsi profiilide ja segmentide kasutamine reaalajas turunduses](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Väljaminevate kliendiränkudega ühtsete segmentide kasutamine

Customer Insights võimaldab teil täpsustada andmeid paljudest allikatest ja ühendada need koondatud kliendisegmentideks. Ühendades [Customer Insightsi väljamineva turundusega](export-dynamics365-marketing.md), kuvatakse *ja* värskendatakse need segmendid automaatselt klienditeekond kujundajas.

Lisateave: [Dynamics 365 Marketingi segmentide Dynamics 365 Customer Insights kasutamine](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Andmete väljatõmbamine omast Azure Data Lake Storage

Kui soovite kasutada Customer Insightsi andmeid turundusega, ei piirdu te pilvsalvestusruumiga. Kui teil on juba oma Azure Data Lake Storage häälestamine olemas, saate luua ühenduse Customer Insightsiga ja seejärel jagada andmeid rakendusega Marketing samamoodi nagu pilvepõhise häälestuse korral.

Lisateave: [Andmete jagamise Dataverse lubamine omaga Azure Data Lake Storage](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)