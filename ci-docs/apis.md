---
title: Customer Insightsi API-dega töötamine
description: Kasutage API-sid ja olge teadlik nende piirangutest.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387335"
---
# <a name="work-with-customer-insights-apis"></a>Customer Insightsi API-dega töötamine

Dynamics 365 Customer Insights pakub API-sid oma rakenduste ehitamiseks, lähtudes teie Customer Insights andmetest.

> [!IMPORTANT]
> Nende API-de üksikasjad on toodud [Customer Insights API-de ülevaade](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Need sisaldavad lisateavet toimingute, parameetrite ja vastuste kohta.

Proovige Customer Insightsi API-sid, looge Azure'i rakenduse registreerimine ja alustage klienditeekide kasutamist.

## <a name="get-started-trying-the-customer-insights-apis"></a>Customer Insightsi API-de proovimise alustamine

Lubage Customer Insightsi API-d ja proovige neid. Customer Insightsi administraator peab lubama API juurdepääsu Customer Insightsile. Kui juurdepääs on lubatud, saab iga kasutaja kasutada API-d koos tellimisvõtmega.

1. [Logige sisse](https://home.ci.ai.dynamics.com) Customer Insightsi. Kui teil pole veel tellimust, [registreeruge Customer Insightsi prooviversiooni kasutamiseks](https://aka.ms/tryci).

1. Minge jaotisse **Administraatori turve** > **ja valige** vahekaart API-d **·**.

1. Kui API juurdepääs keskkonnale pole seadistatud, valige **Luba**.

   API-de lubamine loob teie eksemplari jaoks esmase ja teisese tellimuse võtme, mida kasutatakse API-de päringutes. Klahvide regenereerimiseks valige vahekaardil API-d **primaarne** või **Taasta sekundaarne** **.**

1. API-de proovimiseks valige [**Avasta meie API-d**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) .

1. Otsige ja valige API toiming ning valige **Proovi**.

   :::image type="content" source="media/try-api.png" alt-text="Kuidas API-sid testida.":::

1. Määrake külgpaanil ripploendi **Autoriseerimine** väärtuseks **kaudne**. Päis `Authorization` lisatakse koos kandja tokeniga. Teie tellimuse võti täidetakse automaatselt.
  
1. Soovi korral lisage kõik vajalikud päringuparameetrid.

1. Liikuge külgpaanis kõige alla ja valige **Saada**.

   HTTP-vastus kuvatakse paani allosas.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Uue rakenduse registreeringu loomine Azure'i portaalis

Looge uus [rakenduse registreerimine](/graph/auth-register-app-v2) , et kasutada delegeeritud õiguste abil Azure'i rakenduses Customer Insightsi API-sid.

1. [Täitke jaotis](#get-started-trying-the-customer-insights-apis) Alustamine.

1. Logige [Azure'i portaali](https://portal.azure.com) sisse kontoga, mis pääseb juurde Customer Insightsi andmetele.

1. Otsige üles ja seejärel valige **Rakenduse registreerimised**.

1. Valige **Uus registreering**, sisestage rakenduse nimi ja valige kontotüüp.

   Võite lisada ka ümbersuunamise URL-i. http://localhost on piisav rakenduse arendamiseks teie kohalikus arvutis.

1. Valige **Registreeri**.

1. Minge uues rakenduse registreeringus jaotisse **API õigused**.

1. Valige **Lisa õigus** ja valige **külgpaanil Dynamics 365 AI for Customer Insights** .

1. **Õigusetüüp** valimiseks valige **delegeeritud õigused** ja seejärel valige **kasutaja kehastumine** õigused.

1. Valige **Õiguste lisamine**.

1. Rakenduse registreerimise lõpetamiseks valige **Anna administraatori nõusolek...**.

1. API-le juurdepääsemiseks ilma kasutajat sisse logimata avage [serverivahelise rakenduse õigused](#server-to-server-application-permissions).

Rakenduse/kliendi ID-d saate kasutada selle rakenduse registreerimiseks Microsofti autentimise teegis [(MSAL),](/azure/active-directory/develop/msal-overview) et saada esitaja luba, mille koos taotlusega API-le saata.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Lisateavet API-de kasutamise kohta meie klienditeekides leiate teemast [Customer Insights klienditeegid](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Serverist serverisse rakenduse õigused

Looge rakenduse registreerimine, mis ei vaja kasutaja sekkumist ja mida saab serveris käivitada.

1. Minge Azure'i portaalis oma rakenduse registreeringus jaotisse **API õigused**.

1. Valige **Lisa luba**.

1. Valige vahekaart **APId, mida mu organisatsioon kasutab** ja valige loendist **Dynamics 365 AI Customer Insights /ide jaoks**.

1. **Õigusetüüp** valimiseks valige **Rakenduse õigused** ja seejärel valige **CustomerInsights.Api.All** õigused.

1. Valige **Õiguste lisamine**.

1. Minge oma rakenduse registreeringus tagasi jaotisse **API õigused**.

1. Rakenduse registreerimise lõpetamiseks valige **Anna administraatori nõusolek...**.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Lisage rakenduse kasutajaks registreerimise nimi Customer Insightsis.

   1. Avage Customer Insights, avage **Administraatori turve** > **ja valige** Lisa **kasutajaid**.

   1. Otsige oma rakenduse registreeringu nime, valige see otsingutulemustest ja valige **Salvesta**.

## <a name="sample-queries"></a>Päringute näidised

API-dega töötamiseks vajalike OData näidispäringute lühiloendi leiate OData [päringute näidetest](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Customer Insightsi klienditeegid

Alustage Customer Insightsi API-de jaoks saadaolevate klienditeekide kasutamist. Kõik teegi lähtekoodid ja näidisrakendused leiate lehelt [Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Kasutage C# klienditeeke saidilt NuGet.org. Praegu on pakett suunatud netstandard2.0 ja netcoreapp2.0 raamistikele. Lisateavet paketi kohta leiate jaotisest NuGet [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>C# klienditeegi lisamine C# projekti

1. Avage Visual Studios oma projekti **NuGeti paketihaldur**.

1. Otsige API-t **Microsoft.Dynamics.CustomerInsights.Api**.

1. Selleks, et lisada pakett projekti, valige **Installi**.

   Teise võimalusena käivitage **NuGeti paketihalduri konsoolis** see käsk: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>C# klienditeegi kasutamine

1. Kasutage [Microsofti autentimisteeki (MSAL)](/azure/active-directory/develop/msal-overview), et saada `AccessToken`, kasutades oma olemasolevat [Azure'i rakenduse registreeringut](#create-a-new-app-registration-in-the-azure-portal).

1. Pärast tõendi edukat autentimist ja hankimist looge uus või kasutage olemasolevat, kui DefaultRequestHeadersi "Autoriseerimine"`HttpClient` väärtuseks **on seatud Bearer "access token"** ja **Ocp-Apim-Subscription-Key**, mis on seatud teie Customer Insightsi keskkonna **tellimisvõtmele**[**.**](#get-started-trying-the-customer-insights-apis)   

   Vajadusel lähtestage päis **Autoriseerimine**. Näiteks kui luba on aegunud.

1. Edastage `HttpClient` `CustomerInsights`i kliendi meetodisse.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Kutsuge kliendiga „laiendusmeetodeid“, näiteks `GetAllInstancesAsync`. Kui eelistatakse juurdepääsu alusvarale `Microsoft.Rest.HttpOperationResponse` , kasutage näiteks `GetAllInstancesWithHttpMessagesAsync`"http-sõnumi meetodeid".

1. Vastus on tõenäoliselt `object` tüüp, kuna meetod võib tagastada mitu tüüpi (näiteks `IList<InstanceInfo>` ja `ApiErrorResult`). Tagastustüübi kontrollimiseks kasutage selle toimingu API üksikasjade lehel [määratud](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) vastusetüüpide objekte.

   Kui päringu kohta on vaja rohkem teavet, kasutage **http-sõnumi meetodeid**, et pääseda juurde töötlemata vastuseobjektile.

### <a name="nodejs-package"></a>NodeJS-i pakett

Kasutage NPM-i kaudu kättesaadavaid NodeJS-i klienditeeke: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Pythoni pakett

Kasutage PyPi kaudu kättesaadavaid Pythoni klienditeeke: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
