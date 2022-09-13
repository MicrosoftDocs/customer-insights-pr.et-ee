---
title: Kliendi, konto või kontakti ühendamise sätete värskendamine
description: Värskendage kliendi või konto ühendamise sätete duplikaatreegleid, vastendusreegleid või ühtseid välju.
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392466"
---
# <a name="update-unification-settings"></a>Ühendamissätete värskendamine

Ühendamissätete ülevaatamiseks või muutmiseks pärast ühtse profiili loomist tehke järgmist.

1. Avage **Jaotis Andmete** > **ühendamine**.

   Üksikklientide (B-to-C) **puhul kuvatakse lehel Ühendamine** iga ühendamisetapi ühendatud kliendiprofiilide ja paanide arv.

   :::image type="content" source="media/m3_unified.png" alt-text="Kuvatõmmis lehest Andmete ühendamine pärast andmete ühendamist." lightbox="media/m3_unified.png":::

   Ärikontode (B-to-B) **puhul kuvatakse lehel Ühendamine** iga konto ühendamise etapi ühtsete kontoprofiilide ja paanide arv. Kui kontaktid olid ühendatud, kuvatakse iga kontakti ühendamise etapi ühendatud kontaktiprofiilide ja paanide arv. Valige jaotises **Kontode ühendamine või** Kontaktide **ühendamine (eelvaade)** sobiv paan sõltuvalt sellest, mida soovite värskendada.

   :::image type="content" source="media/b2b_unified.png" alt-text="Kuvatõmmis lehest Data Unify pärast konto ja kontaktandmete ühendamist." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > Paan **Sobitamistingimused** kuvatakse ainult siis, kui on valitud mitu olemit.

