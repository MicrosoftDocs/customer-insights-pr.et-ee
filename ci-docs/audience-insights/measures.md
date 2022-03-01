---
title: Näitajate loomine ja muutmine
description: Määratlege kliendiga seotud meetmed, et analüüsida ja kajastada teatud ärialade tootlikkust.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405565"
---
# <a name="define-and-manage-measures"></a>Meetmete määratlemine ja haldamine

**Meetmed** tähendavad juhtimismõõdikuid (KPI-d), mis kajastavad teatud ärialade tootlikkust ja seisu. Sihtrühmaülevaated pakuvad intuitiivset kogemust eri tüüpi näitajate loomiseks, kasutades päringukujundajat, milles pole vaja koodi kirjutada ega näitajaid manuaalselt kontrollida. Saate lehel **Avaleht** jälgida ettevõtte meetmeid, vaadata **kliendikaardi** klientide meetmeid ja määratleda meetmetega kliendisegmente lehel **Segmendid**.

## <a name="create-a-measure"></a>Meetme loomine

See jaotis juhendab teid uue meetme loomisel. Saate luua meetmeid mitme kliendi olemi kaudu ühendatud andmeallika andmete alusel. Kehtivad [teenusepiirangud](service-limits.md).

1. Avage sihtrühmaülevaadetes jaotis **Näitajad**.

2. Valige **Uus meede**.

3. Valige meede **Tüüp**.

   - **Kliendi atribuut**: üks väli kliendi kohta, kus on kliendi skoor, väärtus või olek. Kliendiatribuudid luuakse uue süsteemi loodud olemi atribuutidena, mida nimetatakse **kliendi meetmeks**.

   - **Kliendi meede**: kliendikäitumise ülevaated struktuuriga, mis põhineb valitud mõõtmetel. Iga meetme jaoks luuakse uus olem, potentsiaalselt mitme kirjega kliendi kohta.

   - **Ärimeede**: jälgib äri tootlikkust ja seisu. Ärimeetmetel võib olla kaks eri väljundit: lehel **Avaleht** asuv numbriline väljund või uus olem, mille leiate lehelt **Olemid**.

4. Sisestage **Nimi** ja valikuline **Kuvatav nimi**, seejärel valige **Järgmine**.

5. Jaotises **Olemid** valige ripploendist esimene olem. Sellel hetkel peaksite otsustama, kas mõõdu määratlusel läheb vaja täiendavaid olemeid.

   > [!div class="mx-imgBorder"]
   > ![Mõõdu määratlus](media/measure-definition.png "Mõõdu määratlus")

   Täiendavate olemite lisamiseks valige **Lisa olem** ja valige meetmetes kasutatavad olemid.

   > [!NOTE]
   > Võite valida ainult olemeid, millel on alustamise olemiga seosed. Lisateavet suhete määratlemise kohta leiate jaotisest [Suhted](relationships.md).

6. Soovi korral saate seadistada muutujaid. Tehke jaotises **Muutujad** valik **Uus muutuja**.

   Muutujad on arvutused, mis luuakse iga valitud kirje puhul. Näiteks iga kliendi kirje puhul kokkuvõtlik müügipunkt (POS) ja võrgumüügid.

7. Sisestage muutuja **nimi**.

8. Jaotises **Avaldis** valige välju, millega algav arvutus.

9. Sisestage avaldis jaotisesse **Avaldis**, samas valige veel välju, mida lisada arvutusse.

   > [!NOTE]
   > Praegu toetatakse ainult aritmeetilisi avaldisi. Lisaks ei toetata eri [olemi teede](relationships.md) muutuja arvutust.

10. Valige nupp **Valmis**.

11. Jaotises **Mõõdu määratlus** saate määratleda, kuidas teie valitud olemid ja arvutatud muutujad liidetakse uue mõõdu olemile või atribuudile.

12. Valige **Uus dimensioon**. Dimensiooni võib ette kujutada ka funktsioonina *rühmitamisalus*. Meetme olemi või atribuudi andmete väljund rühmitatakse kõikide määratletud dimensioonide alusel.

    > [!div class="mx-imgBorder"]
    > ![Koondtsükli valimine](media/measures-businessreport-measure-definition2.png "Koondtsükli valimine")

    Valige või sisestage järgmine teave dimensiooni määratluse osana:

    - **Olem**: kui määratlete meetme olemi, peaks see sisaldama vähemalt üht atribuuti. Kui määratlete meetme atribuudi, sisaldab see tavaliselt vaid üht atribuuti. See valik käib atribuudiga olemi valimise kohta.
    - **Väli**: valige kindel atribuut, mis lisatakse meetme olemisse või atribuuti.
    - **Salv**: valige, kas soovite koondada andmed iga päev, iga kuu või iga aasta. See on kohustuslik valik ainult juhul, kui olete valinud atribuudi tüübi Kuupäev.
    - **Kui**: määratleb uue välja nime.
    - **Kuvatav nimi**: määratleb välja kuvatava nime.

    > [!NOTE]
    > Ettevõtte meede salvestatakse ühe numbrilise olemina ja ilmub lehel **Avaleht**, kui te ei lisa meetmesse täiendavaid dimensioone. Pärast täiendavate dimensioonide lisamist *ei* ilmu meede lehel **Avaleht**.

13. Soovi korral lisage liitmisfunktsioonid. Kõikide liitmiste summadeks on uus väärtus, mis jääb mõõtude olemi või atribuudi raamesse. Toetatud liitmisfunktsioonid on: **min**, **max**, **keskmine**, **mediaan**, **Sum**, **kordumatu arv**, **esimene** (kasutab dimensiooni väärtuse esimest kirjet) ja **viimane** (kasutab dimensiooni väärtusele lisatud viimast kirjet).

14. Mõõtmele tehtud muudatuste kasutamiseks klõpsake käsku **Salvesta**.

## <a name="manage-your-measures"></a>Meetmete haldamine

Pärast vähemalt ühe näitaja loomist näete lehel **Näitajad** näitajate loendit.

Leiate teavet mõõtme tüübi, looja, loomise kuupäeva ja kellaaja, viimase muutmise kuupäeva ja kellaaja, oleku (kas mõõde on aktiivne, passiivne või nurjunud) ning viimase värskendamise kuupäeva ja kellaaja kohta. Kui valite loendist mõõdu, näete selle väljundi eelvaadet.

Kõigi oma meetmete korraga värskendamiseks valige **Värskenda kõik** ilma kindlat meedet valimata.

> [!div class="mx-imgBorder"]
> ![Toimingud üksikute meetmete haldamiseks](media/measure-actions.png "Toimingud üksikute meetmete haldamiseks")

Teise võimalusena valige loendist meede ja tehke üks järgmistest toimingutest.

- Valige meetme nimi, et näha selle üksikasju.
- Meetme konfiguratsiooni **Redigeerimine**.
- Meetme **Ümbernimetamine**.
- Meetme **Kustutamine**.
- Valige kolmikpunkt (...) ja seejärel **Värskenda**, et käivitada meetme värskendamisprotsess.
- Valige kolmikpunkt (...) ja seejärel **Laadi alla**, et saada meetme .CSV-fail.

> [!TIP]
> Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types). Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies). Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku. Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.

## <a name="next-step"></a>Järgmine etapp

Esimese kliendisegmendi loomiseks lehel **Segmendid** saate kasutada olemasolevaid mõõte. Lisateavet vt [Segmendid](segments.md).
