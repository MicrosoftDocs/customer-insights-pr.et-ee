---
title: Customer Insightsi andmetega töötamine teenuses Microsoft Dataverse
description: Siit saate teada, kuidas ühendada Customer Insights ja Microsoft Dataverse mõista väljundolemeid, mis eksporditakse Dataverse.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303824"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Customer Insightsi andmetega töötamine teenuses Microsoft Dataverse

Customer Insights pakub võimalust muuta väljundi olemid kättesaadavaks teenuses [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). See integratsioon võimaldab lihtsat andmete jagamist ja kohandatud arendamist madala koodiga / koodivaba lähenemisviisi kaudu. Väljundolemid [on](#output-entities) keskkonnas tabelitena Dataverse saadaval. Andmeid saate kasutada mis tahes muu tabelitel Dataverse põhineva rakenduse jaoks. Need tabelid võimaldavad selliseid stsenaariume nagu automatiseeritud töövood või Power Automate rakenduste loomine Power Apps.

Keskkonnaga Dataverse ühenduse loomine võimaldab teil andmevoogude ja lüüside abil [alla neelata Power Platform ka andmeid asutusesisene andmeallikatest](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>eeltingimused

- Customer Insights ja Dataverse keskkonnad peavad olema majutatud samas piirkonnas.
- Keskkonnas seadistatud üldadministraatori Dataverse roll. Kontrollige, kas see [Dataverse keskkond on seotud](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) teatud turberühmadega, ja veenduge, et oleksite nendesse turberühmadesse lisatud.
- Ühtegi teist Customer Insightsi keskkonda pole veel seostatud keskkonnaga, Dataverse mida soovite ühendada. Vaadake, kuidas [eemaldada olemasolev ühendus keskkonnaga Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Keskkond Microsoft Dataverse, mis on ühendatud ühe salvestusruumikontoga, kui konfigureerite keskkonna [kasutama oma Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse Õigus ladustamisvõimsusele

Customer Insightsi tellimus annab teile õiguse lisavõimsusele teie organisatsiooni olemasoleva [Dataverse salvestusruumi](/power-platform/admin/capacity-storage) jaoks. Lisatud maht sõltub teie tellimuse kasutatavate profiilide arvust.

**Näide:**

Eeldades, et saate 15 GB andmebaasi salvestusruumi ja 20 GB failisalvestusruumi 100 000 kliendiprofiili kohta. Kui teie tellimus sisaldab 300 000 kliendiprofiili, on teie kogu salvestusmaht 45 GB (3 × 15 GB) andmebaasi salvestusruum ja 60 GB failisalvestusruum (3 × 20 GB). Samamoodi, kui teil on 30K kontoga B-B-tellimus, on teie kogu salvestusmaht 45 GB (3 x 15 GB) andmebaasi salvestusruum ja 60 GB failisalvestusruum (3 × 20 GB).

Logi maht ei ole teie organisatsiooni jaoks astmeline ega fikseeritud.

Lisateavet üksikasjalike võimsuse õiguste kohta leiate jaotisest [Dynamics 365 litsentsimisjuhend](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Keskkonna ühendamine Dataverse Customer Insightsiga

See **Microsoft Dataverse** samm võimaldab teil ühendada Customer Insightsi oma Dataverse keskkonnaga, luues samal ajal [Customer Insightsi keskkonna](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="andmete jagamine Microsoft Dataverse uute keskkondade jaoks automaatselt lubatud.":::

1. Sisestage oma Dataverse keskkonna URL või jätke see tühjaks, et see oleks teie jaoks loodud.

   > [!NOTE]
   > Pärast Ühenduse loomist Customer Insightsi ja Dataverse, ärge muutke keskkonna organisatsiooni nime Dataverse. URL-is kasutatakse Dataverse organisatsiooni nime ja muudetud nimi katkestab ühenduse Customer Insightsiga.

   [Power Platform administraatorid saavad määrata, kes saavad luua uusi Dataverse keskkondi](/power-platform/admin/control-environment-creation). Kui proovite häälestada uut Customer Insightsi keskkonda, kuid ei saa seda teha, võib administraator olla keelanud keskkondade Dataverse loomise kõigi jaoks, välja arvatud administraatorid.

1. Kui kasutate oma Data Lake’i salvestusruumi kontot, tehke järgmist.
   1. Valige **Luba andmete ühiskasutus** rakenduses Dataverse.
   1. Sisestage õiguste **identifikaator**. Loa identifikaatori [saamiseks lubage andmete jagamine Dataverse omaenda Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Andmete ühiskasutuse Dataverse lubamine teie omaga Azure Data Lake Storage (eelvaade)

[Azure Data Lake Storage Veenduge oma kontol](own-data-lake-storage.md), et Customer Insightsi keskkonda seadistaval kasutajal on salvestusruumikonto konteineris vähemalt **salvestusruumi bloobi andmelugeja** õigused `customerinsights`.

### <a name="limitations"></a>Piirangud

- Ainult üks-ühele vastendamine organisatsiooni ja Dataverse konto vahel Azure Data Lake Storage. Kui organisatsioon Dataverse on ühendatud salvestusruumikontoga, ei saa ta mõne muu salvestusruumikontoga ühendust luua. See piirang takistab Dataverse mitme salvestuskonto asustamist.
- Andmete ühiskasutus ei toimi, kui teie Azure Data Lake Storage kontole juurdepääsemiseks on vaja Azure Private Linki seadistust, kuna see asub tulemüüri taga. Dataverse praegu ei toeta privaatse lingi kaudu ühendust privaatsete lõpp-punktidega.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Turberühmade ise seadistamine Azure Data Lake Storage

1. Looge oma Azure’i tellimuses kaks turberühma - üks **Readeri** turberühm ja üks **kaasautorite** turberühm ning Microsoft Dataverse määrake teenus mõlema turberühma omanikuks.

1. Hallake nende turberühmade kaudu oma salvestusruumikonto konteineril olevat `customerinsights` juurdepääsukontrolli loendit (Access Control List – ACL).
   1. Microsoft Dataverse Lisage teenus ja kõik Dataverse põhised ärirakendused, nagu Dynamics 365 Marketing, **kirjutuskaitstud** õigustega **turberühma Reader**.
   1. Lisage *kaasautorite* turberühma ainult **rakendus** Customer Insights, et anda profiilide ja statistika kirjutamiseks nii lugemis- kui ka **kirjutamisõigused**.

### <a name="set-up-powershell"></a>PowerShelli seadistamine

Seadistage PowerShell PowerShelli skriptide käivitamiseks.

1. Installige PowerShell for [Azure Active Directory Graphi](/powershell/azure/active-directory/install-adv2) uusim versioon.
   1. Valige arvutis klaviatuuril Windowsi klahv ja otsige **Windows PowerShell** ning valige **Käivita administraatorina**.
   1. Sisestage avanevasse PowerShelli aknasse `Install-Module AzureAD`.

1. Importige kolm moodulit.
   1. Sisestage `Install-Module -Name Az.Accounts` PowerShelli aknas juhised ja järgige neid.
   1. Korrake ja `Install-Module -Name Az.Resources``Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Käivitage PowerShelli skriptid ja hankige õiguse identifikaator

1. Laadige alla kaks PowerShelli skripti, mida peate käivitama meie inseneri GitHubi [repost](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: nõuab rentniku administraatori õigusi.
   - `ByolSetup.ps1`: nõuab salvestusruumi bloobi andmete omaniku õigusi salvestusruumikonto/konteineri tasemel. See skript loob teile õiguse. Teie rollimäärangu saab pärast skripti edukat käivitamist käsitsi eemaldada.

1. Käivitage `CreateSecurityGroups.ps1` Windows PowerShellis, esitades Azure’i tellimuse ID, mis sisaldab teie Azure Data Lake Storage. Lisateabe ja rakendatud loogika ülevaatamiseks avage redaktoris PowerShelli skript.

   See skript loob teie Azure’i tellimuses kaks turberühma: ühe rühma Reader ja teise kaasautorite rühma jaoks. Microsoft Dataverse teenus on mõlema turvagrupi omanik.

1. Salvestage mõlemad selle skripti loodud turberühma ID väärtused skriptis `ByolSetup.ps1` kasutamiseks.

   > [!NOTE]
   > Turberühma loomise saab rentnikus keelata. Sellisel juhul oleks vaja käsitsi seadistamist ja teie Azure AD administraator peaks lubama [turberühma loomise](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Käivitage `ByolSetup.ps1` Windows PowerShell, sisestades Azure’i tellimuse ID, mis sisaldab teie Azure Data Lake Storage salvestusruumikonto nime, ressursirühma nime ning lugeja ja kaasautori turberühma ID väärtusi. Lisateabe ja rakendatud loogika ülevaatamiseks avage redaktoris PowerShelli skript.

   See skript lisab teenusele ja mis tahes Microsoft Dataverse ärirakendustele Dataverse vajaliku rollipõhise juurdepääsu juhtelemendi. Samuti värskendab see skriptiga `customerinsights` loodud turberühmade konteineris olevat `CreateSecurityGroups.ps1` juurdepääsukontrolli loendit (ACL). Kaasautorite rühmale antakse *rwx-luba* ja lugejate rühmale *ainult r-x-luba*.

1. Kopeerige väljundstring, mis näeb välja järgmine: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Sisestage kopeeritud väljundstring **keskkonna konfigureerimise etapi õiguste identifikaatori** väljale Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfiguratsioonisuvandid andmete jagamise lubamiseks teie enda Azure Data Lake Storage Microsoft Dataverse saidil .":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Olemasoleva ühenduse eemaldamine keskkonnaga Dataverse

Keskkonnaga Dataverse ühenduse loomisel tähendab tõrketeade **See CDS-i organisatsioon on juba teise Customer Insightsi eksemplariga** seotud, et Dataverse keskkonda kasutatakse juba Customer Insightsi keskkonnas. Olemasoleva ühenduse saate eemaldada keskkonna üldadministraatorina Dataverse. Muudatuste asustamiseks võib kuluda paar tundi.

1. Avage [Power Apps](https://make.powerapps.com).
1. Valige keskkonnavalijast keskkond.
1. Avage **Lahendused**.
1. Desinstallige või kustutage lahendus nimega **Dynamics 365 Customer Insights Kliendikaardi lisandmoodul (eelvaade)**.

VÕI

1. Avage oma Dataverse keskkond.
1. Avage **täpsemad sätted** > **Lahendused**.
1. Desinstallige **Lahendus CustomerInsightsCustomerCard**.

Kui ühenduse eemaldamine ebaõnnestub sõltuvuste tõttu, peate ka sõltuvused eemaldama. Lisateavet vaadake jaotisest [Sõltuvuste](/power-platform/alm/removing-dependencies) eemaldamine.

## <a name="output-entities"></a>Väljundolemid

Mõned Customer Insightsi väljundolemid on saadaval tabelitena.Dataverse Allolevates jaotistes kirjeldatakse nende tabelite eeldatavat skeemi.

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
|EntityName        | String        | Üksuse nimi Customer Insightsis. Näiteks: `contact1`.”        |
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
| ametinimetus             | String      | Tegevuse pealkiri või nimi                                                               |
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
| SegmentLiikmetüüp | String       | Selle segmendi liikmekirje kliendi tüüp. Toetab mitut tüüpi, näiteks klienti, kontakti või kontot. Vaikimisi: Klient  |
| Segmendid       | JSON-sõne  | Nimekiri unikaalsetest segmentidest, mille liige kliendiprofiil on      |
| msdynci_identifier  | String   | Segmendi liikmekirje kordumatu identifikaator. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | Deterministlik GUID, mis on loodud`msdynci_identifier`          |


[!INCLUDE [footer-include](includes/footer-banner.md)]
