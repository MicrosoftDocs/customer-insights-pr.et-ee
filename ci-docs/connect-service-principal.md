---
title: Ühendu Azure Data Lake Storage kontoga Azure teenuse subjekti abil
description: Kasutage Azure'i teenuse subjekti oma andmetega ühenduse loomiseks.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 949caa73578dbe0a511726ec045c0fd5f4621de4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082236"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Ühendu Azure Data Lake Storage kontoga Azure teenuse subjekti abil

Selles artiklis käsitletakse, kuidas kontoga Dynamics 365 Customer Insights ühenduse luua Azure Data Lake Storage, kasutades salvestusruumikonto võtmete asemel Azure'i teenuse põhiosa.

Automatiseeritud tööriistad, mis kasutavad Azure'i teenuseid, peaksid alati omama piiratud õigusi. Selleks et rakendused ei saaks logida sisse kõikide õigustega kasutajana, pakub Azure teenusesubjekte. Teenusejuhtide abil saate turvaliselt [lisada või redigeerida kausta Common Data Model andmeallikas](connect-common-data-model.md) või [luua või värskendada keskkonda](create-environment.md).

> [!IMPORTANT]
>
> - Andmejärve salvestuskonto, mis kasutab teenuse põhiosa, peab olema Gen2 ja lubatud on [hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1 salvestuskontosid ei toetata.
> - Hooldusdirektori loomiseks on vaja Azure´i rentnik administraatoriõigusi.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Azure'i teenuse subjekti loomine Customer Insightsi abil

Enne Customer Insightsi jaoks uue hooldusdirektori loomist kontrollige, kas see on teie asutuses juba olemas.

### <a name="look-for-an-existing-service-principal"></a>Olemasoleva teenusesubjekti otsimine

1. Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.

2. Valige suvandist **Azure teenused** suvand **Azure Active Directory**.

3. Valige **jaotises** Haldamine **käsk Microsofti rakendus**.

4. Lisage filter rakenduse ID **alustamiseks**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` või nime `Dynamics 365 AI for Customer Insights` otsimiseks.

5. Kui leiate vastava kirje, tähendab see, et teenuse subjekt on juba olemas.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Kuvatõmmis olemasoleva teenuse subjekti kohta.":::

6. Kui tulemusi ei tagastata, saate [luua uue hooldusdirektori](#create-a-new-service-principal). Enamikul juhtudel on see juba olemas ja salvestuskontole pääsemiseks peate andma hooldusdirektorile ainult õigused.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Teenusesubjektile õiguste andmine salvestuskontole juurdepääsemiseks

Minge Azure'i portaali, et anda õigused selle salvestusruumikonto hooldusdirektorile, mida soovite Customer Insightsis kasutada. Salvestuskontole või konteinerile tuleb määrata üks järgmistest rollidest.

|Mandaadi|Nõuded|
|----------|------------|
|Praegu kasutajasse sisse logitud|**Roll**: salvestusriba andmelugeja, salvestusruumi bloobi kaasautor või salvestusruumi bloobi omanik.<br>**Tase**: õigusi saab anda salvestuskontol või konteineris.</br>|
|Customer Insightsi teenuse direktor –<br>Kasutamine Azure Data Lake Storage andmeallikas</br>|Suvand 1<ul><li>**Roll**: Storage Blob Data Reader, Storage Blob Data Contributor või Storage Blob Data Owner.</li><li>**Tase**: salvestusruumikontol tuleks anda õigused.</li></ul>2 *. valik (ilma teenuse põhiosa juurdepääsuta salvestusruumikontole)*<ul><li>**1**. roll: salvestusruumi bloobi andmelugeja, salvestusruumi bloobi andmete kaasautor või salvestusruumi bloobi andmete omanik.</li><li>**Tase**: konteineris tuleks anda õigused.</li><li>**2**. roll: Storage Blob Data Delegator.</li><li>**Tase**: salvestusruumikontol tuleks anda õigused.</li></ul>|
|Customer Insightsi teenuse direktor – <br>Kasutamine Azure Data Lake Storage väljundina või sihtkohana</br>|Suvand 1<ul><li>**Roll**: Storage Blob Data Contributor või Storage Blob Omanik.</li><li>**Tase**: salvestusruumikontol tuleks anda õigused.</li></ul>2 *. valik (ilma teenuse põhiosa juurdepääsuta salvestusruumikontole)*<ul><li>**Roll**: Storage Blob Data Contributor või Storage Blob Omanik.</li><li>**Tase**: konteineris tuleks anda õigused.</li><li>**Roll 2**: Storage Blob Delegator.</li><li>**Tase**: salvestusruumikontol tuleks anda õigused.</li></ul>|

1. Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.

1. Avage talletuskonto, millele soovite Customer Insightsi hooldusdirektori juurdepääsu.

1. Valige vasakpoolsel paanil **Juurdepääsu juhtelement (IAM)** ja seejärel käsk **Lisa** > **Lisa rolli määratlus**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Kuvatõmmis, kus kuvatakse Azure'i portaal rolli määramise lisamise ajal.":::

1. Määrake paanil **Lisa rolli määratlus** järgmised atribuudid.
   - Roll: Storage Blob Data Reader, Storage Blob contributor või Storage Blob Owner, mis põhineb ülalkirjeldatud identimisteabel.
   - Juurdepääsu määramine: **kasutaja, rühm või teenusesubjekt**
   - Valige liikmed: **Dynamics 365 AI for Customer Insights** ([hooldusdirektor](#create-a-new-service-principal), mille otsisite varem selles protseduuris)

1. Valige **Läbivaatus + määramine**.

Muudatuste rakendamiseks võib kuluda kuni 15 minutit.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Sisestage Azure'i ressursi ID või Azure'i tellimuse üksikasjad Customer Insightsi salvestusruumikonto manusesse

Väljundandmete talletamiseks või [andmeallikas kasutamiseks saate Customer Insightsis lisada Data Lake Storage'i konto Customer Insightsis.](manage-environments.md)[...](connect-dataverse-managed-lake.md) See suvand võimaldab teil valida ressursipõhise või tellimispõhise lähenemisviisi vahel. Sõltuvalt valitud lähenemisviisist järgige ühte järgmistest jaotistest.

### <a name="resource-based-storage-account-connection"></a>Ressursipõhine salvestuskonto ühendus

1. Minge [Azure'i haldusportaali](https://portal.azure.com), logige oma tellimusse sisse ja avage salvestuskonto.

1. Valige vasakpoolsel paanil **sätted** > **Lõpp-punktid**.

1. Kopeerige salvestuskonto ressursi-ID väärtus.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salvestuskonto ressursi-ID kopeerimine.":::

1. Sisestage Customer Insightsis ressursi ID salvestuskonto ühenduse ekraanil kuvatavale ressursiväljale.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Salvestuskonto ressursi-ID teabe sisestamine.":::   

1. Jätkake salvestusruumikonto manustamiseks Customer Insightsi ülejäänud juhistega.

### <a name="subscription-based-storage-account-connection"></a>Tellimusepõhine salvestuskonto ühendus

1. Minge [Azure'i haldusportaali](https://portal.azure.com), logige oma tellimusse sisse ja avage salvestuskonto.

1. Minge vasakpoolsel paanil **Sätted** > **Atribuudid**.

1. **Vaadake üle jaotis** Tellimus **,** Ressurss ja **salvestuskonto nimi**, veendumaks, et valite Customer Insightsis õiged väärtused.

1. Valige jaotises Customer Insights vastavate väljade väärtused salvestuskonto manustamisel.

1. Jätkake salvestusruumikonto manustamiseks Customer Insightsi ülejäänud juhistega.

### <a name="create-a-new-service-principal"></a>Uue teenusesubjekti loomine

1. Installige Azure Active Directory PowerShell for Graphi uusim versioon. Lisateavet leiate teemast [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) installimine.

   1. Vajutage arvutis klaviatuuril Windowsi klahvi ja otsige **windows PowerShelli** ning valige suvand **Käivita administraatorina**.

   1. Sisestage avanevasse PowerShelli aknasse `Install-Module AzureAD`.

2. Looge Customer Insightsi teenuse subjekt Azure AD PowerShelli mooduliga.

   1. Sisestage PowerShelli aknasse `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Asendage *[kataloogi ID]* Azure'i tellimuse tegeliku kataloogi ID-ga, kus soovite teenuse põhiosa luua. Keskkonna nime parameeter `AzureEnvironmentName` on valikuline.
  
   1. Sisestage `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. See käsk loob valitud Azure'i tellimuse customer insightsi hooldusdirektori.

[!INCLUDE [footer-include](includes/footer-banner.md)]
