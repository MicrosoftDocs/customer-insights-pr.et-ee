---
title: Tundmatute profiilide haldamine Customer Insightsi abil
description: Töötage tundmatute kliendiprofiilidega, mis on loodud ja mida hallatakse rakenduses Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: d7e5050ee5832df5ecf40a352f7ea8d42830fa45
ms.sourcegitcommit: f6b6a4c4ce9cf12e449488b24aab80a2cbfe0c47
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/21/2022
ms.locfileid: "9556391"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Tundmatute profiilide haldamine Customer Insightsi abil

Internetikasutajad on internetis sageli tundmatud ja anonüümsed. Kui nad pole sisse logitud, kuna nad kasutavad erinevaid seadmeid või kanaleid, kehtib see isegi kõige lojaalsemate klientide kohta. Kuna kolmanda osapoole küpsised kaovad tõenäoliselt varsti, on kasutajaeelistuste haldamine esimese osapoole andmete põhjal diferentseeritud isikupärastatud kasutuskogemuse saavutamiseks ülioluline. Paljude kaubamärkide puhul on tuntud või autenditud kasutajad vähemuses, hoolimata klientide kasvavatest ootustest isikupärastamise suhtes. Ettevõtetel on hea teada, kes on nende kliendid, tuginedes usaldusväärsetele, üksikasjalikele ja ühtsetele andmetele.

Meeldejääv isikupärastamine sõltub teie kliendiandmete rikkusest ja täielikkusest ning Customer Insights aitab teil neid eesmärke saavutada. Te ei pea klienditeekond alguses kogutud andmete kasutamist piirama ega lõpetama. Customer Insights võimaldab teil tuua oma andmed, et luua tundmatutele kasutajatele kliendiprofiil. Seejärel saate seda profiili kasutada edasisteks toiminguteks, hoolimata puuduvast kontaktteabest. Kliendiprofiilide pideva rikastamiseks importige esimese osapoole andmed sellistest allikatest nagu veebi-, mobiili- või CRM-süsteemid Customer Insightsi. Kui ühendate rohkem suhtlusi, [muutke *tundmatu* klient teadaolevaks *kliendiks*](unknown-to-known.md).

## <a name="sample-scenario"></a>Näidisstsenaarium

E-kaubandus on viimase kümne aasta kõige kiiremini kasvav kanal. Oletame, et kasutaja kasutab teie e-kaubanduse saidi sirvimiseks oma mobiilseadet. Veebisait määrab külastajale kordumatuks identifikaatoriks "mobile_guest123" ja te hakkate koguma käitumistegevusi tema veebitegevuse põhjal. Näiteks milliseid lehti nad külastasid, kui palju aega nad nendel lehtedel veetsid või millistel linkidel klõpsasid. Te ei tea nende nime ega e-posti aadressi, kuid need andmed võivad aidata brändidel selle konkreetse kasutaja kohta sisukat teavet anda. Omakorda saate need ülevaated tööle panna järgmisel korral, kui kasutaja saiti külastab. Küsige Customer Insightsi kohta teadet "mobile_guest123", et tuua kasutaja segmentide loend (nt "orgaanilised kliendid", "mobiilsed ettetellimiskliendid", "väärtuslikud kliendid" jne) või tuua profiil isikupärastatud veebikogemuse loomiseks. Sama tegemiseks saate andmed eksportida ka mis tahes aktiveerimissüsteemi.

## <a name="prerequisites"></a>eeltingimused

- Esimese osapoole andmete allaneelamine Customer Insightsi
- Igal olemil on kordumatu ID, mis on määratud primaarvõtmeks
- Iga isikupärastamiseks primaarvõtmega olem on ühtne
- Teie veebisaidi sisuhaldussüsteem on võimeline kasutama API-sid (veebi isikupärastamiseks, mis põhineb otsesel suhtlusel Customer Insightsiga)

Järgmises tabelis on toodud lihtsustatud näide sellest, kuidas väärtuslikke veebisündmusi võidakse jäädvustada.

|Sündmuse ID|EventTimeStamp|Kasutajatunnus|Esmane võti|Sündmuse nimi|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|abc123|CookieID1|Toote vaade|
|2|09-18-2022 10:05:00|abc123|CookieID1|Toote vaade|
|3|09-18-2022 10:10:00|abc123|CookieID1|Lisa ostukorvi|
|4|09-21-2022 09:05:00|abc123|CookieID1|Toote vaade|

## <a name="data-ingestion"></a>Andmete valmendamine

Lisateavet andmete allaneelamiseks saadaolevate suvandite kohta leiate teemast [Andmeallikate ülevaade](data-sources.md).

## <a name="data-unification"></a>Andmete koondamine

Lisateavet kliendiprofiilide ühendamise kohta leiate teemast [Andmete ühendamise ülevaade](data-unification.md).

## <a name="get-insights"></a>Hangi ülevaateid

[Rikastage](enrichment-hub.md) oma andmeid, koostage [mõõtühikuid](measures.md) ja looge [segmente](segments.md) edasiseks aktiveerimiseks.

Näiteks saate luua segmente tundmatutest kasutajatest, kes sirvisid samu tootelehti, kuid ei lõpetanud kunagi kassat.

## <a name="activation"></a>Aktiveerimine

Kui teie andmed on Customer Insightsis ja teie statistika on töö alustamiseks valmis, saate isikupärastamiseks kasutada Customer Insightsi.

1. [OData API kasutamine](apis.md) segmendi liikmesuse või kliendiprofiili toomiseks Rohkem näiteid leiate teemast [OData päringunäited Customer Insightsi API-de](odata-examples.md) kohta.

1. [Eksportige](export-destinations.md) oma andmed aktiveerimissüsteemidesse.

Näide: tundmatu kasutaja külastab veebisaiti mitu korda ja külastab erinevate nahast kingade mudelite tootelehti. Kui need andmed on Customer Insightsis saadaval, saate kaasata tundmatu kasutaja nahast kingadest huvitatud inimeste segmenti. Kasutage seda segmenti, et teavitada oma veebisaidi loomise isikupärastamisest tagasipöörduvate külastajate jaoks. Järgmisel külastusel tunneb sait tundmatu kasutaja ära ja võib pakkuda neile nahast kingade 10% kupongi.

[!INCLUDE [footer-include](includes/footer-banner.md)]
