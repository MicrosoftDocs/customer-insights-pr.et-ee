---
title: Azure Data Lake Storage Gen2 kontoga ühenduse loomine teenusesubjekti kaudu
description: Kasutage Azure'i teenusesubjekti sihtrühmaülevaadete jaoks, et luua ühendus omaenda andmejärvega, kui lisate selle sihtrühmaülevaadetele.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644083"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="b2b1b-103">Azure Data Lake Storage Gen2 kontoga ühendumine Azure'i teenusesubjekti kaudu sihtrühmaülevaadeteks</span><span class="sxs-lookup"><span data-stu-id="b2b1b-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="b2b1b-104">Automatiseeritud tööriistad, mis kasutavad Azure'i teenuseid, peaksid alati omama piiratud õigusi.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="b2b1b-105">Selleks et rakendused ei saaks logida sisse kõikide õigustega kasutajana, pakub Azure teenusesubjekte.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="b2b1b-106">Lugege edasi, et teada saada, kuidas ühendada sihtrühmaülevaated Azure Data Lake Storage Gen2 kontoga, kasutades selleks salvestuskonto võtmete asemel Azure'i teenusesubjekti.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="b2b1b-107">Saate kasutada teenusesubjekti, et turvaliselt [lisada või redigeerida Common Data Modeli kausta andmeallikana](connect-common-data-model.md) või [luua uus keskkond või värskendada olemasolevat](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="b2b1b-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="b2b1b-108">Teenusesubjekti loomiseks on teil vaja oma Azure'i tellimuse administraatoriõigusi.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="b2b1b-109">Azure'i teenusesubjekti loomine sihtrühmaülevaadeteks</span><span class="sxs-lookup"><span data-stu-id="b2b1b-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="b2b1b-110">Enne uue teenusesubjekti loomist sihtrühmaülevaadete jaoks kontrollige, kas see on teie ettevõttes juba olemas.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="b2b1b-111">Olemasoleva teenusesubjekti otsimine</span><span class="sxs-lookup"><span data-stu-id="b2b1b-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="b2b1b-112">Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="b2b1b-113">Valige Azure'i teenustest **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="b2b1b-114">Valige jaotises **Halda** suvand **Ettevõtterakendused**.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="b2b1b-115">Otsige sihtrühmaülevaadete esimese osapoole rakenduse ID-d `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` või nime `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="b2b1b-116">Kui leiate ühtiva kirje, tähendab see, et teenusesubjekt on sihtrühmaülevaadete jaoks olemas.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="b2b1b-117">Teil pole vaja seda uuesti luua.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Kuvatõmmis olemasolevast teenusesubjektist.":::
   
6. <span data-ttu-id="b2b1b-119">Kui tulemusi ei tagastata, looge uus teenusesubjekt.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="b2b1b-120">Uue teenusesubjekti loomine</span><span class="sxs-lookup"><span data-stu-id="b2b1b-120">Create a new service principal</span></span>

