---
title: Kliendiprofiilide vaatamine
description: Saate ühendatud ülevaate oma koondatud kliendiandmetest.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8ab55d101f98169b8f794ce580ddd0a71ede6642
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554613"
---
# <a name="customer-profiles"></a>Kliendiprofiilid

Lehel **Kliendid** kuvatakse teie klientide kombineeritud vaade, mis põhineb [kõigist andmeallikatest](data-sources.md) kogutud profiiliandmetel. Kliendiprofiilid on saadaval, kui [loote ühendatud kliendiolemi](data-unification.md). Klientide põhjalikemate vaadete hankimiseks viige andmete ühendamine lõpuni. Leht võimaldab otsida ka kliente.

Klientideks võivad olla eraisikud või ettevõtted (eelvaade). Igat kliendi või ettevõtte profiili esindab pealkiri. Kindla kliendi või ettevõtte täiendava teabe nägemiseks valige paan. Täiendavate kirjete nägemiseks kasutage lehe allservas olevaid lehejaotuse juhtelemente.

> [!div class="mx-imgBorder"] 
> ![Jaekliendi profiilid.](media/profiles-customers.png "Jaekliendi profiilid")

Ettevõtted (eelvaade)
> [!div class="mx-imgBorder"] 
> ![Jaekliendi profiilid.](media/profile-customers-b2b.png "B2B kliendi profiilid")

> [!NOTE]
> Kui te ei näe paane, kui valite navigeerimisel **Kliendid**, peab teie administraator [määratleda vähemalt ühe otsitava atribuudi](search-filter-index.md) jaotises **Otsing ja filtri register**.

## <a name="search-for-customers"></a>Otsige kliente

Klientide otsimiseks sisestage otsingukasti nimi või mingi muu atribuut. Otsida saab vaid kliendiprofiili olemist, mille lõite andmete ühendamisel.

Administraatorina saate seadistada otsitavaid atribuute lehel **Otsing ja filtri register**. Lisateavet leiate teemast [Otsingu ja filtri registri haldamine](search-filter-index.md).

## <a name="filter-customers"></a>Filtreerige kliente

Filtreerige kliente kliendiprofiili olemi väljade alusel. Sarnaselt otsingule peab administraator esmalt määrama väljad filtreeritavaks lehel **Otsing ja filtri register**.

1. Valige lehel **Kliendid** suvand **Filtreeri**.

2. Märkige atribuutide, mille alusel tahate filtreerida kliente, kõrval asuvad ruudud.

   > [!div class="mx-imgBorder"] 
   > ![Kliendi profiilid.](media/profiles-customers3.png "Kliendi profiilid")

3. Eemaldage filtrid, valides lehel **Kliendid** suvand **Eemalda filtrid**.

##  <a name="customer-details-page"></a>Kliendi üksikasjade leht

Valige mis tahes kliendipaan, et avada **Kliendi üksikasjade leht**. See vaade sisaldab valitud kliendi koondatud teavet.

Kliendi üksikasjade hulka kuuluvad järgmised.

-   **Kliendiprofiili paan**: See paan näitab ühtse kliendiprofiili üksuse erinevaid väärtusi. Need üksikasjad võivad hõlmata meiliaadressi, nime, linna ja nii edasi. 

-   **Potentsiaalsed huvid, potentsiaalsed kaubamärgid**: näitab, kui olete konfigureerinud esimese osapoole rikastamise. See esindab sellise kliendi potentsiaalseid huve ja lemmikbrände, kellel on praeguse kliendi omaga sarnanev profiil. Lisateavet vaadake teemast [Kliendiprofiilide rikastamine kaubamärgi ja huvide ühtivusega](enrichment-microsoft.md).

-   **Näitajad**: kuvatakse, kui olete konfigureerinud ühe või mitu näitajat, mis on kindlat tüüpi: kliendiatribuudi näitajad. Nende hulka kuuluvad teie klientide arvutatud KPI-sid iga kliendi tasemel. Lisateavet leiate teemast [Näitajate määratlemine ja haldamine](measures.md).

-   **Tegevuse ajaskaala**: kuvatakse, kui teil on konfigureeritud tegevused. Ajaskaala vaade sisaldab selle kliendi kronoloogiliselt sorditud tegevusi, alustades kõige hiljutisest tegevusest. Lisateavet vt teemast [Klienditegevused](activities.md).

Valige **Tagasi klientide lehele**, et naasta kliendiotsingu lehele.

## <a name="next-steps"></a>Järgmised etapid

[Täiendavate andmeallikate lisamine](data-sources.md) või [kliendisegmentide loomine](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
