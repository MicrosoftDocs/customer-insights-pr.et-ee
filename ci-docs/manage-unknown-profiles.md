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
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776816"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Tundmatute profiilide haldamine Customer Insightsi abil

Internetikasutajad on internetis sageli tuvastamata või anonüümsed. Isegi kõige lojaalsemad kliendid võivad tunduda "tundmatud", kui nad pole erinevatesse seadmetesse sisse logitud. Paljude kaubamärkide puhul on tuntud või autenditud kasutajad vähemuses, hoolimata klientide kasvavatest ootustest isikupärastamise suhtes. Kuna kõne all on kolmandate osapoolte küpsiste tulevik, on kasutajaeelistuste haldamine selle asemel esimese osapoole andmete põhjal isikupärastatud kogemuste saavutamiseks ülioluline.

Meeldejääv isikupärastamine sõltub sellest, kui hästi te oma klienti tunnete, ja Customer Insights aitab teil seda teha, jälgides kõiki oma kliente.  Te ei pea klienditeekond alguses kogutud andmete kasutamist piirama ega lõpetama. Customer Insights võimaldab teil tuua oma andmed, et luua tundmatutele kasutajatele kliendiprofiil. Seejärel saate seda profiili kasutada edasisteks toiminguteks, hoolimata puuduvast kontaktteabest. Importige esimese osapoole andmeid sellistest allikatest nagu veebi-, mobiili- või CRM-süsteemid Customer Insightsi, et kliendiprofiile pidevalt rikastada. Kui ühendate rohkem suhtlusi, [muutke *tundmatu* klient teadaolevaks *kliendiks*](unknown-to-known.md).

## <a name="sample-scenario"></a>Näidisstsenaarium

Oletame, et kasutaja kasutab teie e-kaubanduse saidi sirvimiseks oma mobiilseadet. Veebisait määrab külastajale unikaalse identifikaatorina "mobile_guest123" ja hakkate koguma käitumistegevusi nende veebitegevuse põhjal. Näiteks milliseid lehti nad külastasid, kui palju aega nad nendel lehtedel veetsid või millistel linkidel nad klõpsasid. Te ei tea nende nime ega e-posti aadressi, kuid need andmed võivad aidata pakkuda brändidele sisukat ülevaadet selle konkreetse kasutaja kohta. Saate need statistikad omakorda tööle panna järgmisel korral, kui kasutaja saiti külastab. Küsige kliendiülevaadetest "mobile_guest123", et tuua kasutaja segmentide loend (nt "orgaaniline", "mobiilsed ettetellimiskliendid", "väärtuslikud kliendid" jne) või tuua profiil isikupärastatud veebikogemuse loomiseks. Sama tegemiseks saate andmed eksportida ka mis tahes aktiveerimissüsteemi.

## <a name="prerequisites"></a>eeltingimused

- Esimese osapoole andmete allaneelamine Customer Insightsi
- Igal olemil on kordumatu ID, mis on määratud primaarvõtmeks
- Iga olem, millel on isikupärastamiseks primaarvõti, on ühendatud
- Teie veebisaidi sisuhaldussüsteem saab kasutada API-sid (veebi isikupärastamiseks, mis põhineb otsesuhtlusel Customer Insightsiga)

Järgmine tabel näitab lihtsustatud näidet selle kohta, kuidas väärtuslikke veebisündmusi võidakse jäädvustada.

|Sündmuse ID|EventTimeStamp|Kasutaja ID|Esmane võti|Sündmuse nimi|
|--|--|--|--|--|
|1|09-15-2022 9:00:00|ABC123|CookieID1|Toote vaade|
|2|09-18-2022 10:05:00|ABC123|CookieID1|Toote vaade|
|3|09-18-2022 10:10:00|ABC123|CookieID1|Lisa ostukorvi|
|4|09-21-2022 09:05:00|ABC123|CookieID1|Toote vaade|

## <a name="data-ingestion"></a>Andmete valmendamine

Lisateavet andmete allaneelamiseks saadaolevate suvandite kohta leiate teemast [Andmeallikate ülevaade](data-sources.md).

## <a name="data-unification"></a>Andmete koondamine

Lisateavet kliendiprofiilide ühtlustamise kohta leiate teemast [Andmete ühendamise ülevaade](data-unification.md).

## <a name="get-insights"></a>Hangi ülevaateid

[Rikastage](enrichment-hub.md) oma andmeid, koostage [meetmeid](measures.md) ja looge [segmente](segments.md) edasiseks aktiveerimiseks.

Näiteks saate luua tundmatute kasutajate segmente, kes sirvisid samu tootelehti, kuid ei lõpetanud kunagi kassat.

## <a name="activation"></a>Aktiveerimine

Kui teie andmed Customer Insightsis ja ülevaated on tööle asumiseks valmis, saate isikupärastamiseks kasutada Customer Insightsi.

1. OData API kasutamine [segmendi liikmesuse või kliendiprofiili toomiseks Rohkem näiteid leiate jaotisest](apis.md) OData päringu näited Customer Insightsi API-de [kohta](odata-examples.md).

1. [Eksportige](export-destinations.md) oma andmed aktiveerimissüsteemidesse.

Näide: tundmatu kasutaja külastab veebisaiti mitu korda ja külastab nahast kingade erinevate mudelite tootelehti. Kui need andmed on Customer Insightsis saadaval, saate kaasata tundmatu kasutaja nahast kingadest huvitatud inimeste segmenti. Kasutage seda segmenti, et teavitada oma veebisaiti isikupärastamisest naasvate külastajate jaoks. Järgmisel külastusel tunneb sait tundmatu kasutaja ära ja võib neile pakkuda 10% kupongi nahast kingadele.

[!INCLUDE [footer-include](includes/footer-banner.md)]