1. <span data-ttu-id="b2b1b-121">Installige rakenduse **Azure Active Directory PowerShell for Graph** uusim versioon.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="b2b1b-122">Lisateavet leiate teemast [Azure Active Directory PowerShell for Graphi installimine](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="b2b1b-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="b2b1b-123">Valige arvutis klaviatuuril Windowsi klahv ja otsige programmi **Windows PowerShell** ning **käivitage see administraatorina**.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="b2b1b-124">Sisestage avanevasse PowerShelli aknasse `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="b2b1b-125">Looge Azure AD PowerShelli mooduli abil teenusesubjekt sihtrühmaülevaadete jaoks.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="b2b1b-126">Sisestage PowerShelli aknasse `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="b2b1b-127">Asendage „your tenant ID“ oma rentniku tegeliku ID-ga, kus soovite teenusesubjekti luua.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="b2b1b-128">Keskkonna nime parameeter `AzureEnvironmentName` on valikuline.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="b2b1b-129">Sisestage `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="b2b1b-130">See käsk loob valitud rentnikus teenusesubjekti sihtrühmaülevaadete jaoks.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="b2b1b-131">Teenusesubjektile õiguste andmine salvestuskontole juurdepääsemiseks</span><span class="sxs-lookup"><span data-stu-id="b2b1b-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="b2b1b-132">Minge Azure'i portaali, et anda teenusesubjektile õigused selle salvestuskonto jaoks, mida soovite kasutada sihtrühmaülevaadetes.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="b2b1b-133">Minge [Azure'i haldusportaali](https://portal.azure.com) ja logige sisse oma organisatsiooni.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="b2b1b-134">Avage salvestuskonto, millele peaks sihtrühmaülevaadete jaoks mõeldud teenusesubjektil juurdepääs olema.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="b2b1b-135">Valige navigeerimispaanilt **Juurdepääsu haldus (IAM)** ja valige **Lisa** > **Lisa rollimäärang**.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Kuvatõmmis Azure'i portaalist rollimäärangu lisamise ajal.":::
   
1. <span data-ttu-id="b2b1b-137">Määrake paanil **Rollimäärangu lisamine** järgmised atribuudid.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="b2b1b-138">Roll: *salvestusruumi bloobiandmete kaasautor*</span><span class="sxs-lookup"><span data-stu-id="b2b1b-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="b2b1b-139">Juurdepääsu määramine: *kasutaja, rühm või teenusesubjekt*</span><span class="sxs-lookup"><span data-stu-id="b2b1b-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="b2b1b-140">Valige: *Dynamics 365 AI Customer Insightsi jaoks* ([teie loodud teenusesubjekt](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="b2b1b-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="b2b1b-141">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-141">Select **Save**.</span></span>

<span data-ttu-id="b2b1b-142">Muudatuste rakendamiseks võib kuluda kuni 15 minutit.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="b2b1b-143">Salvestuskonto manuse Azure'i ressursi ID või Azure'i tellimuse üksikasjade sisestamine sihtrühmaülevaadetesse.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="b2b1b-144">Lisage Azure Data Lake'i salvestuskonto sihtrühmaülevaadetesse, et [talletada väljundandmeid](manage-environments.md) või [kasutage seda andmeallikana](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="b2b1b-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="b2b1b-145">Azure Data Lake'i valimise korral saate valida ressurssidel või tellimusel põhineva meetodi vahel.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="b2b1b-146">Järgige allolevaid juhiseid, et sisestada valitud meetodi jaoks vajalik teave.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="b2b1b-147">Ressursipõhine salvestuskonto ühendus</span><span class="sxs-lookup"><span data-stu-id="b2b1b-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="b2b1b-148">Minge [Azure'i haldusportaali](https://portal.azure.com), logige oma tellimusse sisse ja avage salvestuskonto.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="b2b1b-149">Minge navigeerimispaanil jaotisse **Sätted** > **Atribuudid**.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="b2b1b-150">Kopeerige salvestuskonto ressursi-ID väärtus.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Salvestuskonto ressursi-ID kopeerimine.":::

1. <span data-ttu-id="b2b1b-152">Sisestage sihtrühmaülevaadetes ressursi ID ressursiväljale, mis on kuvatud salvestuskonto ühenduse ekraanil.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Salvestuskonto ressursi-ID teabe sisestamine.":::   
   
1. <span data-ttu-id="b2b1b-154">Jätkake sihtrühmaülevaadetes allesjäänud sammude järgimist, et lisada salvestuskonto.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="b2b1b-155">Tellimusepõhine salvestuskonto ühendus</span><span class="sxs-lookup"><span data-stu-id="b2b1b-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="b2b1b-156">Minge [Azure'i haldusportaali](https://portal.azure.com), logige oma tellimusse sisse ja avage salvestuskonto.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="b2b1b-157">Minge navigeerimispaanil jaotisse **Sätted** > **Atribuudid**.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="b2b1b-158">Vaadake üle salvestuskonto väärtused **Tellimus**, **Ressursirühm** ja **Nimi**, sihtrühmaülevaadetes oleksid valitud õiged väärtused.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="b2b1b-159">Valige sihtrühmaülevaadetes salvestuskontot lisades väärtused või asjaomased väljad.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="Salvestuskonto ressursi-ID teabe sisestamine.":::
   
1. <span data-ttu-id="b2b1b-161">Jätkake sihtrühmaülevaadetes allesjäänud sammude järgimist, et lisada salvestuskonto.</span><span class="sxs-lookup"><span data-stu-id="b2b1b-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
