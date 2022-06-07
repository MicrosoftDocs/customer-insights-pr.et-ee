---
title: OData näited API-de jaoks Dynamics 365 Customer Insights
description: Tavaliselt kasutatakse avaandmete protokolli (OData) näiteid Customer Insightsi API-de päringute tegemiseks andmete ülevaatamiseks.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cdadd72bfe4272d8d83d923baaa6fd40d008473b
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808456"
---
# <a name="odata-query-examples"></a>OData päringu näited

Avaandmete protokoll (OData) on andmetele juurdepääsu protokoll, mis põhineb põhiprotokollidel nagu HTTP. See kasutab üldtunnustatud meetodeid, nagu REST veebi jaoks. On erinevaid raamatukogusid ja tööriistu, mida saab kasutada OData teenuste tarbimiseks.

Selles artiklis loetletakse mõned sageli taotletud näidispäringud, mis aitavad teil luua oma juurutusi Customer Insights API-de [põhjal](apis.md).

Peate päringunäidiseid muutma, et need sihtkeskkondades töötaksid. 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` kus {instanceId} on selle Customer Insightsi keskkonna GUID, mida soovite pärida. Operatsioon [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) võimaldab teil leida {InstanceId} juurdepääsu.
- {CID}: Ühtse kliendikirje GUID. Näide: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: kliendikirje esmase võtme identifikaator andmeallikas. Näide: `CNTID_1002`
- {DSname}: String, mille olemi nimi on andmeallikas, mis neelatakse Customer Insightsi. Näide: `Website_contacts`.
- {SegmentName}: String, mille segmendi väljundolemi nimi on Customer Insightsis. Näide: `Male_under_40`.

## <a name="customer"></a>klient

Järgmine tabel sisaldab kliendi *olemi näidispäringute* kogumit.

|Päringu tüüp |Näide  | Märkus.  |
|---------|---------|---------|
|Üksikkliendi ID     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|alternatiivvõti    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternatiivsed võtmed püsivad ühtses kliendiolemis       |
|Valige   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Selle ajaühiku järel:    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Alternatiivvõti + Sisse   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Otsige  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Tagastab otsingustringi 10 parimat tulemust.      |
|Segmendi liikmelisus  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Tagastab segmenteerimisolemi eelseadistatud arvu ridu.      |

## <a name="unified-activity"></a>Ühtne tegevus

Järgmine tabel sisaldab olemi UnifiedActivity *näidispäringute* kogumit.

|Päringu tüüp |Näide  | Märkus.  |
|---------|---------|---------|
|CID tegevus     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Loetleb kindla kliendiprofiili tegevused |
|Tegevuse ajaline raamistik    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Kliendiprofiili tegevused aja jooksul       |
|Tegevuse tüüp    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Tegevus kuvatava nime järgi     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Tegevuse sortimine    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Tõusvate või kahanevate tegevuste sortimine       |
|Tegevus laienes segmendi liikmelisuselt  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Muud näited

Järgmine tabel sisaldab näidispäringute kogumit teiste olemite kohta.

|Päringu tüüp |Näide  | Märkus.  |
|---------|---------|---------|
|CID meetmed    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Rikastatud kaubamärgid CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|CID rikastatud huvid    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Klauslisisene + laiendamine     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>OData päringuid ei toetata

Customer Insights ei toeta järgmisi päringuid.

- `$filter` allaneelatud lähteolemites. $filter päringuid saate käitada ainult Customer Insightsi loodud süsteemiolemites.
- `$expand` Päringust`$search`. Näide: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` alates sellest `$select`, kui valitakse ainult atribuutide alamhulk. Näide: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` rikastatud brändi või huvi sarnasused konkreetse kliendi jaoks. Näide: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Päring prognoos mudeliväljundiolemeid alternatiivvõti kaudu. Näide: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
