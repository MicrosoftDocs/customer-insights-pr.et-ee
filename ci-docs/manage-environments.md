---
title: Keskkondade loomine ja haldamine
description: Siit leiate teavet selle kohta, kuidas teenuse kasutamiseks registreeruda ja kuidas keskkondasid hallata.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: fcdb7f073ff73322ff69d0a8684391819a809d00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642784"
---
# <a name="manage-environments"></a>Keskkondade haldamine

## <a name="switch-environments"></a>Vaheta keskkondasid

Keskkondade vahetamiseks valige juhtelement **Keskkond** lehe paremas ülanurgas.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Juhtelemendi kuvatõmmis keskkondade vahetamiseks.":::

Halduskeskused saavad keskkondi [luua](create-environment.md) ja hallata.

## <a name="edit-an-existing-environment"></a>Olemasoleva keskkonna redigeerimine

Saate muuta olemasolevate keskkondade teatud üksikasju.

1.  Valige rakenduse päises valija **Environment** (Keskkond).

2.  Valige ikoon **Edit** (Redigeeri).

3. Väljal **Redigeeri keskkonda** saate keskkonnasätteid värskendada.

Keskkonna sätete kohta leiate lisateavet teemast [Uue keskkonna loomine](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Microsoft Dataverse’iga ühenduse loomine
   
**Microsoft Dataverse** etapp lubab teil Customer Insights'i oma Dataverse keskkonnaga ühendada. 

Pakkuge oma Microsoft Dataverse keskkonda, et jagada andmeid (profiile ja ülevaateid) ärirakendustega, mis põhinevad rakendusel Dataverse(nt Dynamics 365 Marketing või mudelipõhised rakendused Power Apps rakenduses ).

Kui soovite kasutada [karbist välja ennustamise mudeleid](predictions-overview.md#out-of-box-models), siis konfigureerige andmete ühiskasutus rakendusega Dataverse. Võite ka lubada asutusesisestest allikatest pärinevad andmed, pakkudes teie Microsoft Dataverse organisatsiooni hallatava keskkonna URL-i.

Andmejagamise lubamine andmejagamisruudu valimisega Microsoft Dataverse käivitab teie andmeallikate ja kõigi muude protsesside ühekordse täieliku värskendamise.

> [!IMPORTANT]
> 1. Customer Insights ja Dataverse andmete jagamise lubamiseks peab see olema samas piirkonnas.
> 1. Teil peab olema keskkonnas üldadministraatori Dataverse roll. Kontrollige, kas see [Dataverse keskkond on seotud](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) teatud turberühmadega, ja veenduge, et teid lisatakse nendesse turberühmadesse.
> 1. Ükski olemasolev Customer Insightsi keskkond pole selle Dataverse keskkonnaga juba seotud. Siit saate teada, [kuidas olemasolevat ühendust keskkonnaga Dataverse eemaldada](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Konfigureerimissuvandid andmete jagamise lubamiseks Microsoft Dataverse abil.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Andmete ühiskasutuse lubamine enda oma Dataverse kaudu Azure Data Lake Storage (Eelvaade)

Kui teie keskkond on konfigureeritud kasutama enda omasid Azure Data Lake Storage Customer Insightsi andmete salvestamiseks, lubades andmete jagamise vajadustega Microsoft Dataverse mõne lisakonfiguratsiooniga.

1. Looge Azure'i tellimusel kaks turberühma – üks **Readeri** turberühm ja üks **kaasautori** turberühm ning Microsoft Dataverse määrake teenus mõlema turberühma omanikuks.
2. Hallake nende turberühmade kaudu oma salvestusruumikonto konteineri CustomerInsights pääsukontrolli loendit (ACL). Microsoft Dataverse Lisage teenus ja kõik Dataverse põhinevad ärirakendused (nt Dynamics 365 Marketing) **kirjutuskaitstud** õigustega **turberühma Reader**. Lisage *kaasautori* turberühma ainult **rakendus** Customer Insights, et anda profiilide ja ülevaadete kirjutamiseks nii lugemis- kui ka **kirjutamisõigused**.
   
#### <a name="prerequisites"></a>eeltingimused

PowerShelli skriptide käivitamiseks peate importima järgmised kolm moodulit. 

1. Installige PowerShell for Graph [Azure Active Directory uusim](/powershell/azure/active-directory/install-adv2) versioon.
   1. Valige arvutis klaviatuuril Windowsi klahv ja otsige **Windows PowerShell** ning valige **Käivita administraatorina**.
   1. Sisestage avanevasse PowerShelli aknasse `Install-Module AzureAD`.
2. Importige kolm moodulit.
    1. Sisestage `Install-Module -Name Az.Accounts` PowerShelli aknas juhised ja järgige neid. 
    1. Korda ja `Install-Module -Name Az.Resources``Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Konfigureerimise sammud

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
        - Käivitage see PowerShelli skript Windows PowerShellis, pakkudes Azure'i tellimuse ID-d, mis sisaldab teie Azure Data Lake Storage salvestusruumikonto nime, ressursirühma nime ning Readeri ja kaasautori turberühma ID väärtusi. Lisateabe ja rakendatud loogika ülevaatamiseks avage redaktoris PowerShelli skript.
        - Kopeerige väljundstring pärast skripti edukat käivitamist. Väljundstring näeb välja selline: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Sisestage ülalt **kopeeritud väljundstring rakenduse keskkonnakonfiguratsioonietapi väljale** Õiguste identifikaator Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Konfigureerimissuvandid andmete ühiskasutuse lubamiseks rakendusega Azure Data Lake Storage Microsoft Dataverse.":::

Customer Insights ei toeta järgmisi andmete jagamise stsenaariume:
- Kui lubate andmete ühiskasutuse Dataverse-ga, ei saa te [olemis luua ennustatud ega puuduvad väärtused](predictions.md).
- Kui lubate andmete jagamise rakendusega Dataverse, ei saa te oma Customer Insightsi keskkonnas vaadata ühtegi valikulist PowerBI manustatud aruannet.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Olemasoleva ühenduse eemaldamine keskkonnaga Dataverse

Keskkonnaga Dataverse ühenduse loomisel tähendab tõrketeade **See CDS-organisatsioon on juba seotud mõne muu Customer Insightsi eksemplariga**, et Dataverse keskkonda kasutatakse juba Customer Insightsi keskkonnas. Olemasoleva ühenduse saate eemaldada keskkonna üldadministraatorina Dataverse. Muudatuste elluviimiseks võib kuluda paar tundi.

1. Avage [Power Apps](https://make.powerapps.com).
1. Valige keskkond keskkonnavalijast.
1. Avage **lahendused**
1. Desinstallige või kustutage lahendus nimega **Dynamics 365 Customer Insights Kliendikaardi lisandmoodul (eelvaade)**.

VÕI 

1. Avage oma Dataverse keskkond.
1. Avage täpsemad **sättedSolutions** > **·**.
1. Desinstallige **CustomerInsightsCustomerCard** lahendus.

## <a name="copy-the-environment-configuration"></a>Kopeerige keskkonna konfiguratsioon

Administraatorina saate uue keskkonna loomisel valida konfiguratsiooni kopeerimise olemasolevast keskkonnast. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Kuvatõmmis suvandisätetest keskkonnasätetes.":::

Näete teie ettevõtte kõigi saadaolevate keskkondade loendit, kust saate andmeid kopeerida.

Kopeeritakse järgmised konfiguratsioonisätted.

- Valmendatud/imporditud andmeallikad
- Andmete ühtlustamiskonfiguratsioon (kaardistamine, vastendamine, ühendamine)
- Segmendid
- Meetmed
- Seosed
- Tegevused 
- Otsingu ja filtri register
- Ekspordisihtkohad
- Ajastatud värskendamine
- Rikastamised
- Mudeli haldus
- Rolli määramised

## <a name="set-up-a-copied-environment"></a>Kopeeritud keskkonna häälestamine

Keskkonnakonfiguratsiooni kopeerimisel ei *kopeerita järgmisi andmeid*.

- Kliendiprofiilid.
- Andmeallika identimisteave. Peate sisestama identimisteabe iga andmeallika jaoks ja värskendama andmeallikaid käsitsi.
- Andmeallikad ühisandmemudeli kaustast ja Dataverse hallatavatest Data Lake-st. Peate need andmeallikad looma käsitsi sama nimega kui lähtekeskkond.
- Ühenduse saladused, mida kasutatakse ekspordiks ja rikastamiseks. Te peate ühendused uuesti kinnitama ja seejärel taasaktiveerima rikastamised ja ekspordi. 

Keskkonna kopeerimisel näete kinnitusteadet, et loodi uus keskkond. Andmeallikate loendi nägemiseks valige suvand **Ava andmeallikad**.

Kõik andmeallikad kuvavad olekut **Mandaat nõutav**. Redigeerige andmeallikaid ja sisestage nende värskendamiseks identimisteave.

:::image type="content" source="media/data-sources-copied.png" alt-text="Kopeeritud ja autentimist vajav andmeallikate loend.":::

Pärast andmeallikate värskendamist avage jaotis **Andme** > **Ühendamine**. Siit leiate lähtekeskkonna sätted. Redigeerige neid vastavalt vajadusele või valige **Käivita**, et käivitada andmete ühendamise protsess ja luua ühtne kliendi olem.

Kui andmete ühendamine on lõpetatud, avage **Meetmed** ja **Segmendid**, et neid samuti värskendada.

Enne ekspordi ja rikastamise taasaktiveerimist minge **adminconnections'i** > **·**, et taastada ühendused uues keskkonnas.

## <a name="change-the-owner-of-an-environment"></a>Keskkonna omaniku muutmine

Kuigi customer Insightsis võivad administraatoriõigused olla mitmel kasutajal, on keskkonna omanik ainult üks kasutaja. Vaikimisi loob algselt keskkonna administraator. Keskkonna administraatorina saate määrata omandiõiguse teisele administraatoriõigustega kasutajale.

1. Valige rakenduse päises valija **Environment** (Keskkond).

1. Valige ikoon **Edit** (Redigeeri).

1. Avage väljal **Keskkonna** redigeerimine juhised **Põhiteave**.

1. Valige väljal **Keskkonna** omaniku muutmine keskkonna uus omanik.  

1. Muudatuste rakendamiseks valige **Läbivaatus ja lõpeta**, seejärel **Värskenda**. 

## <a name="claim-ownership-of-an-environment"></a>Nõuda keskkonna omandiõigust

Kui keskkonna omanik lahkub organisatsioonist või tema kasutajakonto kustutatakse, ei ole keskkonnal omanikku. Administraatoriõigustega kasutaja saab omandiõiguse endale nõuda ja saada uueks omanikuks. Nad võivad jätkata keskkonna omamist või [omaniku muutmist teisele administraatorile](#change-the-owner-of-an-environment). 

Omandiõiguse taotlemiseks valige **nupp Võta omandiõigus**, mis kuvatakse Customer Insightsi iga lehe ülaosas, kui algne omanik organisatsioonist lahkus.

## <a name="reset-an-existing-environment"></a>Olemasoleva keskkonna lähtestamine

Keskkonna omanikuna saate keskkonna lähtestada tühja olekusse, kui soovite kustutada kõik konfiguratsioonid ja eemaldada allaneelatud andmed.

1.  Valige rakenduse päises valija **Environment** (Keskkond). 

2.  Valige keskkond, mille soovite lähtestada, ja valige ellips (**...**). 

3. Valige suvand **Reset** (Lähtesta). 

4.  Kustutamise kinnitamiseks sisestage keskkonna nimi ja valige **Lähtesta**.

## <a name="delete-an-existing-environment"></a>Olemasoleva keskkonna kustutamine

Keskkonna omanikuna saate kustutada hallatava keskkonna.

1.  Valige rakenduse päises valija **Environment** (Keskkond).

2.  Valige keskkond, mille soovite lähtestada, ja valige ellips (**...**). 

3. Valige suvand **Delete** (Kustuta). 

4.  Kustutamise kinnitamiseks sisestage soovitud keskkonna nimi ja valige **Kustuta**.

> [!NOTE]
> Keskkonna kustutamine ei eemalda seost Dataverse keskkonda. Siit saate teada, [kuidas olemasolevat ühendust keskkonnaga Dataverse](#remove-an-existing-connection-to-a-dataverse-environment) eemaldada.


[!INCLUDE [footer-include](includes/footer-banner.md)]
