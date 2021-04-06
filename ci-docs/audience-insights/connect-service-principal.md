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
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596494"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="f4e83-103">Azure Data Lake Storage Gen2 kontoga ühendumine Azure'i teenusesubjekti kaudu sihtrühmaülevaadeteks</span><span class="sxs-lookup"><span data-stu-id="f4e83-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="f4e83-104">Automatiseeritud tööriistad, mis kasutavad Azure'i teenuseid, peaksid alati omama piiratud õigusi.</span><span class="sxs-lookup"><span data-stu-id="f4e83-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="f4e83-105">Selleks et rakendused ei saaks logida sisse kõikide õigustega kasutajana, pakub Azure teenusesubjekte.</span><span class="sxs-lookup"><span data-stu-id="f4e83-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="f4e83-106">Lugege edasi, et teada saada, kuidas ühendada sihtrühmaülevaated Azure Data Lake Storage Gen2 kontoga, kasutades selleks salvestuskonto võtmete asemel Azure'i teenusesubjekti.</span><span class="sxs-lookup"><span data-stu-id="f4e83-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="f4e83-107">Saate kasutada teenusesubjekti, et turvaliselt [lisada või redigeerida Common Data Modeli kausta andmeallikana](connect-common-data-model.md) või [luua uus keskkond või värskendada olemasolevat](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="f4e83-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="f4e83-108">Azure Data Lake Gen2 salvestusruumi kontol, mis kasutab teenusesubjekti, peab olema [lubatud hierarhiline nimeruum (HNS)](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="f4e83-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="f4e83-109">Teenusesubjekti loomiseks on teil vaja oma Azure'i tellimuse administraatoriõigusi.</span><span class="sxs-lookup"><span data-stu-id="f4e83-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="f4e83-110">Azure'i teenusesubjekti loomine sihtrühmaülevaadeteks</span><span class="sxs-lookup"><span data-stu-id="f4e83-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="f4e83-111">Enne uue teenusesubjekti loomist sihtrühmaülevaadete jaoks kontrollige, kas see on teie ettevõttes juba olemas.</span><span class="sxs-lookup"><span data-stu-id="f4e83-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="f4e83-112">Olemasoleva teenusesubjekti otsimine</span><span class="sxs-lookup"><span data-stu-id="f4e83-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="f4e83-113">Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.</span><span class="sxs-lookup"><span data-stu-id="f4e83-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="f4e83-114">Valige Azure'i teenustest **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="f4e83-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="f4e83-115">Valige jaotises **Halda** suvand **Ettevõtterakendused**.</span><span class="sxs-lookup"><span data-stu-id="f4e83-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="f4e83-116">Otsige sihtrühmaülevaadete esimese osapoole rakenduse ID-d `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` või nime `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="f4e83-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="f4e83-117">Kui leiate ühtiva kirje, tähendab see, et teenusesubjekt on sihtrühmaülevaadete jaoks olemas.</span><span class="sxs-lookup"><span data-stu-id="f4e83-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="f4e83-118">Teil pole vaja seda uuesti luua.</span><span class="sxs-lookup"><span data-stu-id="f4e83-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Kuvatõmmis olemasolevast teenusesubjektist.":::
   
6. <span data-ttu-id="f4e83-120">Kui tulemusi ei tagastata, looge uus teenusesubjekt.</span><span class="sxs-lookup"><span data-stu-id="f4e83-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="f4e83-121">Uue teenusesubjekti loomine</span><span class="sxs-lookup"><span data-stu-id="f4e83-121">Create a new service principal</span></span>

1. <span data-ttu-id="f4e83-122">Installige rakenduse **Azure Active Directory PowerShell for Graph** uusim versioon.</span><span class="sxs-lookup"><span data-stu-id="f4e83-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="f4e83-123">Lisateavet leiate teemast [Azure Active Directory PowerShell for Graphi installimine](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="f4e83-123">For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="f4e83-124">Valige arvutis klaviatuuril Windowsi klahv ja otsige programmi **Windows PowerShell** ning **käivitage see administraatorina**.</span><span class="sxs-lookup"><span data-stu-id="f4e83-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="f4e83-125">Sisestage avanevasse PowerShelli aknasse `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="f4e83-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="f4e83-126">Looge Azure AD PowerShelli mooduli abil teenusesubjekt sihtrühmaülevaadete jaoks.</span><span class="sxs-lookup"><span data-stu-id="f4e83-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="f4e83-127">Sisestage PowerShelli aknasse `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="f4e83-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="f4e83-128">Asendage „your tenant ID“ oma rentniku tegeliku ID-ga, kus soovite teenusesubjekti luua.</span><span class="sxs-lookup"><span data-stu-id="f4e83-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="f4e83-129">Keskkonna nime parameeter `AzureEnvironmentName` on valikuline.</span><span class="sxs-lookup"><span data-stu-id="f4e83-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="f4e83-130">Sisestage `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="f4e83-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="f4e83-131">See käsk loob valitud rentnikus teenusesubjekti sihtrühmaülevaadete jaoks.</span><span class="sxs-lookup"><span data-stu-id="f4e83-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="f4e83-132">Teenusesubjektile õiguste andmine salvestuskontole juurdepääsemiseks</span><span class="sxs-lookup"><span data-stu-id="f4e83-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="f4e83-133">Minge Azure'i portaali, et anda teenusesubjektile õigused selle salvestuskonto jaoks, mida soovite kasutada sihtrühmaülevaadetes.</span><span class="sxs-lookup"><span data-stu-id="f4e83-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="f4e83-134">Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.</span><span class="sxs-lookup"><span data-stu-id="f4e83-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="f4e83-135">Avage salvestuskonto, millele peaks sihtrühmaülevaadete jaoks mõeldud teenusesubjektil juurdepääs olema.</span><span class="sxs-lookup"><span data-stu-id="f4e83-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="f4e83-136">Valige navigeerimispaanilt **Juurdepääsu haldus (IAM)** ja valige **Lisa** > **Lisa rollimäärang**.</span><span class="sxs-lookup"><span data-stu-id="f4e83-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Kuvatõmmis Azure'i portaalist rollimäärangu lisamise ajal.":::
   
1. <span data-ttu-id="f4e83-138">Määrake paanil **Rollimäärangu lisamine** järgmised atribuudid.</span><span class="sxs-lookup"><span data-stu-id="f4e83-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="f4e83-139">Roll: *salvestusruumi bloobiandmete kaasautor*</span><span class="sxs-lookup"><span data-stu-id="f4e83-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="f4e83-140">Juurdepääsu määramine: *kasutaja, rühm või teenusesubjekt*</span><span class="sxs-lookup"><span data-stu-id="f4e83-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="f4e83-141">Valige: *Dynamics 365 AI Customer Insightsi jaoks* ([teie loodud teenusesubjekt](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="f4e83-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="f4e83-142">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="f4e83-142">Select **Save**.</span></span>

<span data-ttu-id="f4e83-143">Muudatuste rakendamiseks võib kuluda kuni 15 minutit.</span><span class="sxs-lookup"><span data-stu-id="f4e83-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="f4e83-144">Salvestuskonto manuse Azure'i ressursi ID või Azure'i tellimuse üksikasjade sisestamine sihtrühmaülevaadetesse.</span><span class="sxs-lookup"><span data-stu-id="f4e83-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="f4e83-145">Lisage Azure Data Lake'i salvestuskonto sihtrühmaülevaadetesse, et [talletada väljundandmeid](manage-environments.md) või [kasutage seda andmeallikana](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="f4e83-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="f4e83-146">Azure Data Lake'i valimise korral saate valida ressurssidel või tellimusel põhineva meetodi vahel.</span><span class="sxs-lookup"><span data-stu-id="f4e83-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="f4e83-147">Järgige allolevaid juhiseid, et sisestada valitud meetodi jaoks vajalik teave.</span><span class="sxs-lookup"><span data-stu-id="f4e83-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="f4e83-148">Ressursipõhine salvestuskonto ühendus</span><span class="sxs-lookup"><span data-stu-id="f4e83-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="f4e83-149">Minge [Azure'i haldusportaali](https://portal.azure.com), logige oma tellimusse sisse ja avage salvestuskonto.</span><span class="sxs-lookup"><span data-stu-id="f4e83-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="f4e83-150">Minge navigeerimispaanil jaotisse **Sätted** > **Atribuudid**.</span><span class="sxs-lookup"><span data-stu-id="f4e83-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="f4e83-151">Kopeerige salvestuskonto ressursi-ID väärtus.</span><span class="sxs-lookup"><span data-stu-id="f4e83-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salvestuskonto ressursi-ID kopeerimine.":::

1. <span data-ttu-id="f4e83-153">Sisestage sihtrühmaülevaadetes ressursi ID ressursiväljale, mis on kuvatud salvestuskonto ühenduse ekraanil.</span><span class="sxs-lookup"><span data-stu-id="f4e83-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Salvestuskonto ressursi-ID teabe sisestamine.":::   
   
1. <span data-ttu-id="f4e83-155">Jätkake sihtrühmaülevaadetes allesjäänud sammude järgimist, et lisada salvestuskonto.</span><span class="sxs-lookup"><span data-stu-id="f4e83-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="f4e83-156">Tellimusepõhine salvestuskonto ühendus</span><span class="sxs-lookup"><span data-stu-id="f4e83-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="f4e83-157">Minge [Azure'i haldusportaali](https://portal.azure.com), logige oma tellimusse sisse ja avage salvestuskonto.</span><span class="sxs-lookup"><span data-stu-id="f4e83-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="f4e83-158">Minge navigeerimispaanil jaotisse **Sätted** > **Atribuudid**.</span><span class="sxs-lookup"><span data-stu-id="f4e83-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="f4e83-159">Vaadake üle salvestuskonto väärtused **Tellimus**, **Ressursirühm** ja **Nimi**, sihtrühmaülevaadetes oleksid valitud õiged väärtused.</span><span class="sxs-lookup"><span data-stu-id="f4e83-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="f4e83-160">Valige sihtrühmaülevaadetes salvestuskontot lisades väärtused või asjaomased väljad.</span><span class="sxs-lookup"><span data-stu-id="f4e83-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="f4e83-161">Jätkake sihtrühmaülevaadetes allesjäänud sammude järgimist, et lisada salvestuskonto.</span><span class="sxs-lookup"><span data-stu-id="f4e83-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]