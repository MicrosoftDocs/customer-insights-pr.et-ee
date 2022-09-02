---
title: OData päringu näited Customer Insightsi API-de jaoks
description: Sageli kasutatavad näited avaandmete protokollist (OData) päringute tegemiseks Customer Insightsi API-dest andmete ülevaatamiseks.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387197"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>OData päringu näited Customer Insightsi API-de jaoks

Avaandmete protokoll (OData) on andmetele juurdepääsu protokoll, mis on ehitatud põhiprotokollidele, nagu HTTP. See kasutab üldtunnustatud metoodikaid, nagu REST veebi jaoks. OData teenuste tarbimiseks saab kasutada mitmesuguseid teeke ja tööriistu.

Selleks et aidata teil Luua oma juurutusi Customer Insightsi API-de [põhjal](apis.md), vaadake üle mõned sageli nõutavad näidispäringud.

Muutke päringunäidiseid, et need töötaksid sihtkeskkondades.

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` kus {instanceId} on selle Customer Insightsi keskkonna GUID, kust soovite päringut teha. Toiming [ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) võimaldab teil leida selle, millele {InstanceId} teil on juurdepääs.
- {CID}: ühtse kliendikirje GUID. Näide: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: kliendikirje primaarvõtme identifikaator andmeallikas. Näide: `CNTID_1002`
- {DSname}: String sellise andmeallikas oleminimega, mis alla neelatakse Customer Insightsi. Näide: `Website_contacts`.
- {SegmentName}: String segmendi väljundolemi nimega Customer Insightsis. Näide: `Male_under_40`.

## <a name="customer"></a>klient

Kliendi *olemi näidispäringud*.

|Päringu tüüp |Näide  | Märkus.  |
|---------|---------|---------|
|Ühe kliendi ID     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|alternatiivvõti    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  Alternatiivvõtmed jäävad ühtses kliendiolemis alles       |
|Valige   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Selle ajaühiku järel:    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|alternatiivvõti + Sisse   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Otsige  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Annab vastuseks otsingustringi 10 parimat tulemit.      |
|Segmendi liikmelisus  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Tagastab segmenteerimisolemi eelseadistatud ridade arvu.      |
|Kliendi liikmelisuse segmentimine | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Tagastab kliendiprofiili, kui ta on antud segmendi liige.     |

## <a name="unified-activity"></a>Ühtne tegevus

Olemi UnifiedActivity *näidispäringud*.

|Päringu tüüp |Näide  | Märkus.  |
|---------|---------|---------|
|CID tegevus     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Loetleb konkreetse kliendiprofiili tegevused |
|Tegevuse ajakava    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Kliendiprofiili tegevused ajalises raamistikus       |
|Tegevuse tüüp    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Tegevus kuvatava nime järgi     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Tegevuste sorteerimine    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Kasvavate või laskuvate tegevuste sortimine       |
|Tegevus laienes segmendi liikmeskonnast  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Muud näited

Teiste olemite näidispäringud.

|Päringu tüüp |Näide  | Märkus.  |
|---------|---------|---------|
|CID meetmed    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|CID rikastatud kaubamärgid    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|CID rikastatud huvid    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Klauslisisene + laiendamine     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>OData päringuid ei toetata

Customer Insights ei toeta järgmisi päringuid.

- `$filter` allaneelatud lähteolemite kohta. Saate käitada ainult $filter päringuid süsteemiolemites, mille Customer Insights loob.
- `$expand` päringust `$search` . Näide: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` alates `$select` , kui valitud on ainult atribuutide alamhulk. Näide: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` rikastatud brändi- või huvisuhted antud kliendi jaoks. Näide: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Päringu prognoos mudeli väljundolemid alternatiivvõti kaudu. Näide: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
