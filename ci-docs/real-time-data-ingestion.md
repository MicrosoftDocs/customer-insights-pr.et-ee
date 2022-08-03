---
title: Reaalajas andmete valmendamine (eelvaade)
description: Üldine teave reaalajas võimaluste kohta Customer Insightsis.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 403cc9dbd3bddcf67f59b5cb0be936af4d268fc2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195653"
---
# <a name="real-time-data-ingestion-preview"></a>Reaalajas andmete valmendamine (eelvaade)

Peaaegu reaalajaline funktsionaalsus võimaldab teil vaadata mõne sekundi jooksul viimaseid suhtlusi, mida teie kliendid on teie toodete või teenuste osas teinud.

[Ajastatud värskendamised](system.md#schedule-tab) hõlmavad palju kirjeid ja mitmesuguseid keerukaid toiminguid. Esmalt tuuakse andmed andmeallikast. Edasi andmed koondatakse ja seejärel rikastatakse täiendava teabega. Selle protsessi iga tsükkel võib kesta minutitest tundideni.

Reaalajas funktsioon pakub andmeid kohe tarbimiseks, kuni järgmine ajastatud värskendamine toob need andmed andmeallikast.

Reaalajalised värskendused aeguvad aja jooksul, mille möödumisel nad enam andmeallikas väärtust ei tühista.

- Profiili värskendusi säilitatakse neli tundi
- Tegevusi säilitatakse 30 päeva

Need väärtused on API kõne parameetrid, mida saate muuta. Nende eesmärk on tagada, et teie lähteandmed oleksid teie tõe allikas. Kui soovite, et reaalajas värskendusi kaasataks kauem, peate need lisama andmeallikasse, et neid saaks järgmise ajastatud värskendamise ajal tuua.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Ühendatud kliendi profiili väljade reaalajaline värskendamine

Värskendatud profiilid kuvatakse kliendikaardi vaates või mõnes muus visualiseeringus mõne sekundi jooksul.

Kuna reaalajalised toimingud toimuvad pärast andmete ühendamise toimumist, kehtivad need ainult ühendatud kliendiprofiilide kohta. Seega ei värskenda reaalajas profiili muudatused meetmeid, segmendi liikmestaatust ega rikastamist.

### <a name="limitations"></a>Piirangud

- Kliendiprofiile saab värskendada, kuid mitte luua ega kustutada.
- Praegu ei ole võimalik eksportida reaalajas värskendusi välistesse süsteemidesse nagu Power BI.

## <a name="real-time-creation-of-activities"></a>Tegevuste loomine reaalajas

Reaalajas API võimaldab teil avaldada uue tegevuse oma lähtesüsteemist (individuaalne lähtekirje) koondatud kliendiprofiilile. Uus tegevus on saadaval ühendatud tegevusena selles kliendiprofiilis mõne sekundi jooksul. Ajaskaalat saate vaadata kliendikaardi vaates või mõnes muus teie konfigureeritud ajaskaala integratsioonis.

> [!NOTE]
>
> - Tegevused on püsivad. Nad ei muutu pärast loomist.
> - Praegu ei värskendata segmente ega meetmeid uue tegevuse põhjal.
> - Ainult reaalajas API kaudu lisatud tegevused ei kuulu ekspordi hulka ja neid ei kuvata PowerBI-s.

Reaalajas API-ga ühenduse loomiseks on kaks võimalust.

- [kaudselt](#connect-via-the-dynamics-365-customer-insights-connector), kasutades [Dynamics 365 Customer Insightskonnektorit](/connectors/customerinsights/)
- [otse](#connect-directly-to-the-real-time-api), koodiga

Mõlemal viisil on järgmised eeltingimused.

- Customer Insightsi keskkond
- Kliendi koondprofiilid
- Konfigureeritud ja käivitatud tegevused
- Kaasautori või administraatori õigused teie konto autentimiseks

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Ühenduse loomine Dynamics 365 Customer Insights-i konnektori kaudu

Reaalaja API saab alla laadida andmeid spetsiaalsest Power Platform-i konnektorist, [Dynamics 365 Customer Insights-i konnektor](/connectors/customerinsights/), ilma et oleks vaja kirjutada ja kasutada mis tahes koodi.    
Konnektor saab teha samu reaalajalisi toiminguid nagu API. Premium-taseme konnektorite jaoks vajate sobivat litsentsi. Lisateavet vt teemast [Power Apps-i ja Power Automate-i litsentsimise KKK](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps ja/või Power Automate](/connectors/)
- Azure [Logicu rakendused](/azure/connectors/apis-list)

Voogude loomise üksikasjad leiate [Power Automate-i dokumentatsioonist](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Otse reaalajas API-ga ühenduse loomine

Saate kasutada reaalajalisi võimalusi, luues oma konveieri ja ühendudes otse reaalajas API-ga.    
Võite tegevuse postitada oma lähtekoodisüsteemi vormingus või UnifiedActivity vormingus. Vormingu saamiseks tehke API kõne/API/instances/{instanceId}/Manage/Entities/UnifiedActivity.

Selle API üksikasjad, sh parameetrid ja vastused, leiate jaotisest **EntityData**, mis asub artiklis [Customer Insightsi API-de ülevaade](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Lisateavet leiate teemast [Customer Insightsi API-dega töötamine](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Oma reaalajas kasutuse mõistmine telemeetria abil

Teil on võimalik vaadata ülevaadet reaalajas API-le saadetud päringute arvu ja süsteemi võimalike probleemide kohta. Pääsete [ligi reaalajalisele telemeetriale](system.md#api-usage-tab) 


[!INCLUDE [footer-include](includes/footer-banner.md)]
