---
title: Ühendamissätete värskendamine
description: Saate värskendada duplikaatreegleid, vastendusreegleid või ühendatud välju ühendamissätetes.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 1af7f018abd412c833ff22b3880f0e4508ff4953
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139573"
---
# <a name="update-the-unification-settings"></a>Ühendamissätete värskendamine

Ühendamissätete ülevaatamiseks või muutmiseks pärast ühtse profiili loomist tehke järgmist.

1. Avage **Jaotis Andmete** > **ühendamine**.

   :::image type="content" source="media/m3_unified.png" alt-text="Kuvatõmmis lehest Andmete ühendamine pärast andmete ühendamist.":::

   > [!TIP]
   > Paan **Sobitamistingimused** kuvatakse ainult siis, kui on valitud mitu olemit.

1. Valige, mida soovite värskendada.
   - [Lähteväljad](#edit-source-fields) olemite või atribuutide lisamiseks või atribuuditüüpide muutmiseks.
   - [Dubleerige kirjeid](#manage-deduplication-rules), et hallata duplikatsioonireegleid või ühendamiseelistusi.
   - [Vastendamistingimused](#manage-match-rules) vastendusreeglite värskendamiseks kahes või enamas olemis.
   - [Ühendatud kliendiväljad väljade](#manage-unified-fields) ühendamiseks või välistamiseks. Samuti saate seotud profiile rühmitada klastritesse.

1. Pärast muudatuste tegemist valige järgmine valik.

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Kuvatõmmis lehest &quot;Andmete ühendamine&quot;, kus on esile tõstetud ühendamissuvandid.":::

   - [Vastendustingimuste (duplikatsiooni- ja vastendusreeglid) kvaliteedi kiireks hindamiseks käivitage vastendustingimused](#run-matching-conditions) ilma ühtset profiili värskendamata. Valikut **Käivita ainult** vastavad tingimused ei kuvata ühe olemi puhul.
   - [Ühendage kliendiprofiilid](#run-updates-to-the-unified-customer-profile), et käivitada vastavusse viimise tingimused ja värskendada ühtset kliendiprofiili olemit, mõjutamata sõltuvusi (nt rikastamised, segmendid või mõõdud). Sõltuvaid protsesse ei käitata, kuid värskendatakse värskendamise [ajakavas määratletud viisil](system.md#schedule-tab).
   - [Ühendage kliendiprofiilid ja sõltuvused](#run-updates-to-the-unified-customer-profile), et käivitada vastavusse viimise tingimused ning värskendada ühtset kliendiprofiili olemit ja kõiki sõltuvusi (nt rikastamised, segmendid või mõõdud). Kõik protsessid käivitatakse automaatselt.

## <a name="edit-source-fields"></a>Allikaväljade redigeerimine

Atribuuti või olemit ei saa eemaldada, kui need on juba ühendatud.

1. Valige **paanil Allikaväljad** käsk **Redigeeri**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Kuvatõmmis lehest Lähteväljad, kus on näha primaarvõtmete arv, vastendatud ja kaardistamata väljad":::

   Kuvatakse kaardistatud ja kaardistamata väljade arv.

1. Valige **Olemite ja väljade** valimine muude atribuutide või olemite lisamiseks. Kasutage otsingut või kerige, et leida ja valida teile huvi pakkuvad atribuudid ja olemid. Valige suvand **Rakenda**.

1. Soovi korral saate muuta olemi primaarvõtit, atribuuditüüpe ja lülitada **intelligentse vastenduse** sisse või välja. Lisateavet vaadake jaotisest [Primaarvõtme ja atribuutide](map-entities.md#select-primary-key-and-semantic-type-for-attributes) semantilise tüübi valimine.

1. Dubleerimisreeglite muutmiseks valige **Edasi või valige** Salvesta ja sule **ning naaske valikusse** Värskenda [ühendamissätted](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Dubleerimisreeglite haldamine

1. Valige **paanil Duplikaatkirjed** käsk **Redigeeri**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Kirje duplikaatkirjete lehe kuvatõmmis, kus on kuvatud dubleeritud kirjete arv" lightbox="media/m3_duplicates_edit.png":::

   Leitud duplikaatkirjete arv kuvatakse jaotises **Duplikaadid**. Veerg **Kirjed eemaldatud** näitab, millistel olemitel olid duplikaatkirjed ja dubleeritud kirjete protsent.

1. Kui lisasite rikastatud olemi, valige **Kasuta rikastatud olemeid**. Lisateavet leiate teemast [Andmeallikate rikastamine](data-sources-enrichment.md).

1. Duplikatsioonireeglite haldamiseks valige üks järgmistest suvanditest.
   - **Loo uus reegel**: valige **lisa reegel** vastava olemi alt. Lisateavet vaadake jaotisest [Dubleerimisreeglite](remove-duplicates.md#define-deduplication-rules) määratlemine.
   - **Muuda reegli tingimusi**: valige reegel ja seejärel **redigeerige**. Muutke välju, lisage või eemaldage tingimusi või lisage või eemaldage erandeid.
   - **Eelvaade**: valige reegel ja seejärel **eelvaade,** et vaadata selle reegli viimaseid käivitamistulemusi.
   - **Desaktiveerige reegel**: valige reegel ja seejärel **inaktiveerige**, et säilitada duplikatsioonireegel, välistades selle sobitamisprotsessist.
   - **Reegli** dubleerimine: valige reegel ja seejärel **dubleerige**, et luua muudatustega sarnane reegel.
   - **Kustuta reegel**: valige reegel ja seejärel **kustutage**.

1. Koosteeelistuste muutmiseks valige olem. Eelistusi saate muuta ainult reegli loomisel.
   1. Valige **Redigeeri koosteeelistusi** ja muutke suvandit **Kirje säilitamiseks**.
   1. Olemi üksikute atribuutide koosteeelistuste muutmiseks valige **Täpsem** ja tehke vajalikud muudatused.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Täpsemate koosteeelistuste kuvatõmmis, millel on kujutatud kõige hiljutisem meiliaadress ja kõige täielikum aadress":::

   1. Valige nupp **Valmis**.

1. Sobivate tingimuste muutmiseks valige **Edasi või valige** Salvesta ja sule **ning naaske valikusse** Värskenda [ühendamissätted](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Vastendusreeglite haldamine

Enamuse vasteparameetritest saate ümber konfigureerida ja peenhäälestada. Olemeid ei saa lisada ega kustutada. Vastendamisreeglid ei kehti ühele olemile.

1. Valige paanil Sobitamistingimused **käsk** **Redigeeri**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Kuvatõmmis vastendusreeglite ja -tingimuste lehest koos statistikaga." lightbox="media/m3_match_edit.png":::

   Lehel kuvatakse vastejärjestus ja määratletud reeglid ning järgmine statistika.
   - **Kordumatud lähtekirjed** näitab viimases vastekäituses töödeldud üksikute lähtekirjete arvu.
   - **Vastendatud ja vastendamata kirjed** tõstab esile, mitu kordumatut kirjet on alles pärast vastendusreeglite töötlemist.
   - **Ainult vastendatud kirjed** näitab ainult vastete arvu kõigis vastepaarides.

1. Kõigi reeglite tulemuste ja nende skooride vaatamiseks valige **Kuva viimane käivitamine**. Kuvatakse tulemused, sh alternatiivsed kontakti ID-d. Tulemused saate alla laadida.

1. Kindla reegli tulemite ja skooride vaatamiseks valige reegel ja seejärel **eelvaade**. Kuvatakse tulemused. Tulemused saate alla laadida.

1. Reegli konkreetse tingimuse tulemite kuvamiseks valige reegel ja seejärel **Redigeeri**. Valige paanil Redigeerimine **tingimuse all Eelvaade**. Tulemused saate alla laadida.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Vastendamata ja vastendatud kirjete graafiline esitus koos andmete loendiga.":::

1. Kui lisasite rikastatud olemi, valige **Kasuta rikastatud olemeid**. Lisateavet leiate teemast [Andmeallikate rikastamine](data-sources-enrichment.md).

1. Reeglite haldamiseks valige üks järgmistest suvanditest.
   - **Loo uus reegel**: valige **lisa reegel** vastava olemi alt. Lisateavet vaadake jaotisest [Vastepaaride](match-entities.md#define-rules-for-match-pairs) reeglite määratlemine.
   - **Reeglite järjestuse muutmine,** kui määratlesite mitu reeglit: lohistage reeglid soovitud järjekorda. Lisateavet vaadake jaotisest [Vastejärjestuse](match-entities.md#specify-the-match-order) määramine.
   - **Muuda reegli tingimusi**: valige reegel ja seejärel **redigeerige**. Muutke välju, lisage või eemaldage tingimusi või lisage või eemaldage erandeid.
   - **Desaktiveerige reegel**: valige reegel ja seejärel **inaktiveerige**, et vastendusreegel säiliks, välistades selle sobitamisprotsessist.
   - **Reegli** dubleerimine: valige reegel ja seejärel **dubleerige**, et luua muudatustega sarnane reegel.
   - **Kustuta reegel**: valige reegel ja seejärel **kustutage**.

1. Ühtsete väljade muutmiseks valige **Edasi või valige** Salvesta ja sule **ning naaske valikusse** Värskenda [ühendamissätted](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Ühendatud väljade haldamine

1. Valige **paanil Ühendatud kliendiväljad** käsk **Redigeeri**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Ühendatud kliendiväljade kuvatõmmis":::

1. Vaadake üle kombineeritud ja välistatud väljad ning tehke vajaduse korral muudatusi. Lisage või muutke CustomerID võtit või rühmitage profiilid klastriteks. Lisateavet vaadake jaotisest [Kliendiväljade ühendamine](merge-entities.md).

1. Valige **Edasi**, et vaadata üle ühendamissätted ning [värskendada ühtset profiili ja sõltuvusi](#run-updates-to-the-unified-customer-profile), või valige **Salvesta ja sule** ning naaske valikusse [Värskenda ühendamissätteid](#update-the-unification-settings), et teha rohkem muudatusi.

## <a name="run-matching-conditions"></a>Käivitage sobivad tingimused

Vastendustingimuste käivitamine käivitab ainult duplikatsiooni- ja vastendusreeglid ning *värskendab olemeid Deduplication_** ja *ConflationMatchPair*.

1. **Tehke lehel Andmete** > **ühendamine** valik **Käivita ainult** vastavad tingimused.

   Paanidel Kirjete **duplikaat** ja **Tingimuste** sobitamine kuvatakse **olek Järjestatud** või **Värskendav**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Kui vastendusprotsess on lõpule viidud, valige paanil Sobitamistingimused käsk **Redigeeri** **.**

   :::image type="content" source="media/match-KPIs.png" alt-text="Numbrite ja üksikasjadega vastete lehe põhimõõdikute kärbitud kuvatõmmis.":::

1. Muudatuste tegemiseks vaadake teemasid [Dubleerimisreeglite](#manage-deduplication-rules) haldamine või [Vastendusreeglite](#manage-match-rules) haldamine.

1. Käivitage vastendusprotsess uuesti või [käivitage kliendiprofiili](#run-updates-to-the-unified-customer-profile) värskendused.

## <a name="run-updates-to-the-unified-customer-profile"></a>Ühtse kliendiprofiili värskenduste käivitamine

1. **Valige lehelt Data Unify (Andmete** > **ühendamine**):

   - **Kliendiprofiilide ühendamine: käivitab** vastendustingimused ja värskendab ühtset kliendiprofiili olemit, mõjutamata sõltuvusi (nt rikastamised, segmendid või mõõdud). Sõltuvaid protsesse ei käitata, kuid värskendatakse värskendamise [ajakavas määratletud viisil](system.md#schedule-tab).

   - **Ühendage kliendiprofiilid ja sõltuvused**: käitatakse vastendustingimusi ning värskendatakse ühtset profiili ja kõiki sõltuvusi. Kõik protsessid käivitatakse automaatselt. Kui kõik järgnevad protsessid on lõpule viidud, kajastab kliendiprofiil värskendatud andmeid.

   Paanidel Kirjete duplikaat **,** Vastendamise tingimused **ja** Ühtsed kliendiväljad **kuvatakse** **järjestatud või** värskendav **olek**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Eduka käitamise tulemused kuvatakse lehel **Ühenda**, mis näitab ühtsete kliendiprofiilide arvu.
