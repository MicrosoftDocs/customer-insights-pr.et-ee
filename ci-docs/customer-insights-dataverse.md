---
title: Customer Insightsi andmetega töötamine teenuses Microsoft Dataverse
description: Siit saate teada, kuidas ühendada Customer Insightsi ja Microsoft Dataverse mõista väljundolemeid, mis eksporditakse rakendusse Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 252723b8c174cb1ec488388c26fd2a1d398e9002
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011515"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Customer Insightsi andmetega töötamine teenuses Microsoft Dataverse

Customer Insights pakub võimalust teha väljundolemid kättesaadavaks rakendusena [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). See integratsioon võimaldab hõlpsat andmete jagamist ja kohandatud arendamist madala koodi / koodita lähenemisviisi kaudu. Väljundolemid [on](#output-entities) keskkonnas tabelitena Dataverse saadaval. Andmeid saate kasutada mis tahes muu rakenduse kohta tabelite põhjal Dataverse. Need tabelid lubavad stsenaariume, nagu automatiseeritud töövood rakenduse kaudu Power Automate või rakenduste loomine rakenduses Power Apps.

Dataverse Keskkonnaga ühenduse loomine võimaldab teil andmevoogude ja lüüside abil [alla neelata Power Platform andmeid ka asutusesisene andmeallikatest](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>eeltingimused

- Customer Insightsi ja Dataverse keskkondi tuleb majutada samas piirkonnas.
- Teil peab olema keskkonnas üldadministraatori Dataverse roll. Veenduge, kas see [Dataverse keskkond on seotud](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) teatud turberühmadega, ja veenduge, et teid lisatakse nendesse turberühmadesse.
- Ükski teine Customer Insightsi keskkond pole juba seotud keskkonnaga, Dataverse mida soovite ühendada. Siit saate teada, [kuidas olemasolevat ühendust keskkonnaga Dataverse](#remove-an-existing-connection-to-a-dataverse-environment) eemaldada.
- Keskkond Microsoft Dataverse saab ühenduse luua ainult ühe salvestusruumikontoga. See kehtib ainult siis, kui konfigureerite keskkonna [oma Azure Data Lake Storage](own-data-lake-storage.md) rakenduse kasutamiseks.

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Dataverse Keskkonna ühendamine Customer Insightsiga

See **Microsoft Dataverse** samm võimaldab teil customer insightsi keskkonnaga ühendada, Dataverse luues samal ajal [Customer Insightsi keskkonna](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="andmete jagamine Microsoft Dataverse automaatselt lubatud uute netokeskkondade jaoks.":::

Administraatorid saavad konfigureerida Customer Insightsi olemasoleva Dataverse keskkonna ühendamiseks. Pakkudes URL-i Dataverse keskkonnale, on see seotud nende uue Customer Insightsi keskkonnaga.

Kui te ei soovi olemasolevat Dataverse keskkonda kasutada, loob süsteem rentniku Customer Insightsi andmete jaoks uue keskkonna. [Power Platform administraatorid saavad määrata, kes saab keskkondi](/power-platform/admin/control-environment-creation) luua. Kui häälestate uut Customer Insightsi keskkonda ja administraator on keelanud keskkondade Dataverse loomise kõigile peale administraatorite, ei pruugi teil olla võimalik uut keskkonda luua.

**Andmete ühiskasutuse** lubamine, Dataverse märkides ruut Andmejagamine.

Kui kasutate oma data lake storage kontot, vajate **ka õiguste identifikaatorit**. Lisateavet õiguse identifikaatori hankimise kohta leiate järgmisest jaotisest.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Andmete ühiskasutuse lubamine enda oma Dataverse kaudu Azure Data Lake Storage (Eelvaade)

Andmete jagamise lubamine, Microsoft Dataverse kui teie keskkond [kasutab teie enda Azure Data Lake Storage kontot](own-data-lake-storage.md), vajab täiendavat konfiguratsiooni. Customer Insightsi keskkonda seadistaval kasutajal **peavad kontol olema vähemalt** salvestusriba andmelugeja *õigused customerInsightsi* ümbrises Azure Data Lake Storage.

1. Looge Azure'i tellimusel kaks turberühma – üks **Readeri** turberühm ja üks **kaasautori** turberühm ning Microsoft Dataverse määrake teenus mõlema turberühma omanikuks.
2. Hallake nende turberühmade kaudu oma salvestusruumikonto konteineri CustomerInsights pääsukontrolli loendit (ACL). Microsoft Dataverse Lisage teenus ja kõik Dataverse põhinevad ärirakendused (nt Dynamics 365 Marketing) **kirjutuskaitstud** õigustega **turberühma Reader**. Lisage *kaasautori* turberühma ainult **rakendus** Customer Insights, et anda profiilide ja ülevaadete kirjutamiseks nii lugemis- kui ka **kirjutamisõigused**.

### <a name="limitations"></a>Piirangud

Oma Dataverse kontoga kasutamisel Azure Data Lake Storage on kaks piirangut:

- Organisatsiooni ja Dataverse konto vahel Azure Data Lake Storage on üks-ühele vastendus. Dataverse Kui organisatsioon on ühendatud salvestusruumikontoga, ei saa ta mõne muu salvestuskontoga ühendust luua. See piirang takistab, et a Dataverse ei asustada mitut salvestusruumikontot.
- Andmete jagamine ei toimi, kui teie Azure Data Lake Storage kontole juurdepääsuks on vaja Azure Private Linki häälestust, kuna see on tulemüüri taga. Dataverse praegu ei toeta eralingi kaudu ühendust privaatsete lõpp-punktidega.

### <a name="set-up-powershell"></a>PowerShelli häälestamine

PowerShelli skriptide käivitamiseks peate kõigepealt seadistama PowerShelli vastavalt.

1. Installige PowerShell for Graph [Azure Active Directory uusim](/powershell/azure/active-directory/install-adv2) versioon.
   1. Valige arvutis klaviatuuril Windowsi klahv ja otsige **Windows PowerShell** ning valige **Käivita administraatorina**.
   1. Sisestage avanevasse PowerShelli aknasse `Install-Module AzureAD`.
2. Importige kolm moodulit.
    1. Sisestage `Install-Module -Name Az.Accounts` PowerShelli aknas juhised ja järgige neid.
    1. Korda ja `Install-Module -Name Az.Resources``Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Konfigureerimise sammud

1. Laadige alla kaks PowerShelli skripti, mida peate meie inseneri GitHubi repo-st [käivitama](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Selle PowerShelli skripti käitamiseks on vaja *rentnikuadministraatori* õigusi.
       - See PowerShelli skript loob teie Azure'i tellimusel kaks turberühma. Üks reader rühmale ja teine kaasautorite rühmale ning teenus muutub Microsoft Dataverse mõlema turberühma omanikuks.
       - Käivitage see PowerShelli skript Windows PowerShellis, pakkudes Azure'i tellimuse ID-d, mis sisaldab teie Azure Data Lake Storage. Lisateabe ja rakendatud loogika ülevaatamiseks avage redaktoris PowerShelli skript.
       - Salvestage mõlemad selle skripti loodud turberühma ID väärtused, kuna kasutame neid skriptis `ByolSetup.ps1`.

        > [!NOTE]
        > Turberühma loomise saab rentnikus keelata. Sellisel juhul oleks vaja käsitsi seadistamist ja teie Azure AD administraator peaks lubama [turberühma loomise](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Selle skripti käitamiseks on vaja *salvestusruumi bloobi andmeomaniku* õigusi salvestusruumi konto/konteineri tasemel või see skript loob selle teie jaoks. Pärast skripti edukat käivitamist saab rollimäärangu käsitsi eemaldada.
        - See PowerShelli skript lisab teenuse ja mis tahes Microsoft Dataverse ärirakenduste jaoks Dataverse vajaliku tole-põhise juurdepääsukontrolli (RBAC). Samuti värskendab see skriptiga `CreateSecurityGroups.ps1` loodud turberühmade access control listi (ACL) CustomerInsightsi konteineris. Kaasautorite rühmal on *RWX-i* luba ja lugejate rühmal on *ainult R-x-luba*.
        - Käivitage see PowerShelli skript Windows PowerShellis, pakkudes Azure'i tellimuse ID-d, mis sisaldab teie Azure Data Lake Storage, salvestusruumikonto nime, ressursirühma nime ning readeri ja kaasautori turberühma ID väärtusi. Lisateabe ja rakendatud loogika ülevaatamiseks avage redaktoris PowerShelli skript.
        - Kopeerige väljundstring pärast skripti edukat käivitamist. Väljundstring näeb välja selline: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Sisestage ülalt **kopeeritud väljundstring rakenduse keskkonnakonfiguratsioonietapi väljale Õiguste identifikaator** Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigureerimissuvandid andmete ühiskasutuse lubamiseks rakendusega Azure Data Lake Storage Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Olemasoleva ühenduse eemaldamine keskkonnaga Dataverse

Keskkonnaga Dataverse ühenduse loomisel tähendab tõrketeade **See CDS-organisatsioon on juba seotud mõne muu Customer Insightsi eksemplariga**, et Dataverse keskkonda kasutatakse juba Customer Insightsi keskkonnas. Olemasoleva ühenduse saate eemaldada keskkonna üldadministraatorina Dataverse. Muudatuste elluviimiseks võib kuluda paar tundi.

1. Avage [Power Apps](https://make.powerapps.com).
1. Valige keskkond keskkonnavalijast.
1. Avage **lahendused**
1. Desinstallige või kustutage lahendus nimega **Dynamics 365 Customer Insights Kliendikaardi lisandmoodul (eelvaade)**.

VÕI

1. Avage oma Dataverse keskkond.
1. Avage täpsemate **sätete** > **lahendused**.
1. Desinstallige **CustomerInsightsCustomerCard** lahendus.

Kui ühenduse eemaldamine sõltuvuste tõttu ebaõnnestub, peate eemaldama ka sõltuvused. Lisateavet leiate teemast [Sõltuvuste](/power-platform/alm/removing-dependencies) eemaldamine.

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

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
