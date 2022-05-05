---
title: Ühendu Azure Data Lake Storage kontoga teenuse subjekti abil
description: Kasutage Azure'i teenuse subjekti oma andmetega ühenduse loomiseks.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 1dd99edc327bd41b0442b390f2e4f8664269f553
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642655"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Ühendu Azure Data Lake Storage kontoga Azure teenuse subjekti abil

Selles artiklis käsitletakse, kuidas kontoga Dynamics 365 Customer Insights ühenduse luua Azure Data Lake Storage, kasutades salvestusruumikonto võtmete asemel Azure'i teenuse põhiosa. 

Automatiseeritud tööriistad, mis kasutavad Azure'i teenuseid, peaksid alati omama piiratud õigusi. Selleks et rakendused ei saaks logida sisse kõikide õigustega kasutajana, pakub Azure teenusesubjekte. Teenusejuhtide abil saate turvaliselt [lisada või redigeerida kausta Common Data Model andmeallikas](connect-common-data-model.md) või [luua või värskendada keskkonda](create-environment.md).

> [!IMPORTANT]
> - Andmejärve salvestuskonto, mis kasutab teenuse põhiosa, peab olema Gen2 ja lubatud on [hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace). Azure Data Lake Gen1 salvestuskontosid ei toetata.
> - Teenuse põhiosa loomiseks on vaja Azure'i tellimuse administraatoriõigusi.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Azure'i teenuse subjekti loomine Customer Insightsi abil

Enne Customer Insightsi jaoks uue hooldusdirektori loomist kontrollige, kas see on teie asutuses juba olemas.

### <a name="look-for-an-existing-service-principal"></a>Olemasoleva teenusesubjekti otsimine

1. Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.

2. Valige suvandist **Azure teenused** suvand **Azure Active Directory**.

3. Valige jaotises **Halda** suvand **Ettevõtterakendused**.

4. Otsige Microsofti rakenduse ID-d `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` nimega `Dynamics 365 AI for Customer Insights`.

5. Kui leiate vastava kirje, tähendab see, et teenuse subjekt on juba olemas. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Kuvatõmmis olemasoleva teenuse subjekti kohta.":::
   
6. Kui tulemusi ei tagastata, looge uus teenusesubjekt.

### <a name="create-a-new-service-principal"></a>Uue teenusesubjekti loomine

1. Installige Azure Active Directory PowerShell for Graphi uusim versioon. Lisateavet leiate teemast [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) installimine.

   1. Valige arvutis klaviatuuril Windowsi klahv ja otsige **Windows PowerShell** ning valige **Käivita administraatorina**.
   
   1. Sisestage avanevasse PowerShelli aknasse `Install-Module AzureAD`.

2. Looge Customer Insightsi teenuse subjekt Azure AD PowerShelli mooduliga.

   1. Sisestage PowerShelli aknasse `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Asendage *[kataloogi ID]* Azure'i tellimuse tegeliku kataloogi ID-ga, kus soovite teenuse põhiosa luua. Keskkonna nime parameeter `AzureEnvironmentName` on valikuline.
  
   1. Sisestage `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. See käsk loob valitud Azure'i tellimuse customer insightsi hooldusdirektori. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Teenusesubjektile õiguste andmine salvestuskontole juurdepääsemiseks

Minge Azure'i portaali, et anda õigused selle salvestusruumikonto hooldusdirektorile, mida soovite Customer Insightsis kasutada.

1. Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.

1. Avage talletuskonto, millele soovite Customer Insightsi hooldusdirektori juurdepääsu.

1. Valige vasakpoolsel paanil **Juurdepääsu juhtelement (IAM)** ja seejärel käsk **Lisa** > **Lisa rolli määratlus**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Kuvatõmmis, kus kuvatakse Azure'i portaal rolli määramise lisamise ajal.":::

1. Määrake paanil **Lisa rolli määratlus** järgmised atribuudid.
   - Roll: **salvestusruumi bloobiandmete kaasautor**
   - Juurdepääsu määramine: **kasutaja, rühm või teenusesubjekt**
   - Liikmete valimine: **Dynamics 365 AI for Customer Insights** ([teenuse direktor](#create-a-new-service-principal), mille lõite selle toiminguga varem)

1.  Valige **Läbivaatus + määramine**.

Muudatuste rakendamiseks võib kuluda kuni 15 minutit.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Sisestage Azure'i ressursi ID või Azure'i tellimuse üksikasjad Customer Insightsi salvestusruumikonto manusesse

Väljundandmete talletamiseks või [andmeallikas kasutamiseks saate Customer Insightsis lisada Data Lake Storage'i konto Customer Insightsis.](manage-environments.md)[...](connect-dataverse-managed-lake.md) See suvand võimaldab teil valida ressursipõhise või tellimispõhise lähenemisviisi vahel. Sõltuvalt valitud lähenemisviisist järgige ühte järgmistest jaotistest.

### <a name="resource-based-storage-account-connection"></a>Ressursipõhine salvestuskonto ühendus

1. Minge [Azure'i haldusportaali](https://portal.azure.com), logige oma tellimusse sisse ja avage salvestuskonto.

1. Minge vasakpoolsel paanil **Sätted** > **Atribuudid**.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]