---
title: Dynamics 365 Customer Insights Audit azure monitoriga
description: Vaadake, kuidas saata logisid Microsoft Azure Monitorile.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
ms.openlocfilehash: d962c359d70a068fcf939b61e340f86de088b419
ms.sourcegitcommit: 0c3c473e0220de9ee3c1f1ee1825de0b3b3663c3
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920865"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Azure Monitori abil edasisaatmine Dynamics 365 Customer Insights (Eelvaade)

Dynamics 365 Customer Insights pakub otsest integreerimist Azure Monitoriga. Azure Monitori ressursilogid võimaldavad teil jälgida ja saata logisid [Azure](https://azure.microsoft.com/services/storage/) Storage'i, [Azure Log Analyticsisse või](/azure/azure-monitor/logs/log-analytics-overview) voogesitada neid [Azure Event Hubsisse](https://azure.microsoft.com/services/event-hubs/).

Customer Insights saadab järgmised sündmuste logid.

- **Auditisündmused**
  - **APIEvent** - võimaldab kasutajaliidese kaudu tehtud muudatuste jälgimist. Dynamics 365 Customer Insights
- **Operatiivsündmused**
  - **WorkflowEvent** – töövoog võimaldab seadistada [andmeallikaid](data-sources.md), [ühendada](data-unification.md) ja [rikastada](enrichment-hub.md) ning lõpuks [eksportida](export-destinations.md) andmeid teistesse süsteemidesse. Kõiki neid samme saab teha individuaalselt (nt käivitada üks eksport) või orkestreerida (nt andmete värskendamine andmeallikatest, mis käivitavad ühendamisprotsessi, mis toob kaasa täiendavad rikastamised ja kui see on tehtud, ekspordivad andmed teise süsteemi). Lisateavet leiate [teemast WorkflowEvent Schema](#workflow-event-schema).
  - **APIEvent** - kõik API kõned klientide eksemplari. Dynamics 365 Customer Insights Lisateavet vt [APIEvent Schema](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Diagnostikasätete häälestamine

### <a name="prerequisites"></a>eeltingimused

Diagnostika konfigureerimiseks Customer Insightsis peavad olema täidetud järgmised eeltingimused.

- Teil on aktiivne [Azure'i tellimus](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Teil on [customer](permissions.md#administrator) Insightsis administraatoriõigused.
- **Azure'i** sihtressursil on roll kaasautori ja **kasutajajuurdepääsu** administraatori rollis. Ressurss võib olla Azure'i salvestusruumikonto, Azure Event Hub või Azure Log Analyticsi tööruum. Lisateavet leiate teemast [Azure'i rolliülesannete lisamine või eemaldamine Azure'i portaali abil](/azure/role-based-access-control/role-assignments-portal).
- [Azure](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) Storage'i, Azure Event Hubi või Azure Log Analyticsi sihtkohanõuded kohtusid.
- Teil on vähemalt **lugeja** roll ressursirühmas, kuhu ressurss kuulub.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnostika häälestamine Azure Monitoriga

1. Valige customer **Insightsis** > **süsteemidiagnostika,** et näha diagnostika sihtkohti, mis on konfigureeritud selle eksemplari.

1. Valige **Lisa sihtkoht**.

   > [!div class="mx-imgBorder"]
   > ![Diagnostika ühendus](media/diagnostics-pane.png "Diagnostika ühendus")

1. Sisestage nimi **väljal Diagnostika sihtkoha** nimi.

1. Valige **azure**'i tellimuse rentnik sihtressursiga ja valige **logi sisse**.

1. Valige **ressursitüüp** (salvestuskonto, sündmuse keskus või logianalüüs).

1. Valige **sihtressursi** tellimus.

1. Valige **sihtressursi jaoks rühm** Ressurss.

1. Valige **ressurss**.

1. Kinnitage **andmete privaatsus- ja** vastavusavaldus.

1. **Sihtressursiga ühenduse loomiseks valige Ühenda** süsteemiga. Logid hakkavad sihtkohas ilmuma 15 minuti pärast, kui API on kasutusel ja tekitab sündmusi.

### <a name="remove-a-destination"></a>Sihtkoha eemaldamine

1. Avage **·** > **süsteemidiagnostika**.

1. Valige loendist diagnostika sihtkoht.

1. Valige **veerus** Toimingud **ikoon** Kustuta.

1. Kinnitage kustutamine logi edasisaatmise peatamiseks. Azure'i tellimuse ressurssi ei kustutata. Saate valida **lingi** veerus Toimingud, et avada valitud ressursi Azure'i portaal ja kustutada see seal.

## <a name="log-categories-and-event-schemas"></a>Logikategooriad ja sündmuste skeemid

Praegu [toetatakse API-sündmusi](apis.md) ja töövoosündmusi ning kehtivad järgmised kategooriad ja skeemid.
Logiskeem järgib [Azure Monitori ühist skeemi](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategooriad

Customer Insights pakub kahte kategooriat.

- **Auditisündmused** : API sündmused teenuse [konfiguratsioonimuudatuste](#api-event-schema) jälgimiseks. `POST|PUT|DELETE|PATCH` Operatsioonid lähevad sellesse kategooriasse.
- **Tegevussündmused** : teenuse kasutamise käigus loodud [API-sündmused](#api-event-schema) või [töövoosündmused.](#workflow-event-schema)  Näiteks `GET` töövoo päringud või täitmissündmused.

## <a name="configuration-on-the-destination-resource"></a>Sihtressursi konfiguratsioon

Ressursitüübi valiku põhjal rakendatakse automaatselt järgmisi juhiseid.

### <a name="storage-account"></a>Salvestusruumi konto

Customer Insightsi teenuse juht saab **valitud** ressursi salvestusruumikonto kaasautori õiguse ja loob valitud nimeruumi all kaks konteinerit.

- `insight-logs-audit`**auditisündmusi sisaldav**
- `insight-logs-operational`**tegevussündmusi sisaldav**

### <a name="event-hub"></a>Sündmuskeskus

Customer Insightsi teenuse juht saab **ressursi azure event hubs andmeomaniku** õiguse ja loob valitud nimeruumi all kaks sündmusekeskust.

- `insight-logs-audit`**auditisündmusi sisaldav**
- `insight-logs-operational`**tegevussündmusi sisaldav**

### <a name="log-analytics"></a>Logianalüütika

Customer Insightsi teenuse juht saab **ressursi** logianalüüsi kaasautori õiguse. Logid on saadaval **jaotises** > **Logitabelite** > **logihaldus valitud** Logianalüüsi tööruumis. Laiendage **logihalduse** lahendust ning leidke `CIEventsAudit` tabelid ja `CIEventsOperational` tabelid.

- `CIEventsAudit`**auditisündmusi sisaldav**
- `CIEventsOperational`**tegevussündmusi sisaldav**

Laiendage **aknas Päringud** **auditilahendust** ja leidke otsinguga esitatud näidispäringud. `CIEvents`

## <a name="event-schemas"></a>Sündmuste skeemid

API sündmustel ja töövoosündmustel on ühine struktuur ja üksikasjad, kus need erinevad, vt [API sündmuste skeemi või](#api-event-schema)[töövoosündmuste skeemi](#workflow-event-schema).

### <a name="api-event-schema"></a>API sündmuste skeem

| Väli             | DataType  | Nõutav/valikuline | Kirjeldus       | Näide        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Üksuse ajatempel | Nõutav          | Sündmuse ajatempl (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Nõutav          | Sündmuse välja paiskanud eksemplari ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Nõutav          | Selle sündmusega esindatud toimingu nimi.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Nõutav          | Sündmuse logikategooria. Kas `Operational` või `Audit`. Kõik POST/PUT/PATCH/DELETE HTTP-taotlused on sildistatud `Audit`, kõik muu`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Nõutav          | Sündmuse olek. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Valikuline          | Sündmuse tulemi olek. Kui toiming vastab REST API kõnele, on see HTTP-oleku kood.        | `200`             |
| `durationMs`      | Pikk      | Valikuline          | Operatsiooni kestus millisekundites.     | `133`     |
| `callerIpAddress` | String    | Valikuline          | Helistaja IP-aadress, kui toiming vastab API-kõnele, mis pärineb avalikult kättesaadavalt IP-aadressilt.                                                 | `144.318.99.233`         |
| `identity`        | String    | Valikuline          | JSON-objekt, mis kirjeldab toimingu teinud kasutaja või rakenduse identiteeti.       | Vaadake [jaotist](#identity-schema) Identiteet.     |  |
| `properties`      | String    | Valikuline          | JSON-objekt, millel on konkreetse sündmuste kategooria jaoks rohkem atribuute.      | Vt [jaotis](#api-properties-schema) Atribuudid.    |
| `level`           | String    | Nõutav          | Sündmuse raskusastme tase.    | `Informational`, `Warning``Error` või `Critical`.           |
| `uri`             | String    | Valikuline          | Absoluutne taotlus URI.    |               |

#### <a name="identity-schema"></a>Identiteediskeem

`identity` JSON-objektil on järgmine struktuur

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
| `Authorization.UserRole`      | Kasutajale või rakendusele määratud roll. Lisateavet leiate teemast [Kasutajaõigused](permissions.md).                                     |
| `Authorization.RequiredRoles` | Operatsiooni tegemiseks vajalikud rollid. `Admin` Rollil on lubatud teha kõiki toiminguid.                                                    |
| `Claims`                      | Kasutaja või rakenduse JSON veebiloa (JWT) nõuded. Nõude atribuudid on organisatsiooni ja konfiguratsiooni lõikes Azure Active Directory erinevad. |

#### <a name="api-properties-schema"></a>API atribuutide skeem

[API](apis.md) sündmustel on järgmised omadused.

| Väli                        | Kirjeldus                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Alati `ApiEvent`, märkides logisündmuse API sündmuseks.                                                                 |
| `properties.userAgent`       | Brauseri agent, kes saadab taotluse või `unknown`.                                                                        |
| `properties.method`          | HTTP meetod:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Taotluse suhteline tee.                                                                                          |
| `properties.origin`          | URI näitab, kust toomine pärineb või `unknown`.                                                                  |
| `properties.operationStatus` | `Success` HTTP olekukoodi < 400 puhul <br> `ClientError` HTTP olekukoodi < 500 puhul <br> `Error` HTTP-oleku >= 500 puhul |
| `properties.tenantId`        | Organisatsiooni ID                                                                                                        |
| `properties.tenantName`      | Organisatsiooni nimi.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Helistaja objektiid.                                                                         |
| `properties.instanceId`      | Klientide ülevaated`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Töövoo sündmuse skeem

Töövoog sisaldab mitut toimingut. [Andmeallikate,](data-sources.md)[ühendage,](data-unification.md)[rikastage](enrichment-hub.md) ja [eksportige](export-destinations.md) andmeid. Kõik need sammud võivad töötada individuaalselt või orkestreerida järgmiste protsessidega. 

#### <a name="operation-types"></a>Toimingu tüübid

| Toimingu tüüp     | Grupp                                     |
| ----------------- | ----------------------------------------- |
| Allaneelamine         | [Andmeallikad](data-sources.md)           |
| DataPreparation   | [Andmeallikad](data-sources.md)           |
| Vastendus               | [Andmete koondamine](data-unification.md)   |
| Vastenda             | [Andmete koondamine](data-unification.md)   |
| Liida             | [Andmete koondamine](data-unification.md)   |
| ProfileStore      | [Kliendi profiilid](customer-profiles.md) |
| Otsige            | [Kliendi profiilid](customer-profiles.md) |
| Tegevus          | [Tegevused](activities.md)                  |
| AttributeMeasures | [Segmendid ja mõõdud](segments.md)      |
| EntityMeasures    | [Segmendid ja mõõdud](segments.md)      |
| Näitajad          | [Segmendid ja mõõdud](segments.md)      |
| Segmendid      | [Segmendid ja mõõdud](segments.md)      |
| Rikastamine        | [Rikastamine](enrichment-hub.md)                                          |
| Ärianalüüs      | [Prognoosid](predictions-overview.md)                                          |
| AiBuilder         | [Prognoosid](predictions-overview.md)                                          |
| Ülevaated          | [Prognoosid](predictions-overview.md)                                          |
| Export            | [Eksportimised](export-destinations.md)                                          |
| ModelManagement   | [Prognoosid](custom-models.md)                                           |
| Seos      | [Andmete koondamine](relationships.md)                                           |

#### <a name="field-description"></a>Välja kirjeldus

| Väli           | DataType  | Nõutav/valikuline | Kirjeldus                                                                                                                                                   | Näide                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Üksuse ajatempel | Nõutav          | Sündmuse ajatempl (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Nõutav          | Sündmuse eraldanud eksemplari ResourceId.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Nõutav          | Selle sündmusega esindatud toimingu nimi. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Vt [viite kohta operatsioonitüübid.](#operation-types) | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Nõutav          | Sündmuse logikategooria. Alati `Operational` töövoosündmuste jaoks                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Nõutav          | Sündmuse olek. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Pikk      | Valikuline          | Operatsiooni kestus millisekundites.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Valikuline          | JSON-objekt, millel on konkreetse sündmuste kategooria jaoks rohkem atribuute.                                                                                        | Alamjaotise [töövoo atribuutide kuvamine](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Nõutav          | Sündmuse raskusastme tase.                                                                                                                                  | `Informational`, `Warning` või `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Töövoo atribuutide skeem

Töövoosündmustel on järgmised atribuudid.

| Väli              | Workflow | Toiming | Kirjeldus            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ja      | Ja  | Alati `WorkflowEvent`, tähistades sündmuse töövoo sündmusena.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ja      | Ja  | Töövoo käivitamise ID. Kõigil töövoo käivitamise töövoo- ja ülesandesündmustel on samad `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ja      | Ja  | Toimingu ID vt [Operatsioonitüübid]. (#operation tüüpi)                                                                                                                                                                                       |
| `properties.tasksCount`                      | Ja      | No   | Ainult töövoog. Töövoo käivitatud ülesannete arv.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ja      | No   | Valikuline. Ainult töövoo sündmused. Azure Active Directory [Töövoo käivitanud kasutaja objektiid](/azure/marketplace/find-tenant-object-id#find-user-object-id) vt ka `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ja      | No   | `full` või `incremental` värskendada.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ja      | No   | `OnDemand` või `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ja      | No   | `Running` või `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ja      | Ja  | UTC ajatempel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ja      | Ja  | UTC ajatempel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ja      | Ja  | UTC ajatempel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ja      | Ja  | Klientide ülevaated`instanceId`                                                                                                                                                                                                                              |  |
| `properties.identifier`                      | No       | Ja  | - Operatsioonitüübi = `Export` puhul on identifikaatoriks ekspordikonfiguratsiooni guid. <br> - Operatsioonitüübi = `Enrichment` puhul on see rikastamise kavand <br> - Operatsioonitüübi `Measures` ja `Segmentation`, identifikaatoriks on olemi nimi. |
| `properties.friendlyName`                    | No       | Ja  | Ekspordi või töödeldava olemi kasutajasõbralik nimi.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ja  | Valikuline. Tõrketeade koos üksikasjadega.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ja  | Valikuline. Ainult operatsioonitüübi `Export` jaoks. Tuvastab ekspordi tüübi. Lisateavet leiate [ekspordisihtkohtade ülevaatest](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ja  | Valikuline. Ainult operatsioonitüübi `Export` jaoks. Sisaldab ekspordis konfigureeritud olemite loendit.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ja  | Valikuline. Ainult operatsioonitüübi `Export` jaoks. Ekspordi üksikasjalik sõnum.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ja  | Valikuline. Ainult operatsioonitüübi `Segmentation` jaoks. Näitab segmendi liikmete koguarvu.                                                                                                                                                    |
