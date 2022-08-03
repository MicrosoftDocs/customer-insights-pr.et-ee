---
title: Duplikaatide eemaldamine enne andmete ühendamist
description: Ühendamisprotsessi teine samm on valida, millist kirjet duplikaatide leidmisel säilitada.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: a838fbdabdb3bfffc6d3835a3f0e97306a43964a
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139424"
---
# <a name="remove-duplicates-before-unifying-data"></a>Duplikaatide eemaldamine enne andmete ühendamist

See ühendamise etapp võimaldab valikuliselt seadistada reeglid duplikaatkirjete käsitlemiseks olemis. *Duplikaadi eemaldamine* tuvastab duplikaatkirjed ja ühendab need üheks kirjeks. Lähtekirjed lingitakse alternatiivsete ID-dega ühendatud kirjega. Kui reegleid ei konfigureerita, rakendatakse süsteemi määratletud reegleid.

## <a name="include-enriched-entities-preview"></a>Rikastatud olemite kaasamine (eelvaade)

Kui rikastasite olemeid andmeallikas tasemel, et aidata ühendamise tulemusi parandada, valige need. Lisateavet leiate teemast [Andmeallikate rikastamine](data-sources-enrichment.md).

1. **Valige lehel Kirjete** dubleerimine lehe ülaosas suvand **Kasuta rikastatud olemeid**.

1. **Valige paanilt Rikastatud olemite** kasutamine üks või mitu rikastatud olemit.

1. Valige nupp **Valmis**.

## <a name="define-deduplication-rules"></a>Dubleerimisreeglite määratlemine

