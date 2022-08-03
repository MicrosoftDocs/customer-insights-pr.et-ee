---
title: Kliendiprofiilide otsingu- ja filtreerimisregistri haldamine
description: Leidke kiiresti teavet ühtsete klientide profiilide kohta ja filtreerige määratud atribuute.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187904"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Kliendiprofiilide otsingu- ja filtreerimisregistri haldamine

Teie kliendiandmete ühendamise tulemuseks *on kliendi* olem, mis pakub ühtset vaadet teie kogu kliendibaasile. Selleks et kasutajad leiaksid kiiresti [teavet konkreetse kliendi või klientide rühma](customer-profiles.md) kohta, peab administraator konfigureerima **lehe Kliendid** otsingu **-** ja **filtreerimisvõimalused**.

   :::image type="content" source="media/search-filter.png" alt-text="Otsingufilter":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Otsitavate atribuutide ja indekseeritud väljade määratlemine

Kui määratlete otsitavaid atribuute administraatorina esimest korda, määratlege esmalt indekseeritud väljad. Soovitame valida kõik atribuudid, millega kasutajad saavad kliente otsida ja filtreerida lehel **Kliendid**. Määrata saab ainult atribuute, mis on olemas *andmete ühendamise protsessi käigus loodud kliendi* olemis.

1. Minge jaotisse **Kliendid ja valige** Otsing ja filtreeri **register**.

1. Valige **+ Lisa**.

1. Valige loendis atribuudid, mille soovite lisada indekseeritud väljadena, ja klõpsake nuppu **Rakenda**.

1. Atribuutide lisamiseks valige **Lisa**. Valitud atribuudi eemaldamiseks valige atribuut ja seejärel **kustutage**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Otsi ja filtreeri registrilehte.":::

1. Valige **Käivita**, kui olete otsingu- ja filtreerimissätete rakendamiseks valmis. Pärast muudatuste töötlemist vaadake neid [kliendilehel](customer-profiles.md) olevatel kliendikaartidel.

## <a name="define-filtering-options-for-a-given-attribute"></a>Antud atribuudi filtreerimissuvandite määratlemine

Seadistage väljad, mida saab kasutada klientide **filtreerimiseks lehel Kliendid**.

1. Minge jaotisse **Kliendid ja valige** Otsing ja filtreeri **register**.

1. Valige atribuut ja **lisage filter**. Määratlege tulemuste arv ja nende korraldamise järjekord. Olenevalt atribuudi andmetüübist kuvatakse üks järgmistest paanidest.

   - Stringitüüpi atribuudid: määrake stringifiltri **paanil soovitud tulemuste** arv ja nende korraldamise järjestuspoliitika.

   - Numbritüüpi atribuudid: määrake paanil Numbrifiltri **kaasatud** intervallid ja nende korraldamise järjestuspoliitika.

   - Kuupäevatüübi atribuudid: määrake paanil Kuupäevafilter **kaasatud** intervallid ja järjestuspoliitika, mille alusel neid korraldatakse.

1. Valige **OK**. Korrake toimingut kõigi atribuutide puhul, mille alusel soovite filtreerida.

1. Valige **Käivita**, kui olete otsingu- ja filtreerimissätete rakendamiseks valmis. Pärast muudatuste töötlemist vaadake neid [kliendilehel](customer-profiles.md) olevatel kliendikaartidel.

## <a name="view-indexed-customer-fields"></a>Indekseeritud kliendiväljade vaatamine

Lehel **Otsing ja filter** kuvatakse järgmine teave.

- **Nimi**: tähistab atribuudi nime nii, nagu see kuvatakse *kliendi* olemis.
- **Andmetüüp**: määrab, kas andmetüüp on string, arv või kuupäev.
- **Kaasatud otsingusse**: määrab, kas selle atribuudiga saab otsida kliente lehel **Kliendid** välja **Otsing** abil.
- **Lisa filter** juhtelement, millega määratletakse atribuudi kasutamist lehel **Kliendid** filtreerimiseks.

## <a name="next-steps"></a>Järgmised toimingud

Vaadake profiilide otsimiseks läbi [ühendatud profiilide leht](customer-profiles.md) või kasutage indekseeritud välju kõigi ühendatud profiilide alamhulga vaatamiseks.

[!INCLUDE [footer-include](includes/footer-banner.md)]
