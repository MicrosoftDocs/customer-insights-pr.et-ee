---
title: Ühtse kontaktiprofiili loomine (eelvaade)
description: Läbige andmete ühendamise protsess, et luua ühtne kontaktide koondandmestik.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305064"
---
# <a name="create-a-unified-contact-profile-preview"></a>Ühtse kontaktiprofiili loomine (eelvaade)

Pärast [ettevõttekontode](map-entities.md) ühendamist saate soovi korral nende kontode kontaktid ühendada ja ühendatud kontaktid ühendatud kontodega linkida. Kontaktide ühendamise protsess vastendab mitmest andmeallikast pärit kontaktandmed, eemaldab duplikaadid, vastendab olemite andmed, häälestab semantilise vastenduse, loob kontaktide ja kontode vahelised seosed ning loob seejärel ühtse kontaktiprofiili.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

Esimesed paar sammu on identsed kontode ühendamise sammudega.

## <a name="prerequisites"></a>eeltingimused

Konto- ja kontaktikirjetel peab olema kordumatu võti (mida nimetatakse võõrvõtmeks), mis neid ühendab. Näiteks konto ID, mis on olemas kontokirjes ja kontaktikirjes, mis seob konto ja kontakti kokku.

## <a name="preview-limitations"></a>Eelvaate piirangud

- Konto lingita kontaktid loobutakse.
- Kui konto on dubleeritud, tuvastatakse võitjakirje ühendamiseelistuste põhjal. Kaotaja kirjeid ei valita ja seetõttu loobutakse neist. Kaotavate kirjetega seotud kontaktid loobutakse.
- Kontol võib olla mitu kontakti, kuid kontakt on lingitud ühe kontoga.
- Semantilise vastendamise etapis vastendatud kontaktiatribuudid on ainsad atribuudid, mida saab kliendikaardil kuvada. Siiski on saadaval 17 atribuuti.

## <a name="select-source-fields"></a>Allikaväljade valimine

1. Jaotises **Kontaktide ühendamine (eelvaade)** valige **Alustamine**.

1. [Valige oma kontaktandmete allikate olemid ja väljad](map-entities.md), sh primaarvõtmed ja atribuuditüübid.

1. Tehke valik **Edasi**.

## <a name="remove-duplicate-records"></a>Duplikaatkirjete eemaldamine

1. [Soovi korral saate valitud olemite jaoks määratleda dubleerimise eemaldamise reeglid](remove-duplicates.md).

1. Tehke valik **Edasi**.

## <a name="match-conditions"></a>Mängu tingimused

1. [Määratlege vastejärjekord ja olemiülese vastendamise reeglid](match-entities.md).

1. Tehke valik **Edasi**.

## <a name="unify-contact-fields"></a>Kontaktiväljade ühendamine

1. [Kontaktiväljade](merge-entities.md) kombineerimine ja välistamine.

1. Tehke valik **Edasi**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Määratlege ühendatud kontaktide semantilised väljad

See ühendamisprotsessi etapp vastendab teie ühendatud kontaktiväljad semantiliste tüüpidega. B-to-B-s näitavad kliendikaardid kontosid. Kui kaart on valitud, kuvatakse kõik kontoga seotud kontaktid. Selles etapis kaardistatavad väljad on väljad, mis kuvatakse kaartidel.

1. Valige semantiline tüüp, mis vastendab iga ühtse väljaga. Valige **Pole,** kui semantiline tüüp pole saadaval.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Kuvatõmmis semantiliste väljade lehest semantiliste tüüpide määratlemiseks." lightbox="media/semantic_mapping.png":::

1. Pärast kõigi ühtsete väljade vastendamist valige **Edasi**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Kontaktide ja kontode vahelise seose määramine

See ühendamisprotsessi etapp ühendab teie kontaktandmed vastavate kontoandmetega.

1. Sisestage iga olemi kohta järgmine teave.

   - **Kontaktiolemi välisvõti**: valige atribuut, mis ühendab teie kontaktiolemi kontoga.
   - **Konto olemiks**: valige kontaktiga seotud kontoolem.

   :::image type="content" source="media/contact_relationship.png" alt-text="Kuvatõmmis seoselehest kontakti ja konto olemite ühendamiseks.":::

1. Tehke valik **Edasi**.

## <a name="review-contact-unification"></a>Kontaktide ühendamise ülevaatamine

Vaadake üle muudatuste kokkuvõte, looge ühtne profiil ja vaadake tulemused üle.

### <a name="review-and-create-contact-profiles"></a>Kontaktiprofiilide ülevaatamine ja loomine

