---
title: API-dega töötamine
description: Kasutage API-sid ja olge teadlik nende piirangutest.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304737"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="e44c4-103">Customer Insightsi API-dega töötamine</span><span class="sxs-lookup"><span data-stu-id="e44c4-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="e44c4-104">Dynamics 365 Customer Insights pakub API-sid oma rakenduste ehitamiseks, lähtudes teie Customer Insights andmetest.</span><span class="sxs-lookup"><span data-stu-id="e44c4-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e44c4-105">Nende API-de üksikasjad on toodud [Customer Insights API-de ülevaade](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="e44c4-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="e44c4-106">Need sisaldavad lisateavet toimingute, parameetrite ja vastuste kohta.</span><span class="sxs-lookup"><span data-stu-id="e44c4-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="e44c4-107">Selles artiklis kirjeldatakse, kuidas pääseda juurde Customer Insights API-dele, luua Azure'i rakenduse registreerimine ja alustada saadavalolevate klienditeekidega.</span><span class="sxs-lookup"><span data-stu-id="e44c4-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="e44c4-108">Customer Insightsi API-de proovimise alustamine</span><span class="sxs-lookup"><span data-stu-id="e44c4-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="e44c4-109">[Logige sisse](https://home.ci.ai.dynamics.com) Customer Insightsi.</span><span class="sxs-lookup"><span data-stu-id="e44c4-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="e44c4-110">Kui teil pole veel tellimust, [registreeruge Customer Insightsi prooviversiooni kasutamiseks](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="e44c4-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="e44c4-111">Customer Insightsi keskkonnas API-de lubamiseks minge jaotisse **Haldus** > **Õigused**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="e44c4-112">Selleks on teil vaja administraatoriõigusi.</span><span class="sxs-lookup"><span data-stu-id="e44c4-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="e44c4-113">Minge vahekaardile **API-d** ja valige nupp **Luba**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="e44c4-114">API-de lubamine loob teie eksemplari jaoks esmase ja teisese tellimuse võtme, mida kasutatakse API-de päringutes.</span><span class="sxs-lookup"><span data-stu-id="e44c4-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="e44c4-115">Saate võtmed uuesti luua, kui valite **Loo esmane uuesti** või **Loo teisene uuesti** jaotises **Haldus** > **Õigused** > **API-d**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insightsi API-de lubamine":::

1. <span data-ttu-id="e44c4-117">[API-de proovimiseks](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) valige **Tutvuge meie API-dega**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="e44c4-118">Valige API-toiming ja valige **Proovi**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="e44c4-119">Määrake külgpaanil ripploendi **Autoriseerimine** väärtuseks **kaudne**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="e44c4-120">Päis `Authorization` lisatakse koos kandja tokeniga.</span><span class="sxs-lookup"><span data-stu-id="e44c4-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="e44c4-121">Teie tellimuse võti asustatakse automaatselt.</span><span class="sxs-lookup"><span data-stu-id="e44c4-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="e44c4-122">Soovi korral lisage kõik vajalikud päringuparameetrid.</span><span class="sxs-lookup"><span data-stu-id="e44c4-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="e44c4-123">Liikuge külgpaanis kõige alla ja valige **Saada**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="e44c4-124">HTTP-vastus kuvatakse varsti allpool.</span><span class="sxs-lookup"><span data-stu-id="e44c4-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Kuidas API-sid testida.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="e44c4-126">Uue rakenduse registreeringu loomine Azure'i portaalis</span><span class="sxs-lookup"><span data-stu-id="e44c4-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="e44c4-127">Need etapid aitavad teil kasutada Azure'i rakenduses Customer Insights API-sid, kasutades volitatud õigusi.</span><span class="sxs-lookup"><span data-stu-id="e44c4-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="e44c4-128">Viige esmalt lõpule [Alustamise jaotis](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="e44c4-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="e44c4-129">Logige [Azure'i portaali](https://portal.azure.com) sisse kontoga, mis pääseb juurde Customer Insightsi andmetele.</span><span class="sxs-lookup"><span data-stu-id="e44c4-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="e44c4-130">Valige vasakul **Rakenduse registreeringud**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="e44c4-131">Valige **Uus registreering**, sisestage rakenduse nimi ja valige kontotüüp.</span><span class="sxs-lookup"><span data-stu-id="e44c4-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="e44c4-132">Võite lisada ka ümbersuunamise URL-i.</span><span class="sxs-lookup"><span data-stu-id="e44c4-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="e44c4-133">http://localhost on piisav rakenduse arendamiseks teie kohalikus arvutis.</span><span class="sxs-lookup"><span data-stu-id="e44c4-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="e44c4-134">Minge uues rakenduse registreeringus jaotisse **API õigused**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="API-õiguste määramine rakenduse registreerimiseks.":::

1. <span data-ttu-id="e44c4-136">Valige **Lisa õigus** ja valige külgpaanil **Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="e44c4-137">**Õigusetüüp** valimiseks valige **delegeeritud õigused** ja seejärel valige **kasutaja kehastumine** õigused.</span><span class="sxs-lookup"><span data-stu-id="e44c4-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="e44c4-138">Valige **Õiguste lisamine**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-138">Select **Add permissions**.</span></span> <span data-ttu-id="e44c4-139">Kui teil on vaja juurdepääsu API-sse ilma, et kasutaja sisse logiks, vaadake üle jaotis [Serverist serverisse rakenduse õigused](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="e44c4-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="e44c4-140">Rakenduse registreerimise lõpetamiseks valige **Anna administraatori nõusolek...**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="e44c4-141">Saate kasutada selle rakenduse registreeringu rakenduse/kliendi ID-d Microsofti autentimisteegis (MSAL), et saada kandeluba, mida koos päringuga API-le saata.</span><span class="sxs-lookup"><span data-stu-id="e44c4-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Administraatori loa andmine.":::

<span data-ttu-id="e44c4-143">Lisateavet MSAL kohta leiate teemast [Microsofti autentimisteegi (MSAL) ülevaade](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="e44c4-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="e44c4-144">Azure'is rakenduse registreerimise kohta leiate lisateavet teemast [Rakenduse registreerimine](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="e44c4-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="e44c4-145">Lisateavet API-de kasutamise kohta meie klienditeekides leiate teemast [Customer Insights klienditeegid](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="e44c4-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="e44c4-146">Serverist serverisse rakenduse õigused</span><span class="sxs-lookup"><span data-stu-id="e44c4-146">Server-to-server application permissions</span></span>

<span data-ttu-id="e44c4-147">[Rakenduse registreerimise jaotises](#create-a-new-app-registration-in-the-azure-portal) kirjeldatakse, kuidas registreerida rakendus, mis nõuab kasutajalt autentimiseks sisselogimist.</span><span class="sxs-lookup"><span data-stu-id="e44c4-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="e44c4-148">Siit leiate teavet selle kohta, kuidas luua rakenduse registreering, mis ei vaja kasutaja sekkumist ja mida saab serveris käitada.</span><span class="sxs-lookup"><span data-stu-id="e44c4-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="e44c4-149">Minge Azure'i portaalis oma rakenduse registreeringus jaotisse **API õigused**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="e44c4-150">Valige **Lisa luba**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="e44c4-151">Valige vahekaart **APId, mida mu organisatsioon kasutab** ja valige loendist **Dynamics 365 AI Customer Insights /ide jaoks**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="e44c4-152">**Õigusetüüp** valimiseks valige **Rakenduse õigused** ja seejärel valige **CustomerInsights.Api.All** õigused.</span><span class="sxs-lookup"><span data-stu-id="e44c4-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="e44c4-153">Valige **Õiguste lisamine**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="e44c4-154">Minge oma rakenduse registreeringus tagasi jaotisse **API õigused**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="e44c4-155">Rakenduse registreerimise lõpetamiseks valige **Anna administraatori nõusolek...**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Administraatori loa andmine.":::

1. <span data-ttu-id="e44c4-157">Lõpetamiseks peame lisama rakenduse registreeringu nime Customer Insightsis kasutajana.</span><span class="sxs-lookup"><span data-stu-id="e44c4-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="e44c4-158">Avage Customer Insights, minge jaotisse **Haldus** > **Õigused** ja valige **Lisa kasutaja**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="e44c4-159">Otsige oma rakenduse registreeringu nime, valige see otsingutulemustest ja valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="e44c4-160">Customer Insightsi klienditeegid</span><span class="sxs-lookup"><span data-stu-id="e44c4-160">Customer Insights client libraries</span></span>

<span data-ttu-id="e44c4-161">See jaotis aitab teil alustada klienditeekide kasutamist, mis on saadaval Customer Insightsi API-de jaoks.</span><span class="sxs-lookup"><span data-stu-id="e44c4-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="e44c4-162">Kõik teegi lähtekoodid ja näidisrakendused leiate lehelt [Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="e44c4-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="e44c4-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="e44c4-163">C# NuGet</span></span>

<span data-ttu-id="e44c4-164">Teave selle kohta, kuidas alustada C# klienditeekide kasutamist, leiate aadressilt NuGet.org. Lisateavet NuGeti paketi kohta leiate teemast [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="e44c4-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="e44c4-165">See pakett kasutab praegu netstandard2.0 ja netcoreapp2.0 raamistikke.</span><span class="sxs-lookup"><span data-stu-id="e44c4-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="e44c4-166">C# klienditeegi lisamine C# projekti</span><span class="sxs-lookup"><span data-stu-id="e44c4-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="e44c4-167">Avage Visual Studios oma projekti **NuGeti paketihaldur**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="e44c4-168">Otsige API-t **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="e44c4-169">Selleks, et lisada pakett projekti, valige **Installi**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="e44c4-170">Teise võimalusena käivitage **NuGeti paketihalduri konsoolis** see käsk: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="e44c4-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="NuGeti paketi lisamine Visual Studio projekti":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="e44c4-172">C# klienditeegi kasutamine</span><span class="sxs-lookup"><span data-stu-id="e44c4-172">Use the C# client library</span></span>

1. <span data-ttu-id="e44c4-173">Kasutage [Microsofti autentimisteeki (MSAL)](/azure/active-directory/develop/msal-overview), et saada `AccessToken`, kasutades oma olemasolevat [Azure'i rakenduse registreeringut](#create-a-new-app-registration-in-the-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="e44c4-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="e44c4-174">Pärast õnnestunud autentimist ja loa omandamist looge uus või kasutage olemasolevat üksust `HttpClient` ning määrake üksuse **DefaultRequestHeaders "Authorization"** väärtuseks **Bearer <access token>** ja üksuse **Ocp-Apim-Subscription-Key** väärtuseks [**tellimuse võti**, mis pärineb teie Customer Insightsi keskkonnast](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="e44c4-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="e44c4-175">Vajadusel lähtestage päis **Autoriseerimine**.</span><span class="sxs-lookup"><span data-stu-id="e44c4-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="e44c4-176">Näiteks kui luba on aegunud.</span><span class="sxs-lookup"><span data-stu-id="e44c4-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="e44c4-177">Edastage `HttpClient` `CustomerInsights`i kliendi meetodisse.</span><span class="sxs-lookup"><span data-stu-id="e44c4-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpcliendi näidis":::

1. <span data-ttu-id="e44c4-179">Helistage kliendiga "laiendusmeetoditele" - näiteks `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="e44c4-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="e44c4-180">Kui eelistate juurdepääsu aluseks olevale üksusele `Microsoft.Rest.HttpOperationResponse`, kasutage „http message methods“, näiteks meetodit `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="e44c4-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="e44c4-181">Vastus tüüp on tõenäoliselt `object`, kuna meetod võib tagastada mitut tüüpi (nt `IList<InstanceInfo>` ja `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="e44c4-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="e44c4-182">Vastusetüübi kontrollimiseks saate objektid ohutult teisendada toimingu vastusetüüpideks, mida kirjeldatakse [API üksikasjade lehel](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="e44c4-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="e44c4-183">Kui päringu kohta on vaja rohkem teavet, kasutage **http-sõnumi meetodeid**, et pääseda juurde töötlemata vastuseobjektile.</span><span class="sxs-lookup"><span data-stu-id="e44c4-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="e44c4-184">NodeJS-i pakett</span><span class="sxs-lookup"><span data-stu-id="e44c4-184">NodeJS package</span></span>

<span data-ttu-id="e44c4-185">Kasutage NPM-i kaudu kättesaadavaid NodeJS-i klienditeeke: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="e44c4-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="e44c4-186">Pythoni pakett</span><span class="sxs-lookup"><span data-stu-id="e44c4-186">Python package</span></span>

<span data-ttu-id="e44c4-187">Kasutage PyPi kaudu kättesaadavaid Pythoni klienditeeke: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="e44c4-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
