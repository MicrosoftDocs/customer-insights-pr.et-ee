---
title: Customer Insightsi olemiskeemid Common Data Modelis
description: Töötage olemitega Common Data Modelis.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 66d846c3e9404ca7993cae742ea6e16833233fba
ms.sourcegitcommit: 205f931ec671a0ab1850f2c1c94df3307ffb62c9
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/13/2021
ms.locfileid: "7380738"
---
# <a name="entity-schemas-in-common-data-model"></a>Olemi skeemid ühises andmemudelis

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Ühine andmemudel](/common-data-model/) on deklaratiivne määratlus ja standardolemite definitsioon, mis esindavad sageli kasutatavaid kontseptsioone ja tegevusi ettevõtete ja tootmisrakenduste üleselt. Mudelit laiendatakse ka vaatlus-ja analüüsiandmetele. Üldine andmemudel esitab täpselt määratletud, modulaarsed ja laiendatavad äriolemid (nt Konto, Äriüksus, Teenindusjuhtum, Kontakt, Müügivihje, Müügivõimalus ja Toode) ning suhtluse tarnijate, töötajate ja klientidega (nt tegevused ja teeninduse taseme lepingud). Igaüks saab Common Data Modeli määratlusi luua ja laiendada, et hõlmata täiendavaid äripõhiseid ideid.

Jagatud andmemudel muudab rakenduste ja andmete lõimijate koostöö lihtsamaks, tagades ühtse andmemääratluse. Ühine andmemudel sisaldab rikkalikku metaandmete süsteemi standardsete olemite, seoste, hierarhiate, tunnuste ja muuga. See pärineb Dynamics 365 rakendustest ning on GitHubis avaliku allikana, kus on üle 260 standardolemi. Üldise andmemudeli tööstuspõhiseid kontseptsioone täiendab suur sise- ja välispartnerite süsteem.

Tänapäeval rakendavad Common Data Modelit mitmesugused süsteemid ja platvormid, sh Power BI andmevood ja Azure Data Services. See on juba toetatud rakenduses Microsoft Dataverse, Dynamics 365, Power Apps -is, Power BI -is ja eelseisvates Azure'i andmeteenustes, mis lisavad väärtust [Avatud Andmeinitsatiivile](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Customer Insightsi olemi skeemid

Kliendist 360-kraadise vaate loomiseks ja laiendatavuseks Customer Instightsi mudelite üldises andmemudelis kättesaadavaks tegemiseks, oleme avaldanud järgmised olemiskeemid.

| Olem | Kirjeldus |
|---------|---------|
|[Kliendi tegevus](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Kasutaja teostatav tegevus, millel on äri seisukohalt vaatluslik väärtus. |
|[Kliendi profiil](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Isik või organisatsioon, kes teostas äritegevused või kellel on võimalus osaleda äritegevustes. |
|[Mõõdu määratlus](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Null- või rohkemate mõõtmetega eraldatud KPI-de määratlus (nt igakuised aktiivsed kasutajad, kliendi kogukulutus, keskmise kliendi soetamishind) |
|[Segment](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Määratleb ühiste tunnustega liikmete rühma. |
|[Segmendi liikmesus](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Konkreetses segmendis osalevad liikmed. |

Lisateabe saamiseks vt teemat [Customer Insightsi olemi skeemid üldises andmemudelis](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview) dokumentatsiooni.

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Olemite kuvamine Common Data Modeli Entity Navigatori kaudu

Olemeid saate vaadata [Common Data Modeli oleminavigaatori kaudu](https://microsoft.github.io/CDM/). Valige jaotisest Insights Application üksus, et saada loend Customer Insights olemite ja nende määratluste kohta.
> [!div class="mx-imgBorder"]
> ![CDMi Entity Navigatoris kuvatakse kliendi tegevuse olem.](media/CDM-entity-navigator.png "CDMi Entity Navigatoris kuvatakse kliendi tegevuse olem")


[!INCLUDE[footer-include](../includes/footer-banner.md)]