See ühendamisprotsessi viimane etapp kuvab protsessi etappide kokkuvõtte ja annab võimaluse teha muudatusi enne ühtse kontaktiprofiili loomist.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Kontaktiprofiilide ülevaatamise ja loomise kuvatõmmis.":::

1. Mis tahes kontakti ühendamise etapis valige **Redigeeri**, et see üle vaadata ja muudatusi teha.

1. Kui olete oma valikutega rahul, valige **Loo kontaktiprofiilid**. Leht **Ühenda** kuvatakse ühtse kontaktiprofiili loomise ajal.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Kuvatõmmis lehest Kontaktide ühendamine paanidega, kus on kuvatud järjestatud või Värskendav paanid.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Ühendamise algoritmi lõpuleviimine võtab aega ja te ei saa konfiguratsiooni muuta enne, kui see on lõpule viidud.

### <a name="view-the-results-of-contact-unification"></a>Kontaktide ühendamise tulemuste kuvamine

Kui ühendamine on lõpule viidud, **kuvatakse lehel Andmete** > **ühendamine** ühendatud kontaktiprofiilide arv. Ühendamisprotsessi iga etapi tulemused kuvatakse igal plaadil. Näiteks **allikaväljad** näitavad vastendatud atribuutide (väljade) arvu ja **duplikaatkirjed** leitud duplikaatkirjete arvu.

:::image type="content" source="media/unified_contacts.png" alt-text="Kuvatõmmis andmete ühendamise lehest pärast kontaktide ühendamist.":::

> [!TIP]
> Paan **Sobitamistingimused** kuvatakse ainult siis, kui on valitud mitu olemit.

Soovitame teil tulemused üle vaadata, eriti mängureeglite [kvaliteet](data-unification-update.md#manage-match-rules), ja neid vajaduse korral täpsustada.

Vajadusel [muutke kontaktide ühendamise sätteid](data-unification-update.md) ja käivitage ühendatud profiil uuesti.

### <a name="verify-output-entities-from-data-unification"></a>Väljundolemite kontrollimine andmete ühendamisest

Väljundolemite kontrollimiseks minge jaotisse **Andmeüksused** > **·**.

Ühendatud kontaktiprofiili olem ContactProfile *kuvatakse* jaotises Semantilised **olemid**. Esimene edukas ühendamiskäivitus loob ühtse *ContactProfile’i* olemi. Kõik järgnevad jooksud laiendavad seda olemit.

Olem *ContactsCustomer* (eelvaade) on loodud ja kuvatakse **jaotises Profiilid**. See üksus sisaldab kontaktandmeid ilma kontode linkideta. Seda olemit kasutatakse sisendina kontaktide ühendamise semantilise kaardistamise ja seoste etappides.

Duplikatsiooni- ja liitmisolemid luuakse ja kuvatakse jaotises **Süsteem**. Iga lähteolemi jaoks luuakse dubleeritud olem nimega **Deduplication_DataSource_Entity**. Olem **ContactsConflationMatchPairs sisaldab teavet olemiüleste** vastete kohta.

Pöördduplitseeritava väljundi olem sisaldab järgmist teavet:
- ID-d/võtmed
  - Primaarvõtme ja alternatiivse ID väljad. Väli Alternatiivne ID koosneb kõigist kirje jaoks tuvastatud alternatiivsetest ID-dest.
  - Deduplication_GroupId väli näitab olemi sees tuvastatud rühma või klastrit, mis rühmitab kõik sarnased kirjed määratud pöördduplitseerimise väljade põhjal. Seda kasutatakse süsteemi töötlemise eesmärkidel. Kui pole määratud pole manuaalseid pöördduplitseerimise reegleid ja süsteemi määratletud pöördduplitseerimise väljade subjektireeglid kehtivad, ei pruugi te seda välja pöördduplitseerimise väljundi olemist leida.
  - Deduplication_WinnerId: see väli sisaldab tuvastatud rühma või klastri võitja ID-d. Kui Deduplication_WinnerId on sama, mis kirje primaarvõtme väärtus, tähendab see, et kirje on võitja kirje.
- Väljad, mida kasutatakse pöördduplitseerimise reeglite määratlemiseks.
- Reeglid ja punktisumma väljad, mis tähistavad rakendatavaid pöördduplitseerimise reegleid ja millist punktisummat tagastas sobitusalgoritm.

## <a name="next-step"></a>Järgmine etapp

Konfigureerige [tegevusi](activities.md), [rikastamist](enrichment-hub.md) või [seoseid](relationships.md), et saada oma kontaktide kohta rohkem teavet.
