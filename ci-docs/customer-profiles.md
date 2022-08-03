---
title: Kliendiprofiilide vaatamine
description: Ühtsete kliendiandmete vaatamine,sh otsingu ja filtri kasutamine
ms.date: 06/08/2022
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
ms.openlocfilehash: 6cdf47e6997f230811dcb0f2cf5542f3a6db2367
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188088"
---
# <a name="view-customer-profiles"></a>Kliendiprofiilide vaatamine

Kliendiprofiilid on saadaval pärast [ühtse *kliendiolemi* loomist](data-unification.md). Teie ühendatud kliendiprofiilide kombineeritud vaade kuvatakse **lehel Kliendid**. Kliendid võivad olla üksikisikud või organisatsioonid.

Minge **lehele Kliendid**, et vaadata oma kliente ja nende profiile. Iga kliendiprofiili tähistab paan. Kasutage lehekülgedena kasutamise juhtelemente, et saada rohkem kirjeid. Kaardil kuvatakse *Kliendi* olemi väljad, nagu see on määratletud **Otsingu- ja filtriregistris**. Iga kaardi väljade järjekorra valib süsteem.

> [!NOTE]
> Kui te ei näe valiku Kliendid valimisel **paane, peab** teie administraator määratlema registris [Otsing](search-filter-index.md) ja filter vähemalt ühe otsitava atribuudi **.**

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Leht Kliendid, kus on kuvatud tulemipaanid.":::

Valige üks järgmistest toimingutest.
- [Kliendiandmete vaatamine](#view-customer-details)
- [Otsingu ja filtri registri](search-filter-index.md) haldamine (ainult administraatorid)
- [Klientide filtreerimine](#filter-customers)
- **Laiendage kaarte** või **Ahendage kaarte** kliendipaanil kuvatava teabe laiendamiseks või ahendamiseks
- **Kindla atribuudi järgi** sortimine
- [Otsige kliente](#search-for-customers)

  > [!NOTE]
  > Otsingu ja filtreerimise kasutamiseks peab administraator konfigureerima otsitavad atribuudid ja määratlema filtreeritavad väljad otsinguregistri abil.

## <a name="search-for-customers"></a>Otsige kliente

Otsige kliente, sisestades otsinguklientidele **nime või mõne muu atribuudi**. Otsitavad atribuudid määratleb administraator ja need pärinevad ühtsest *kliendi* olemist.

> [!NOTE]
> **String** on ainus andmetüüp, mis otsingusse kaasatakse. Kasutage seda **klientide** otsimiseks lehe Kliendid väljal Otsi kliente.

## <a name="filter-customers"></a>Klientide filtreerimine

Filtreerige kliente väljade *Kliendi* olem järgi. Filtreeritavad väljad määrab administraator.

1. **Tehke lehel Kliendid** valik **Kuva filtrid**. Kuvatakse paan Filter.

1. Märkige atribuutide, mille alusel tahate filtreerida kliente, kõrval asuvad ruudud.

1. Eemaldage kõik filtrid, valides **Tühjenda filtrid** või tühjendage valitud atribuudi kõrval olev märkeruut.

1. Filtripaani sulgemiseks valige **Peida filtrid**.

1. Filtritulemite salvestamiseks segmendina [valige](segments.md) **Salvesta filtrid segmendina**.
   1. Sisestage segmendi nimi.
   1. Segmendi salvestamiseks valige **Salvesta**.
   1. Valige, kas käivitada segment kohe, valides Aktiveeri **või** käivita see **hiljem**.

## <a name="view-customer-details"></a>Kliendiandmete vaatamine

**Valige lehel Kliendid** kliendipaan, et vaadata valitud kliendi üksikasju.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Kliendiandmete leht.":::

Kliendi üksikasjade hulka kuuluvad järgmised.

**Paanil** Kliendiprofiil kuvatakse ühendatud *kliendi* olemi erinevad väärtused. Kui väljal pole valitud kliendiprofiili jaoks väärtust, siis seda ei kuvata, välja arvatud aadressiväli. Paan on struktureeritud jaotisteks:

- Esimeses jaotises kuvatakse eelmääratletud väljakomplekt, millele järgneb kõik otsingu ja filtriregistrisse kuuluvad väljad. Kõik aadressiga seotud väljad ühendatakse üheks reaks, mis näitab isegi siis, kui profiil ei sisalda aadressiteavet.
- **Selle kliendi** kontaktid kuvatakse ärikontode keskkondades. Iga kontakti kuvatakse koos nende väljadega. Tühjad väljad on peidetud.
- **Lisaväljad** näitavad valitud kliendi ülejäänud välju, välja arvatud ID-d.
- **ID-d loetlevad** kõik ID-d vastava üksuse nime all. Väljad identifitseeritakse ID-dena nende semantika järgi.

**Tegevuste ajaskaala** näitab andmeid, kui olete tegevusi [konfigureerinud](activities.md). Ajajoonevaade sisaldab valitud kliendi tegevusi kronoloogilises järjekorras, alustades viimasest tegevusest.

**Ülevaated**:

- **Mõõdud** näitavad, kas olete konfigureerinud kliendi atribuudi [mõõdud](measures.md). Nende hulka kuuluvad teie klientide arvutatud KPI-sid iga kliendi tasemel.

- **Potentsiaalsed huvid, potentsiaalsed kaubamärgid** näitavad, kas olete konfigureerinud brändi või huvide afiinsuse [rikastamise](enrichment-microsoft.md). See esindab potentsiaalseid huvisid kaubamärkide suhtes, mis põhinevad teistel klientidel, kelle profiil sarnaneb valitud kliendiprofiiliga.

Lehele Kliendid **naasmiseks** valige **Tagasi klientide** juurde.

## <a name="next-steps"></a>Järgmised toimingud

[Lisage rohkem andmeallikaid](data-sources.md), [rikastage ühendatud profiile](enrichment-hub.md) või [looge segmente](segments.md), et töötada ühtsete kliendiprofiilidega teistes rakendustes.

[!INCLUDE [footer-include](includes/footer-banner.md)]
