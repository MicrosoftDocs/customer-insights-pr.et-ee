---
title: Kliendiprofiilide otsimine ja filtreerimine
description: Leidke kiiresti teavet ühtsete klientide profiilide kohta ja filtreerige määratud atribuute.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: b6cc0ad1a47a6c00e3bf220271f42870fc53621b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597138"
---
# <a name="customer-profiles-search--filter-index"></a>Kliendiprofiilid: otsing ja filtri register

Kliendiandmete ühtlustamise tulemusena tekib kliendiprofiili olem, mis pakub kogu kliendibaasi ühtset vaadet. [Kindla kliendi või klientide rühma teabe](customer-profiles.md) kiireks leidmiseks saate seadistada lehe **Kliendid** võimalused **Otsi** ja **Filtreeri**. Lugege edasi, et õppida, kuidas administraatorid saavad muuta lehe **Otsing ja filtri register** atribuute, millega kasutajad saavad otsida ja filtreerida.

> [!div class="mx-imgBorder"]
> ![Otsingufilter](media/search-filter.png "Otsingufilter")

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

3. Valige **Käivita**, kui olete valmis seadete rakendamiseks.

## <a name="next-steps"></a>Järgmised etapid

Kliendiprofiilide otsimiseks või indekseeritud väljade kasutamiseks minge lehele **Kliendid**, et näha kõigi kliendiprofiilide alamhulka.


[!INCLUDE[footer-include](../includes/footer-banner.md)]