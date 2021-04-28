---
title: Olemite ühendamine andmete koondamise ajal
description: Ühendage olemid, et luua koondatud kliendiprofiile.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4ad06a0baf57e612fc0e0214dfd23d28e7d2b6be
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896506"
---
# <a name="merge-entities"></a>Olemite liitmine

Liitmine on andmete ühendamise viimane etapp. Selle eesmärk on vastavusse viia vastuolus andmed. Vastuolulisteks andmeteks võivad olla kahes andmebaasis olev kliendi nimi, mida näidatakse veidi erinevalt (võrrelge: „Grant Marshall“ ja „Grant Marshal“) või erinevas vormingus telefoninumber (võrrelge: 617-803-091X ja 617803091X). Nende vastuoluliste andmepunktide liitmine toimub järgmisel alusel: atribuut atribuudi järel.

Pärast [vastendamisetappi](match-entities.md) algab liitmisetapp, valides lehel **Ühendamine** paani **Liitmine**.

## <a name="review-system-recommendations"></a>Vaadake üle süsteemi soovitused

Lehel **Liitmine** valite ja välistate atribuudid, et liita oma ühendatud kliendiprofiili olemiga (seadistamise tulemus). Osa atribuute liidab süsteem ise.

### <a name="view-merged-attributes"></a>Vaadake ühendatud atribuute

Automaatselt liidetud atribuutide hulgast ühe vaatamiseks valige see liidetud atribuut. Kaks atribuuti, millest see liidetud atribuut koosneb, kuvatakse liidetud atribuudi all eraldi kahes uues reas.

> [!div class="mx-imgBorder"]
> ![Valige ühendatud atribuut](media/configure-data-merge-profile-attributes.png "Valige ühendatud atribuut")

### <a name="separate-merged-attributes"></a>Eraldage liidetud atribuudid

Automaatselt liidetud atribuutide eraldamiseks või liitmiseks leidke tabelist **Profiili atribuudid** atribuut.

1. Valige kolmikpunkt (...).
  
2. Valige ripploendis suvand **Eralda väljad**.

### <a name="remove-merged-attributes"></a>Eemaldage liidetud atribuudid

Viimase kliendiprofiili olemi atribuudi välistamiseks leidke see tabelis **Prodiili atribuudid**.

1. Valige kolmikpunkt (...).
  
2. Valige ripploendis suvand **Mitte liita**.

   Atribuut liigutatakse jaotisesse **Kliendi kirjest eemaldatud**.

## <a name="manually-add-a-merged-attribute"></a>Lisa ise ühendatud atribuut

Liidetud atribuudi lisamiseks minge lehele **Liitmine**.

1. Valige **Lisa liidetud atribuut**.

2. Sisestage hiljem lehel **Liitmine** selle tuvastamiseks **nimi**.

3. Soovi korral sisestage **Kuvatav nimi**, mis ilmub ühendatud kliendiprofiili olemis.

4. Liidetavate vastendatud olemite atribuutide valimiseks seadistage **Vali duplikaatatribuudid**. Samuti saate otsida atribuute.

5. Ühe atribuudi esile tõstmiseks valige **Tähtsuse järgi järjestamine**. Näiteks, kui olem *WebAccountCSV* sisaldab atribuudi *Täisnimed* kõige täpsemaid andmeid, saate selle olemi ettepoole tõsta olemist *ContactCSV*, valides selleks *WebAccountCSV*. Selle tulemusel muutub *WebAccountCSV* kõige tähtsamaks, samas *ContactCSV* langeb teisele kohale atribuudi *Täisnimi* väärtuste hankimisel.

## <a name="run-your-merge"></a>Käivitage kooste

Olenemata sellest, kas liidate atribuute ise või lasete seda teha süsteemil, saate alati käivitada kooste. Toimingu käivitamiseks valige lehel **Liitmine** valik **Käivita**.

> [!div class="mx-imgBorder"]
> ![Andmete liitmine „Salvesta ja Käivita“](media/configure-data-merge-save-run.png "Andmete liitmine „Salvesta ja Käivita“")

Täiendavate muudatuste tegemiseks ja etapi uuesti käivitamiseks saate poolelioleva ühendamise tühistada. Valige **Värskendamine ...** ja valige nähtavale ilmuva külgpaani suvand **Tühista töö**.

Kui tekst **Värskendamine ...** asendub tekstiga **Õnnestus**, on ühendamine lõpule jõudnud ja vastuolud on vastavalt teie määratud poliitikatele lahendatud. Ühendatud ja ühendamata atribuudid kaasatakse ühendatud profiili olemisse. Välja jäetud atribuute ei kaasata ühendatud profiili olemisse.

Kui see ei olnud esimene kord edukalt ühendamine läbi viia, käivitatakse kõik järgnevad protsessid, sealhulgas rikastamine, segmentimine ja meetmed, automaatselt. Kui kõik järgnevad protsessid on uuesti läbi viidud, kajastuvad kõik tehtud muudatused kliendiprofiilidel.

> [!TIP]
> Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types). Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies). Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku. Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.

## <a name="next-step"></a>Järgmine etapp

Klientide kohta täiendavate ülevaadete saamiseks seadistage [toiminguid](activities.md), [rikastamist](enrichment-hub.md) või [seosed](relationships.md).

Kui olete juba tegevused, rikastamise või seoseid konfigureerinud või kui olete määratlenud segmendid, töödeldakse neid automaatselt, et kasutada värskeimaid kliendiandmeid.




[!INCLUDE[footer-include](../includes/footer-banner.md)]