---
title: Kliendiprofiilide vaatamine
description: Saate ühendatud ülevaate oma koondatud kliendiandmetest.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 45ef6abcd612178a097569825e32ff9ac779de01
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642504"
---
# <a name="customer-profiles"></a>Kliendi profiilid

Lehel **Kliendid** kuvatakse teie ühendatud kliendiprofiilide ühendatud vaade. Kliendiprofiilid on saadaval pärast [olemi Unified Customer loomist](data-unification.md). Lehel saate otsida kliente ja määratleda selle otsingu registri.

Kliendid võivad olla üksikisikud või organisatsioonid. Iga kliendiprofiili tähistab paan. Kasutage lehekülgedena kasutamise juhtelemente, et saada rohkem kirjeid. Kaardil kuvatakse *Kliendi* olemi väljad, nagu see on määratletud **Otsingu- ja filtriregistris**. Iga kaardi väljade järjestuse valib süsteem.

Valige paan, mille kaudu soovite valitud kliendi andmeid vaadata sihtotstarbelisel lehel nimega [Kliendi üksikasjad](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"] 
> ![Klientide leht, kus kuvatakse tulemipaanid](media/customers-page-result-tiles-B2C.png "Klientide leht, kus kuvatakse tulemipaanid")

> [!NOTE]
> Kui navigeerimisel ei saa paane kuvada, kui valite navigeerimisel **Kliendid**, peab teie administraator **Otsingu- ja filtriregistris** [määratlema vähemalt ühe otsitava atribuudi](search-filter-index.md).

## <a name="search-for-customers"></a>Otsige kliente

Klientide otsimiseks sisestage otsingukasti nimi või mingi muu atribuut. Otsing töötab ainult andmete ühendamise ajal loodud _Kliendiolemis_.

Administraatorina saate seadistada otsitavaid atribuute lehel **Otsing ja filtri register**. Lisateavet leiate teemast [Otsingu- ja filtriregistri haldamine](search-filter-index.md).

## <a name="filter-customers"></a>Klientide filtreerimine

Kliente saate filtreerida _Kliendiolemi_ väljade alusel. Sarnaselt otsingule peab administraator esmalt määrama väljad filtreeritavaks lehel **Otsing ja filtri register**.

1. Valige **Kuva filtrid** lehel **Kliendid**.

1. Märkige atribuutide, mille alusel tahate filtreerida kliente, kõrval asuvad ruudud.

1. Eemaldage filtrid, valides lehel **Kliendid** suvand **Eemalda filtrid**.

## <a name="customer-details-page"></a>Kliendi üksikasjade leht

Valige mis tahes kliendipaan, et avada **Kliendi üksikasjade leht**. See vaade sisaldab valitud kliendi koondatud teavet. Kliendi üksikasjad sisaldavad järgmist sisu:

**Kliendiprofiili paan**: sellel paanil kuvatakse ühtse _Kliendiolemi_ erinevad väärtused. Kui väljal pole valitud kliendiprofiili väärtust, siis seda ei näidata. Paan on struktureeritud jaotisteks:  
  - Esimeses jaotises kuvatakse eelmääratletud väljakomplekt, millele järgneb kõik otsingu ja filtriregistrisse kuuluvad väljad. Kui profiil sisaldab neid välju, ühendatakse kõik aadressiga seotud väljad ühele reale. 
  - **Selle kliendi kontaktid**: Äriettevõtete keskkondades näete teise jaotisena kõiki selle kliendiga seotud kontakte. Iga kontakti kuvatakse koos nende väljadega. Tühjad väljad on peidetud.
  - **Lisaväljad**: Kuvatakse valitud kliendi ülejäänud väljad, välja arvatud ID-d. 
  - **ID-d**: Loetletakse kõik ID-d nende vastava olemi nime all. Väljad on identifitseeritud ID-de järgi nende semantika poolt, mis kategoriseerib need sellistena.

**Tegevuse ajajoon**: Kuvatakse andmed, kui olete konfigureerinud tegevusi. Ajajoonevaade sisaldab valitud kliendi tegevusi kronoloogilises järjekorras, alustades viimasest tegevusest. Lisateabe saamiseks minge [Kliendi tegevused](activities.md).

**Ülevaated**:  
  - **Väärtused**: Kuvab, kas olete konfigureerinud ühe või mitu kliendi atribuudi mõõdet. Nende hulka kuuluvad teie klientide arvutatud KPI-sid iga kliendi tasemel. Lisateavet leiate jaotisest [Määratle ja halda mõõtmeid](measures.md).

  - **Potentsiaalsed huvid, potentsiaalsed kaubamärgid**: Kuvab, kas olete konfigureerinud kaubamärgi või huvi ühtivuse rikastamise. See esindab potentsiaalseid huvisid kaubamärkide suhtes, mis põhinevad teistel klientidel, kelle profiil sarnaneb valitud kliendiprofiiliga. Lisateavet leiate jaotisest [Rikastage kliendiprofiile brändi- ja huvisidemetega](enrichment-microsoft.md).

Kliendi otsingu lehele naasmiseks valige **Tagasi klientidele**.

## <a name="next-steps"></a>Järgmised etapid

[Lisage rohkem andmeallikaid](data-sources.md), [rikastage ühendatud profiile](enrichment-hub.md) või [looge segmente](segments.md), et töötada ühtsete kliendiprofiilidega teistes rakendustes.


[!INCLUDE [footer-include](includes/footer-banner.md)]
