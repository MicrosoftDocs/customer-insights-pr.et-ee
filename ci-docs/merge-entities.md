---
title: Kliendiväljade ühendamine andmete ühendamiseks
description: Ühendage olemid, et luua koondatud kliendiprofiile.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 4a19b753e7a5979fe72d7e96bc4452d7795c2d48
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139652"
---
# <a name="unify-customer-fields-for-data-unification"></a>Kliendiväljade ühendamine andmete ühendamiseks

Ühendamisprotsessi selles etapis valige ja välistage atribuudid, mis ühendatakse ühtse profiili olemiga. Näiteks kui kolmel olemil olid meiliandmed, võiksite säilitada kõik kolm eraldi meilivälja või ühendada need ühtse profiili jaoks üheks meiliväljaks. Mõned atribuudid ühendab süsteem automaatselt. Saate luua stabiilseid ja ainulaadseid kliendi ID-sid ja rühmitada klastrisse seotud profiile.

:::image type="content" source="media/m3_unify.png" alt-text="Ühenda leht andmete ühtsustamise protsessiga näidates tabelit koos ühendatud väljadega, mis defineerivad ühendatud kliendiprofiili.":::

## <a name="review-and-update-the-customer-fields"></a>Kliendiväljade ülevaatamine ja värskendamine

