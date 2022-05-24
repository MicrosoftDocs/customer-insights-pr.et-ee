---
title: Ühendamissätete värskendamine
description: Saate värskendada ühendamissätete duplikaatreegleid, vastereegleid või ühtseid välju.
ms.date: 05/04/2022
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
ms.openlocfilehash: be399da9b98d8803d7d1a90f44a40e0d638a8d47
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755585"
---
# <a name="update-the-unification-settings"></a>Ühendamissätete värskendamine

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Mis tahes ühendamissätete ülevaatamiseks või muutmiseks pärast ühtse profiili loomist tehke järgmist.

1. **Avage jaotisSe Andmete** > **ühendamine**.

   :::image type="content" source="media/m3_unified.png" alt-text="Kuvatõmmis lehest Andmete ühendamine pärast andmete ühendamist.":::

   > [!TIP]
   > Paanil **Sobivad tingimused** kuvatakse ainult siis, kui on valitud mitu olemit.

1. Valige, mida soovite värskendada.
   - [Lähteväljad](#edit-source-fields) olemite või atribuutide lisamiseks või atribuuditüüpide muutmiseks.
   - [Duplikaatkirjed](#manage-deduplication-rules) deduplatsioonireeglite haldamiseks või eelistuste ühendamiseks.
   - [Tingimuste sobitamine](#manage-match-rules), et värskendada sobitamisreegleid kahes või enamas olemis.
   - [Ühtsed kliendiväljad](#manage-unified-fields) väljade ühendamiseks või välistamiseks. Samuti saate rühmitada seotud profiilid klastritesse.

1. Pärast muudatuste tegemist valige järgmine valik.

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Kuvatõmmis lehest Andmete ühendamine, kus on esile tõstetud suvandid Ühendamine.":::

   - Ühtse kliendiprofiili värskendamiseks (sõltuvustega või ilma) lugege teemat [Kliendiprofiili](#run-updates-to-the-unified-customer-profile) värskenduste käivitamine.
   - Sobivate tingimuste kvaliteedi hindamiseks ilma ühtset profiili värskendamata lugege teemat [Käivita sobivad tingimused](#run-matching-conditions). Suvand Käivita **ainult** vastavad tingimused ei kuvata ühe olemi puhul.

## <a name="edit-source-fields"></a>Lähteväljade redigeerimine

Atribuuti või olemit ei saa eemaldada, kui need on juba ühendatud.

1. Valige **paanil** Allikas käsk **Redigeeri**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Lehe Lähteväljade kuvatõmmis, kus kuvatakse primaarvõtmete arv, vastendatud ja vastendamata väljade arv":::

   Vastendatud ja vastendamata väljade kuvamise arv.

1. Muude atribuutide või olemite lisamiseks valige **Vali olemid ja väljad**. Kasutage otsingut või kerige, et leida ja valida teile huvi pakkuvad atribuudid ja olemid. Valige suvand **Rakenda**.

1. Soovi korral saate muuta olemi esmast võtit, atribuuditüüpe ja lülitada **intelligentne vastendamine** sisse või välja. Lisateavet leiate teemast [Atribuutide](map-entities.md#select-primary-key-and-semantic-type-for-attributes) primaarvõtme ja semantilise tüübi valimine.

1. Deduplatsioonireeglite muutmiseks valige Edasi või valige **Salvesta ja sulge** ning naaske ühendussätete värskendamise juurde.**·**[...](#update-the-unification-settings)

## <a name="manage-deduplication-rules"></a>Deduplatsioonireeglite haldamine

1. Valige **paanil** Duplikaatkirjed **käsk Redigeeri**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Duplikaatkirjete lehe kuvatõmmis, kus on kuvatud duplikaatkirjete arv" lightbox="media/m3_duplicates_edit.png":::

   Duplikaatide alt **leitud duplikaatkirjete** arv kuvatakse jaotises Duplikaadid. Veerus **Kirjed on näidatud, millistel** olemitel olid duplikaatkirjed ja duplikaatkirjete protsent.

1. Kui lisasite rikastatud olemi, valige **Kasuta rikastatud olemeid**. Lisateavet leiate teemast [Andmeallikate rikastamine](data-sources-enrichment.md).

1. Deduplatsioonireeglite haldamiseks valige mõni järgmistest suvanditest.
   - **Uue reegli** loomine: valige **sobiva olemi all Lisa reegel**. Lisateavet leiate teemast [Deduplatsioonireeglite](remove-duplicates.md#define-deduplication-rules) määratlemine.
   - **Reeglitingimuste** muutmine: valige reegel ja seejärel **redigeerige**. Muutke välju, lisage või eemaldage tingimused või lisage või eemaldage erandid.
   - **Eelvaade**: valige reegel ja seejärel **vaadake eelvaadet**, et vaadata selle reegli viimaseid käitustulemusi.
   - **Reegli** desaktiveerimine: valige reegel ja seejärel **desaktiveerige**, et säilitada deduplatsioonireegel, välistades selle sobitamisprotsessist.
   - **Reegli** dubleerimine: valige reegel ja seejärel **dubleerige**, et luua sarnane reegel muudatustega.
   - **Kustuta** reegel: valige reegel ja seejärel **kustutage**.

1. Koosteeelistuste muutmiseks valige olem. Eelistusi saab muuta ainult siis, kui reegel on loodud.
   1. Valige **Redigeeri koosteelistusi** ja muutke suvandi Kirje **säilitamiseks**.
   1. Olemi üksikute atribuutide koosteelistuste muutmiseks valige **Täpsemalt** ja tehke vajalikud muudatused.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Kuvatõmmis täpsematest koosteelistustest, mis näitavad uusimat meilisõnumit ja kõige täielikumat aadressi":::

   1. Valige nupp **Valmis**.

1. Sobivates tingimustes muudatuste tegemiseks valige Edasi või valige **Salvesta ja sule** ning naaske valikusse **Värskenda ühendamise sätteid**.[...](#update-the-unification-settings)

## <a name="manage-match-rules"></a>Vastendusreeglite haldamine

Enamuse vasteparameetritest saate ümber konfigureerida ja peenhäälestada. Olemeid ei saa lisada ega kustutada. Vastereeglid ei kehti ühele olemile.

1. Valige **paanil** Sobitamistingimused **käsk Redigeeri**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Kuvatõmmis lehelt Vaste reeglid ja tingimused statistikaga." lightbox="media/m3_match_edit.png":::

   Lehel kuvatakse vaste järjekord ja määratletud reeglid ning järgmine statistika.
   - **Kordumatud lähtekirjed** näitab viimases vastekäituses töödeldud üksikute lähtekirjete arvu.
   - **Vastendatud ja vastendamata kirjed** tõstab esile, mitu kordumatut kirjet on alles pärast vastendusreeglite töötlemist.
   - **Ainult vastendatud kirjed** näitab ainult vastete arvu kõigis vastepaarides.

1. Kõigi reeglite ja nende tulemuste kuvamiseks valige **Kuva viimane käivitamine**. Kuvatakse tulemused, sh alternatiivsed kontakti ID-d. Saate tulemused alla laadida.

1. Konkreetse reegli tulemuste ja skooride vaatamiseks valige reegel ja seejärel **eelvaade**. Tulemused kuvatakse. Saate tulemused alla laadida.

1. Reegli kindla tingimuse tulemuste vaatamiseks valige reegel ja seejärel **Redigeeri**. Valige paanil **Redigeerimine tingimuse all Eelvaade**. Saate tulemused alla laadida.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Tasakaalustamata ja sobitatud kirjete graafiline esitus koos andmete loendiga.":::

1. Kui lisasite rikastatud olemi, valige **Kasuta rikastatud olemeid**. Lisateavet leiate teemast [Andmeallikate rikastamine](data-sources-enrichment.md).

1. Reeglite haldamiseks valige mõni järgmistest suvanditest.
   - **Uue reegli** loomine: valige **sobiva olemi all Lisa reegel**. Lisateavet leiate teemast [Vastepaaride](match-entities.md#define-rules-for-match-pairs) reeglite määratlemine.
   - **Muutke reeglite** järjekorda, kui määratlesite mitu reeglit: lohistage reeglid soovitud järjekorda. Lisateavet leiate teemast [Vastendamise tellimuse](match-entities.md#specify-the-match-order) määramine.
   - **Reeglitingimuste** muutmine: valige reegel ja seejärel **redigeerige**. Muutke välju, lisage või eemaldage tingimused või lisage või eemaldage erandid.
   - **Reegli** desaktiveerimine: valige reegel ja seejärel **desaktiveerige** vastereegli säilitamiseks, välistades selle sobitamisprotsessist.
   - **Reegli** dubleerimine: valige reegel ja seejärel **dubleerige**, et luua sarnane reegel muudatustega.
   - **Kustuta** reegel: valige reegel ja seejärel **kustutage**.

1. Ühtsetes väljades muudatuste tegemiseks valige Edasi või valige **Salvesta ja sule** ning naaske ühendussätete värskendamise **juurde**.[...](#update-the-unification-settings)

## <a name="manage-unified-fields"></a>Ühtsete väljade haldamine

1. Valige **Redigeeri** paanil **Ühendatud kliendiväljad**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Ühtsete kliendiväljade kuvatõmmis":::

1. Vaadake üle kombineeritud ja välistatud väljad ning tehke vajadusel muudatusi. Kliendi ID võtme- või rühmaprofiilide lisamine või redigeerimine klastritesse. Lisateavet vt teemast [Unify customer fields](merge-entities.md).

1. Ühendamissätete ülevaatamiseks ja ühtse profiili ja sõltuvuste **värskendamiseks valige** Edasi [või valige](#run-updates-to-the-unified-customer-profile) Salvesta ja sulge **ning naaske** ühendamise sätete [värskendamisse, et teha rohkem muudatusi.](#update-the-unification-settings)

## <a name="run-matching-conditions"></a>Käivita sobivad tingimused

1. **Valige lehel** > **Andmete** ühendamine **käsk Käivita ainult** vastavad tingimused.

   Paanidel **Duplikaatkirjed** ja **kattuvad tingimused** kuvatakse **järjekorras** või **värskendav**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

1. Kui sobitamisprotsess on lõpule jõudnud, valige **paanil** Sobitamistingimused **käsk Redigeeri**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Numbrite ja üksikasjadega vastete lehe põhimõõdikute kärbitud kuvatõmmis.":::

1. Muudatuste tegemiseks lugege teemat [Tükeldamisreeglite](#manage-deduplication-rules) haldamine või [Vastereeglite](#manage-match-rules) haldamine.

1. Käivitage vasteprotsess uuesti või [käivitage kliendiprofiili](#run-updates-to-the-unified-customer-profile) värskendused.

## <a name="run-updates-to-the-unified-customer-profile"></a>Ühtse kliendiprofiili värskenduste käivitamine

1. **Valige lehel Andmete** > **ühendamine**.

   - **Kliendiprofiilide** ühendamine: värskendab ühtset kliendiprofiili olemit, mõjutamata sõltuvusi (nt rikastamine, segmendid või meetmed). Sõltuvaid protsesse ei käitata, kuid neid värskendatakse värskendamisgraafikus [määratletud viisil](system.md#schedule-tab).

   - **Kliendiprofiilide ja sõltuvuste** ühendamine: värskendab ühtset profiili ja kõiki sõltuvusi. Kõik protsessid käivitatakse automaatselt. Pärast seda, kui kõik tootmisahela järgmise etapi protsessid on lõpule viidud, kajastab kliendi profiil värskendatud andmeid.

   Paanidel **Duplikaatkirjed**, **vastavad tingimused** ja **Ühtsed kliendiväljad** kuvatakse **järjekorras** või **värskendav**.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]
