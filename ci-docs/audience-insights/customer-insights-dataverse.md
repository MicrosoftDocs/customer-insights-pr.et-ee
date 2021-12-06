---
title: Customer Insightsi andmed Microsoft Dataverse
description: Customer Insightsi olemite kasutamine tabelitena Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 6f74559b34a95ed976a4e353c2dbabe59e1a8839
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866929"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Customer Insightsi andmetega töötamine Microsoft Dataverse

Customer Insights pakub võimalust teha väljundolemid [Microsoft Dataverse kättesaadavaks](/powerapps/maker/data-platform/data-platform-intro.md). See integratsioon võimaldab lihtsat andmete jagamist ja kohandatud arendamist vähese koodiga/koodita. Väljundolemid on saadaval tabelitena Dataverse. Need tabelid võimaldavad Power Apps kaudu stsenaariume, nagu [automatiseeritud töövood](/power-automate/getting-started)[Power Automate, mudelipõhiste rakenduste](/powerapps/maker/model-driven-apps/) ja [lõuendirakenduste](/powerapps/maker/canvas-apps/) kaudu. Andmeid saate kasutada mis tahes muu rakenduse jaoks, mis põhineb Dataverse tabelitel. Praegune juurutus toetab peamiselt otsinguid, kus konkreetse kliendi ID jaoks saab hankida andmeid olemasolevate vaatajaskonna statistiliste üksuste kohta.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Dataverse keskkonna lisamine Customer Insightsile

**Organisatsioonid, millel on olemasolevad Dataverse keskkonnad**

Organisatsioonid, kes juba kasutavad Dataverse saavad [kasutada mõnda oma olemasolevat Dataverse](create-environment.md) keskkonda, kui administraator häälestab vaatajaskonna ülevaateid. Pakkudes URL-i Dataverse keskkonnale, lisab see nende uue vaatajaskonna ülevaatekeskkonna. Parima võimaliku jõudluse tagamiseks tuleb samas piirkonnas majutada Customer Insightsi ja Dataverse keskkondi.

**Uus organisatsioon**

Kui loote Customer Insightsi seadistamisel uue organisatsiooni, saate automaatselt uue Dataverse keskkonna.

> [!NOTE]
> Kui teie organisatsioonid juba kasutavad oma rentnikus Dataverse, on oluline meeles pidada, et [Dataverse keskkonna loomist kontrollib administraator](/power-platform/admin/control-environment-creation.md) . Näiteks kui häälestate oma organisatsioonikontoga uut vaatajaskonna ülevaatekeskkonda ja administraator on keelanud Dataverse proovikeskkondade loomise kõigile peale administraatorite, ei saa te uut proovikeskkonda luua.
> 
> Customer Insightsis loodud Dataverse proovikeskkondadel on 3 GB salvestusruumi, mida ei arvestata rentnikule õigusega üldise võimsuse hulka. Tasulised tellimused saavad Dataverse andmebaasi jaoks 15 GB ja failisalvestuse jaoks 20 GB.

## <a name="output-entities"></a>Väljundolemid

Mõned vaatajaskonna ülevaate väljundolemid on saadaval tabelitena Dataverse. Allolevates jaotistes kirjeldatakse nende tabelite eeldatavat skeemi.

- [Kliendi profiil](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Rikastamine](#enrichment)
- [Prognoos](#prediction)
- [Segmendi liikmelisus](#segment-membership)


### <a name="customerprofile"></a>Kliendi profiil

See tabel sisaldab Customer Insightsi ühildatud kliendiprofiili. Ühildatud kliendiprofiili skeem sõltub ühendamisel kasutatavatest olemitest ja atribuutidest. Kliendiprofiili skeem sisaldab tavaliselt atribuutide alamhulka [CustomerProfile Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) mudelist.

### <a name="alternatekey"></a>AlternateKey

Tabel AlternateKey sisaldab olemite võtmeid, mis osalevad ühildamisprotsessis.

|Column  |Tüüp  |Kirjeldus  |
|---------|---------|---------|
|DataSourceName    |String         | Andmeallika nimi. Näiteks: `datasource5`.”        |
|EntityName        | String        | Olemi nimi sihtrühma ülevaadetes. Näiteks: `contact1`.”        |
|AlternateValue (Alternatiivne väärtus)    |String         |Alternatiivne ID, mis on vastendatud kliendi ID-ga. Näide: `cntid_1078`         |
|KeyRing           | Mitmerealine tekstiväli        | JSON-väärtus  </br> Näidis: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"võtmed":[" cntid_1078"]}]       |
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

### <a name="segment-membership"></a>Segmendi liikmelisus

See tabel sisaldab kliendiprofiilide segmendi liikmelisuse teavet.

| Column        | Tüüp | Kirjeldus                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Kliendiprofiili ID        |
| SegmentProvider      | String       | Rakendus, mis avaldab segmente. Vaikeülevaated: vaatajaskonna ülevaated         |
| SegmentMembershipType | String       | Selle segmendi liikmesuse kirje kliendi tüüp. Toetab mitut tüüpi, näiteks klient, kontakt või konto. Vaikeväärtus: klient  |
| Segmendid       | JSON-sõne  | Kordumatute segmentide loend, mille liige kliendiprofiil on      |
| msdynci_identifier  | String   | Segmendi liikmesuse kirje ainuidentifikaator. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministlik GUID, mis on loodud`msdynci_identifier`          |