1. **Valige lehel Kirjete** dubleerimine olem ja valige **reegel**, et määratleda duplikatsioonireeglid.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Kuvatõmmis kirjete dubleerimisest, kus on esile tõstetud kuva rohkem":::

   1. Sisestage **paanil Reegli** lisamine järgmine teave.
      - **Vali väli**: valige saadaolevate väljade loendist olemist, mida soovite duplikaatide osas kontrollida. Valige väljad, mis on tõenäoliselt iga kliendi jaoks kordumatud. Näiteks meiliaadress või nime, linna ja telefoninumbri kombinatsioon.
      - **Normaliseeri**: valige valitud atribuutide puhul mõni järgmistest normaliseerimissuvanditest.
        - **Numbrid**: teisendab muud numbrisüsteemid (nt rooma numbrid) araabia numbriteks. *VIII* asemel on kasutusel *8*.
        - **Sümbolid**: eemaldab kõik sümbolid ja erimärgid. Tekstist *Head&Shoulder* saab tekst *HeadShoulder*.
        - **Tekst väiketähtedeks: teisendab kõik märgid väiketähtedeks**. Tekstist *ALL CAPS ja Title Case* saab *all caps ja title case*.
        - **Tüüp (telefon, nimi, aadress, organisatsioon):** Standardiseerib nimed, pealkirjad, telefoninumbrid, aadressid jne.
        - **Unicode ascii-ks**: teisendab unicode'i märke ASCII-märkideks. */u00B2* asemel on kasutusel *2*.
        - **Tühik**: eemaldab kõik tühikud. Tekstist *Hello   World* saab tekst *HelloWorld*.
      - **Täpsus**: saate määrata selle tingimuse jaoks rakendatava täpsustaseme.
        - **Põhiline**: valige *madala (30%)*, *keskmise (60%)*, *kõrge (80%)* ja *täpse (100%) vahel*. Valige **Täpne**, et vastendada ainult kirjeid, mis vastavad 100 protsendile.
        - **Kohandatud**: saate määrata protsendi, millele kirjed peavad vastama. Süsteem vastendab ainult seda läve ületavad kirjed.
      - **Nimi**: reegli nimi.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Kuvatõmmis reegli lisamise paanist duplikaatide eemaldamiseks.":::

   1. Soovi korral valige **Lisa** > **tingimus**, et lisada reeglile rohkem tingimusi. Tingimused on ühendatud loogika tehtemärkiga AND ja käivitatakse seega ainult juhul, kui kõik tingimused on täidetud.

   1. **Soovi korral lisage** > **reeglile**[erandite](match-entities.md#add-exceptions-to-a-rule) lisamiseks erand. Erandeid kasutatakse harvadel juhtudel valepositiivsete ja valenegatiivsete tulemuste käsitlemiseks.

   1. Reegli loomiseks valige **Valmis**.

1. Võite ka [rohkem reegleid lisada](#define-deduplication-rules).

1. Valige olem ja seejärel **redigeerige koosteeelistusi**.

1. **Tehke paanil Ühendamiseelistused** järgmist.
   1. Valige üks kolmest võimalusest, et määrata, millist kirjet duplikaadi leidmisel säilitada.
      - **Enim täidetud**: tuvastab võitjana kirje, millel on kõige rohkem asustatud atribuudivälju. See on vaikeühendamissuvand.
      - **Kõige hiljutisem**: tuvastab võitjana kirje, millega tegeleti kõige viimasena. Hiljutisuse määratlemiseks on vaja kuupäeva- või numbrilist välja.
      - **Kõige vanem**: tuvastab võitjana kirje, millega tegeleti kõige varem. Hiljutisuse määratlemiseks on vaja kuupäeva- või numbrilist välja.
      
      Viigi korral on võitja rekordiks MAX(PK) või suurema primaarvõtme väärtusega rekord.
      
   1. Soovi korral valige **olemi üksikute atribuutide koosteeelistuste määratlemiseks paani allservas Täpsemalt**. Näiteks saate valida, kas säilitada kõige hiljutisem e-posti aadress JA kõige täielikum aadress erinevatest kirjetest. Laiendage olemit, et näha kõiki selle atribuute, ja määratlege, millist suvandit üksikute atribuutide jaoks kasutada. Kui valite hiljutisusel põhineva valiku, peate määrama ka kuupäeva/kellaaja välja, mis määratleb hiljutisuse.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Kooste täpsemate eelistuste paan, kus on kuvatud hiljutine meiliaadress ja täielik aadress":::

   1. Koosteeelistuste rakendamiseks valige **Valmis**.

1. Pärast duplikatsioonireeglite ja ühendamiseelistuste määratlemist valige **Edasi**.
  
> [!div class="nextstepaction"]
> [Ühe olemi järgmine etapp: väljade ühendamine](merge-entities.md)

> [!div class="nextstepaction"]
> [Järgmine samm mitme olemi puhul: tingimuste vastavusse viimine](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Pöördduplitseerimise väljund olemina

Duplikatsiooniprotsess loob iga lähteolemi jaoks uue dubleeritud olemi. Neid olemeid võib leida koos suvandiga **ConflationMatchPairs:CustomerInsights** jaotises **Süsteem** leheküljel **Olemid** nimega **Deduplication_Datasource_Entity**.

Pöördduplitseeritava väljundi olem sisaldab järgmist teavet:

- ID-d/võtmed
  - Primaarvõtme ja alternatiivse ID väljad. Väli Alternatiivne ID koosneb kõigist kirje jaoks tuvastatud alternatiivsetest ID-dest.
  - Deduplication_GroupId väli näitab olemi sees tuvastatud rühma või klastrit, mis rühmitab kõik sarnased kirjed määratud pöördduplitseerimise väljade põhjal. Seda kasutatakse süsteemi töötlemise eesmärkidel. Kui pole määratud pole manuaalseid pöördduplitseerimise reegleid ja süsteemi määratletud pöördduplitseerimise väljade subjektireeglid kehtivad, ei pruugi te seda välja pöördduplitseerimise väljundi olemist leida.
  - Deduplication_WinnerId: see väli sisaldab tuvastatud rühma või klastri võitja ID-d. Kui Deduplication_WinnerId on sama, mis kirje primaarvõtme väärtus, tähendab see, et kirje on võitja kirje.
- Väljad, mida kasutatakse pöördduplitseerimise reeglite määratlemiseks.
- Reeglid ja punktisumma väljad, mis tähistavad rakendatavaid pöördduplitseerimise reegleid ja millist punktisummat tagastas sobitusalgoritm.

[!INCLUDE[footer-include](includes/footer-banner.md)]
