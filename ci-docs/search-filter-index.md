---
title: Kliendiprofiilide otsimine ja filtreerimine
description: Leidke kiiresti teavet ühtsete klientide profiilide kohta ja filtreerige määratud atribuute.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: 35bfd6530b9b80a4b0ec8ff992d9014534721907
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642767"
---
# <a name="customer-profiles-search--filter-index"></a>Kliendiprofiilid: otsing ja filtri register

Kliendiandmete ühtlustamise tulemusena tekib kliendiprofiili olem, mis pakub kogu kliendibaasi ühtset vaadet. [Kindla kliendi või klientide rühma teabe](customer-profiles.md) kiireks leidmiseks saate seadistada lehe **Kliendid** võimalused **Otsi** ja **Filtreeri**. Lugege edasi, et õppida, kuidas administraatorid saavad muuta lehe **Otsing ja filtri register** atribuute, millega kasutajad saavad otsida ja filtreerida.

   :::image type="content" source="media/search-filter.png" alt-text="Otsingufilter":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Lisage välju ja määrake atribuute

Kui määratlete otsitavaid atribuute administraatorina esimest korda, peate esmalt määratlema indekseeritud välju. Soovitame valida kõik atribuudid, millega kasutajad saavad kliente otsida ja filtreerida lehel **Kliendid**. Saate määrata vaid kliendiprofiili olemi atribuute, mida lõite andmete ühendamisel.

1. Avage leht **Kliendid** ja valige **Otsingu ja filtri register**.

2. Valige **+ Lisa** indekseeritud väljade määramiseks.

3. Valige loendist indekseeritud väljadena lisatavad atribuudid. Saate alati lisada rohkem atribuute, valides **Lisa**. Saate eemaldada kõiki valitud atribuute, kui valite sümboli **Eemalda**.

## <a name="explore-the-indexed-customer-fields-table"></a>Uudistage indekseeritud kliendiväljade tabelit

Järgmine teave asub tabelis.

- **Nimi**: tähistab atribuudi nime kliendiprofiili olemis.
- **Andmetüüp**: määrab, kas andmetüüp on string, arv või kuupäev.
- **Kaasatud otsingusse**: määrab, kas selle atribuudiga saab otsida kliente lehel **Kliendid** välja **Otsing** abil.
- **Lisa filter** juhtelement, millega määratletakse atribuudi kasutamist lehel **Kliendid** filtreerimiseks.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Kindla atribuudi filtreerimisvalikute muutmine

Lehel **Kliendid** asuva **Filter** menüü võib sisaldada erinevas koguses atribuutide tasemeid (nt erinevate vanuserühmade puhul filtreeritakse kliente järgmiselt).

1. Valige lehel **Otsing ja registri filtreerimine** kindla atribuudi puhul **Lisa filter**. Saate määratleda tulemuste arvu ja nende järjestust. Olenevalt atribuudi andmetüübist ilmub üks järgmistest paanidest.

- Stringi tüüpi atribuudid: täpsustage paanil **Stringi filtreerimissuvandid** soovitud tulemuste arvu ja nende järjestusreegleid.

- Numbrilist tüüpi atribuudid: täpsustage paanil **Numbrilised filtreerimissuvandid** hõlmatud intervallid ja nende järjestusreegleid.

- Kuupäeva tüüpi atribuudid: täpsustage paanil **Kuupäevafiltri suvandid** hõlmatud intervallid ja nende järjestusreegleid.

2. Vajutage nuppu **Salvesta**, et muudatused rakendada.

3. Valige **Käivita**, kui olete valmis seadete rakendamiseks. Pärast muudatuste töötlemist leiate need [kliendikaartidelt lehel Klient](customer-profiles.md). 

## <a name="next-steps"></a>Järgmised etapid

Vaadake profiilide otsimiseks läbi [ühendatud profiilide leht](customer-profiles.md) või kasutage indekseeritud välju kõigi ühendatud profiilide alamhulga vaatamiseks.


[!INCLUDE [footer-include](includes/footer-banner.md)]
