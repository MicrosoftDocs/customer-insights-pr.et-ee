---
title: Ühendu Azure Data Lake Storage kontoga teenuse subjekti abil
description: Kasutage Azure'i teenuse subjekti oma andmetega ühenduse loomiseks.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: faef3583337fd495e7baf40b0a208f1d9f10281a
ms.sourcegitcommit: 11b343f6622665251ab84ae39ebcd91fa1c928ca
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/08/2021
ms.locfileid: "7900253"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Ühendu Azure Data Lake Storage kontoga Azure teenuse subjekti abil

Selles artiklis käsitletakse, kuidas kontoga ühenduse Dynamics 365 Customer Insights Azure Data Lake Storage luua, kasutades salvestusruumikonto võtmete asemel Azure'i teenusedirektorit. 

Automatiseeritud tööriistad, mis kasutavad Azure'i teenuseid, peaksid alati omama piiratud õigusi. Selleks et rakendused ei saaks logida sisse kõikide õigustega kasutajana, pakub Azure teenusesubjekte. Teenuse põhijuhtide abil saate [ühisandmete mudeli kausta turvaliselt lisada või redigeerida andmeallikas](connect-common-data-model.md) või [luua või värskendada keskkonda](create-environment.md).

> [!IMPORTANT]
> - Teenuse subjekti kasutaval Data Lake Storage kontol peab olema [lubatud hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace).
> - Teenuse põhiteenuse loomiseks on vaja Azure'i tellimuse administraatoriõigusi.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Azure'i teenuse subjekti loomine Customer Insightsi abil

Enne Customer Insightsi uue hooldusdirektori loomist kontrollige, kas see on teie asutuses juba olemas.

### <a name="look-for-an-existing-service-principal"></a>Olemasoleva teenusesubjekti otsimine

1. Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.

2. Valige suvandist **Azure teenused** suvand **Azure Active Directory**.

3. Valige jaotises **Halda** suvand **Ettevõtterakendused**.

4. Otsige Microsofti rakenduse ID-d:
   - Sihtrühma ülevaated: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` nimega `Dynamics 365 AI for Customer Insights`
   - Kaasamisülevaated: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` nimega `Dynamics 365 AI for Customer Insights engagement insights`

5. Kui leiate vastava kirje, tähendab see, et teenuse subjekt on juba olemas. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Kuvatõmmis olemasoleva teenuse subjekti kohta.":::
   
6. Kui tulemusi ei tagastata, looge uus teenusesubjekt.

>[!NOTE]
>Kui soovite kasutada täielikku Dynamics 365 Customer Insights võimsust, soovitame teil lisada mõlemad rakendused teenuse subjekti.

### <a name="create-a-new-service-principal"></a>Uue teenusesubjekti loomine

1. Installige Azure Active Directory PowerShell for Graphi uusim versioon. Lisateavet leiate teemast [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) installimine.

   1. Valige arvutis klaviatuuril Windowsi klahv ja otsige **Windows PowerShell** ning valige **Käivita administraatorina**.
   
   1. Sisestage avanevasse PowerShelli aknasse `Install-Module AzureAD`.

2. Looge Customer Insightsi teenuse subjekt Azure AD PowerShelli mooduliga.

   1. Sisestage PowerShelli aknasse `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Asendage *[your tenant ID]* oma rentniku tegeliku ID-ga, kus soovite teenusesubjekti luua. Keskkonna nime parameeter `AzureEnvironmentName` on valikuline.
  
   1. Sisestage `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. See käsk loob valitud rentnikus teenusesubjekti sihtrühmaülevaadete jaoks. 

   1. Sisestage `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Selle käsuga luuakse kaasamisülevaadete teenusesubjekt valitud rentnikul.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Teenusesubjektile õiguste andmine salvestuskontole juurdepääsemiseks

Minge Azure'i portaali, et anda teenusesubjektile õigused selle salvestuskonto jaoks, mida soovite kasutada sihtrühmaülevaadetes.

1. Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.

1. Avage salvestuskonto, millele peaks sihtrühmaülevaadete jaoks mõeldud teenusesubjektil juurdepääs olema.

1. Valige vasakpoolsel paanil **Juurdepääsu juhtelement (IAM)** ja seejärel käsk **Lisa** > **Lisa rolli määratlus**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Kuvatõmmis, kus kuvatakse Azure'i portaal rolli määramise lisamise ajal.":::

1. Määrake paanil **Lisa rolli määratlus** järgmised atribuudid.
   - Roll: **salvestusruumi bloobiandmete kaasautor**
   - Juurdepääsu määramine: **kasutaja, rühm või teenusesubjekt**
   - Valige: **Dynamics 365 AI for Customer Insights** ja **Dynamics 365 AI for Customer Insights kaasamise ülevaated** (kaks [teenuse subjekti](#create-a-new-service-principal), mille olete varem protseduuri jooksul loonud)

1.  Valige **Salvesta**.

Muudatuste rakendamiseks võib kuluda kuni 15 minutit.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Salvestuskonto manuse Azure'i ressursi ID või Azure'i tellimuse üksikasjade sisestamine sihtrühma ülevaadetesse

Saate manustada sihtrühma ülevaadetes Data Lake mäluruumi konto, et [talletada väljundandmeid](manage-environments.md) või [kasutada seda andmeallikana](connect-common-data-service-lake.md). See suvand võimaldab teil valida ressursipõhise või tellimispõhise lähenemisviisi vahel. Sõltuvalt valitud lähenemisviisist järgige ühte järgmistest jaotistest.

### <a name="resource-based-storage-account-connection"></a>Ressursipõhine salvestuskonto ühendus

1. Minge [Azure'i haldusportaali](https://portal.azure.com), logige oma tellimusse sisse ja avage salvestuskonto.

1. Minge vasakpoolsel paanil **Sätted** > **Atribuudid**.

1. Kopeerige salvestuskonto ressursi-ID väärtus.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salvestuskonto ressursi-ID kopeerimine.":::

1. Sihtrühma ülevaadetes sisestage ressursi ID mäluruumi konto ühenduskuval kuvatavale ressursi väljale.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Salvestuskonto ressursi-ID teabe sisestamine.":::   

1. Jätkake sihtrühmaülevaadetes allesjäänud sammude järgimist, et lisada salvestuskonto.

### <a name="subscription-based-storage-account-connection"></a>Tellimusepõhine salvestuskonto ühendus

1. Minge [Azure'i haldusportaali](https://portal.azure.com), logige oma tellimusse sisse ja avage salvestuskonto.

1. Minge vasakpoolsel paanil **Sätted** > **Atribuudid**.

1. Vaadake üle salvestuskonto väärtused **Tellimus**, **Ressursirühm** ja **Nimi**, sihtrühmaülevaadetes oleksid valitud õiged väärtused.

1. Valige sihtrühma ülevaadetes salvestusruumikonto manustamise korral vastavate väljade väärtused.

1. Jätkake sihtrühmaülevaadetes allesjäänud sammude järgimist, et lisada salvestuskonto.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
