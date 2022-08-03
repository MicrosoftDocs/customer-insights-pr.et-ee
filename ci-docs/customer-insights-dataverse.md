---
title: Customer Insightsi andmetega töötamine teenuses Microsoft Dataverse
description: Siit saate teada, kuidas ühendada Customer Insights ja Microsoft Dataverse mõista väljundolemeid, mis eksporditakse Dataverse.
ms.date: 07/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 89ff629033230de3c6252b6a3a16816d9b3c1287
ms.sourcegitcommit: 85b198de71ff2916fee5500ed7c37c823c889bbb
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/15/2022
ms.locfileid: "9153399"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Customer Insightsi andmetega töötamine teenuses Microsoft Dataverse

Customer Insights pakub võimalust muuta väljundolemid kättesaadavaks kujul [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). See integratsioon võimaldab lihtsat andmete jagamist ja kohandatud arendamist madala koodiga / koodivaba lähenemisviisi kaudu. Väljundolemid [on](#output-entities) keskkonnas tabelitena Dataverse saadaval. Andmeid saate kasutada mis tahes muu tabelitel Dataverse põhineva rakenduse jaoks. Need tabelid võimaldavad selliseid stsenaariume nagu automatiseeritud töövood või Power Automate rakenduste loomine Power Apps.

Keskkonnaga Dataverse ühenduse loomine võimaldab teil andmevoogude ja lüüside abil [alla neelata Power Platform ka andmeid asutusesisene andmeallikatest](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>eeltingimused

- Customer Insights ja Dataverse keskkonnad peavad olema majutatud samas piirkonnas.
- Teil peab olema keskkonnas üldadministraatori Dataverse roll. Kontrollige, kas see [Dataverse keskkond on seotud](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) teatud turberühmadega, ja veenduge, et oleksite nendesse turberühmadesse lisatud.
- Ükski teine Customer Insightsi keskkond pole veel seostatud keskkonnaga, Dataverse mida soovite ühendada. Vaadake, kuidas [eemaldada olemasolev ühendus keskkonnaga Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Keskkond Microsoft Dataverse saab luua ühenduse ainult ühe salvestusruumikontoga. See kehtib ainult siis, kui konfigureerite keskkonna [oma Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse Õigus ladustamisvõimsusele

Customer Insightsi tellimus annab teile õiguse lisavõimsusele teie organisatsiooni olemasoleva [Dataverse salvestusruumi](/power-platform/admin/capacity-storage) jaoks. Lisatud maht sõltub teie tellimuse kasutatavate profiilide arvust.

**Näide:**

Eeldades, et saate 15 GB andmebaasi salvestusruumi ja 20 GB failisalvestusruumi 100 000 kliendiprofiili kohta. Kui teie tellimus sisaldab 300 000 kliendiprofiili, on teie kogu salvestusmaht 45 GB (3 × 15 GB) andmebaasi salvestusruum ja 60 GB failisalvestusruum (3 × 20 GB). Samamoodi, kui teil on 30K kontoga B2B-tellimus, oleks teie kogu salvestusmaht 45 GB (3 x 15 GB) andmebaasi salvestusruum ja 60 GB failisalvestusruum (3 x 20 GB).

Logi maht ei ole teie organisatsiooni jaoks astmeline ega fikseeritud.

Lisateavet üksikasjalike võimsuse õiguste kohta leiate jaotisest [Dynamics 365 litsentsimisjuhend](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Keskkonna ühendamine Dataverse Customer Insightsiga

See **Microsoft Dataverse** samm võimaldab teil ühendada Customer Insightsi oma Dataverse keskkonnaga, luues samal ajal [Customer Insightsi keskkonna](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="andmete jagamine Microsoft Dataverse automaatselt lubatud uutes netikeskkondades.":::

Administraatorid saavad konfigureerida Customer Insightsi olemasoleva Dataverse keskkonna ühendamiseks. Andes keskkonnale URL-i Dataverse, loob see ühenduse nende uue Customer Insightsi keskkonnaga. Pärast Ühenduse loomist Customer Insightsi ja Dataverse, ärge muutke keskkonna organisatsiooni nime Dataverse. URL-is kasutatakse Dataverse organisatsiooni nime ja muudetud nimi katkestab ühenduse Customer Insightsiga.

Kui te ei soovi olemasolevat Dataverse keskkonda kasutada, loob süsteem teie rentniku Customer Insightsi andmete jaoks uue keskkonna. [Power Platform administraatorid saavad määrata, kes saavad keskkondi luua](/power-platform/admin/control-environment-creation). Kui häälestate uut Customer Insightsi keskkonda ja administraator on keelanud keskkondade Dataverse loomise kõigile peale administraatorite, ei pruugi teil olla võimalik uut keskkonda luua.

**Andmete jagamise lubamiseks** Dataverse märkige ruut Andmete jagamine.

Kui kasutate oma Data Lake'i salvestusruumi kontot, on teil vaja **ka õiguste identifikaatorit**. Õiguse IDENTIFIKAATORI hankimise kohta lisateabe saamiseks vaadake järgmist jaotist.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Andmete ühiskasutuse lubamine enda omaga Dataverse Azure Data Lake Storage (eelvaade)

Andmete jagamise Microsoft Dataverse lubamine, kui teie keskkond [kasutab teie enda Azure Data Lake Storage kontot](own-data-lake-storage.md), vajab täiendavat konfigureerimist. Customer Insightsi keskkonda häälestaval kasutajal peavad kontol olevas **CustomerInsightsi konteineris olema vähemalt** salvestusruumi bloobi *andmelugeja* Azure Data Lake Storage õigused.

1. Looge oma Azure'i tellimuses kaks turberühma - üks **Readeri** turberühm ja üks **kaasautorite** turberühm ning Microsoft Dataverse määrake teenus mõlema turberühma omanikuks.
2. Hallake nende turberühmade kaudu oma salvestusruumikontol oleval CustomerInsightsi konteineril olevat juurdepääsukontrolli loendit (ACL). Microsoft Dataverse Lisage teenus ja kõik Dataverse põhised ärirakendused, nagu Dynamics 365 Marketing, **kirjutuskaitstud** õigustega **turberühma Reader**. Lisage *kaasautorite* turberühma ainult **rakendus** Customer Insights, et anda profiilide ja statistika kirjutamiseks nii lugemis- kui ka **kirjutamisõigused**.

### <a name="limitations"></a>Piirangud

Oma Dataverse kontoga kasutamisel Azure Data Lake Storage on kaks piirangut:

- Organisatsiooni ja konto vahel Dataverse toimub üks-ühele kaardistamine Azure Data Lake Storage. Kui organisatsioon Dataverse on ühendatud salvestusruumikontoga, ei saa ta mõne muu salvestusruumikontoga ühendust luua. See piirang takistab seda, et Dataverse a ei asuta mitut salvestusruumikontot.
- Andmete ühiskasutus ei toimi, kui teie Azure Data Lake Storage kontole juurdepääsemiseks on vaja Azure Private Linki seadistust, kuna see asub tulemüüri taga. Dataverse praegu ei toeta privaatse lingi kaudu ühendust privaatsete lõpp-punktidega.

### <a name="set-up-powershell"></a>PowerShelli seadistamine

PowerShelli skriptide käivitamiseks peate kõigepealt vastavalt seadistama PowerShelli.

1. Installige PowerShell for [Azure Active Directory Graphi](/powershell/azure/active-directory/install-adv2) uusim versioon.
   1. Valige arvutis klaviatuuril Windowsi klahv ja otsige **Windows PowerShell** ning valige **Käivita administraatorina**.
   1. Sisestage avanevasse PowerShelli aknasse `Install-Module AzureAD`.
2. Importige kolm moodulit.
    1. Sisestage `Install-Module -Name Az.Accounts` PowerShelli aknas juhised ja järgige neid.
    1. Korrake ja `Install-Module -Name Az.Resources``Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>Konfigureerimise sammud

1. Laadige alla kaks PowerShelli skripti, mida peate käivitama meie inseneri GitHubi [repost](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - Selle PowerShelli skripti käitamiseks on teil vaja *rentniku* administraatori õigusi.
       - See PowerShelli skript loob teie Azure'i tellimuses kaks turberühma. Üks lugejarühmale ja teine kaasautorite rühmale ning teenib Microsoft Dataverse mõlema turberühma omanikuna.
       - Käivitage see PowerShelli skript Windows PowerShellis, esitades Azure'i tellimuse ID, mis sisaldab teie Azure Data Lake Storage. Avage redaktoris PowerShelli skript, et vaadata üle lisateave ja rakendatud loogika.
       - Salvestage mõlemad selle skripti loodud turberühma ID väärtused, kuna kasutame neid skriptis `ByolSetup.ps1`.

        > [!NOTE]
        > Turberühma loomise saab rentnikus keelata. Sellisel juhul oleks vaja käsitsi seadistamist ja teie Azure AD administraator peaks lubama [turberühma loomise](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Selle skripti käitamiseks vajate *salvestusruumi bloobi andmete omaniku* õigusi salvestusruumikonto/konteineri tasemel või see skript loob selle teie jaoks. Teie rollimäärangu saab pärast skripti edukat käivitamist käsitsi eemaldada.
        - See PowerShelli skript lisab teenusele ja mis tahes Microsoft Dataverse põhistele ärirakendustele Dataverse vajaliku rollipõhise juurdepääsukontrolli. Samuti värskendab see skriptiga loodud turberühmade juurdepääsukontrolli loendit (ACL) CustomerInsightsi konteineris `CreateSecurityGroups.ps1`. Kaasautorite rühmal on *rwx* õigus ja lugejate rühmal ainult *r-x* õigus.
        - Käivitage see PowerShelli skript Windows PowerShellis, sisestades Azure'i tellimuse ID, mis sisaldab teie Azure Data Lake Storage salvestusruumikonto nime, ressursirühma nime ning lugeja ja kaasautori turberühma ID väärtusi. Avage redaktoris PowerShelli skript, et vaadata üle lisateave ja rakendatud loogika.
        - Kopeerige väljundstring pärast skripti edukat käivitamist. Väljundstring näeb välja selline: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. Sisestage ülalt **kopeeritud väljundstring keskkonna konfigureerimise etapi õiguste identifikaatori** väljale Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfiguratsioonisuvandid andmete jagamise lubamiseks teie enda Azure Data Lake Storage Microsoft Dataverse saidil .":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Olemasoleva ühenduse eemaldamine keskkonnaga Dataverse

Keskkonnaga Dataverse ühenduse loomisel tähendab tõrketeade **See CDS-i organisatsioon on juba teise Customer Insightsi eksemplariga** seotud, et Dataverse keskkonda kasutatakse juba Customer Insightsi keskkonnas. Olemasoleva ühenduse saate eemaldada keskkonna üldadministraatorina Dataverse. Muudatuste asustamiseks võib kuluda paar tundi.

1. Avage [Power Apps](https://make.powerapps.com).
1. Valige keskkonnavalijast keskkond.
1. Avage **lahendused**
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
| SegmentLiikmetüüp | String       | Kliendi tüüp see segmendi liikmelisuse kirje. Toetab mitut tüüpi, näiteks klienti, kontakti või kontot. Vaikimisi: Klient  |
| Segmendid       | JSON-sõne  | Nimekiri unikaalsetest segmentidest, mille liige kliendiprofiil on      |
| msdynci_identifier  | String   | Segmendi liikmekirje kordumatu identifikaator. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
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
