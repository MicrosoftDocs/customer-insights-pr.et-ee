---
title: Customer Insightsi olemiskeemid Common Data Modelis
description: Töötage olemitega Common Data Modelis.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2cf01029ef6b64fe566022d09ce65bca3603189c
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643903"
---
# <a name="entity-schemas-in-common-data-model"></a>Olemi skeemid ühises andmemudelis

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Ühine andmemudel](https://docs.microsoft.com/common-data-model/) on deklaratiivne määratlus ja standardolemite definitsioon, mis esindavad sageli kasutatavaid kontseptsioone ja tegevusi ettevõtete ja tootmisrakenduste üleselt. Mudelit laiendatakse ka vaatlus-ja analüüsiandmetele. Üldine andmemudel esitab täpselt määratletud, modulaarsed ja laiendatavad äriolemid (nt Konto, Äriüksus, Teenindusjuhtum, Kontakt, Müügivihje, Müügivõimalus ja Toode) ning suhtluse tarnijate, töötajate ja klientidega (nt tegevused ja teeninduse taseme lepingud). Igaüks saab Common Data Modeli määratlusi luua ja laiendada, et hõlmata täiendavaid äripõhiseid ideid.

Jagatud andmemudel muudab rakenduste ja andmete lõimijate koostöö lihtsamaks, tagades ühtse andmemääratluse. Ühine andmemudel sisaldab rikkalikku metaandmete süsteemi standardsete olemite, seoste, hierarhiate, tunnuste ja muuga. See pärineb Dynamics 365 rakendustest ning on GitHubis avaliku allikana, kus on üle 260 standardolemi. Üldise andmemudeli tööstuspõhiseid kontseptsioone täiendab suur sise- ja välispartnerite süsteem.

Mitmed süsteemid ja platvormid rakendavad praegu üldist andmemudelit, sh Power BI andmevood ja Azure’i andmeteenused. Seda toetavad juba rakendused Common Data Service, Dynamics 365, Power Apps, Power BI ja varsti avaldatav Azure Data Services, panustades seeläbi otseselt [Open Data Initiative'i](https://www.microsoft.com/open-data-initiative) väärtustamisse.

## <a name="customer-insights-entity-schemas"></a>Customer Insightsi olemi skeemid

Kliendist 360-kraadise vaate loomiseks ja laiendatavuseks Customer Instightsi mudelite üldises andmemudelis kättesaadavaks tegemiseks, oleme avaldanud järgmised olemiskeemid.

| Olem | Kirjeldus |
|---------|---------|
|[Kliendi tegevus](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Kasutaja teostatav tegevus, millel on äri seisukohalt vaatluslik väärtus. |
|[Kliendi profiil](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Isik või organisatsioon, kes teostas äritegevused või kellel on võimalus osaleda äritegevustes. |
|[Mõõdu määratlus](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Null- või rohkemate mõõtmetega eraldatud KPI-de määratlus (nt igakuised aktiivsed kasutajad, kliendi kogukulutus, keskmise kliendi soetamishind) |
|[Segment](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Määratleb ühiste tunnustega liikmete rühma. |
|[Segmendi liikmesus](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Konkreetses segmendis osalevad liikmed. |

Lisateabe saamiseks vt teemat [Customer Insightsi olemi skeemid üldises andmemudelis](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview) dokumentatsiooni.

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Olemite kuvamine Common Data Modeli Entity Navigatori kaudu

Olemeid saate vaadata [Common Data Modeli oleminavigaatori kaudu](https://microsoft.github.io/CDM/). Valige **Laadige rakendusest GitHub!** nupp ja liikuge järgmiselt: **foundationCommon** > **crmCommon** > **lahendused** > **customerInsights**, kus leiate Customer Insightsi olemite loetelu ja määratlused.
> [!div class="mx-imgBorder"]
> ![CDMi Entity Navigatoris kuvatakse kliendi tegevuse olem](media/CDM-entity-navigator.png "CDMi Entity Navigatoris kuvatakse kliendi tegevuse olem")
