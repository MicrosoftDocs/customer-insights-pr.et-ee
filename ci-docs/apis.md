---
title: API-dega töötamine
description: Kasutage API-sid ja olge teadlik nende piirangutest.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: a460ec87ec85f0614f944d352588d4ca899f8120
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755445"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insightsi API-dega töötamine

Dynamics 365 Customer Insights pakub API-sid oma rakenduste ehitamiseks, lähtudes teie Customer Insights andmetest.

> [!IMPORTANT]
> Nende API-de üksikasjad on toodud [Customer Insights API-de ülevaade](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Need sisaldavad lisateavet toimingute, parameetrite ja vastuste kohta.

Selles artiklis kirjeldatakse, kuidas pääseda juurde Customer Insightsi API-dele, luua Azure'i rakenduse registreerimine ja alustada klienditeekidega.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insightsi API-de proovimise alustamine

1. [Logige sisse](https://home.ci.ai.dynamics.com) Customer Insightsi. Kui teil pole veel tellimust, [registreeruge Customer Insightsi prooviversiooni kasutamiseks](https://aka.ms/tryci).

1. Customer Insightsi keskkonnas API-de lubamiseks minge jaotisse **Haldus** > **Õigused**. Selleks on teil vaja administraatoriõigusi.

1. Minge vahekaardile **API-d** ja valige nupp **Luba**.    
 
   API-de lubamine loob teie eksemplari jaoks esmase ja teisese tellimuse võtme, mida kasutatakse API-de päringutes. Saate võtmed uuesti luua, kui valite **Loo esmane uuesti** või **Loo teisene uuesti** jaotises **Haldus** > **Õigused** > **API-d**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. [API-de proovimiseks](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) valige **Tutvuge meie API-dega**.

1. Valige API-toiming ja valige **Proovi**.

1. Määrake külgpaanil ripploendi **Autoriseerimine** väärtuseks **kaudne**. Päis `Authorization` lisatakse koos kandja tokeniga. Teie tellimuse võti asustatakse automaatselt.
  
1. Soovi korral lisage kõik vajalikud päringuparameetrid.

1. Liikuge külgpaanis kõige alla ja valige **Saada**.

HTTP-vastus kuvatakse varsti allpool.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Uue rakenduse registreeringu loomine Azure'i portaalis

Need etapid aitavad teil kasutada Azure'i rakenduses Customer Insights API-sid, kasutades volitatud õigusi. Viige esmalt lõpule [Alustamise jaotis](#get-started-trying-the-customer-insights-apis).

1. Logige [Azure'i portaali](https://portal.azure.com) sisse kontoga, mis pääseb juurde Customer Insightsi andmetele.

1. Valige vasakul **Rakenduse registreeringud**.

1. Valige **Uus registreering**, sisestage rakenduse nimi ja valige kontotüüp.
 
   Võite lisada ka ümbersuunamise URL-i. http://localhost on piisav rakenduse arendamiseks teie kohalikus arvutis.

1. Minge uues rakenduse registreeringus jaotisse **API õigused**.

<!--   :::image type="content" source="media/app-registration-1.gif" alt-text="How to set API permissions in App registration."::: -->

1. Valige **Lisa õigus** ja valige külgpaanil **Customer Insights**.

1. **Õigusetüüp** valimiseks valige **delegeeritud õigused** ja seejärel valige **kasutaja kehastumine** õigused.

1. Valige **Õiguste lisamine**. Kui teil on vaja juurdepääsu API-sse ilma, et kasutaja sisse logiks, vaadake üle jaotis [Serverist serverisse rakenduse õigused](#server-to-server-application-permissions).

1. Rakenduse registreerimise lõpetamiseks valige **Anna administraatori nõusolek...**.

Saate kasutada selle rakenduse registreeringu rakenduse/kliendi ID-d Microsofti autentimisteegis (MSAL), et saada kandeluba, mida koos päringuga API-le saata.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Lisateavet MSAL kohta leiate teemast [Microsofti autentimisteegi (MSAL) ülevaade](/azure/active-directory/develop/msal-overview).

Azure'is rakenduse registreerimise kohta leiate lisateavet teemast [Rakenduse registreerimine](/graph/auth-register-app-v2).

Lisateavet API-de kasutamise kohta meie klienditeekides leiate teemast [Customer Insights klienditeegid](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Serverist serverisse rakenduse õigused

[Rakenduse registreerimise jaotises](#create-a-new-app-registration-in-the-azure-portal) kirjeldatakse, kuidas registreerida rakendus, mis nõuab kasutajalt autentimiseks sisselogimist. Siit saate teada, kuidas luua rakenduse registreerimine, mis ei vaja kasutajate suhtlemist ja mida saab serveris käitada.

1. Minge Azure'i portaalis oma rakenduse registreeringus jaotisse **API õigused**.

1. Valige **Lisa luba**. 

1. Valige vahekaart **APId, mida mu organisatsioon kasutab** ja valige loendist **Dynamics 365 AI Customer Insights /ide jaoks**. 

1. **Õigusetüüp** valimiseks valige **Rakenduse õigused** ja seejärel valige **CustomerInsights.Api.All** õigused.

1. Valige **Õiguste lisamine**.

1. Minge oma rakenduse registreeringus tagasi jaotisse **API õigused**.

1. Rakenduse registreerimise lõpetamiseks valige **Anna administraatori nõusolek...**.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Lõpetamiseks peame lisama rakenduse registreeringu nime Customer Insightsis kasutajana.  
   
   Avage Customer Insights, minge jaotisse **Haldus** > **Õigused** ja valige **Lisa kasutaja**.

1. Otsige oma rakenduse registreeringu nime, valige see otsingutulemustest ja valige **Salvesta**.

## <a name="sample-queries"></a>Näidispäringud

Oleme koostanud lühikese loendi OData näidispäringutest, et töötada API-dega: [OData päringu näited](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insightsi klienditeegid

See jaotis aitab teil alustada klienditeekide kasutamist, mis on saadaval Customer Insightsi API-de jaoks. Kõik teegi lähtekoodid ja näidisrakendused leiate lehelt [Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Teave selle kohta, kuidas alustada C# klienditeekide kasutamist, leiate aadressilt NuGet.org. Lisateavet NuGeti paketi kohta leiate teemast [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). See pakett kasutab praegu netstandard2.0 ja netcoreapp2.0 raamistikke.

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# klienditeegi lisamine C# projekti

1. Avage Visual Studios oma projekti **NuGeti paketihaldur**.

1. Otsige API-t **Microsoft.Dynamics.CustomerInsights.Api**.

1. Selleks, et lisada pakett projekti, valige **Installi**.
 
   Teise võimalusena käivitage **NuGeti paketihalduri konsoolis** see käsk: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>C# klienditeegi kasutamine

1. Kasutage [Microsofti autentimisteeki (MSAL)](/azure/active-directory/develop/msal-overview), et saada `AccessToken`, kasutades oma olemasolevat [Azure'i rakenduse registreeringut](#create-a-new-app-registration-in-the-azure-portal).

1. Pärast loa edukat autentimist ja omandamist ehitage uus või kasutage olemasolevat, mille `HttpClient` vaikerequestHeadersi "Autoriseerimine"**on seatud Bearerile**"juurdepääsuluba"**ja** Ocp-Apim-Subscription-Key **komplektile tellimuse võtmele**[**teie Customer Insightsi keskkonnast**.](#get-started-trying-the-customer-insights-apis)   
 
   Vajadusel lähtestage päis **Autoriseerimine**. Näiteks kui luba on aegunud.

1. Edastage `HttpClient` `CustomerInsights`i kliendi meetodisse.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Helistage kliendiga "laiendusmeetoditele" - näiteks `GetAllInstancesAsync`. Kui eelistate juurdepääsu aluseks olevale üksusele `Microsoft.Rest.HttpOperationResponse`, kasutage „http message methods“, näiteks meetodit `GetAllInstancesWithHttpMessagesAsync`.

1. Vastus tüüp on tõenäoliselt `object`, kuna meetod võib tagastada mitut tüüpi (nt `IList<InstanceInfo>` ja `ApiErrorResult`). Tagastustüübi kontrollimiseks kasutate selle toimingu api üksikasjade lehel [määratud](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) vastusetüüpides olevaid objekte.    
   
   Kui päringu kohta on vaja rohkem teavet, kasutage **http-sõnumi meetodeid**, et pääseda juurde töötlemata vastuseobjektile.

### <a name="nodejs-package"></a>NodeJS-i pakett

Kasutage NPM-i kaudu kättesaadavaid NodeJS-i klienditeeke: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Pythoni pakett

Kasutage PyPi kaudu kättesaadavaid Pythoni klienditeeke: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]