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
ms.openlocfilehash: ceb2724ad490c1ba44fd9b7ff2be04721892fca4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082950"
---
# <a name="unify-customer-fields-for-data-unification"></a>Kliendiväljade ühendamine andmete ühendamiseks

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Selles ühendamisprotsessi etapis valige ja välistage atribuudid, mis ühinevad teie ühtse profiili olemiga. Näiteks kui kolmel olemil olid meiliandmed, võiksite säilitada kõik kolm eraldi meilivälja või ühendada need ühtse profiili jaoks üheks meiliväljaks. Süsteem ühendab mõned atribuudid automaatselt. Saate luua stabiilseid ja kordumatuid kliendi ID-sid ning rühmitada seotud profiile klastrisse.

:::image type="content" source="media/m3_unify.png" alt-text="Ühenda leht andmete ühtsustamise protsessiga näidates tabelit koos ühendatud väljadega, mis defineerivad ühendatud kliendiprofiili.":::

## <a name="review-and-update-the-customer-fields"></a>Kliendiväljade ülevaatamine ja värskendamine

1. Vaadake üle tabeli vahekaardi Kliendi **väljade** all ühendatavate väljade loend. Vajadusel tehke muudatusi.

   1. Mis tahes kombineeritud väljade puhul saate teha järgmist.
      - [Muuda](#edit-a-merged-field)
      - [Nimeta ümber](#rename-fields)
      - [Eralda](#separate-merged-fields)
      - [Välista](#exclude-fields)
      - [Liikumine üles või alla](#change-the-order-of-fields)

   1. Mis tahes väljade puhul saate teha järgmist.
      - [Ühenda väljad](#combine-fields-manually)
      - [Väljade rühma ühendamine](#combine-a-group-of-fields)
      - [Nimeta ümber](#rename-fields)
      - [Välista](#exclude-fields)
      - [Liikumine üles või alla](#change-the-order-of-fields)

1. Soovi korral [looge kliendi ID konfiguratsioon](#configure-customer-id-generation).

1. Soovi korral rühmitage [profiilid kodumajapidamistesse või klastritesse](#group-profiles-into-households-or-clusters).

> [!div class="nextstepaction"]
> [Järgmine samm: Ühinemise läbivaatamine](review-unification.md)

### <a name="edit-a-merged-field"></a>Redigeeri ühendatud välja

1. Valige ühendatud väli ja valige **Redigeeri**. Kuvatakse paani Kombineeri väljad.

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

Saate muuta ühendatud või eraldi väljade kuvatavat nime. Toodanguolemi nime ei saa muuta.

1. Valige väli ja valige **Nimeta ümber**.

1. Sisestage uus kuvatav nimi.

1. Valige nupp **Valmis**.

### <a name="separate-merged-fields"></a>Eraldaga ühendatud väljad

Ühendatud väljade eraldamiseks leidke atribuut tabelist. Eraldatud väljad kuvatakse üksikute andmepunktidena ühendatud kliendi profiilil.

1. Valige ühendatud väli ja valige **Eralda väljad**.

1. eralduse kinnitamine.

### <a name="exclude-fields"></a>Välista väljad

Välistage ühendatud või eraldi väli ühtsest kliendiprofiilist. Kui seda välja kasutatakse muudes protsessides (nt segmendis), eemaldage see nendest protsessidest, enne selle kliendiprofiililt eemaldamist.

1. Valige väli ja valige **Välista**.

1. Kinnitage välistamine.

Kõigi välistatud väljade loendi vaatamiseks valige **Väljad** Välistatud. Vajadusel saate lugeda välistatud välja.

### <a name="change-the-order-of-fields"></a>Väljade järjekorra muutmine

Mõned olemid sisaldavad rohkem üksikasju kui teised. Kui olem sisaldab välja kohta värskeid andmeid, saate väärtusi ühendades prioriseerida selle teiste olemite suhtes.

1. Valige väli.
  
1. Tellimuse seadmiseks valige **Nihuta üles/alla** või lohistage neid soovitud asendisse.

### <a name="combine-fields-manually"></a>Väljade käsitsi kombineerimine

Ühendatud atribuudi loomiseks ühendage eraldatud väljad.

1. Valige **Kombineeri** > **väljad**. Kuvatakse paani Kombineeri väljad.

1. Määrake ripploendis **Väljade ühendamine** koostevõitja poliitika.

1. Rohkemate väljade ühendamiseks valige **Lisa väli**.

1. Sisestage **Nimi** ja **Väljundvälja nimi**.

1. Muudatuse rakendamiseks valige **Tehtud**.

### <a name="combine-a-group-of-fields"></a>Väljade rühma ühendamine

Käsitlege väljade rühma ühe ühikuna. Näiteks kui meie kirjed sisaldavad välju Address1, Address2, City, State ja Zip, ei soovi me mõne muu kirje aadressiga2 liituda, arvates, et see muudaks meie andmed täielikumaks.

1. Valige **Kombineeri** > **väljade** rühm.

1. Määrake koostevõitja poliitika **jaotises Auaste ripploendi alusel**.

1. Valige **Lisa** ja valige, kas soovite väljadele lisada veel välju või rühmi.

1. **Esitage igale kombineeritud väljale nimi** ja **väljundnimi**.

1. Määrake **väljade rühmale nimi**.

1. Muudatuse rakendamiseks valige **Tehtud**.

## <a name="configure-customer-id-generation"></a>Kliendi ID loomise konfigureerimine

Määratlege, kuidas luua kliendi ID väärtusi, kliendi profiili kordumatuid identifikaatoreid. Andmete ühendamise protsessi ühendamisväljade etapp loob kliendiprofiili kordumatu identifikaatori. ID on *olemi CustomerId* *·*, mis tuleneb andmete ühendamise protsessist.

*CustomerId* põhineb mitte-null võitja esmavõtmete esimese väärtuse räsil. Need võtmed pärinevad andmete ühendamisel kasutatavatest olemitest ja neid mõjutab vastejärjestus.Nii võib loodud kliendi ID muutuda, kui vastetellimuse esmases olemis muutub primaarne võtmeväärtus. Esmane põhiväärtus ei pruugi alati esindada sama klienti.

Stabiilse kliendi ID konfigureerimine võimaldab teil seda käitumist vältida.

1. Valige vahekaart **Võtmed**.

1. Liikuge kursoriga **real CustomerId** ja valige **Konfigureeri**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Juhtelement ID loomise kohandamiseks.":::

1. Valige kuni viis välja, mille ID on kordumatu ja stabiilsem. Kirjed, mis ei vasta teie konfiguratsioonile, kasutavad selle asemel süsteemi konfigureeritud ID-d.  

1. Valige nupp **Valmis**.

## <a name="group-profiles-into-households-or-clusters"></a>Rühmitage profiilid leibkondadesse või klastritesse

Saate määratleda reeglid seotud profiilide rühmitamiseks klastrisse. Praegu on saadaval kahte tüüpi klastrid – Leibkonna ja kohandatud klastrid. Kui *Kliendi* olem sisaldab semantilisi välju *Person.LastName* ja *Location.Address*, valib süsteem eelmääratletud reeglitega subjekti automaatselt. Saate luua klastri ka oma reeglite ja tingimustega, mis sarnanevad [reeglitele](match-entities.md#define-rules-for-match-pairs).

1. Valige **Täpsem** > **loo klaster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Juhtelement uue klastri loomiseks.":::

1. Valige **Leibkonna** või **Kohandatud** klastri vahel. Kui semantilised väljad *Person.LastName* ja *Location.Address* on olemas *Kliendi* olemis, valitakse automaatselt leibkond.

1. Sisestage klastrile nimi ja valige **Valmis**.

1. Loodud klastri leidmiseks valige vahekaart **Klastrid**.

1. Määrake klastri määratlemiseks reeglid ja tingimused.

1. Valige nupp **Valmis**. Klaster luuakse siis, kui ühendamisprotsess on lõpule viidud. Klastri identifikaatorid lisatakse olemile *Klient* uute väljadena.

> [!div class="nextstepaction"]
> [Järgmine samm: Ühinemise läbivaatamine](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
