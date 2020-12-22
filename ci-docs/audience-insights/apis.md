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
# <a name="work-with-customer-insights-apis"></a>Customer Insightsi API-dega töötamine

Dynamics 365 Customer Insights pakub API-sid, et luua rakendusi Customer Insightsis olevate andmete põhjal.

> [!IMPORTANT]
> Nende API-de üksikasjad on toodud [Customer Insightsi API-de ülevaates](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Need sisaldavad lisateavet toimingute, parameetrite ja vastuste kohta.

See artikkel annab juhiseid Customer Insightsi API-dele juurdepääsemise, Azure'i rakenduse registreeringu loomise kohta ning aitab alustada saadaolevate klienditeekide põhjal.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insightsi API-de proovimise alustamine

1. [Logige sisse](https://home.ci.ai.dynamics.com) Customer Insightsi. Kui teil pole veel tellimust, [registreeruge Customer Insightsi prooviversiooni kasutamiseks](https://aka.ms/tryci).

1. Customer Insightsi keskkonnas API-de lubamiseks minge jaotisse **Haldus** > **Õigused**. Selleks on teil vaja administraatoriõigusi.

1. Minge vahekaardile **API-d** ja valige nupp **Luba**.    
   API-de lubamine loob teie eksemplari jaoks esmase ja teisese tellimuse võtme, mida kasutatakse API-de päringutes. Saate võtmed uuesti luua, kui valite **Loo esmane uuesti** või **Loo teisene uuesti** jaotises **Haldus** > **Õigused** > **API-d**.

   :::image type="content" source="media/enable-apis.gif" alt-text="Customer Insightsi API-de lubamine":::

1. API-de proovimiseks valige **Tutvuge meie API-dega**.

1. Valige API-toiming ja valige **Proovi**.

1. Määrake külgpaanil rippmenüü **Autoriseerimine** väärtuseks **kaudne**. Päis `Authorization` lisatakse koos kandeloaga. Teie tellimuse võti asustatakse automaatselt.
  
1. Soovi korral lisage kõik vajalikud päringuparameetrid.

1. Liikuge külgpaanis kõige alla ja valige **Saada**.

HTTP-vastus kuvatakse varsti allpool.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Uue rakenduse registreeringu loomine Azure'i portaalis

Need juhised aitavad teil alustada Customer Insightsi API-de kasutamist Azure'i rakenduses, kasutades delegeeritud õigusi. Veenduge, et olete esiteks [tutvunud alustamise jaotisega](#get-started-trying-the-customer-insights-apis).

1. Logige [Azure'i portaali](https://portal.azure.com) sisse kontoga, mis pääseb juurde Customer Insightsi andmetele.

1. Valige vasakul **Rakenduse registreeringud**.

1. Valige **Uus registreering**, sisestage rakenduse nimi ja valige kontotüüp.
   Võite lisada ka ümbersuunamise URL-i. http://localhost on piisav rakenduse arendamiseks teie kohalikus arvutis.

1. Minge uues rakenduse registreeringus jaotisse **API õigused**.

1. Valige **Lisa õigus** ja valige külgpaanil **Customer Insights**.

1. Valige **õiguse tüübiks** **Delegeeritud õigused** ja valige õigus **user_impersonation**.

1. Valige **Õiguste lisamine**. Kui teil on vaja juurdepääsu API-sse ilma, et kasutaja sisse logiks, vaadake üle jaotis [Serverist serverisse rakenduse õigused](#server-to-server-application-permissions).

1. Rakenduse registreerimise lõpetamiseks valige **Anna administraatori nõusolek...**.

Saate kasutada selle rakenduse registreeringu rakenduse/kliendi ID-d Microsofti autentimisteegis (MSAL), et saada kandeluba, mida koos päringuga API-le saata.

Lisateavet MSAL kohta leiate teemast [Microsofti autentimisteegi (MSAL) ülevaade](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

Azure'is rakenduste registreerimise kohta lisateabe saamiseks lugege teemat [Uus Azure'i portaali rakenduse registreerimise kogemus](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

Lisateavet meie klienditeekide API-de kasutamise kohta leiate jaotisest [Customer Insightsi klienditeegid](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Serverist serverisse rakenduse õigused

[Rakenduse registreerimise jaotises](#create-a-new-app-registration-in-the-azure-portal) kirjeldatakse, kuidas registreerida rakendus, mis nõuab kasutajalt autentimiseks sisselogimist. Siit leiate teavet selle kohta, kuidas luua rakenduse registreering, mis ei vaja kasutaja sekkumist ja mida saab serveris käitada.

1. Minge Azure'i portaalis oma rakenduse registreeringus jaotisse **API õigused**.

1. Valige **Lisa õigus** ja valige külgpaanil **Customer Insights**.

1. Valige **õiguse tüübiks** **Rakenduse õigused** ja valige õigus **CustomerInsights.Api.All**.

1. Valige **Õiguste lisamine**.

1. Administraatori nõusoleku andmiseks selles rakenduse õiguses peate lisama teenusesubjekti.

   1. Installige Azure Active Directory (AD) PowerShelli moodul: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. Looge ühendus oma AD kontoga: `Connect-AzureAD -TenantId <your tenant id>`. Oma rentniku ID leiate jaotisest **Ülevaade** > **Azure Active Directory**.
   1. Azure AD teenusesubjekti lisamiseks käivitage järgmine käsk : `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` Parameeter AppId on seotud Customer Insightsi API rakendusega.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="Näidisteenusesubjekt":::

1. Minge oma rakenduse registreeringus tagasi jaotisse **API õigused**.

1. Rakenduse registreerimise lõpetamiseks valige **Anna administraatori nõusolek...**.

1. Lõpetamiseks peame lisama rakenduse registreeringu nime Customer Insightsis kasutajana.    
   Avage Customer Insights, minge jaotisse **Haldus** > **Õigused** ja valige **Lisa kasutaja**.

1. Otsige oma rakenduse registreeringu nime, valige see otsingutulemustest ja valige **Salvesta**.

## <a name="customer-insights-client-libraries"></a>Customer Insightsi klienditeegid

See jaotis aitab teil alustada klienditeekide kasutamist, mis on saadaval Customer Insightsi API-de jaoks.

### <a name="c-nuget"></a>C# NuGet

Teave selle kohta, kuidas alustada C# klienditeekide kasutamist, leiate aadressilt NuGet.org. Lisateavet NuGeti paketi kohta leiate teemast [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). See pakett kasutab praegu netstandard2.0 ja netcoreapp2.0 raamistikke.

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# klienditeegi lisamine C# projekti

1. Avage Visual Studios oma projekti **NuGeti paketihaldur**.

1. Otsige API-t **Microsoft.Dynamics.CustomerInsights.Api**.

1. Selleks, et lisada pakett projekti, valige **Installi**.
   Teise võimalusena käivitage **NuGeti paketihalduri konsoolis** see käsk: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="NuGeti paketi lisamine Visual Studio projekti":::

#### <a name="use-the-c-client-library"></a>C# klienditeegi kasutamine

1. Kasutage [Microsofti autentimisteeki (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview), et saada `AccessToken`, kasutades oma olemasolevat [Azure'i rakenduse registreeringut](#create-a-new-app-registration-in-the-azure-portal).

1. Pärast õnnestunud autentimist ja loa omandamist looge uus või kasutage olemasolevat üksust `HttpClient` ning määrake üksuse **DefaultRequestHeaders "Authorization"** väärtuseks **Bearer <access token>** ja üksuse **Ocp-Apim-Subscription-Key** väärtuseks [**tellimuse võti**, mis pärineb teie Customer Insightsi keskkonnast](#get-started-trying-the-customer-insights-apis).    
   Vajadusel lähtestage päis **Autoriseerimine**. Näiteks kui luba on aegunud.

1. Edastage `HttpClient` `CustomerInsights`i kliendi meetodisse.

   :::image type="content" source="media/httpclient-sample.png" alt-text="Httpcliendi näidis":::

1. Kutsuge kliendiga „laiendusmeetodeid“, näiteks `GetAllInstancesAsync`. Kui eelistate juurdepääsu aluseks olevale üksusele `Microsoft.Rest.HttpOperationResponse`, kasutage „http-sõnumi meetodeid“, näiteks meetodit `GetAllInstancesWithHttpMessagesAsync`.

1. Vastus tüüp on tõenäoliselt `object`, kuna meetod võib tagastada mitut tüüpi (nt `IList<InstanceInfo>` ja `ApiErrorResult`). Vastusetüübi kontrollimiseks saate objektid ohutult teisendada toimingu vastusetüüpideks, mida kirjeldatakse [API üksikasjade lehel](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).    
   Kui päringu kohta on vaja rohkem teavet, kasutage **http-sõnumi meetodeid**, et pääseda juurde töötlemata vastuseobjektile.
