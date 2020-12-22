---
title: API-dega töötamine
description: Kasutage API-sid ja olge teadlik nende piirangutest.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689125"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="dd5a6-103">Customer Insightsi API-dega töötamine</span><span class="sxs-lookup"><span data-stu-id="dd5a6-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="dd5a6-104">Dynamics 365 Customer Insights pakub API-sid, et luua rakendusi Customer Insightsis olevate andmete põhjal.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd5a6-105">Nende API-de üksikasjad on toodud [Customer Insightsi API-de ülevaates](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="dd5a6-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="dd5a6-106">Need sisaldavad lisateavet toimingute, parameetrite ja vastuste kohta.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="dd5a6-107">See artikkel annab juhiseid Customer Insightsi API-dele juurdepääsemise, Azure'i rakenduse registreeringu loomise kohta ning aitab alustada saadaolevate klienditeekide põhjal.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="dd5a6-108">Customer Insightsi API-de proovimise alustamine</span><span class="sxs-lookup"><span data-stu-id="dd5a6-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="dd5a6-109">[Logige sisse](https://home.ci.ai.dynamics.com) Customer Insightsi.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="dd5a6-110">Kui teil pole veel tellimust, [registreeruge Customer Insightsi prooviversiooni kasutamiseks](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="dd5a6-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="dd5a6-111">Customer Insightsi keskkonnas API-de lubamiseks minge jaotisse **Haldus** > **Õigused**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="dd5a6-112">Selleks on teil vaja administraatoriõigusi.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="dd5a6-113">Minge vahekaardile **API-d** ja valige nupp **Luba**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="dd5a6-114">API-de lubamine loob teie eksemplari jaoks esmase ja teisese tellimuse võtme, mida kasutatakse API-de päringutes.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="dd5a6-115">Saate võtmed uuesti luua, kui valite **Loo esmane uuesti** või **Loo teisene uuesti** jaotises **Haldus** > **Õigused** > **API-d**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insightsi API-de lubamine":::

