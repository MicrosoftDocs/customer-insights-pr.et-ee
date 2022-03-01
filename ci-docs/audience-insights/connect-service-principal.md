---
title: Azure Data Lake Storage Gen2 kontoga ühenduse loomine teenusesubjekti kaudu
description: Kasutage Azure'i teenusesubjekti sihtrühmaülevaadete jaoks, et luua ühendus oma Data Lake'iga, kui lisate selle sihtrühmaülevaadetele.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: cc94ad49f12067d513db4663bff60620d6501eb0
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692108"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Azure Data Lake Storage Gen2 kontoga ühendumine Azure'i teenusesubjekti kaudu sihtrühmaülevaadeteks

Automatiseeritud tööriistad, mis kasutavad Azure'i teenuseid, peaksid alati omama piiratud õigusi. Selleks et rakendused ei saaks logida sisse kõikide õigustega kasutajana, pakub Azure teenusesubjekte. Lugege edasi, et teada saada, kuidas ühendada sihtrühmaülevaated Azure Data Lake Storage Gen2 kontoga, kasutades selleks salvestuskonto võtmete asemel Azure'i teenusesubjekti. 

Saate kasutada teenusesubjekti, et turvaliselt [lisada või redigeerida Common Data Modeli kausta andmeallikana](connect-common-data-model.md) või [luua uus keskkond või värskendada olemasolevat](get-started-paid.md).

> [!IMPORTANT]
> - Azure Data Lake Gen2 salvestusruumi kontol, mis kasutab teenusesubjekti, peab olema [lubatud hierarhiline nimeruum (HNS)](/azure/storage/blobs/data-lake-storage-namespace).
> - Teenusesubjekti loomiseks on teil vaja oma Azure'i tellimuse administraatoriõigusi.

## <a name="create-azure-service-principal-for-audience-insights"></a>Azure'i teenusesubjekti loomine sihtrühmaülevaadeteks

Enne uue teenusesubjekti loomist sihtrühmaülevaadete jaoks kontrollige, kas see on teie ettevõttes juba olemas.

### <a name="look-for-an-existing-service-principal"></a>Olemasoleva teenusesubjekti otsimine

1. Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.

2. Valige Azure'i teenustest **Azure Active Directory**.

3. Valige jaotises **Halda** suvand **Ettevõtterakendused**.

4. Otsige sihtrühmaülevaadete esimese osapoole rakenduse ID-d `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` või nime `Dynamics 365 AI for Customer Insights`.

5. Kui leiate ühtiva kirje, tähendab see, et teenusesubjekt on sihtrühmaülevaadete jaoks olemas. Teil pole vaja seda uuesti luua.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Kuvatõmmis olemasolevast teenusesubjektist.":::
   
6. Kui tulemusi ei tagastata, looge uus teenusesubjekt.

### <a name="create-a-new-service-principal"></a>Uue teenusesubjekti loomine

1. Installige rakenduse **Azure Active Directory PowerShell for Graph** uusim versioon. Lisateavet leiate teemast [Azure Active Directory PowerShell for Graphi installimine](/powershell/azure/active-directory/install-adv2).
   - Valige arvutis klaviatuuril Windowsi klahv ja otsige programmi **Windows PowerShell** ning **käivitage see administraatorina**.
   
   - Sisestage avanevasse PowerShelli aknasse `Install-Module AzureAD`.

2. Looge Azure AD PowerShelli mooduli abil teenusesubjekt sihtrühmaülevaadete jaoks.
   - Sisestage PowerShelli aknasse `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Asendage „your tenant ID“ oma rentniku tegeliku ID-ga, kus soovite teenusesubjekti luua. Keskkonna nime parameeter `AzureEnvironmentName` on valikuline.
  
   - Sisestage `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. See käsk loob valitud rentnikus teenusesubjekti sihtrühmaülevaadete jaoks.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Teenusesubjektile õiguste andmine salvestuskontole juurdepääsemiseks

Minge Azure'i portaali, et anda teenusesubjektile õigused selle salvestuskonto jaoks, mida soovite kasutada sihtrühmaülevaadetes.

1. Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.

1. Avage salvestuskonto, millele peaks sihtrühmaülevaadete jaoks mõeldud teenusesubjektil juurdepääs olema.

1. Valige navigeerimispaanilt **Juurdepääsu haldus (IAM)** ja valige **Lisa** > **Lisa rollimäärang**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Kuvatõmmis Azure'i portaalist rollimäärangu lisamise ajal.":::
   
1. Määrake paanil **Rollimäärangu lisamine** järgmised atribuudid.
   - Roll: *salvestusruumi bloobiandmete kaasautor*
   - Juurdepääsu määramine: *kasutaja, rühm või teenusesubjekt*
   - Valige: *Dynamics 365 AI Customer Insightsi jaoks* ([teie loodud teenusesubjekt](#create-a-new-service-principal))

1.  Valige **Salvesta**.

Muudatuste rakendamiseks võib kuluda kuni 15 minutit.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Salvestuskonto manuse Azure'i ressursi ID või Azure'i tellimuse üksikasjade sisestamine sihtrühmaülevaadetesse.

Lisage Azure Data Lake'i salvestuskonto sihtrühmaülevaadetesse, et [talletada väljundandmeid](manage-environments.md) või [kasutage seda andmeallikana](connect-dataverse-managed-lake.md). Azure Data Lake'i valimise korral saate valida ressurssidel või tellimusel põhineva meetodi vahel.

Järgige allolevaid juhiseid, et sisestada valitud meetodi jaoks vajalik teave.

### <a name="resource-based-storage-account-connection"></a>Ressursipõhine salvestuskonto ühendus

1. Minge [Azure'i haldusportaali](https://portal.azure.com), logige oma tellimusse sisse ja avage salvestuskonto.

1. Minge navigeerimispaanil jaotisse **Sätted** > **Atribuudid**.

1. Kopeerige salvestuskonto ressursi-ID väärtus.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salvestuskonto ressursi-ID kopeerimine.":::

1. Sisestage sihtrühmaülevaadetes ressursi ID ressursiväljale, mis on kuvatud salvestuskonto ühenduse ekraanil.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Salvestuskonto ressursi-ID teabe sisestamine.":::   
   
1. Jätkake sihtrühmaülevaadetes allesjäänud sammude järgimist, et lisada salvestuskonto.

### <a name="subscription-based-storage-account-connection"></a>Tellimusepõhine salvestuskonto ühendus

1. Minge [Azure'i haldusportaali](https://portal.azure.com), logige oma tellimusse sisse ja avage salvestuskonto.

1. Minge navigeerimispaanil jaotisse **Sätted** > **Atribuudid**.

1. Vaadake üle salvestuskonto väärtused **Tellimus**, **Ressursirühm** ja **Nimi**, sihtrühmaülevaadetes oleksid valitud õiged väärtused.

1. Valige sihtrühmaülevaadetes salvestuskontot lisades väärtused või asjaomased väljad.
   
1. Jätkake sihtrühmaülevaadetes allesjäänud sammude järgimist, et lisada salvestuskonto.


[!INCLUDE[footer-include](../includes/footer-banner.md)]