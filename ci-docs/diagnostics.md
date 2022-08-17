---
title: Diagnostikalogide eksportimine (eelvaade)
description: Vaadake, kuidas logisid monitorile Microsoft Azure saata.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245920"
---
# <a name="export-diagnostic-logs-preview"></a>Diagnostikalogide eksportimine (eelvaade)

Logide edasisaatmine Customer Insightsist Azure Monitori abil. Azure Monitori ressursilogid võimaldavad teil jälgida ja saata logisid [Azure Storage’i](https://azure.microsoft.com/services/storage/), [Azure Log Analyticsisse](/azure/azure-monitor/logs/log-analytics-overview) või voogesitada [neid Azure Event Hubsi](https://azure.microsoft.com/services/event-hubs/).

Customer Insights saadab järgmised sündmuselogid.

- **Auditi sündmused**
  - **APIEvent** - võimaldab muudatuste jälgimist kasutajaliidese Dynamics 365 Customer Insights kaudu.
- **Operatiivsed sündmused**
  - **WorkflowEvent** – võimaldab teil seadistada [andmeallikaid](data-sources.md), [ühendada](data-unification.md), [rikastada](enrichment-hub.md) ja [eksportida](export-destinations.md) andmeid teistesse süsteemidesse. Neid samme saab teha individuaalselt (näiteks käivitada üks eksport). Neid saab käivitada ka orkestreeritud kujul (näiteks andmete värskendamine andmeallikatest, mis käivitavad ühendamisprotsessi, mis tõmbab sisse rikastamise ja ekspordib andmed teise süsteemi). Lisateavet leiate [teemast WorkflowEvent Schema](#workflow-event-schema).
  - **APIEvent** - saadab kõik kliendi eksemplari API-kõned aadressile Dynamics 365 Customer Insights. Lisateabe saamiseks vaadake [APIEvent skeemi](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Diagnostikasätete seadistamine

### <a name="prerequisites"></a>eeltingimused

- Aktiivne [Azure’i tellimus](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [Administraatori](permissions.md#admin) õigused Customer Insightsis.
- [Kaasautori ja kasutaja juurdepääsu administraatori roll](/azure/role-based-access-control/role-assignments-portal) Azure’i sihtressursis. Ressurss võib olla Azure Data Lake Storage konto, Azure’i sündmuste keskus või Azure Log Analyticsi tööruum. See õigus on vajalik Diagnostikasätete konfigureerimisel Customer Insightsis, kuid seda saab pärast edukat seadistamist muuta.
- [Azure Storage’i, Azure Event Hubi või Azure Log Analyticsi sihtkohanõuded](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) on täidetud.
- Vähemalt **lugeja** roll ressursirühmas, kuhu ressurss kuulub.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnostika häälestamine Azure Monitori abil

1. Minge Customer Insightsis jaotisse **Haldussüsteem** > **ja** valige **vahekaart Diagnostika**.

1. Valige **Lisa sihtkoht**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="Diagnostika ühendus.":::

1. Sisestage nimi väljale **Diagnostika sihtkoha** nimi.

1. Valige **ressursi tüüp** (salvestusruumikonto, sündmuste keskus või logianalüüs).

1. Valige **sihtressursi jaoks tellimus**, **ressursirühm** ja **ressurss**. Õiguse [ja logiteabe leiate teemast Sihtressursi](#configuration-on-the-destination-resource) konfigureerimine.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Sihtressursiga ühenduse loomiseks valige **Loo ühendus süsteemiga**. Logid hakkavad sihtkohas ilmuma 15 minuti pärast, kui API on kasutusel ja genereerib sündmusi.

## <a name="configuration-on-the-destination-resource"></a>Sihtressursi konfigureerimine

Sõltuvalt teie valitud ressursitüübist toimuvad automaatselt järgmised muudatused.

### <a name="storage-account"></a>Salvestusruumi konto

Customer Insightsi teenindaja saab **valitud ressursile salvestusruumikonto kaasautori** õiguse ja loob valitud nimeruumi alla kaks konteinerit.

- `insight-logs-audit` mis sisaldavad **auditisündmusi**
- `insight-logs-operational` mis sisaldavad **operatiivsündmusi**

### <a name="event-hub"></a>Sündmuskeskus

Customer Insightsi teenusejuht saab **ressursile Azure’i sündmuskeskuste andmete omaniku** õiguse ja loob valitud nimeruumi alla kaks sündmuste keskust:

- `insight-logs-audit` mis sisaldavad **auditisündmusi**
- `insight-logs-operational` mis sisaldavad **operatiivsündmusi**

### <a name="log-analytics"></a>Logi analüütika

Customer Insightsi teenindaja saab **ressursile logianalüüsi kaasautori** õiguse. Logid on saadaval jaotises **Logitabelite** > **·** > **logihaldus** valitud tööruumis Logianalüüs. Laiendage **log management** lahendust ja leidke ja `CIEventsAudit``CIEventsOperational` tabelid.

- `CIEventsAudit` mis sisaldavad **auditisündmusi**
- `CIEventsOperational` mis sisaldavad **operatiivsündmusi**

Laiendage **aknas Päringud** auditilahendust **ja** leidke näidispäringud, mida pakutakse otsides `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>Diagnostika sihtkoha eemaldamine

1. Avage **Haldussüsteem** > **ja** valige **vahekaart Diagnostika**.

1. Valige loendist diagnostika sihtkoht.

   > [!TIP]
   > Sihtkoha eemaldamine peatab logi edasisaatmise, kuid ei kustuta Azure’i tellimuse ressurssi. Ressursi kustutamiseks Azure’is valige veerus Toimingud **link**, et avada valitud ressursi Azure’i portaal ja see sealt kustutada. Seejärel kustutage diagnostika sihtkoht.

1. **Valige** veerus Toimingud **ikoon Kustuta**.

1. Sihtkoha eemaldamiseks ja logi edastamise peatamiseks kinnitage kustutamine.

## <a name="log-categories-and-event-schemas"></a>Logi kategooriad ja sündmuste skeemid

Praegu [toetatakse API-sündmusi](apis.md) ja töövoosündmusi ning rakendatakse järgmisi kategooriaid ja skeeme.
Logiskeem järgib [Azure Monitori ühist skeemi](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategooriad

Customer Insights pakub kahte kategooriat.

- **Auditisündmused**: [API sündmused](#api-event-schema) teenuse konfiguratsioonimuutuste jälgimiseks. `POST|PUT|DELETE|PATCH` toimingud lähevad sellesse kategooriasse.
- **Operatiivsündmused**: [teenuse kasutamise ajal loodud API](#api-event-schema) sündmused või [töövoo sündmused](#workflow-event-schema).  Näiteks `GET` taotlused või töövoo täitmissündmused.

## <a name="event-schemas"></a>Sündmuse skeemid

API sündmustel ja töövoosündmustel on ühine struktuur, kuid mõned erinevused. Lisateavet leiate teemast [API sündmuste skeem](#api-event-schema) või [töövoosündmuse skeem](#workflow-event-schema).

### <a name="api-event-schema"></a>API sündmuste skeem

| Väli             | DataType  | Nõutav/valikuline | Kirjeldus       | Näide        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Üksuse ajatempel | Nõutav          | Sündmuse ajatempel (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Nõutav          | Sündmuse väljastanud eksemplari ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Nõutav          | Selle sündmusega esindatud toimingu nimi.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Nõutav          | Sündmuse logi kategooria. Kas `Operational` või `Audit`. Kõik POST/PUT/PATCH/DELETE HTTP-päringud on sildistatud `Audit`, kõik muu koos`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Nõutav          | Sündmuse staatus. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Valikuline          | Sündmuse tulemuse olek. Kui toiming vastab REST API kõnele, on see HTTP-olekukood.        | `200`             |
| `durationMs`      | Pikk      | Valikuline          | Operatsiooni kestus millisekundites.     | `133`     |
| `callerIpAddress` | String    | Valikuline          | Helistaja IP-aadress, kui toiming vastab API-kõnele, mis pärineb avalikult kättesaadavalt IP-aadressilt.                                                 | `144.318.99.233`         |
| `identity`        | String    | Valikuline          | JSON-objekt, mis kirjeldab toimingu teinud kasutaja või rakenduse identiteeti.       | Vt [jaotist Identiteet](#identity-schema).     |  
| `properties`      | String    | Valikuline          | JSON-objekt, millel on konkreetsele sündmuste kategooriale rohkem atribuute.      | Vt [jaotist Atribuudid](#api-properties-schema).    |
| `level`           | String    | Nõutav          | Sündmuse raskusaste.    | `Informational`, `Warning`, `Error` või `Critical`.           |
| `uri`             | String    | Valikuline          | Absoluutne taotlus URI.    |               |

#### <a name="identity-schema"></a>Identiteedi skeem

JSON-objektil `identity` on järgmine struktuur

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Väli                         | Kirjeldus                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Kasutajale või rakendusele määratud roll. Lisateavet vaadake jaotisest [Kasutajaõigused](permissions.md).                                     |
| `Authorization.RequiredRoles` | Operatsiooni tegemiseks vajalikud rollid. `Admin` roll on lubatud teha kõiki toiminguid.                                                    |
| `Claims`                      | Kasutaja või rakenduse JSON veebimärgi (JWT) nõuded. Nõude atribuudid erinevad olenevalt organisatsioonist ja konfiguratsioonist Azure Active Directory. |

#### <a name="api-properties-schema"></a>API atribuutide skeem

[API sündmustel](apis.md) on järgmised atribuudid.

| Väli                        | Kirjeldus                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Alati `ApiEvent`– logisündmuse api-sündmuseks märkimine.                                                                 |
| `properties.userAgent`       | Brauseri agent, kes saadab päringu või `unknown`.                                                                        |
| `properties.method`          | HTTP meetod:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Taotluse suhteline tee.                                                                                          |
| `properties.origin`          | URI näitab, kust toomine pärineb või `unknown`.                                                                  |
| `properties.operationStatus` | `Success` HTTP olekukoodi < 400 puhul <br> `ClientError` HTTP olekukoodi < 500 puhul <br> `Error` HTTP olek > = 500 |
| `properties.tenantId`        | Organisatsiooni ID                                                                                                        |
| `properties.tenantName`      | Organisatsiooni nimi.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId helistaja.                                                                         |
| `properties.instanceId`      | Klientide ülevaated`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Töövoo sündmuse skeem

Töövoog sisaldab mitut etappi. [Andmeallikate allaneelamine](data-sources.md), [andmete ühendamine](data-unification.md), [rikastamine](enrichment-hub.md) ja [eksportimine](export-destinations.md). Kõiki neid samme saab käivitada individuaalselt või orkestreerida järgmiste protsessidega.

#### <a name="operation-types"></a>Operatsiooni tüübid

| Toimingu tüüp     | Grupp                                     |
| ----------------- | ----------------------------------------- |
| Allaneelamine         | [Andmeallikad](data-sources.md)           |
| Andmete ettevalmistamine   | [Andmeallikad](data-sources.md)           |
| Vastendus               | [Andmete koondamine](data-unification.md)   |
| Vastenda             | [Andmete koondamine](data-unification.md)   |
| Liida             | [Andmete koondamine](data-unification.md)   |
| ProfiilStore      | [Kliendi profiilid](customer-profiles.md) |
| Otsige            | [Kliendi profiilid](customer-profiles.md) |
| Tegevus          | [Tegevused](activities.md)                  |
| AtribuutMõõturid | [Segmendid ja meetmed](segments.md)      |
| Olemimeetmed    | [Segmendid ja meetmed](segments.md)      |
| Näitajad          | [Segmendid ja meetmed](segments.md)      |
| Segmendid      | [Segmendid ja meetmed](segments.md)      |
| Rikastamine        | [Rikastamine](enrichment-hub.md)                                          |
| Ärianalüüs      | [Prognoosid](predictions-overview.md)                                          |
| AiBuilder         | [Prognoosid](predictions-overview.md)                                          |
| Ülevaated          | [Prognoosid](predictions-overview.md)                                          |
| Export            | [Eksportimised](export-destinations.md)                                          |
| Mudeli haldamine   | [Prognoosid](custom-models.md)                                           |
| Seos      | [Andmete koondamine](relationships.md)                                           |

#### <a name="field-description"></a>Välja kirjeldus

| Väli           | DataType  | Nõutav/valikuline | Kirjeldus                                                                                                                                                   | Näide                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Üksuse ajatempel | Nõutav          | Sündmuse ajatempel (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Nõutav          | Sündmuse väljastanud eksemplari ResourceId.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Nõutav          | Selle sündmusega esindatud toimingu nimi. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Lisateavet leiate [teemast Toimingu tüübid](#operation-types). | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Nõutav          | Sündmuse logi kategooria. Alati `Operational` töövoosündmuste jaoks                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Nõutav          | Sündmuse staatus. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Pikk      | Valikuline          | Operatsiooni kestus millisekundites.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Valikuline          | JSON-objekt, millel on konkreetsele sündmuste kategooriale rohkem atribuute.                                                                                        | Vaadake alamjaotise [Töövoo atribuudid](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Nõutav          | Sündmuse raskusaste.                                                                                                                                  | `Informational`, `Warning` või `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>Töövoo atribuutide skeem

Töövoosündmustel on järgmised atribuudid.

| Väli              | Workflow | Toiming | Kirjeldus            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ja      | Ja  | Alati `WorkflowEvent`– sündmuse märkimine töövoosündmuseks.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ja      | Ja  | Töövookäivituse identifikaator. Kõigil töövoo ja ülesande sündmustel töövoo täitmises on sama `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ja      | Ja  | Toimingu identifikaator, vt [Operatsiooni tüübid](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Ja      | No   | Ainult töövoog. Tööülesannete arv, mille töövoog käivitab.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ja      | No   | Valikuline. Ainult töövoo sündmused. Azure Active Directory [Töövoo käivitanud kasutaja](/azure/marketplace/find-tenant-object-id#find-user-object-id) objectId, vt ka `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ja      | No   | `full` või `incremental` värskendage.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ja      | No   | `OnDemand` või `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ja      | No   | `Running` või `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ja      | Ja  | UTC ajatempel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ja      | Ja  | UTC ajatempel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ja      | Ja  | UTC ajatempel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ja      | Ja  | Klientide ülevaated`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Ja  | - OperationType = `Export` puhul on identifikaator ekspordikonfiguratsiooni guid. <br> - OperationType = `Enrichment`, see on rikastumise guid <br> - OperationType `Measures` ja `Segmentation`, identifikaatoriks on üksuse nimi. |
| `properties.friendlyName`                    | No       | Ja  | Ekspordi või töödeldava olemi kasutajasõbralik nimi.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ja  | Valikuline. Tõrketeade koos lisateabega.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ja  | Valikuline. Ainult OperationType’i `Export` jaoks. Tuvastab ekspordi tüübi. Lisateavet leiate [ekspordisihtkohtade](export-destinations.md) ülevaatest.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ja  | Valikuline. Ainult OperationType’i `Export` jaoks. Sisaldab ekspordi konfigureeritud olemite loendit.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ja  | Valikuline. Ainult OperationType’i `Export` jaoks. Üksikasjalik teade ekspordi kohta.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ja  | Valikuline. Ainult OperationType’i `Segmentation` jaoks. Näitab liikmete koguarvu, mis segmendil on.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