1. Valige, mida soovite värskendada.
   - [Lähteväljad](#edit-source-fields) atribuutide või olemite lisamiseks või atribuuditüüpide muutmiseks. Atribuudi eemaldamise kohta leiate teavet teemast [Ühtse välja](#remove-a-unified-field) eemaldamine. Olemi eemaldamise kohta leiate teavet teemast [Ühtse olemi](#remove-a-unified-entity) eemaldamine.
   - [Dubleerige kirjeid](#manage-deduplication-rules), et hallata duplikatsioonireegleid või ühendamiseelistusi.
   - [Vastendamistingimused](#manage-match-rules) vastendusreeglite värskendamiseks kahes või enamas olemis.
   - [Ühendatud kliendiväljad väljade](#manage-unified-fields) ühendamiseks või välistamiseks. Samuti saate seotud profiile rühmitada klastritesse.
   - [Semantilised väljad](#manage-semantic-fields-for-unified-contacts) ühendatud kontaktiväljade semantiliste tüüpide haldamiseks.
   - [Seosed](#manage-contact-and-account-relationships) kontakti ja konto vahelise seose haldamiseks.

1. Pärast muudatuste tegemist valige järgmine valik.

   - [Vastendustingimuste (duplikatsiooni- ja vastendusreeglid) kvaliteedi kiireks hindamiseks käivitage vastendustingimused](#run-matching-conditions) ilma ühtset profiili värskendamata. Valikut **Käivita ainult** vastavad tingimused ei kuvata ühe olemi puhul.
   - [Ühendage profiilid](#run-updates-to-the-unified-profile), et käivitada sobitamistingimused ja värskendada ühtse profiili olemit, ilma et see mõjutaks sõltuvusi (nt rikastamised, segmendid või mõõdud). Sõltuvaid protsesse ei käitata, kuid värskendatakse värskendamise [ajakavas määratletud viisil](schedule-refresh.md).
   - [Ühendage profiilid ja sõltuvused, et käivitada kattuvad](#run-updates-to-the-unified-profile) tingimused, värskendada ühtse profiili olemit ja värskendada kõiki sõltuvusi (nt rikastamised, segmendid või mõõdud). Kõik protsessid käivitatakse automaatselt. B-to-B-s käivitatakse ühendamine nii konto- kui ka kontaktiolemites, kes värskendavad ühendatud profiile.

## <a name="edit-source-fields"></a>Allikaväljade redigeerimine

1. Valige **paanil Allikaväljad** käsk **Redigeeri**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Kuvatõmmis lehest Lähteväljad, kus on näha primaarvõtmete arv, vastendatud ja kaardistamata väljad":::

   Kuvatakse kaardistatud ja kaardistamata väljade arv.

1. Muude atribuutide või olemite lisamiseks valige **Olemite ja väljade** valimine.

1. Soovi korral saate muuta olemi primaarvõtit, atribuuditüüpe ja lülitada **intelligentse vastenduse** sisse või välja. Lisateavet leiate teemast [Allikaväljade](map-entities.md) valimine.

1. Dubleerimisreeglite muutmiseks valige **Edasi või valige** Salvesta ja sule **ning naaske jaotisse** Värskenda [ühendamissätted](#update-unification-settings).

### <a name="remove-a-unified-field"></a>Ühtse välja eemaldamine

Ühendatud välja eemaldamiseks tuleb väli eemaldada kõigist sõltuvustest (nt segmendid, mõõdud, rikastamised või seosed).

1. Kui kõik välja sõltuvused on eemaldatud, avage **Data** > **Unify**.

1. Valige **paanil Ühendatud kliendiväljad** käsk **Redigeeri**.

1. Valige välja kõik esinemiskorrad ja seejärel valige **Välista**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Kuvatõmmis ühendatud väljade lehest, kus on kuvatud valitud väljad ja nupp Välista":::

1. Kinnitamiseks valige **Valmis** ja seejärel valige **Salvesta ja sule**.

   > [!TIP]
   > Kui näete teadet "Ei õnnestunud ühendada. Määratud ressurssi ei saa muuta ega kustutada allavoolu sõltuvuste tõttu", siis kasutatakse välja endiselt järgnevas sõltuvuses.

1. Kui välja kasutatakse duplikaatkirjete või vastendustingimuste reeglis, tehke järgmist. Vastasel juhul minge järgmisele sammule.
   1. Valige **paanil Duplikaatkirjed** käsk **Redigeeri**.
   1. Eemaldage väli kõigist reeglitest, milles seda kasutatakse (kui see on olemas) ja seejärel valige **Edasi**.
   1. Eemaldage **lehel Tingimuste** sobitamine väli kõigist reeglitest, milles seda kasutatakse (kui see on olemas) ja seejärel valige **Salvesta ja sule**.
   1. Valige **Ühenda** > **kliendiprofiilid ja sõltuvused**. Enne järgmise sammu juurde asumist oodake ühendamise lõpuleviimist.

1. Valige **paanil Allikaväljad** käsk **Redigeeri**.

1. Valige **Olemite ja väljade** valimine ning tühjendage välja iga esinemiskorra kõrval olev ruut.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Kuvatõmmis olemite ja väljade valimise dialoogiboksist, kus on näha tühjendatud märkeruudud":::

1. Valige suvand **Rakenda**.

1. Valige **Salvesta ja sule**.

1. Valige **Ühenda** > **kliendiprofiilid ja sõltuvused**, et värskendada ühtset profiili.

### <a name="remove-a-unified-entity"></a>Ühendatud olemi eemaldamine

Ühendatud olemi eemaldamiseks tuleb olem eemaldada kõigist sõltuvustest, nagu segmendid, mõõdud, rikastamised või seosed.

1. Kui kõik olemi sõltuvused on eemaldatud, avage **Jaotis Andmete** > **ühendamine**.

1. Valige **paanil Ühendatud kliendiväljad** käsk **Redigeeri**.

1. Valige olemi jaoks kõik väljad ja seejärel valige **Välista**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Kuvatõmmis ühendatud väljadest, kus on valitud kõik olemi väljad ja nupp Välista":::

1. Kinnitamiseks valige **Valmis** ja seejärel valige **Salvesta ja sule**.

   > [!TIP]
   > Kui näete teadet "Ei õnnestunud ühendada. Määratud ressurssi ei saa muuta ega kustutada järgmise etapi sõltuvuste tõttu", siis kasutatakse üksust endiselt järgnevas sõltuvuses.

1. Valige **paanil Duplikaatkirjed** käsk **Redigeeri**.

1. Eemaldage olemist kõik reeglid (kui neid on) ja seejärel valige **Edasi**.

1. **Valige lehel Vastavusse viimise tingimused** olem ja seejärel valige **Kustuta**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Kuvatõmmis tingimustest, kus olem on valitud ja nupp Kustuta":::

1. Valige **Salvesta ja sule**.

1. Valige **paanil Allikaväljad** käsk **Redigeeri**.

1. Valige **Olemite ja väljade** valimine ning tühjendage olemi kõrval olev märkeruut.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Kuvatõmmis olemite ja väljade valimise dialoogiboksist, kus olemi märkeruut on tühjendatud":::

1. Valige suvand **Rakenda**.

1. Valige **Salvesta ja sule**.

1. Valige **Ühenda** > **kliendiprofiilid ja sõltuvused**, et värskendada ühtset profiili.

## <a name="manage-deduplication-rules"></a>Dubleerimisreeglite haldamine

1. Valige **paanil Duplikaatkirjed** käsk **Redigeeri**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Kirje duplikaatkirjete lehe kuvatõmmis, kus on kuvatud dubleeritud kirjete arv" lightbox="media/m3_duplicates_edit.png":::

   Leitud duplikaatkirjete arv kuvatakse jaotises **Duplikaadid**. Veerg **Kirjed eemaldatud** näitab, millistel olemitel olid duplikaatkirjed ja dubleeritud kirjete protsent.

1. Rikastatud olemi kasutamiseks valige **Kasuta rikastatud olemeid**. Lisateavet leiate teemast [Andmeallikate](data-sources-enrichment.md) rikastamine.

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

   1. Valige nupp **Valmis**.

1. Sobivate tingimuste muutmiseks valige **Edasi või valige** Salvesta ja sule **ning naaske valikusse** Värskenda [ühendamissätted](#update-unification-settings).

## <a name="manage-match-rules"></a>Vastendusreeglite haldamine

Enamuse vasteparameetritest saate ümber konfigureerida ja peenhäälestada. Olemeid ei saa lisada ega kustutada. Vastendamisreeglid ei kehti ühele olemile.

1. Valige paanil Sobitamistingimused **käsk** **Redigeeri**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Kuvatõmmis vastendusreeglite ja -tingimuste lehest koos statistikaga." lightbox="media/m3_match_edit.png":::

   Lehel kuvatakse vastejärjestus ja määratletud reeglid ning järgmine statistika.
   - **Kordumatud lähtekirjed** näitavad üksikute lähtekirjete arvu, mida töödeldi viimase vaste käitamise käigus.
   - **Vastendatud ja vastendamata kirjed** tõstavad esile, kui palju kordumatuid kirjeid jääb pärast vastereeglite töötlemist alles.
   - **Vastendatud kirjed näitavad ainult** vastete arvu kõigis teie matšipaarides.

1. Kõigi reeglite tulemuste ja nende skooride vaatamiseks valige **Kuva viimane käivitamine**. Kuvatakse tulemused, sh alternatiivsed kontakti ID-d. Tulemused saate alla laadida.

1. Kindla reegli tulemite ja skooride vaatamiseks valige reegel ja seejärel **eelvaade**. Tulemused kuvatakse. Tulemused saate alla laadida.

1. Reegli konkreetse tingimuse tulemite kuvamiseks valige reegel ja seejärel **Redigeeri**. Valige paanil Redigeerimine **tingimuse all Eelvaade**. Tulemused saate alla laadida.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Vastendamata ja vastendatud kirjete graafiline esitus koos andmete loendiga.":::

1. Kui lisasite rikastatud olemi, valige **Kasuta rikastatud olemeid**. Lisateavet leiate teemast [Andmeallikate](data-sources-enrichment.md) rikastamine.

1. Reeglite haldamiseks valige üks järgmistest suvanditest.
   - **Loo uus reegel**: valige **lisa reegel** vastava olemi alt. Lisateavet vaadake jaotisest [Vastepaaride](match-entities.md#define-rules-for-match-pairs) reeglite määratlemine.
   - **Reeglite järjestuse muutmine,** kui määratlesite mitu reeglit: lohistage reeglid soovitud järjekorda. Lisateavet vaadake jaotisest [Vastejärjestuse](match-entities.md#specify-the-match-order) määramine.
   - **Muuda reegli tingimusi**: valige reegel ja seejärel **redigeerige**. Muutke välju, lisage või eemaldage tingimusi või lisage või eemaldage erandeid.
   - **Desaktiveerige reegel**: valige reegel ja seejärel **inaktiveerige**, et vastendusreegel säiliks, välistades selle sobitamisprotsessist.
   - **Reegli** dubleerimine: valige reegel ja seejärel **dubleerige**, et luua muudatustega sarnane reegel.
   - **Kustuta reegel**: valige reegel ja seejärel **kustutage**.

1. Ühtsete väljade muutmiseks valige **Edasi või valige** Salvesta ja sule **ning naaske valikusse** Värskenda [ühendamissätted](#update-unification-settings).

## <a name="manage-unified-fields"></a>Ühendatud väljade haldamine

1. Valige **paanil Ühendatud kliendiväljad** käsk **Redigeeri**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Ühendatud kliendiväljade kuvatõmmis":::

1. Vaadake üle kombineeritud ja välistatud väljad ning tehke vajaduse korral muudatusi. Lisage või muutke CustomerID võtit või rühmitage profiilid klastriteks. Lisateavet vaadake jaotisest [Kliendiväljade ühendamine](merge-entities.md).

1. Klientide või kontode puhul valige **Ühendatud profiili ja** sõltuvuste [ülevaatamiseks ja värskendamiseks nupp Edasi](#run-updates-to-the-unified-profile). Või valige **Salvesta ja sule** ning naaske valikusse [Värskenda ühendamissätteid](#update-unification-settings), et teha rohkem muudatusi.

   Kontaktide puhul valige **semantiliste väljade haldamiseks Nupp Edasi**. Või valige **Salvesta ja sule** ning naaske valikusse [Värskenda ühendamissätteid](#update-unification-settings), et teha rohkem muudatusi.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Ühendatud kontaktide semantiliste väljade haldamine

1. Valige paanil Semantilised väljad **käsk** Redigeeri **·**.

1. Ühtse välja semantilise tüübi muutmiseks valige uus tüüp. Lisateavet leiate teemast [Ühendatud kontaktide](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts) semantiliste väljade määratlemine.

1. Konto ja kontaktiseose haldamiseks valige **Edasi või valige** Salvesta ja sule **ning naaske valikusse** Värskenda ühendamise sätteid [, et teha](#update-unification-settings) rohkem muudatusi.

## <a name="manage-contact-and-account-relationships"></a>Kontakti- ja kontosuhete haldamine

1. Valige **paanil Seosed** käsk **Redigeeri**.

1. Kontakti ja konto seose muutmiseks muutke mõnda järgmistest andmetest.

   - **Kontaktiolemi välisvõti**: valige atribuut, mis ühendab teie kontaktiolemi kontoga.
   - **Konto olemiks**: valige kontaktiga seotud kontoolem.

1. Valige **Edasi**, et vaadata üle ühendamissätted ning [värskendada ühtset profiili ja sõltuvusi](#run-updates-to-the-unified-profile), või valige **Salvesta ja sule** ning naaske valikusse [Värskenda ühendamise sätteid](#update-unification-settings), et teha rohkem muudatusi.

## <a name="run-matching-conditions"></a>Käivitage sobivad tingimused

Vastendustingimuste käivitamine käivitab ainult duplikatsiooni- ja vastendusreeglid ning *värskendab olemeid Deduplication_** ja *ConflationMatchPair*.

1. **Tehke lehel Andmete** > **ühendamine** valik **Käivita ainult** vastavad tingimused.

   Paanidel Kirjete **duplikaat** ja **Tingimuste** sobitamine kuvatakse **olek Järjestatud** või **Värskendav**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Kui vastendusprotsess on lõpule viidud, valige paanil Sobitamistingimused käsk **Redigeeri** **.**

   :::image type="content" source="media/match-KPIs.png" alt-text="Numbrite ja üksikasjadega vastete lehe põhimõõdikute kärbitud kuvatõmmis.":::

1. Muudatuste tegemiseks vaadake teemasid [Dubleerimisreeglite](#manage-deduplication-rules) haldamine või [Vastendusreeglite](#manage-match-rules) haldamine.

1. Käivitage vastendusprotsess uuesti või [käivitage profiili](#run-updates-to-the-unified-profile) värskendused.

## <a name="run-updates-to-the-unified-profile"></a>Ühtse profiili värskenduste käivitamine

- Vastendustingimuste käitamiseks ja ühtse profiili olemi *värskendamiseks ilma sõltuvusi mõjutamata* (nt kliendikaardid, rikastamised, segmendid või mõõdud) valige **Ühenda kliendiprofiilid**. Kontode puhul valige **Ühenda kontod** > **Profiilide** ühendamine. Kontaktide puhul valige **Kontaktide ühendamine (eelvaade)** > **Profiilide** ühendamine. Sõltuvaid protsesse ei käitata, kuid värskendatakse värskendamise [ajakavas määratletud viisil](schedule-refresh.md).
- Vastendustingimuste käivitamiseks värskendage ühtset profiili ja käivitage kõik sõltuvused, valige **Ühenda kliendiprofiilid ja sõltuvused**. Kõik protsessid käivitatakse automaatselt. Kontode ja kontaktide puhul valige **Ühenda kontod** > **Profiilide ja sõltuvuste** ühendamine. Vastendamistingimusi käitatakse nii kontodele kui ka kontaktidele, kes värskendavad nii ühtseid profiile kui ka kõiki muid sõltuvusi.

Kõigil paanidel, välja arvatud **allikaväljadel**, kuvatakse **järjestatud** või **värskendamine**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Eduka käitamise tulemused kuvatakse **lehel Ühendamine**, kus kuvatakse ühendatud profiilide arv.
