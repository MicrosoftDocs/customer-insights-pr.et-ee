---
title: Sihtrühma ülevaadete võimalustega alustamine rakenduses Dynamics 365 Customer Insights
description: Sihtrühma ülevaade aitab ressurssidel kiiresti alustada.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5e8545bc9bf0d953150248fa859c6ca71a12f9cf
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645259"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Dynamics 365 Customer Insights sihtrühma ülevaadete võimalustega alustamine

Sihtrühma ülevaated aitavad teil luua klientidest arusaamist klientidest. 360-kraadise kliendiülevaate loomiseks ühendage varasemad tehingute, käitumise ja vaatlustega seotud allikad. Neid ülevaateid saate kasutada kliendikesksete kogemuste ja protsesside loomiseks. Koondage ja mõistke kliendiandmeid ning rakendage neid intelligentsete ülevaadete ja tegevuste jaoks.

## <a name="step-1-create-an-environment"></a>1. samm: keskkonna loomine

Alustamiseks tuleb esmalt luua keskkond, kus töötada. Kui teie organisatsioon on juba litsentsi ostnud, lugege teemat [Keskkonna loomine](create-environment.md). Sihtrühma ülevaadete prooviversiooni alustamiseks vaadake teemat [Proovikeskkonna seadistamine](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>2. samm: sihtrühma ülevaadete vaatamine

Esmakordsel sihtrühma ülevaatesse sisselogimisel saate konfigureerida sätteid ja tootega tutvuda.

1. [Logige sisse sihtrühma ülevaadetesse](https://home.ci.ai.dynamics.com) oma Microsofti Azure Active Directory (AAD) kasutajakonto abil.

1. [Muutke keskkonda](manage-environments.md#switch-environments), et näha demoandmeid ja [uurida sihtrühma ülevaateid](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3. samm: andmetega seoste kuvamine, idutamine ja seadistamine

Ühtsed profiilid on aluseks statistika saamiseks ja andmetega tegelemiseks. Saate tuua andmeid erinevatest allikatest ja käivitada andmete ühendamise protsessi ühendatud profiilide ühendamiseks. Saate määrata seosed allaneetud olemite vahel, et lisada profiilidele teavet rikastusfunktsiooni abil. 

1. Andmete hankimine, luues andmeallikaid mitmest valikust. Valige [Power Query konnektorite](connect-power-query.md), [ühisandmemudeli kausta](connect-common-data-model.md) või [Microsoft Dataverse](connect-common-data-service-lake.md) vahel. 

1. Käivitage [andmete ühendamise protsess](data-unification.md) läbides [kaardi](map-entities.md), [vastendamise](match-entities.md) ja [ühendamise](merge-entities.md) järgud.

1. Tutvuge [olemitega, mida süsteem loob](entities.md) ja loob [seoseid allaneetud olemite vahel](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>4. samm: ühtse profiilide laiendamine ennustamise, tegevuste ja mõõdikutega

Ühendatud profiilide häälestamise korral saate oma andmeid laiendada ja pakutavat teavet veelgi suurendada.

1. [Kliendiandmete rikastamiseks](enrichment-hub.md) valige rikastamise pakkujate laiendatud teegist.

1. Kasutage [valmismudeleid](predictions-overview.md), et ennustada prognooside tõenäosust või eeldatavaid prognoose.

1. [Tegevuste konfigureerimine](activities.md) allaneetud andmete põhjal ja klientidega suhtlemise visualiseerimine kronoloogiline ajaskaalas. 

1. [Mõõdikute koostamine](measures.md) oma ärieesmärkide ja KPI -de hindamiseks.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>5. samm: segmentide loomine ja andmete aktiveerimine erinevate ekspordisuvandite kaudu

Nüüd, kui teie andmed on täielikud ja sisaldavad laia valikut teavet teie klientide kohta, on aeg otsida võimalusi nende andmetega tegelemiseks. 

1. [Looge segmente](segments.md), kliendibaasi alamsegmente, et tagada tegevuste asjakohane jaotus sihtklientide jaoks.

1. Saate sirvida [ekspordisuvandite](export-destinations.md) laiendamist kataloogis, kus saate kliendi andmeid kasutada. Andmete abil näiteks saate hallata kampaaniaid ja kontakte digitaalturundusega.

1. Vaadake üle integratsioonisuvandid, näiteks [otseühenduse kaudu kaasamisülevaadete](../engagement-insights/integrate-audience-insights-engagement-insights.md) või muude Dynamics 365 rakendustega koos [kliendikaardi lisandmooduliga](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