1. Vaadake üle tabeli vahekaardil Kliendiväljad ühendatavate **väljade** loend. Tehke vajaduse korral muudatusi.

   1. Kõigi kombineeritud väljade puhul saate teha järgmist.
      - [Muuda](#edit-a-merged-field)
      - [Nimeta ümber](#rename-fields)
      - [Eralda](#separate-merged-fields)
      - [Välista](#exclude-fields)
      - [Üles või alla liikumine](#change-the-order-of-fields)

   1. Mis tahes väljade puhul saate teha järgmist.
      - [Ühenda väljad](#combine-fields-manually)
      - [Väljade rühma ühendamine](#combine-a-group-of-fields)
      - [Nimeta ümber](#rename-fields)
      - [Välista](#exclude-fields)
      - [Üles või alla liikumine](#change-the-order-of-fields)

1. [Soovi korral looge kliendi ID konfiguratsioon](#configure-customer-id-generation).

1. Soovi korral rühmitage [profiilid leibkondadesse või klastritesse](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Järgmine samm: ühendamise ülevaatamine](review-unification.md)

### <a name="edit-a-merged-field"></a>Redigeeri ühendatud välja

1. Valige ühendatud väli ja valige **Redigeeri**. Kuvatakse paan Kombineeri väljad.

1. Määrake väljade ühendamise või ühendamise viis ühest kolmest valikust.
    - **Olulisus**: tuvastab võitja väärtuse osalevatele valdkondadele määratud tähtsusastme alusel. See on vaikeühendamissuvand. Valige järjekoha prioritiseerimiseks **Nihuta üles/alla**.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Tähtsuse valik ühendamisväljade dialoogis.":::

    - **Viimased**: tuvastab võitja väärtuse kõige hiljutisema aja järgi. Nõuab kuupäeva või arvvälja iga koosteväljade osalemisolemi jaoks, et määrata olemi aega.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Hiljutisuse valik ühendamisväljade dialoogis.":::

    - **Hiljutine**: tuvastab võitja väärtuse kõige kaugema aja järgi. Nõuab kuupäeva või arvvälja iga koosteväljade osalemisolemi jaoks, et määrata olemi aega.

1. Saate ühendamise protsessi lisada veel välju.

1. Ühendatud välja saate ümber nimetada.

1. Muudatuse rakendamiseks valige **Tehtud**.

### <a name="rename-fields"></a>Väljade ümbernimetamine

Muutke ühendatud või eraldi väljade kuvatavat nime. Toodanguolemi nime ei saa muuta.

1. Valige väli ja valige Nimeta **ümber**.

1. Sisestage uus kuvatav nimi.

1. Valige nupp **Valmis**.

### <a name="separate-merged-fields"></a>Eraldaga ühendatud väljad

Ühendatud väljade eraldamiseks leidke atribuut tabelist. Eraldatud väljad kuvatakse üksikute andmepunktidena ühendatud kliendi profiilil.

1. Valige ühendatud väli ja valige **Eralda väljad**.

1. eralduse kinnitamine.

### <a name="exclude-fields"></a>Väljade välistamine

Välistage ühendatud või eraldi väli ühtsest kliendiprofiilist. Kui seda välja kasutatakse muudes protsessides (nt segmendis), eemaldage see nendest protsessidest, enne selle kliendiprofiililt eemaldamist.

1. Valige väli ja valige **Välista**.

1. Kinnitage välistamine.

Kõigi välistatud väljade loendi kuvamiseks valige **Välistatud väljad**. Vajadusel saate välja jäetud välja lugeda.

### <a name="change-the-order-of-fields"></a>Väljade järjekorra muutmine

Mõned olemid sisaldavad rohkem üksikasju kui teised. Kui olem sisaldab välja kohta värskeid andmeid, saate väärtusi ühendades prioriseerida selle teiste olemite suhtes.

1. Valige väli.
  
1. Tellimuse seadmiseks valige **Liigu üles/alla** või lohistage need soovitud asendisse.

### <a name="combine-fields-manually"></a>Väljade käsitsi ühendamine

Ühendatud atribuudi loomiseks ühendage eraldatud väljad.

1. Valige **Ühenda** > **väljad**. Kuvatakse paan Kombineeri väljad.

1. Määrake ripploendis **Väljade ühendamine** koostevõitja poliitika.

1. Rohkemate väljade **ühendamiseks valige** Lisa väli.

1. Sisestage **Nimi** ja **Väljundvälja nimi**.

1. Muudatuse rakendamiseks valige **Tehtud**.

### <a name="combine-a-group-of-fields"></a>Väljade rühma ühendamine

Käsitlege väljade rühma ühe üksusena. Näiteks kui meie kirjed sisaldavad välju Aadress1, Aadress2, Linn, Osariik ja Zip, ei soovi me ühendada teise kirje aadressiga Aadress2, arvates, et see muudaks meie andmed täielikumaks.

1. Valige **Ühenda** > **väljade** rühm.

1. Määrake koostevõitja poliitika rippmenüüs **Asetusrühmade järgi**.

1. Valige **Lisa** ja valige, kas soovite väljadele veel välju või rühmi lisada.

1. Sisestage **igale** kombineeritud väljale nimi **ja** väljundnimi.

1. Sisestage **väljade** rühma nimi.

1. Muudatuse rakendamiseks valige **Tehtud**.

## <a name="configure-customer-id-generation"></a>Kliendi ID genereerimise konfigureerimine

Määratlege, kuidas luua kliendi ID väärtusi, kordumatuid kliendiprofiili identifikaatoreid. Andmete ühendamise protsessi väljade ühendamise etapp loob kordumatu kliendiprofiili identifikaatori. Identifikaator on *Kliendi olemis olev* CustomerId *·*, mis tuleneb andmete ühendamise protsessist.

*ClientId* põhineb mitte-null võitja primaarvõtmete esimese väärtuse räsimisel. Need võtmed pärinevad andmete ühendamisel kasutatavatest olemitest ja neid mõjutab vastete järjekord.Seega saab loodud kliendi ID muutuda, kui vastendustellimuse esmases olemis muutub primaarvõtme väärtus. Esmase võtme väärtus ei pruugi alati esindada sama klienti.

Stabiilse kliendi ID konfigureerimine võimaldab teil seda käitumist vältida.

1. Valige vahekaart **Võtmed**.

1. Hõljutage **kursorit real ClientId** ja valige **Konfigureeri**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Juhtelement ID loomise kohandamiseks.":::

1. Valige kuni viis välja, mille ID on kordumatu ja stabiilsem. Kirjed, mis ei vasta teie konfiguratsioonile, kasutavad selle asemel süsteemi konfigureeritud ID-d.  

1. Valige nupp **Valmis**.

## <a name="group-profiles-into-households-or-clusters"></a>Rühmitage profiilid leibkondadesse või klastritesse

Saate määratleda reeglid seotud profiilide rühmitamiseks klastrisse. Praegu on saadaval kahte tüüpi klastrid – Leibkonna ja kohandatud klastrid. Kui *Kliendi* olem sisaldab semantilisi välju *Person.LastName* ja *Location.Address*, valib süsteem eelmääratletud reeglitega subjekti automaatselt. Saate luua klastri ka oma reeglite ja tingimustega, mis sarnanevad [reeglitele](match-entities.md#define-rules-for-match-pairs).

1. Valige **Klastri** > **Täpsem** loomine.

   :::image type="content" source="media/create-cluster.png" alt-text="Juhtelement uue klastri loomiseks.":::

1. Valige **Leibkonna** või **Kohandatud** klastri vahel. Kui semantilised väljad *Person.LastName* ja *Location.Address* on olemas *Kliendi* olemis, valitakse automaatselt leibkond.

1. Sisestage klastrile nimi ja valige **Valmis**.

1. Loodud klastri leidmiseks valige vahekaart **Klastrid**.

1. Määrake klastri määratlemiseks reeglid ja tingimused.

1. Valige nupp **Valmis**. Klaster luuakse siis, kui ühendamisprotsess on lõppenud. Klastri identifikaatorid lisatakse uute väljadena kliendi *olemile*.

> [!div class="nextstepaction"]
> [Järgmine samm: ühendamise ülevaatamine](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
