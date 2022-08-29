---
title: Ühendu Azure Data Lake Storage kontoga Azure teenuse subjekti abil
description: Kasutage Azure'i teenuse subjekti oma andmetega ühenduse loomiseks.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304192"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Ühendu Azure Data Lake Storage kontoga Azure teenuse subjekti abil

Dynamics 365 Customer Insights pakub võimalust luua kontoga ühendus Azure Data Lake Storage, kasutades salvestusruumikonto võtmete asemel Azure’i teenuse printsipaali.

Azure’i teenuseid kasutavatel automatiseeritud tööriistadel peavad olema piiratud õigused. Selleks et rakendused ei saaks logida sisse kõikide õigustega kasutajana, pakub Azure teenusesubjekte. Teenuse printsipaalide abil saate turvaliselt [lisada või redigeerida common data model kausta andmeallikas](connect-common-data-model.md) või [luua või värskendada keskkonda](create-environment.md).

## <a name="prerequisites"></a>eeltingimused

- Data Lake’i salvestusruumi konto, mis kasutab teenuse põhiosa, peab olema Gen2. Azure Data Lake Gen1 salvestusruumi kontosid ei toetata.
- Data Lake’i salvestusruumi kontol on [lubatud hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace).
- Administraatoriõigused teie Azure´i rentnik, kui peate looma uue hooldustöötaja.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Azure'i teenuse subjekti loomine Customer Insightsi abil

Enne Customer Insightsi jaoks uue hooldusjuhise loomist kontrollige, kas see on teie organisatsioonis juba olemas. Enamikul juhtudel on see juba olemas.

### <a name="look-for-an-existing-service-principal"></a>Olemasoleva teenusesubjekti otsimine

1. Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.

2. Valige suvandist **Azure teenused** suvand **Azure Active Directory**.

3. Tehke jaotises **Haldamine** valik **Microsofti rakendus**.

4. Rakenduse ID filtri **lisamine algab nimega**`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` või otsige seda `Dynamics 365 AI for Customer Insights`.

