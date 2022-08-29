---
title: Dynamics 365 Customer Insightsi kasutamise alustamine
description: Customer Insightsi ülevaade aitab ressurssidel kiiresti alustada.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: ce0336c4bf853bc81ec01c45410169a63b69eb03
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304606"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Dynamics 365 Customer Insightsi kasutamise alustamine

Customer Insights aitab teil oma kliente sügavamalt mõista. 360-kraadise kliendiülevaate loomiseks ühendage varasemad tehingute, käitumise ja vaatlustega seotud allikad. Neid ülevaateid saate kasutada kliendikesksete kogemuste ja protsesside loomiseks. Koondage ja mõistke kliendiandmeid ning rakendage neid intelligentsete ülevaadete ja tegevuste jaoks.

## <a name="step-1-create-an-environment"></a>1. samm: keskkonna loomine

Esiteks looge keskkond, kus töötada. Kui teie organisatsioon on juba litsentsi ostnud, lugege teemat [Keskkonna loomine](create-environment.md). Customer Insightsi prooviversiooni käivitamise kohta leiate teavet teemast [Proovikeskkonna seadistamine](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>2. toiming: tutvuge Customer Insightsiga

Esimest korda Customer Insightsi sisselogimisel konfigureerige sätted ja uurige toodet.

1. [logige sisse Customer Insightsi](https://home.ci.ai.dynamics.com) oma Microsofti Azure Active Directory (AAD) kasutajakontoga.

1. Muutke keskkonda, et näha demoandmeid ja [uurida Customer Insightsi](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>3. samm: andmetega seoste kuvamine, idutamine ja seadistamine

Ühtsed profiilid on aluseks statistika saamiseks ja andmetega tegelemiseks. Saate tuua andmeid erinevatest allikatest ja käivitada andmete ühendamise protsessi ühendatud profiilide ühendamiseks. Määrake allaneelatud olemite vahelised seosed ja kasutage profiilidele teabe lisamiseks rikastamisfunktsioone.

1. Andmete hankimine, luues andmeallikaid mitmest valikust. [Azure Data Lake Storage Valige, sh Common Data Model](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), või [Microsoft Dataverse](connect-dataverse-managed-lake.md)[Power Query konnektorid](connect-power-query.md).

1. Käivitage [andmete ühendamise protsess](data-unification.md), tuvastades [lähteväljad](map-entities.md), eemaldades [duplikaadid](remove-duplicates.md), [sobitamistingimused](match-entities.md) ja [ühendavad väljad](merge-entities.md).

1. Tutvuge [olemitega, mida süsteem loob](entities.md) ja loob [seoseid allaneetud olemite vahel](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>4. samm: ühtse profiilide laiendamine ennustamise, tegevuste ja mõõdikutega

Kui profiilid on seadistatud ühtselt, täiustage oma andmeid ja suurendage nende pakutavat teavet veelgi.

1. [Kliendiandmete rikastamiseks](enrichment-hub.md) valige rikastamise pakkujate laiendatud teegist.

1. Kasutage [valmismudeleid](predictions-overview.md), et ennustada prognooside tõenäosust või eeldatavaid prognoose.

1. [Tegevuste konfigureerimine](activities.md) allaneetud andmete põhjal ja klientidega suhtlemise visualiseerimine kronoloogiline ajaskaalas.

1. [Mõõdikute koostamine](measures.md) oma ärieesmärkide ja KPI -de hindamiseks.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>5. samm: segmentide loomine ja andmete aktiveerimine erinevate ekspordisuvandite kaudu

Nüüd, kui teie andmed on täielikud ja sisaldavad teie klientide kohta mitmesugust teavet, otsige võimalusi nende andmetega toimingute tegemiseks.

1. [Looge segmente](segments.md), kliendibaasi alamsegmente, et tagada tegevuste asjakohane jaotus sihtklientide jaoks.

1. Saate sirvida [ekspordisuvandite](export-destinations.md) laiendamist kataloogis, kus saate kliendi andmeid kasutada. Andmete abil näiteks saate hallata kampaaniaid ja kontakte digitaalturundusega.

1. Vaadake üle integreerimissuvandid, näiteks teiste Dynamics 365-i rakendustega, millel on [kliendikaardi lisandmoodul](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
