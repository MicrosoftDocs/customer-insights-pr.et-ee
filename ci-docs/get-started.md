---
title: Dynamics 365 Customer Insights-iga alustamine
description: Customer Insightsi ülevaade aitab ressurssidel kiiresti alustada.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1a19d83930d667bdca5301dcc5a3ffa5db6a7bdc
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741128"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights-iga alustamine

Customer Insights aitab teil oma klientidest sügavamalt aru saada. 360-kraadise kliendiülevaate loomiseks ühendage varasemad tehingute, käitumise ja vaatlustega seotud allikad. Neid ülevaateid saate kasutada kliendikesksete kogemuste ja protsesside loomiseks. Koondage ja mõistke kliendiandmeid ning rakendage neid intelligentsete ülevaadete ja tegevuste jaoks.

## <a name="step-1-create-an-environment"></a>1. samm: keskkonna loomine

Alustamiseks tuleb esmalt luua keskkond, kus töötada. Kui teie organisatsioon on juba litsentsi ostnud, lugege teemat [Keskkonna loomine](create-environment.md). Customer Insightsi prooviversiooni alustamiseks lugege teemat [Proovikeskkonna häälestamine](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>2. samm: tutvuge klientide ülevaadetega

Customer Insightsi esmakordsel sisselogimisel saate sätteid konfigureerida ja toodet uurida.

1. [logige Customer Insightsi](https://home.ci.ai.dynamics.com) sisse oma Microsofti Azure Active Directory (AAD) kasutajakonto abil.

1. [Muutke keskkonda](manage-environments.md#switch-environments) demoandmete vaatamiseks ja [Customer Insightsi uurimiseks](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3. samm: andmetega seoste kuvamine, idutamine ja seadistamine

Ühtsed profiilid on aluseks statistika saamiseks ja andmetega tegelemiseks. Saate tuua andmeid erinevatest allikatest ja käivitada andmete ühendamise protsessi ühendatud profiilide ühendamiseks. Saate määrata seosed allaneetud olemite vahel, et lisada profiilidele teavet rikastusfunktsiooni abil.

1. Andmete hankimine, luues andmeallikaid mitmest valikust. [Power Query Valige konnektorite](connect-power-query.md), [ühise andmemudeli kausta](connect-common-data-model.md) või [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

1. Käivitage [andmete ühendamise protsess](data-unification.md), tuvastades [lähteväljad](map-entities.md), eemaldades [duplikaadid](remove-duplicates.md), [sobitades tingimused](match-entities.md) ja [ühendades väljad](merge-entities.md).

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

1. Vaadake üle integratsioonisuvandid (nt muudesse Dynamics 365 rakendustesse kliendikaardi [lisandmooduliga](customer-card-add-in.md)).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
