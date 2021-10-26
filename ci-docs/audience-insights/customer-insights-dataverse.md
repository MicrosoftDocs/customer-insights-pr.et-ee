---
title: Customer Insightsi andmed teenuses Microsoft Dataverse
description: Customer Insights olemite kasutamine Microsoft Dataverse tabelitena.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9855ff6908001dd18bc19a286fc56620d0a127e5
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645213"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Customer Insightsi andmetega töötamine teenuses Microsoft Dataverse

Customer Insights pakub võimalust muuta väljundi olemid kättesaadavaks teenuses [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). See integratsioon võimaldab lihtsat andmete jagamist ja kohandatud arendamist vähese koodiga/koodita. Väljundi olemid on saadaval tabelitena teenuses Dataverse. Need tabelid võimaldavad stsenaariumeid, nagu [automaatsed töövood Power Automate](/power-automate/getting-started), [mudelipõhised rakendused](/powerapps/maker/model-driven-apps/) ja [lõuendirakendused](/powerapps/maker/canvas-apps/) Power Apps kaudu. Saate kasutada andmeid mis tahes muu Dataverse tabelitel põhineva rakenduse jaoks. Praegune juurutus toetab peamiselt otsinguid, kus konkreetse kliendi ID jaoks saab hankida andmeid olemasolevate vaatajaskonna statistiliste üksuste kohta.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Dataverse Customer Insignts keskkonna lisamiseks

**Asutused, kus on olemasolevad Dataverse keskkonnad**

Asutused, mis Dataverse juba kasutavad, saavad [kasutada ühte olemasolevat Dataversekeskkonda](create-environment.md), kui administraator seadistab sihtrühma ülevaated. Andes Dataverse keskkonna URL-i, lisab see uutele publiku ülevaadete keskkonnale. Parima võimaliku toimivuse tagamiseks peavad Customer Insightsi ja Dataverse keskkonnad olema majutatud samas piirkonnas.

**Uus organisatsioon**

Kui loote Customer Insightsi seadistamisel uue organisatsiooni, saate automaatselt uue Dataverse keskkonna.

> [!NOTE]
> Kui teie organisatsioonid kasutavad juba rentnikus teenust Dataverse, on oluline meeles pidada, et [Dataverse keskkonna loomist kontrollib administraator](/power-platform/admin/control-environment-creation.md). Näiteks kui seadistate uut sihtrühma ülevaatekeskkonda oma ettevõttega ja administraator on keelanud proovikeskkondade loomise kõigile peale administraatorite, ei saa te luua uut Dataverse proovikeskkonda.
> 
> Customer Insightsi kaudu loodud Dataverse proovikeskkondades on 3 GB mäluruumi, mida ei arvestata rentniku kogu mäluruumi sisse. Tasulised Dataverse kordustellimused annavad 15 GB andmebaasi mäluruumi ja 20 GB faili mäluruumi.

## <a name="output-entities"></a>Väljundolemid

Mõned sihtrühma ülevaadete väljundolemid on saadaval Dataverse tabelitena. Allolevates jaotistes kirjeldatakse nende tabelite eeldatavat skeemi.

- [Kliendi profiil](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Rikastamine](#enrichment)
- [Prognoos](#prediction)


### <a name="customerprofile"></a>Kliendi profiil

See tabel sisaldab Customer Insightsi ühildatud kliendiprofiili. Ühildatud kliendiprofiili skeem sõltub ühendamisel kasutatavatest olemitest ja atribuutidest. Kliendiprofiili skeem sisaldab tavaliselt atribuutide alamhulka [CustomerProfile Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) mudelist.

### <a name="alternatekey"></a>AlternateKey

Tabel AlternateKey sisaldab olemite võtmeid, mis osalevad ühildamisprotsessis.

|Column  |Tüüp  |Kirjeldus  |
|---------|---------|---------|
|DataSourceName    |String         | Andmeallika nimi. Näiteks: `datasource5`.”        |
|EntityName        | String        | Olemi nimi sihtrühma ülevaadetes. Näiteks: `contact1`.”        |
|AlternateValue (Alternatiivne väärtus)    |String         |Alternatiivne ID, mis on vastendatud kliendi ID-ga. Näide: `cntid_1078`         |
|KeyRing           | Mitmerealine tekstiväli        | JSON-väärtus  </br> Näide: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | String        | Ühildatud kliendiprofiili ID.         |
|AlternateKeyId     | GUID         |  AlternateKeyl deterministlik GUID, mis põhineb msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> Näidis: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

See tabel sisaldab kasutajate tegevusi, mis on saadaval jaotises Customer Insights.

| Column            | Tüüp        | Kirjeldus                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | Kliendiprofiili ID                                                                      |
| ActivityId        | String      | Klienditegevuse sisemine ID (esmane võti)                                       |
| SourceEntityName  | String      | Lähteolemi nimi                                                                |
| SourceActivityId  | String      | Lähteolemi esmane võti                                                       |
| ActivityType      | String      | Semantilise tegevuse tüüp või kohandatud tegevuse nimi                                        |
| ActivityTimeStamp | DATETIME    | Tegevuse ajatempel                                                                      |
| Tiitel             | String      | Tegevuse pealkiri või nimi                                                               |
| Kirjeldus       | String      | Tegevuse kirjeldus                                                                     |
| URL               | String      | Link tegevusele omase välise URL-i juurde                                         |
| SemanticData      | JSON-sõne | Sisaldab tegevusetüübile omaste semantilise vastendusväljade põhiväärtusepaaride loendit |
| RangeIndex        | String      | Unixi ajatempel, mida kasutatakse tegevuse ajaskaala ja efektiivsete vahemikupäringute sorteerimiseks |
| mydynci_unifiedactivityid   | GUID | Klienditegevuse sisemine ID (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

See tabel sisaldab kliendiatribuudipõhiste elementide väljundandmeid.

| Column             | Tüüp             | Kirjeldus                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | String           | Kliendiprofiili ID        |
| Näitajad           | JSON-sõne      | Sisaldab põhiväärtusepaaride loendit antud kliendi nime ja väärtuste mõõtmiseks | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | Kliendiprofiili ID |


### <a name="enrichment"></a>Rikastamine

See tabel sisaldab rikastamise protsessi väljundit.

| Column               | Tüüp             |  Kirjeldus                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | String           | Kliendiprofiili ID                                 |
| EnrichmentProvider   | String           | Rikastamise pakkuja nimi                                  |
| EnrichmentType       | String           | Rikastamise tüüp                                      |
| Väärtused               | JSON-sõne      | Rikastamise protsessiga seotud atribuutide loend |
| msdynci_enrichmentid | GUID             | Deterministlik GUID, mis on loodud msdynci_identifierilt |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prognoos

See tabel sisaldab mudeliprognooside väljundit.

| Column               | Tüüp        | Kirjeldus                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | Kliendiprofiili ID                                  |
| ModelProvider        | String      | Mudeli pakkuja nimi                                      |
| Mudel                | String      | Mudeli nimi                                                |
| Väärtused               | JSON-sõne | Mudeliga seotud atribuutide loend |
| msdynci_predictionid | GUID        | Deterministlik GUID, mis on loodud msdynci_identifierilt | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |
