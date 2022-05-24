---
title: Duplikaatide eemaldamine enne andmete ühendamist
description: Teine samm ühendamisprotsessis on valida, millist kirjet duplikaatide leidmisel alles hoida.
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
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8742942"
---
# <a name="remove-duplicates-before-unifying-data"></a>Duplikaatide eemaldamine enne andmete ühendamist

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

See ühendamise etapp võimaldab teil valikuliselt seadistada reeglid duplikaatkirjete käsitlemiseks olemis. *Dedupleerimine* tuvastab duplikaatkirjed ja ühendab need üheks kirjeks. Lähtekirjed lingitakse alternatiivsete ID-dega ühendatud kirjega. Kui reegleid pole konfigureeritud, rakendatakse süsteemi määratletud reegleid.

## <a name="include-enriched-entities-preview"></a>Kaasa rikastatud olemid (eelvaade)

Kui rikastasite olemeid andmeallikas tasemel, et aidata oma ühinemistulemusi parandada, valige need. Lisateavet leiate teemast [Andmeallikate rikastamine](data-sources-enrichment.md).

1. **Valige lehel Kirjete** duplikaat lehe ülaosas suvand **Kasuta rikastatud olemeid**.

1. Valige paanil **Rikastatud olemite** kasutamine üks või mitu rikastatud olemit.

1. Valige nupp **Valmis**.

## <a name="define-deduplication-rules"></a>Deduplatsioonireeglite määratlemine

1. **Valige lehel Kirjete** duplikaat olem ja valige deduplatsioonireeglite määratlemiseks Lisa **reegel**.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Kuvatõmmis kirjete duplikaadilehtedest, kus on esile tõstetud kuvand rohkem":::

   1. Sisestage paanile **Reegli** lisamine järgmine teave.
      - **Valige väli**: valige saadaolevate väljade loendist olemist, mida soovite duplikaatide suhtes kontrollida. Valige väljad, mis on tõenäoliselt iga kliendi jaoks kordumatud. Näiteks meiliaadress või nime, linna ja telefoninumbri kombinatsioon.
      - **Normaliseeri**: valige valitud atribuutide puhul mõni järgmistest normaliseerimissuvanditest.
        - **Numbrid**: teisendab teised numbrisüsteemid, näiteks Rooma numbrid, araabia numbriteks. *VIII* asemel on kasutusel *8*.
        - **Sümbolid**: eemaldab kõik sümbolid ja erimärgid. Tekstist *Head&Shoulder* saab tekst *HeadShoulder*.
        - **Tekst väiketähtedeks: teisendab kogu märgi väiketähtedeks**. Tekstist *ALL CAPS ja Title Case* saab *all caps ja title case*.
        - **Tüüp (telefon, nimi, aadress, organisatsioon)**: standardiseerib nimed, pealkirjad, telefoninumbrid, aadressid jne.
        - **Unicode väärtuseks ASCII**: teisendab unicode'i märke ASCII märkideks. */u00B2* asemel on kasutusel *2*.
        - **Tühimik**: eemaldab kõik tühikud. Tekstist *Hello   World* saab tekst *HelloWorld*.
      - **Täpsus**: saate määrata selle tingimuse jaoks rakendatava täpsustaseme.
        - **Põhiline**: valige *madal (30%),*, *keskmine (60%)*, *kõrge (80%)* ja *täpne (100%)*. Valige **Täpne**, et sobitada ainult kirjed, mis vastavad 100 protsendile.
        - **Kohandatud**: saate määrata protsendi, millele kirjed peavad vastama. Süsteem vastendab ainult seda läve ületavad kirjed.
      - **Nimi**: reegli nimi.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Duplikaatide eemaldamise reeglipaani lisamine kuvatõmmis.":::

   1. Soovi korral valige **Lisa** > **tingimus**, et lisada reeglile rohkem tingimusi. Tingimused on ühendatud loogika tehtemärkiga AND ja käivitatakse seega ainult juhul, kui kõik tingimused on täidetud.

   1. Soovi korral **lisage** > **reeglile** [erandi lisamine erandite lisamiseks](match-entities.md#add-exceptions-to-a-rule). Erandeid kasutatakse harvaesinevate valepositiivsete ja valenegatiivsete juhtumite käsitlemiseks.

   1. Reegli loomiseks valige **Valmis**.

1. Võite ka [rohkem reegleid lisada](#define-deduplication-rules).

1. Valige olem ja seejärel **redigeerige koosteelistusi**.

1. Tehke paanil **Ühenda eelistused** järgmist.
   1. Valige üks kolmest võimalusest, et määrata, millist kirjet duplikaadi leidmisel säilitada.
      - **Enim täidetud**: tuvastab võitjana kirje, millel on kõige rohkem asustatud atribuudivälju. See on vaikeühendamissuvand.
      - **Kõige hiljutisem**: tuvastab võitjana kirje, millega tegeleti kõige viimasena. Hiljutisuse määratlemiseks on vaja kuupäeva- või numbrilist välja.
      - **Kõige vanem**: tuvastab võitjana kirje, millega tegeleti kõige varem. Hiljutisuse määratlemiseks on vaja kuupäeva- või numbrilist välja.
      
      Viigi korral on võitjarekord max(PK) või suurema primaarväärtusega.
      
   1. Soovi korral valige olemi **üksikute atribuutide koosteeelistuste määratlemiseks paani allservas Täpsemalt**. Näiteks saate valida, kas jätta kõige värskem e-kiri JA kõige täielikum aadress erinevatest kirjetest. Laiendage olemit, et näha kõiki selle atribuute ja määratleda, millist suvandit kasutada üksikute atribuutide jaoks. Kui valite võlgnevusel põhineva suvandi, peate määrama ka kuupäeva/kellaaja välja, mis määratleb müügivõlga.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Täpsemad koosteelistuste paan, kus on kuvatud hiljutine meilisõnum ja täielik aadress":::

   1. Koosteeelistuste rakendamiseks valige **Valmis**.

1. Pärast deduplatsioonireeglite ja liitmiseelistuste määratlemist valige **Edasi**.
  
> [!div class="nextstepaction"]
> [Järgmine samm ühe olemi jaoks: väljade ühendamine](merge-entities.md)

> [!div class="nextstepaction"]
> [Järgmine samm mitme olemi jaoks: tingimuste sobitamine](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>Pöördduplitseerimise väljund olemina

Deduplatsiooniprotsess loob iga lähteolemi jaoks uue likvideeritud olemi. Neid olemeid võib leida koos suvandiga **ConflationMatchPairs:CustomerInsights** jaotises **Süsteem** leheküljel **Olemid** nimega **Deduplication_Datasource_Entity**.

Pöördduplitseeritava väljundi olem sisaldab järgmist teavet:

- ID-d/võtmed
  - Primaarvõtme ja alternatiivse ID väljad. Alternatiivne ID väli koosneb kõigist kirje jaoks tuvastatud alternatiivsetest ID-dest.
  - Deduplication_GroupId väli näitab olemi sees tuvastatud rühma või klastrit, mis rühmitab kõik sarnased kirjed määratud pöördduplitseerimise väljade põhjal. Seda kasutatakse süsteemi töötlemise eesmärkidel. Kui pole määratud pole manuaalseid pöördduplitseerimise reegleid ja süsteemi määratletud pöördduplitseerimise väljade subjektireeglid kehtivad, ei pruugi te seda välja pöördduplitseerimise väljundi olemist leida.
  - Deduplication_WinnerId: see väli sisaldab tuvastatud rühma või klastri võitja ID-d. Kui Deduplication_WinnerId on sama, mis kirje primaarvõtme väärtus, tähendab see, et kirje on võitja kirje.
- Väljad, mida kasutatakse pöördduplitseerimise reeglite määratlemiseks.
- Reeglid ja punktisumma väljad, mis tähistavad rakendatavaid pöördduplitseerimise reegleid ja millist punktisummat tagastas sobitusalgoritm.

[!INCLUDE[footer-include](includes/footer-banner.md)]
