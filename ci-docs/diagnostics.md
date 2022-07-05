---
title: Edasisaatmine Dynamics 365 Customer Insights Azure Monitoriga (eelvaade)
description: Vaadake, kuidas logisid monitorile Microsoft Azure saata.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8c72df7054a682244215bbee54968d6aef4bbf59
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052648"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Edasisaatmine Dynamics 365 Customer Insights Azure Monitoriga (eelvaade)

Dynamics 365 Customer Insights pakub otsest integratsiooni Azure Monitoriga. Azure Monitori ressursilogid võimaldavad teil jälgida ja saata logisid [Azure Storageisse](https://azure.microsoft.com/services/storage/), [Azure Log Analyticsisse](/azure/azure-monitor/logs/log-analytics-overview) või voogesitada neid [Azure Event Hubsi](https://azure.microsoft.com/services/event-hubs/).

Customer Insights saadab järgmised sündmuste logid.

- **Auditi sündmused**
  - **APIEvent** - võimaldab kasutajaliidese kaudu tehtud muudatuste jälgimist Dynamics 365 Customer Insights.
- **Operatiivsündmused**
  - **WorkflowEvent** – töövoog võimaldab teil seadistada [andmeallikaid](data-sources.md), [ühendada,](data-unification.md) rikastada [ja](enrichment-hub.md) lõpuks [eksportida](export-destinations.md) andmeid teistesse süsteemidesse. Kõiki neid samme saab teha individuaalselt (näiteks käivitada üks eksport). Samuti saab käivitada orkestreeritud (näiteks andmete värskendamine andmeallikatest, mis käivitavad ühendamisprotsessi, mis tõmbab rikastamised ja kui see on tehtud, eksportige andmed teise süsteemi). Lisateavet leiate teemast [WorkflowEvent skeem](#workflow-event-schema).
  - **APIEvent** - kõik API-kõned klientide eksemplarile Dynamics 365 Customer Insights. Lisateavet leiate APIEvent [Skeemist](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Diagnostikasätete häälestamine

### <a name="prerequisites"></a>eeltingimused

Diagnostika konfigureerimiseks Customer Insightsis peavad olema täidetud järgmised eeltingimused.

- Teil on aktiivne [Azure'i tellimus](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- Teil on [Customer Insightsis administraatoriõigused](permissions.md#admin).
- Teil on **Azure'i sihtressursis kaasautori** ja **kasutajajuurdepääsu administraatori** roll. Ressurss võib olla Azure Data Lake Storage konto, Azure Event Hub või Azure Log Analyticsi tööruum. Lisateavet leiate teemast [Azure'i rollimäärangute lisamine või eemaldamine Azure'i portaali](/azure/role-based-access-control/role-assignments-portal) abil. See õigus on vajalik diagnostikasätete konfigureerimisel Customer Insightsis, seda saab pärast edukat seadistamist muuta.
- [Azure Storage'i, Azure Event Hubi või Azure Log Analyticsi sihtkoha nõuded](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) said täidetud.
- Teil on vähemalt **lugeja** roll ressursirühmas, kuhu ressurss kuulub.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Diagnostika häälestamine Azure Monitori abil

1. Selle eksemplari konfigureeritud diagnostikasihtkohtade kuvamiseks valige Customer Insightsis suvand **Süsteemidiagnostika** > **·**.

1. Valige **Lisa sihtkoht**.

   > [!div class="mx-imgBorder"]
   > ![Diagnostika ühendus](media/diagnostics-pane.png "Diagnostika ühendus")

1. Sisestage nimi väljale **Diagnostika sihtkoha nimi**.

1. **Valige sihtkoha ressursiga Azure'i tellimuse rentnik** ja valige **logige sisse**.

1. **Valige ressursi tüüp** (salvestusruumikonto, sündmuste jaotur või logianalüüs).

1. **Valige sihtressursi tellimus**.

1. **Valige sihtressursi jaoks ressursirühm**.

1. **Valige ressurss**.

1. **Kinnitage andmete privaatsus- ja vastavusavaldus**.

1. Sihtressursiga ühenduse loomiseks valige **Ühenda süsteemiga**. Logid hakkavad sihtkohas ilmuma 15 minuti pärast, kui API on kasutusel ja genereerib sündmusi.

### <a name="remove-a-destination"></a>Sihtkoha eemaldamine

1. **Avage süsteemidiagnostika** > **·**.

1. Valige loendist diagnostika sihtkoht.

1. Valige **veerus** Toimingud **ikoon Kustuta**.

1. Logi edasisaatmise peatamiseks kinnitage kustutamine. Azure'i tellimuse ressurssi ei kustutata. Saate valida lingi veerus **Toimingud**, et avada valitud ressursi Jaoks Azure'i portaal ja kustutada see seal.

## <a name="log-categories-and-event-schemas"></a>Logi kategooriad ja sündmuse skeemid

Praegu [toetatakse API sündmusi](apis.md) ja töövoosündmusi ning kehtivad järgmised kategooriad ja skeemid.
Logiskeem järgib Azure Monitori [ühist skeemi](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Kategooriad

Customer Insights pakub kahte kategooriat.

- **Auditi sündmused**: [API sündmused](#api-event-schema) teenuse konfiguratsioonimuutuste jälgimiseks. `POST|PUT|DELETE|PATCH` operatsioonid lähevad sellesse kategooriasse.
- **Operatiivsündmused**: [teenuse kasutamisel loodud API sündmused](#api-event-schema) või [töövoosündmused](#workflow-event-schema).  Näiteks `GET` töövoo taotlused või täitmissündmused.

## <a name="configuration-on-the-destination-resource"></a>Sihtressursi konfiguratsioon

Ressursitüübi valiku põhjal rakenduvad automaatselt järgmised juhised.

### <a name="storage-account"></a>Salvestusruumi konto

Customer Insightsi teenusedirektor saab **valitud ressursil salvestuskonto kaasautori** õiguse ja loob valitud nimeruumi all kaks konteinerit.

- `insight-logs-audit` auditisündmusi **sisaldav**
- `insight-logs-operational` tegevussündmusi **sisaldav**

### <a name="event-hub"></a>Sündmuskeskus

Customer Insightsi teenusedirektor saab **ressursile Azure Event Hubsi andmeomaniku** õiguse ja loob valitud nimeruumi all kaks event hubi.

- `insight-logs-audit` auditisündmusi **sisaldav**
- `insight-logs-operational` tegevussündmusi **sisaldav**

### <a name="log-analytics"></a>Logi analüütika

Customer Insightsi teenuse direktor saab **ressursi logianalüüsi kaasautori** loa. Logid on saadaval valitud Logianalüüsi tööruumi jaotises **Logitabelite** > **·** > **logihaldus**. Laiendage **logihalduse** lahendust ja `CIEventsAudit` leidke tabelid ja `CIEventsOperational` tabelid.

- `CIEventsAudit` auditisündmusi **sisaldav**
- `CIEventsOperational` tegevussündmusi **sisaldav**

Laiendage aknas **Päringud** lahendust Auditeerimine **ja leidke otsingu otsimisel** esitatud näidispäringud .`CIEvents`

## <a name="event-schemas"></a>Sündmuse skeemid

API sündmustel ja töövoosündmustel on ühine struktuur ja üksikasjad, kus need erinevad, vt [API sündmuse skeem](#api-event-schema) või [töövoosündmuse](#workflow-event-schema) skeem.

### <a name="api-event-schema"></a>API sündmuse skeem

| Väli             | DataType  | Nõutav/valikuline | Kirjeldus       | Näide        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Üksuse ajatempel | Nõutav          | Sündmuse ajatempel (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Nõutav          | Sündmuse õhku paisanud eksemplari ResourceId         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Nõutav          | Selle sündmusega esindatud toimingu nimi.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Nõutav          | Sündmuse logikategooria. Kas `Operational` või `Audit`. Kõik POST/PUT/PATCH/DELETE HTTP-taotlused on sildistatud rakendusega `Audit`, kõik muu on`Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Nõutav          | Sündmuse olek. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Valikuline          | Sündmuse tulemi olek. Kui toiming vastab REST API kõnele, on see HTTP oleku tähis.        | `200`             |
| `durationMs`      | Pikk      | Valikuline          | Operatsiooni kestus millisekundites.     | `133`     |
| `callerIpAddress` | String    | Valikuline          | Helistaja IP-aadress, kui toiming vastab API-kõnele, mis pärineb avalikult kättesaadavalt IP-aadressilt.                                                 | `144.318.99.233`         |
| `identity`        | String    | Valikuline          | JSON objekt, mis kirjeldab toimingu teinud kasutaja või rakenduse identiteeti.       | Vt [jaotis Identiteet](#identity-schema).     |  
| `properties`      | String    | Valikuline          | JSON-objekt, millel on konkreetsele sündmuste kategooriale rohkem atribuute.      | Vt [jaotis Atribuudid](#api-properties-schema).    |
| `level`           | String    | Nõutav          | Sündmuse raskusaste.    | `Informational`, `Warning`, või `Error``Critical`.           |
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
| `Claims`                      | Kasutaja või rakenduse JSON veebiloa (JWT) nõuded. Nõude atribuudid varieeruvad organisatsiooni ja Azure Active Directory konfiguratsiooni lõikes. |

#### <a name="api-properties-schema"></a>API atribuutide skeem

[API sündmustel](apis.md) on järgmised atribuudid.

| Väli                        | Kirjeldus                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Alati `ApiEvent`, märkides logisündmuse API sündmuseks.                                                                 |
| `properties.userAgent`       | Brauseri agent, kes saadab taotluse või `unknown`.                                                                        |
| `properties.method`          | HTTP meetod:`GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Taotluse suhteline tee.                                                                                          |
| `properties.origin`          | URI näitab, kust toomine pärineb või `unknown`.                                                                  |
| `properties.operationStatus` | `Success` HTTP olekukoodi < 400 puhul <br> `ClientError` HTTP olekukoodi < 500 puhul <br> `Error` HTTP olek > = 500 puhul |
| `properties.tenantId`        | Organisatsiooni ID                                                                                                        |
| `properties.tenantName`      | Organisatsiooni nimi.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory Helistaja ObjectId.                                                                         |
| `properties.instanceId`      | Customer Insights`instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>Töövoo sündmuse skeem

Töövoog sisaldab mitut toimingut. [Andmeallikate](data-sources.md) allaneelamine, [andmete ühendamine](data-unification.md), [rikastamine](enrichment-hub.md) ja [eksportimine](export-destinations.md). Kõik need sammud võivad kulgeda individuaalselt või orkestreerida järgmiste protsessidega.

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
| Atribuudi mõõturid | [Segmendid ja mõõdud](segments.md)      |
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
| `time`          | Üksuse ajatempel | Nõutav          | Sündmuse ajatempel (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Nõutav          | Sündmuse välja paisanud eksemplari ResourceId.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Nõutav          | Selle sündmusega esindatud toimingu nimi. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Viite kohta vt [toimingutüübid](#operation-types). | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Nõutav          | Sündmuse logikategooria. Töövoosündmuste jaoks alati`Operational`                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | Nõutav          | Sündmuse olek. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Pikk      | Valikuline          | Operatsiooni kestus millisekundites.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Valikuline          | JSON-objekt, millel on konkreetsele sündmuste kategooriale rohkem atribuute.                                                                                        | Alamjaotise [Töövoo atribuutide kuvamine](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Nõutav          | Sündmuse raskusaste.                                                                                                                                  | `Informational`, `Warning` või `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Töövoo atribuutide skeem

Töövoosündmustel on järgmised atribuudid.

| Väli              | Workflow | Toiming | Kirjeldus            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Ja      | Ja  | Alati `WorkflowEvent`, märkides sündmuse töövoosündmuseks.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Ja      | Ja  | Töövoo käivitamise ID. Kõigil töövoo käivitamise töövoo- ja tööülesandesündmustel on sama `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Ja      | Ja  | Toimingu ID vt teemat [Toimingutüübid](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Ja      | No   | Ainult töövoog. Töövoo käivitatavate ülesannete arv.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Ja      | No   | Valikuline. Ainult töövoo sündmused. Töövoo Azure Active Directory [käivitanud kasutaja](/azure/marketplace/find-tenant-object-id#find-user-object-id) objectId vt ka `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Ja      | No   | `full` või `incremental` värskendada.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Ja      | No   | `OnDemand` või `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Ja      | No   | `Running` või `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Ja      | Ja  | UTC ajatempel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Ja      | Ja  | UTC ajatempel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Ja      | Ja  | UTC ajatempel`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Ja      | Ja  | Customer Insights`instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Ja  | - OperationType = `Export` puhul on identifikaator ekspordikonfiguratsiooni guid. <br> - OperationType = `Enrichment` jaoks on see rikastamise varjund <br> - – OperationType'i `Measures` ja `Segmentation` rakenduse puhul on identifikaator olemi nimi. |
| `properties.friendlyName`                    | No       | Ja  | Ekspordi või töödeldava olemi kasutajasõbralik nimi.                                                                                                                                                                                           |
| `properties.error`                           | No       | Ja  | Valikuline. Tõrketeade koos üksikasjadega.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Ja  | Valikuline. Ainult Operatsioonitüübi `Export` puhul. Tuvastab ekspordi tüübi. Lisateavet leiate [ekspordisihtkohtade](export-destinations.md) ülevaatest.                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Ja  | Valikuline. Ainult Operatsioonitüübi `Export` puhul. Sisaldab ekspordi konfigureeritud olemite loendit.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Ja  | Valikuline. Ainult Operatsioonitüübi `Export` puhul. Üksikasjalik sõnum ekspordi kohta.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Ja  | Valikuline. Ainult Operatsioonitüübi `Segmentation` puhul. Näitab segmendi liikmete koguarvu.                                                                                                                                                    |