1. <span data-ttu-id="dd5a6-117">API-de proovimiseks valige **Tutvuge meie API-dega**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="dd5a6-118">Valige API-toiming ja valige **Proovi**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="dd5a6-119">Määrake külgpaanil rippmenüü **Autoriseerimine** väärtuseks **kaudne**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="dd5a6-120">Päis `Authorization` lisatakse koos kandeloaga.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="dd5a6-121">Teie tellimuse võti asustatakse automaatselt.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="dd5a6-122">Soovi korral lisage kõik vajalikud päringuparameetrid.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="dd5a6-123">Liikuge külgpaanis kõige alla ja valige **Saada**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="dd5a6-124">HTTP-vastus kuvatakse varsti allpool.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="dd5a6-125">Uue rakenduse registreeringu loomine Azure'i portaalis</span><span class="sxs-lookup"><span data-stu-id="dd5a6-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="dd5a6-126">Need juhised aitavad teil alustada Customer Insightsi API-de kasutamist Azure'i rakenduses, kasutades delegeeritud õigusi.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="dd5a6-127">Veenduge, et olete esiteks [tutvunud alustamise jaotisega](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="dd5a6-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="dd5a6-128">Logige [Azure'i portaali](https://portal.azure.com) sisse kontoga, mis pääseb juurde Customer Insightsi andmetele.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="dd5a6-129">Valige vasakul **Rakenduse registreeringud**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="dd5a6-130">Valige **Uus registreering**, sisestage rakenduse nimi ja valige kontotüüp.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="dd5a6-131">Võite lisada ka ümbersuunamise URL-i.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="dd5a6-132">http://localhost on piisav rakenduse arendamiseks teie kohalikus arvutis.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="dd5a6-133">Minge uues rakenduse registreeringus jaotisse **API õigused**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="dd5a6-134">Valige **Lisa õigus** ja valige külgpaanil **Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="dd5a6-135">Valige **õiguse tüübiks** **Delegeeritud õigused** ja valige õigus **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="dd5a6-136">Valige **Õiguste lisamine**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-136">Select **Add permissions**.</span></span> <span data-ttu-id="dd5a6-137">Kui teil on vaja juurdepääsu API-sse ilma, et kasutaja sisse logiks, vaadake üle jaotis [Serverist serverisse rakenduse õigused](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="dd5a6-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="dd5a6-138">Rakenduse registreerimise lõpetamiseks valige **Anna administraatori nõusolek...**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="dd5a6-139">Saate kasutada selle rakenduse registreeringu rakenduse/kliendi ID-d Microsofti autentimisteegis (MSAL), et saada kandeluba, mida koos päringuga API-le saata.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="dd5a6-140">Lisateavet MSAL kohta leiate teemast [Microsofti autentimisteegi (MSAL) ülevaade](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="dd5a6-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="dd5a6-141">Azure'is rakenduste registreerimise kohta lisateabe saamiseks lugege teemat [Uus Azure'i portaali rakenduse registreerimise kogemus](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="dd5a6-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="dd5a6-142">Lisateavet meie klienditeekide API-de kasutamise kohta leiate jaotisest [Customer Insightsi klienditeegid](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="dd5a6-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="dd5a6-143">Serverist serverisse rakenduse õigused</span><span class="sxs-lookup"><span data-stu-id="dd5a6-143">Server-to-server application permissions</span></span>

<span data-ttu-id="dd5a6-144">[Rakenduse registreerimise jaotises](#create-a-new-app-registration-in-the-azure-portal) kirjeldatakse, kuidas registreerida rakendus, mis nõuab kasutajalt autentimiseks sisselogimist.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="dd5a6-145">Siit leiate teavet selle kohta, kuidas luua rakenduse registreering, mis ei vaja kasutaja sekkumist ja mida saab serveris käitada.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="dd5a6-146">Minge Azure'i portaalis oma rakenduse registreeringus jaotisse **API õigused**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="dd5a6-147">Valige **Lisa õigus** ja valige külgpaanil **Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="dd5a6-148">Valige **õiguse tüübiks** **Rakenduse õigused** ja valige õigus **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="dd5a6-149">Valige **Õiguste lisamine**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="dd5a6-150">Administraatori nõusoleku andmiseks selles rakenduse õiguses peate lisama teenusesubjekti.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="dd5a6-151">Installige Azure Active Directory (AD) PowerShelli moodul: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="dd5a6-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="dd5a6-152">Looge ühendus oma AD kontoga: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="dd5a6-153">Oma rentniku ID leiate jaotisest **Ülevaade** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="dd5a6-154">Azure AD teenusesubjekti lisamiseks käivitage järgmine käsk : `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Parameeter AppId on seotud Customer Insightsi API rakendusega.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Näidisteenusesubjekt":::

1. <span data-ttu-id="dd5a6-156">Minge oma rakenduse registreeringus tagasi jaotisse **API õigused**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="dd5a6-157">Rakenduse registreerimise lõpetamiseks valige **Anna administraatori nõusolek...**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="dd5a6-158">Lõpetamiseks peame lisama rakenduse registreeringu nime Customer Insightsis kasutajana.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="dd5a6-159">Avage Customer Insights, minge jaotisse **Haldus** > **Õigused** ja valige **Lisa kasutaja**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="dd5a6-160">Otsige oma rakenduse registreeringu nime, valige see otsingutulemustest ja valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="dd5a6-161">Customer Insightsi klienditeegid</span><span class="sxs-lookup"><span data-stu-id="dd5a6-161">Customer Insights client libraries</span></span>

<span data-ttu-id="dd5a6-162">See jaotis aitab teil alustada klienditeekide kasutamist, mis on saadaval Customer Insightsi API-de jaoks.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="dd5a6-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="dd5a6-163">C# NuGet</span></span>

<span data-ttu-id="dd5a6-164">Teave selle kohta, kuidas alustada C# klienditeekide kasutamist, leiate aadressilt NuGet.org. Lisateavet NuGeti paketi kohta leiate teemast [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="dd5a6-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="dd5a6-165">See pakett kasutab praegu netstandard2.0 ja netcoreapp2.0 raamistikke.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="dd5a6-166">C# klienditeegi lisamine C# projekti</span><span class="sxs-lookup"><span data-stu-id="dd5a6-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="dd5a6-167">Avage Visual Studios oma projekti **NuGeti paketihaldur**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="dd5a6-168">Otsige API-t **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="dd5a6-169">Selleks, et lisada pakett projekti, valige **Installi**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="dd5a6-170">Teise võimalusena käivitage **NuGeti paketihalduri konsoolis** see käsk: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="dd5a6-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="NuGeti paketi lisamine Visual Studio projekti":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="dd5a6-172">C# klienditeegi kasutamine</span><span class="sxs-lookup"><span data-stu-id="dd5a6-172">Use the C# client library</span></span>

1. <span data-ttu-id="dd5a6-173">Kasutage [Microsofti autentimisteeki (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview), et saada `AccessToken`, kasutades oma olemasolevat [Azure'i rakenduse registreeringut](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="dd5a6-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="dd5a6-174">Pärast õnnestunud autentimist ja loa omandamist looge uus või kasutage olemasolevat üksust `HttpClient` ning määrake üksuse **DefaultRequestHeaders "Authorization"** väärtuseks **Bearer <access token>** ja üksuse **Ocp-Apim-Subscription-Key** väärtuseks [**tellimuse võti**, mis pärineb teie Customer Insightsi keskkonnast](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="dd5a6-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="dd5a6-175">Vajadusel lähtestage päis **Autoriseerimine**.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="dd5a6-176">Näiteks kui luba on aegunud.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="dd5a6-177">Edastage `HttpClient` `CustomerInsights`i kliendi meetodisse.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpcliendi näidis":::

1. <span data-ttu-id="dd5a6-179">Kutsuge kliendiga „laiendusmeetodeid“, näiteks `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="dd5a6-180">Kui eelistate juurdepääsu aluseks olevale üksusele `Microsoft.Rest.HttpOperationResponse`, kasutage „http-sõnumi meetodeid“, näiteks meetodit `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="dd5a6-181">Vastus tüüp on tõenäoliselt `object`, kuna meetod võib tagastada mitut tüüpi (nt `IList<InstanceInfo>` ja `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="dd5a6-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="dd5a6-182">Vastusetüübi kontrollimiseks saate objektid ohutult teisendada toimingu vastusetüüpideks, mida kirjeldatakse [API üksikasjade lehel](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="dd5a6-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="dd5a6-183">Kui päringu kohta on vaja rohkem teavet, kasutage **http-sõnumi meetodeid**, et pääseda juurde töötlemata vastuseobjektile.</span><span class="sxs-lookup"><span data-stu-id="dd5a6-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>
