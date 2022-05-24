---
title: Customer Insightsi andmed teenuses Microsoft Dataverse
description: Customer Insights olemite kasutamine Microsoft Dataverse tabelitena.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741360"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Customer Insightsi andmetega töötamine teenuses Microsoft Dataverse

Customer Insights pakub võimalust muuta väljundi olemid kättesaadavaks teenuses [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). See integratsioon võimaldab hõlpsat andmete jagamist ja kohandatud arendamist madala koodi / koodita lähenemisviisi kaudu. Väljundolemid [on](#output-entities) keskkonnas tabelitena Dataverse saadaval. Andmeid saate kasutada mis tahes muu rakenduse kohta tabelite põhjal Dataverse. Need tabelid lubavad stsenaariume, nagu automatiseeritud töövood rakenduse kaudu Power Automate või rakenduste loomine rakenduses Power Apps. Praegune juurutus toetab peamiselt otsinguid, kust saadaolevate Customer Insightsi olemite andmeid saab konkreetse kliendi ID jaoks hankida.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Dataverse Customer Insignts keskkonna lisamiseks

**Olemasolev organisatsioon**

Administraatorid saavad konfigureerida Customer Insightsi kasutama [olemasolevat Dataverse keskkonda](create-environment.md) Customer Insightsi keskkonna loomisel. Pakkudes URL-i Dataverse keskkonnale, on see seotud nende uue Customer Insightsi keskkonnaga. Customer Insightsi ja Dataverse keskkondi tuleb majutada samas piirkonnas. 

Kui te ei soovi olemasolevat Dataverse keskkonda kasutada, loob süsteem rentniku Customer Insightsi andmete jaoks uue keskkonna. 

> [!NOTE]
> Kui teie organisatsioonid juba kasutavad Dataverse oma rentnikus, on oluline meeles pidada, et [Dataverse keskkonna loomist kontrollib administraator](/power-platform/admin/control-environment-creation). Näiteks kui häälestate oma organisatsioonikontoga uut Customer Insightsi keskkonda ja administraator on keelanud proovikeskkondade Dataverse loomise kõigile peale administraatorite, ei saa te uut proovikeskkonda luua.
> 
> Customer Insightsi kaudu loodud Dataverse proovikeskkondades on 3 GB mäluruumi, mida ei arvestata rentniku kogu mäluruumi sisse. Tasulised Dataverse kordustellimused annavad 15 GB andmebaasi mäluruumi ja 20 GB faili mäluruumi.

**Uus organisatsioon**

Kui loote Customer Insightsi häälestamisel uue organisatsiooni, loob süsteem teie asutuses teie jaoks automaatselt uue Dataverse keskkonna.

## <a name="output-entities"></a>Väljundolemid

Mõned Customer Insightsi väljundolemid on rakenduses tabelitena Dataverse saadaval. Allolevates jaotistes kirjeldatakse nende tabelite eeldatavat skeemi.

- [Kliendi profiil](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Rikastamine](#enrichment)
- [Prognoos](#prediction)
- [Segmendi liikmelisus](#segment-membership)


### <a name="customerprofile"></a>Kliendi profiil

See tabel sisaldab Customer Insightsi ühildatud kliendiprofiili. Ühtse kliendiprofiili skeem sõltub andmete ühendamise protsessis kasutatavatest olemitest ja atribuutidest. Kliendiprofiili skeem sisaldab tavaliselt atribuutide alamhulka [CustomerProfile Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) mudelist.

### <a name="alternatekey"></a>AlternateKey

Tabel AlternateKey sisaldab olemite võtmeid, mis osalevad ühildamisprotsessis.

|Column  |Tüüp  |Kirjeldus  |
|---------|---------|---------|
|DataSourceName    |String         | Andmeallika nimi. Näiteks: `datasource5`.”        |
|EntityName        | String        | Olemi nimi Customer Insightsis. Näiteks: `contact1`.”        |
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

### <a name="segment-membership"></a>Segmendi liikmelisus

See tabel sisaldab kliendiprofiilide segmendi liikmelisuse teavet.

| Column        | Tüüp | Kirjeldus                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | Kliendiprofiili ID        |
| SegmentProvider      | String       | Rakendus, mis avaldab segmendid.      |
| SegmentMembershipType | String       | Selle segmendi liikmekirje kliendi tüüp. Toetab mitut tüüpi(nt klient, kontakt või konto). Vaikimisi: klient  |
| Segmendid       | JSON-sõne  | Kordumatute segmentide loend, mille liige kliendiprofiil on      |
| msdynci_identifier  | String   | Segmendi liikmelisuse kirje ainuidentifikaator. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministlik GUID, mis on loodud`msdynci_identifier`          |
