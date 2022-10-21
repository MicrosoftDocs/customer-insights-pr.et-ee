---
title: Customer Insightsi andmetega töötamine teenuses Microsoft Dataverse
description: Vaadake, kuidas ühendada Customer Insights, ja Microsoft Dataverse mõistke väljundolemeid, mis eksporditakse jaotisse Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671246"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Customer Insightsi andmetega töötamine teenuses Microsoft Dataverse

Customer Insights pakub võimalust muuta väljundi olemid kättesaadavaks teenuses [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). See integratsioon võimaldab hõlpsat andmete jagamist ja kohandatud arendamist madala koodiga / koodita lähenemise kaudu. Väljundolemid [on](#output-entities) keskkonnas saadaval tabelitena Dataverse. Andmeid saate kasutada mis tahes muus tabelitel Dataverse põhinevas rakenduses. Need tabelid võimaldavad selliseid stsenaariume nagu automatiseeritud töövood rakenduste kaudu Power Automate või rakenduste loomine rakendustega Power Apps.

Keskkonnaga Dataverse ühenduse loomine võimaldab teil andmevoogude ja lüüside [abil Power Platform alla neelata](connect-power-query.md#add-data-from-on-premises-data-sources) ka asutusesisene andmeallikatest pärinevaid andmeid.

## <a name="prerequisites"></a>eeltingimused

- Customer Insights ja Dataverse keskkonnad peavad olema majutatud samas piirkonnas.
- Keskkonnas seadistatud Dataverse üldadministraatori roll. Kontrollige, kas see [Dataverse keskkond on seotud](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) teatud turberühmadega, ja veenduge, et teid lisatakse nendesse turberühmadesse.
- Ükski teine Customer Insightsi keskkond pole veel seotud keskkonnaga, mida Dataverse soovite ühendada. Vaadake, kuidas [eemaldada olemasolev ühendus keskkonnaga Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Keskkond, mis Microsoft Dataverse on ühendatud ühe salvestusruumikontoga, kui konfigureerite keskkonna [kasutama oma Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Dataverse Laomahu saamise õigus

Customer Insightsi tellimus annab teile õiguse täiendavale mahule teie organisatsiooni olemasoleva [Dataverse salvestusmahu](/power-platform/admin/capacity-storage) jaoks. Lisatud maht sõltub profiilide arvust, mida teie tellimus kasutab.

**Näide:**

Eeldades, et saate 15 GB andmebaasi salvestusruumi ja 20 GB failisalvestusruumi 100 000 kliendiprofiili kohta. Kui teie tellimus sisaldab 300 000 kliendiprofiili, on teie kogumaht 45 GB (3 × 15 GB) andmebaasi salvestusruumi ja 60 GB failisalvestusruumi (3 × 20 GB). Samamoodi, kui teil on 30K kontoga B-B tellimus, on teie kogu salvestusmaht 45 GB (3 × 15 GB) andmebaasi salvestusruumi ja 60 GB failisalvestusruumi (3 × 20 GB).

Logimaht ei ole teie organisatsiooni jaoks astmeline ja fikseeritud.

Lisateavet üksikasjalike võimsusõiguste kohta leiate jaotisest [Dynamics 365 litsentsimisjuhend](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Keskkonna ühendamine Dataverse Customer Insightsiga

See **Microsoft Dataverse** samm võimaldab teil ühendada Customer Insightsi oma Dataverse keskkonnaga, luues samal ajal [Customer Insightsi keskkonna](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="andmete jagamine Microsoft Dataverse uute keskkondade jaoks automaatselt lubatud.":::

1. Sisestage URL oma Dataverse keskkonda või jätke see tühjaks, et see teie jaoks luua.

   > [!NOTE]
   > Pärast Customer Insightsi ja Dataverse funktsiooni, vahel ühenduse loomist ärge muutke keskkonna organisatsiooni Dataverse nime. URL-is Dataverse kasutatakse organisatsiooni nime ja muudetud nimi katkestab ühenduse Customer Insightsiga.

   [Power Platform Administraatorid saavad määrata, kes saavad luua uue Dataverse keskkonna.](/power-platform/admin/control-environment-creation) Kui proovite seadistada uut Customer Insightsi keskkonda, kuid ei saa seda teha, võib administraator olla keelanud keskkondade Dataverse loomise kõigile peale administraatorite.

1. Kui kasutate oma Data Lake Storage’i kontot, toimige järgmiselt.
   1. Valige Luba **andmete ühiskasutus** rakendusega Dataverse.
   1. Sisestage **õiguste identifikaator**. Õiguse identifikaatori [saamiseks lubage andmete jagamine oma ettevõttega Dataverse Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Andmete ühiskasutuse lubamine oma kasutajaga Dataverse Azure Data Lake Storage (eelvaade)

Veenduge oma kontol [, et kliendistatistika keskkonda seadistaval kasutajal oleks salvestuskontol konteineril Azure Data Lake Storage](own-data-lake-storage.md) vähemalt **Storage Blob Data Readeri**`customerinsights` õigused.

> [!NOTE]
> Andmete jagamine kehtib ainult siis, kui kasutate oma Azure Data Lake Storage kontot. See säte pole saadaval, kui Customer Insightsi keskkond kasutab vaikesalvestusruumi Dataverse.

### <a name="limitations"></a>Piirangud

- Ainult üks-ühele vastendamine organisatsiooni ja Dataverse konto vahel Azure Data Lake Storage. Dataverse Kui organisatsioon on salvestusruumikontoga ühendatud, ei saa ta teise salvestusruumikontoga ühendust luua. See piirang takistab Dataverse mitme salvestusruumi konto asustamist.
- Andmete jagamine ei toimi, kui teie Azure Data Lake Storage kontole juurdepääsuks on vaja Azure’i privaatlingi seadistust, kuna see on tulemüüri taga. Dataverse praegu ei toeta privaatsete lõpp-punktidega ühenduse loomist Private Linki kaudu.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Turberühmade seadistamine ise Azure Data Lake Storage

1. Looge oma Azure’i tellimuses kaks turberühma – üks Readeri **turberühm ja üks** **kaasautori** turberühm ning määrake Microsoft Dataverse teenus mõlema turberühma omanikuks.

1. Hallake nende turberühmade kaudu oma salvestuskontol oleval konteineril `customerinsights` olevat juurdepääsu kontrollloendit (ACL).
   1. Microsoft Dataverse Lisage teenus ja mis tahes Dataverse põhised ärirakendused (nt Dynamics 365 Marketing) **kirjutuskaitstud** õigustega **turberühma Reader**.
   1. Lisage *kaasautorite* turberühma ainult **rakendus** Klientide ülevaated, et anda nii lugemis- kui ka **kirjutamisõigused** profiilide ja ülevaadete kirjutamiseks.

### <a name="set-up-powershell"></a>PowerShelli häälestamine

Seadistage PowerShell PowerShelli skriptide käivitamiseks.

1. Installige PowerShelli [Azure Active Directory uusim versioon Graphi](/powershell/azure/active-directory/install-adv2) jaoks.
   1. Valige arvutis klaviatuuril Windowsi klahv ja otsige **Windows PowerShell** ning valige **Käivita administraatorina**.
   1. Sisestage avanevasse PowerShelli aknasse `Install-Module AzureAD`.

1. Importige kolm moodulit.
   1. Sisestage `Install-Module -Name Az.Accounts` PowerShelli aknas juhised ja järgige neid.
   1. Korrake ja `Install-Module -Name Az.Resources``Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Käivitage PowerShelli skriptid ja hankige loa identifikaator

1. Laadige alla kaks PowerShelli skripti, mida peate käivitama, meie inseneri [GitHubi repost](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: nõuab rentniku administraatori õigusi.
   - `ByolSetup.ps1`: nõuab salvestusruumi bloobiandmete omaniku õigusi salvestuskonto/konteineri tasemel. See skript loob teile õiguse. Pärast skripti edukat käivitamist saab rolliülesande käsitsi eemaldada.

1. Käivitage `CreateSecurityGroups.ps1` Windows PowerShellis, sisestades Azure’i tellimuse ID, mis sisaldab teie .Azure Data Lake Storage Avage redaktoris PowerShelli skript, et vaadata üle lisateave ja rakendatud loogika.

   See skript loob teie Azure’i tellimuses kaks turberühma: ühe lugejarühma ja teise kaasautorite rühmale. Microsoft Dataverse teenus on mõlema turvarühma omanik.

1. Salvestage mõlemad selle skripti loodud turberühma ID väärtused skriptis `ByolSetup.ps1` kasutamiseks.

   > [!NOTE]
   > Turberühma loomise saab rentnikus keelata. Sellisel juhul oleks vaja käsitsi seadistamist ja teie Azure AD administraator peaks lubama [turberühma loomise](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Käivitage `ByolSetup.ps1` Windows PowerShellis, sisestades Azure’i tellimuse ID, mis sisaldab teie Azure Data Lake Storage salvestusruumi konto nime, ressursirühma nime ning lugeja ja kaasautori turberühma ID väärtusi. Avage redaktoris PowerShelli skript, et vaadata üle lisateave ja rakendatud loogika.

   See skript lisab teenusele Microsoft Dataverse ja mis tahes Dataverse põhistele ärirakendustele vajaliku rollipõhise juurdepääsukontrolli. Samuti värskendab see skriptiga `customerinsights` loodud turberühmade konteineri juurdepääsu `CreateSecurityGroups.ps1` kontrollloendit (ACL). Kaasautorite rühmale antakse *rwx* luba ja lugejate rühmale ainult *r-x* luba.

1. Kopeerige väljastusstring, mis näeb välja järgmine: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Sisestage kopeeritud väljundstring **keskkonna konfiguratsioonietapi** väljale Õiguste identifikaator Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfiguratsioonivalikud, et lubada andmete jagamist teie enda funktsiooniga Azure Data Lake Storage Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Olemasoleva keskkonnaga ühenduse Dataverse eemaldamine

Keskkonnaga Dataverse ühenduse loomisel tähendab tõrketeade **See CDS-i organisatsioon on juba manustatud teise Customer Insightsi eksemplari**, et Dataverse keskkonda kasutatakse juba Customer Insightsi keskkonnas. Saate olemasoleva ühenduse eemaldada keskkonna üldadministraatorina Dataverse. Muudatuste täitmiseks võib kuluda paar tundi.

1. Avage [Power Apps](https://make.powerapps.com).
1. Valige keskkond keskkonnavalijast.
1. Avage **Lahendused**.
1. Desinstallige või kustutage lahendus nimega **Dynamics 365 Customer Insights Kliendikaardi lisandmoodul (eelvaade)**).

VÕI

1. Avage oma Dataverse keskkond.
1. Avage **Täpsemate sätete** > **lahendused**.
1. Desinstallige **CustomerInsightsCustomerCardi** lahendus.

Kui ühenduse eemaldamine ebaõnnestub sõltuvuste tõttu, peate eemaldama ka sõltuvused. Lisateavet leiate teemast [Sõltuvuste](/power-platform/alm/removing-dependencies) eemaldamine.

## <a name="output-entities"></a>Väljundolemid

Mõned Customer Insightsi väljundolemid on saadaval tabelitena jaotises Dataverse. Allolevates jaotistes kirjeldatakse nende tabelite eeldatavat skeemi.

- [Kliendi profiil](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Rikastamine](#enrichment)
- [Prognoos](#prediction)
- [Segmendi liikmelisus](#segment-membership)

### <a name="customerprofile"></a>Kliendi profiil

See tabel sisaldab Customer Insightsi ühildatud kliendiprofiili. Ühtse kliendiprofiili skeem sõltub andmete ühendamise protsessis kasutatavatest olemitest ja atribuutidest. Kliendiprofiili skeem sisaldab tavaliselt atribuutide alamhulka [CustomerProfile Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) mudelist. Stsenaariumi B-st B-sse puhul sisaldab kliendiprofiil ühtseid kontosid ja skeem sisaldab tavaliselt atribuutide alamhulka konto [ühise andmemudeli definitsioonist](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

ContactProfile sisaldab ühtset teavet kontakti kohta. Kontaktid on [isikud, kes vastendatakse kontoga](data-unification-contacts.md) B-st B-sse stsenaariumis.

| Column                       | Tüüp                | Kirjeldus     |
| ---------------------------- | ------------------- | --------------- |
|  Sünnikuupäev            | DateTime       |  Kontakti sünniaeg               |
|  Linn                 | Tekstsõnum |  Kontaktaadressi linn               |
|  ContactId            | Tekstsõnum |  Kontaktprofiili ID               |
|  ContactProfileId     | Ainuidentifikaator   |  GUID kontakti jaoks               |
|  CountryOrRegion      | Tekstsõnum |  Kontaktaadressi riik/regioon               |
|  CustomerId           | Tekstsõnum |  Selle konto ID, millega kontakt on vastendatud               |
|  EntityName           | Tekstsõnum |  Üksus, kust andmed pärinevad                |
|  FirstName            | Tekstsõnum |  Kontakti eesnimi               |
|  Sugu               | Tekstsõnum |  Kontakti sugu               |
|  ID                   | Tekstsõnum |  Deterministlik GUID, mis põhineb`Identifier`               |
|  identifikaator           | Tekstsõnum |  Kontaktprofiili sisemine ID: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | Tekstsõnum |  Kontakti ametinimetus               |
|  LastName             | Tekstsõnum |  Kontakti perekonnanimi               |
|  PostalCode           | Tekstsõnum |  Kontaktaadressi sihtnumber               |
|  Esmane meiliteenus         | Tekstsõnum |  Kontakti e-posti aadress               |
|  Esmane telefon         | Tekstsõnum |  Kontakti telefoninumber               |
|  Osariik või maakond      | Tekstsõnum |  Kontaktaadressi osariik või provints               |
|  StreetAddress        | Tekstsõnum |  Kontaktaadressi tänav               |

### <a name="alternatekey"></a>AlternateKey

Tabel AlternateKey sisaldab olemite võtmeid, mis osalevad ühildamisprotsessis.

|Column  |Tüüp  |Kirjeldus  |
|---------|---------|---------|
|DataSourceName    |Tekstsõnum         | Andmeallika nimi. Näiteks: `datasource5`.”        |
|EntityName        | Tekstsõnum        | Olemi nimi Customer Insightsis. Näiteks: `contact1`.”        |
|AlternateValue (Alternatiivne väärtus)    |Tekstsõnum         |Alternatiivne ID, mis on vastendatud kliendi ID-ga. Näide: `cntid_1078`         |
|KeyRing           | Tekstsõnum        | JSON-väärtus  </br> Näide: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Tekstsõnum        | Ühildatud kliendiprofiili ID.         |
|AlternateKeyId     | Ainuidentifikaator        |  Alternatiivvõtme deterministlik GUID, mis põhineb`Identifier`      |
|identifikaator |   Tekstsõnum      |   `DataSourceName|EntityName|AlternateValue`  </br> Näidis: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

See tabel sisaldab kasutajate tegevusi, mis on saadaval jaotises Customer Insights.

| Column            | Tüüp        | Kirjeldus                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Tekstsõnum      | Kliendiprofiili ID                                                                      |
| ActivityId        | Tekstsõnum      | Klienditegevuse sisemine ID (esmane võti)                                       |
| SourceEntityName  | Tekstsõnum      | Lähteolemi nimi                                                                |
| SourceActivityId  | Tekstsõnum      | Lähteolemi esmane võti                                                       |
| ActivityType      | Tekstsõnum      | Semantilise tegevuse tüüp või kohandatud tegevuse nimi                                        |
| ActivityTimeStamp | DateTime    | Tegevuse ajatempel                                                                      |
| ametinimetus             | Tekstsõnum      | Tegevuse pealkiri või nimi                                                               |
| Kirjeldus       | Tekstsõnum      | Tegevuse kirjeldus                                                                     |
| URL               | Tekstsõnum      | Link tegevusele omase välise URL-i juurde                                         |
| SemanticData      | Tekstsõnum | Sisaldab tegevusetüübile omaste semantilise vastendusväljade põhiväärtusepaaride loendit |
| RangeIndex        | Tekstsõnum      | Unixi ajatempel, mida kasutatakse tegevuse ajaskaala ja efektiivsete vahemikupäringute sorteerimiseks |
| UnifiedActivityId   | Ainuidentifikaator | Klienditegevuse sisemine ID (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

See tabel sisaldab kliendiatribuudipõhiste elementide väljundandmeid.

| Column             | Tüüp             | Kirjeldus                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Tekstsõnum           | Kliendiprofiili ID        |
| Näitajad           | Tekstsõnum      | Sisaldab põhiväärtusepaaride loendit antud kliendi nime ja väärtuste mõõtmiseks |
| identifikaator | Tekstsõnum           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | Ainuidentifikaator     | Kliendiprofiili ID |

### <a name="enrichment"></a>Rikastamine

See tabel sisaldab rikastamise protsessi väljundit.

| Column               | Tüüp             |  Kirjeldus                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Tekstsõnum           | Kliendiprofiili ID                                 |
| EnrichmentProvider   | Tekstsõnum           | Rikastamise pakkuja nimi                                  |
| EnrichmentType       | Tekstsõnum           | Rikastamise tüüp                                      |
| Väärtused               | Tekstsõnum      | Rikastamise protsessiga seotud atribuutide loend |
| RikastamineId | Ainuidentifikaator            | Deterministlik GUID, mis on loodud`Identifier` |
| identifikaator   | Tekstsõnum           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Prognoos

See tabel sisaldab mudeliprognooside väljundit.

| Column               | Tüüp        | Kirjeldus                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Tekstsõnum      | Kliendiprofiili ID                                  |
| ModelProvider        | Tekstsõnum      | Mudeli pakkuja nimi                                      |
| Mudel                | Tekstsõnum      | Mudeli nimi                                                |
| Väärtused               | Tekstsõnum | Mudeliga seotud atribuutide loend |
| EnnustusId | Ainuidentifikaator       | Deterministlik GUID, mis on loodud`Identifier` |
| identifikaator   | Tekstsõnum      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Segmendi liikmelisus

See tabel sisaldab kliendiprofiilide segmendi liikmelisuse teavet.

| Column        | Tüüp | Kirjeldus                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | Tekstsõnum       | Kliendiprofiili ID        |
| SegmentProvider      | Tekstsõnum       | Rakendus, mis avaldab segmendid.      |
| Segmendi liikmelisuse tüüp | Tekstsõnum       | Selle segmendi liikmesuse kirje kliendi tüüp. Toetab mitut tüüpi, nagu klient, kontakt või konto. Vaikimisi: klient  |
| Segmendid       | Tekstsõnum  | Unikaalsete segmentide loend, mille liige kliendiprofiil on      |
| identifikaator  | Tekstsõnum   | Segmendi liikmesuse kirje kordumatu identifikaator. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | Ainuidentifikaator      | Deterministlik GUID, mis on loodud`Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