5. Kui leiate vastava kirje, tähendab see, et teenuse subjekt on juba olemas. [Andke teenuse printsipaalile](#grant-permissions-to-the-service-principal-to-access-the-storage-account) õigused salvestusruumikontole juurdepääsemiseks.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Kuvatõmmis olemasoleva teenuse subjekti kohta.":::

6. Kui tulemusi ei tagastata, [looge uus teenuse printsipaal](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Uue teenusesubjekti loomine

1. Installige Azure Active Directory PowerShell for Graphi uusim versioon. Lisateavet leiate teemast [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) installimine.

   1. Vajutage arvutis klaviatuuril Windowsi klahvi, otsige üles **Windows PowerShell** ja valige **Käivita administraatorina**.

   1. Sisestage avanevasse PowerShelli aknasse `Install-Module AzureAD`.

2. Looge Customer Insightsi teenuse subjekt Azure AD PowerShelli mooduliga.

   1. Sisestage PowerShelli aknasse `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Asendage *[teie kataloogi ID]* oma Azure’i tellimuse tegeliku kataloogi-ID-ga, kus soovite teenuse printsipaali luua. Keskkonna nime parameeter `AzureEnvironmentName` on valikuline.
  
   1. Sisestage `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. See käsk loob valitud Azure’i tellimuse Customer Insightsi jaoks teenuse printsipaal.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Teenusesubjektile õiguste andmine salvestuskontole juurdepääsemiseks

Teenuse printsipaalile õiguste andmiseks salvestusruumikonto jaoks, mida soovite Customer Insightsis kasutada, tuleb laokontole või konteinerile määrata üks järgmistest rollidest.

|Mandaadi|Nõuded|
|----------|------------|
|Praegu sisselogitud kasutaja|**Roll**: salvestusruumi bloobi andmelugeja, salvestusruumi bloobi kaasautor või salvestusruumi bloobi omanik.<br>**Tase**: salvestusruumikontole või konteinerile antud õigused.</br>|
|Customer Insightsi teenindusjuht -<br>Kasutamine Azure Data Lake Storage andmeallikas</br>|Suvand 1<ul><li>**Roll**: salvestusruumi bloobi andmelugeja, salvestusruumi bloobi andmete kaasautor või salvestusruumi bloobi andmete omanik.</li><li>**Tase**: salvestusruumikontol antud õigused.</li></ul>2 *. võimalus (ilma teenusepõhise juurdepääsuta salvestusruumikontole)*<ul><li>**Roll 1**: salvestusruumi bloobi andmelugeja, salvestusruumi bloobi andmete kaasautor või salvestusruumi bloobi andmete omanik.</li><li>**Tase**: konteinerile antud õigused.</li><li>**Roll 2**: salvestusruumi bloobi andmete delegeerija.</li><li>**Tase**: salvestusruumikontol antud õigused.</li></ul>|
|Customer Insightsi teenindusjuht - <br>Kasutamine Azure Data Lake Storage väljundi või sihtkohana</br>|Suvand 1<ul><li>**Roll**: salvestusruumi bloobi andmete kaasautor või salvestusruumi bloobi omanik.</li><li>**Tase**: salvestusruumikontol antud õigused.</li></ul>2 *. võimalus (ilma teenusepõhise juurdepääsuta salvestusruumikontole)*<ul><li>**Roll**: salvestusruumi bloobi andmete kaasautor või salvestusruumi bloobi omanik.</li><li>**Tase**: konteinerile antud õigused.</li><li>**Roll 2**: Storage Blob Delegator.</li><li>**Tase**: salvestusruumikontol antud õigused.</li></ul>|

1. Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.

1. Avage salvestusruumikonto, millele soovite Customer Insightsi hooldustöötajale juurde pääseda.

1. Valige vasakpoolsel paanil **Juurdepääsu juhtelement (IAM)** ja seejärel käsk **Lisa** > **Lisa rolli määratlus**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Kuvatõmmis, kus kuvatakse Azure'i portaal rolli määramise lisamise ajal.":::

1. Määrake paanil **Lisa rolli määratlus** järgmised atribuudid.
   - **Roll**: salvestusruumi bloobi andmelugeja, salvestusruumi bloobi kaasautor või salvestusruumi bloobi omanik ülaltoodud mandaatide põhjal.
   - **Juurdepääsu** määramine: **kasutaja, rühma või teenuse printsipaal**
   - **Liikmete valimine**: **Dynamics 365 AI for Customer Insights** (hooldusjuht, [kelle](#create-a-new-service-principal) te selles protseduuris varem üles otsisite)

1. Valige **Läbivaatus + määra**.

Muudatuste rakendamiseks võib kuluda kuni 15 minutit.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Azure’i ressursi ID või Azure’i tellimuse üksikasjade sisestamine Customer Insightsi salvestuskonto manusesse

Andmejärve salvestusruumi konto manustamine Customer Insightsis väljundandmete [talletamiseks](manage-environments.md) või [andmeallikas](connect-dataverse-managed-lake.md) kasutamiseks. Valige ressursi- või [tellimuspõhise](#resource-based-storage-account-connection)[lähenemisviisi vahel](#subscription-based-storage-account-connection) ja järgige neid juhiseid.

### <a name="resource-based-storage-account-connection"></a>Ressursipõhine salvestuskonto ühendus

1. Minge [Azure'i haldusportaali](https://portal.azure.com), logige oma tellimusse sisse ja avage salvestuskonto.

1. Minge vasakpoolsel paanil jaotisse **Sätted** > **lõpp-punktid**.

1. Kopeerige salvestuskonto ressursi-ID väärtus.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salvestuskonto ressursi-ID kopeerimine.":::

1. Sisestage Customer Insightsis ressursi ID ressursiväljale, mis kuvatakse salvestusruumikonto ühenduse kuval.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Salvestuskonto ressursi-ID teabe sisestamine.":::

1. Jätkake salvestuskonto manustamiseks Customer Insightsi ülejäänud toimingutega.

### <a name="subscription-based-storage-account-connection"></a>Tellimusepõhine salvestuskonto ühendus

1. Minge [Azure'i haldusportaali](https://portal.azure.com), logige oma tellimusse sisse ja avage salvestuskonto.

1. Minge vasakpoolsel paanil **Sätted** > **Atribuudid**.

1. **Vaadake üle tellimus**, **ressursirühm** ja **salvestusruumikonto nimi**, et veenduda, et valite Customer Insightsis õiged väärtused.

1. Valige Customer Insightsis salvestusruumikonto manustamisel vastavate väljade väärtused.

1. Jätkake salvestuskonto manustamiseks Customer Insightsi ülejäänud toimingutega.

[!INCLUDE [footer-include](includes/footer-banner.md)]
