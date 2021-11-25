---
title: Olemite ühendamine andmete koondamise ajal
description: Ühendage olemid, et luua koondatud kliendiprofiile.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-merge
ms.openlocfilehash: c218f9c1a1b7711ee48419470bf6c352450ffc0c
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732767"
---
# <a name="merge-entities"></a>Olemite liitmine

Liitmine on andmete ühendamise viimane etapp. Selle eesmärk on vastavusse viia vastuolus andmed. Vastuolulisteks andmeteks võivad olla kahes andmebaasis olev kliendi nimi, mida näidatakse veidi erinevalt (võrrelge: „Grant Marshall“ ja „Grant Marshal“) või erinevas vormingus telefoninumber (võrrelge: 617-803-091X ja 617803091X). Nende vastuoluliste andmepunktide liitmine toimub järgmisel alusel: atribuut atribuudi järel.

:::image type="content" source="media/merge-fields-page.png" alt-text="Ühenda leht andmete ühtsustamise protsessiga näidates tabelit koos ühendatud väljadega, mis defineerivad ühendatud kliendiprofiili.":::

Pärast [vastendamisetappi](match-entities.md) algab liitmisetapp, valides lehel **Ühendamine** paani **Liitmine**.

## <a name="review-system-recommendations"></a>Vaadake üle süsteemi soovitused

Funktsioonis **Andmed** > **Unify** > **Sulata** saate valida ja välistada atribuudid, mida soovite oma unified customer profile'i profiili sees sulatada. Ühendatud kliendiprofiil on andmete ühendamise protsessi tulemus. Osa atribuute liidab süsteem ise.

Kui soovite vaadata atribuute, mis on kaasatud ühte teie automaatselt ühendatud atribuudisse, valige see ühendatud atribuut tabeli **Kliendi väljad** vahekaardil. Atribuudid, mis koostavad ühendatud atribuuti kuvatakse kahes uues rollis ühendatud atribuudi all.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Eralda, nimeta ümber, välista ja redigeeri ühendatud väljad

Saate muuta, kuidas süsteem töötleb ühendatud atribuute ühtse kliendiprofiili loomiseks. Valige **Kuva veel** ja valige, mida soovite muuta.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Ühendatud atribuutide haldamiseks rippmenüü Kuva veel valikud.":::

Järgmisest jaotisest leiate lisateavet.

## <a name="separate-merged-fields"></a>Eraldaga ühendatud väljad

Ühendatud väljade eraldamiseks leidke atribuut tabelist. Eraldatud väljad kuvatakse üksikute andmepunktidena ühendatud kliendi profiilil. 

1. Valige ühendatud väli.
  
1. Valige **Kuva veel** ja valige **Eraldi väljad**.
 
1. eralduse kinnitamine.

1. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .

## <a name="rename-merged-fields"></a>Ühendatud väljade ümbernimetamine

Muutke ühendatud atribuutide kuvatavat nime. Toodanguolemi nime ei saa muuta.

1. Valige ühendatud väli.
  
1. Valige **Kuva veel** ja valige **Nimeta ümber**.

1. Kinnitage muudetud kuvatav nimi. 

1. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .

## <a name="exclude-merged-fields"></a>Jäta ühendatud väljad välja

Atribuudi välistamine ühtsest kliendiprofiilist. Kui seda välja kasutatakse muudes protsessides (nt segmendis), eemaldage see nendest protsessidest, enne selle kliendiprofiililt eemaldamist. 

1. Valige ühendatud väli.
  
1. Valige **Kuva veel** ja valige **Välista**.

1. Kinnitage välistamine.

1. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** . 

Lehel **Ühenda** valige **Välistatud väljad** et näha välistatud väljade loendit. Selle paani abil saate väljad tagasi lisada.

## <a name="edit-a-merged-field"></a>Redigeeri ühendatud välja

1.  Valige ühendatud väli.

1.  Valige **Kuva veel** ja valige **Redigeeri**.

1.  Määrake väljade ühendamise või ühendamise viis ühest kolmest valikust.
    - **Olulisus**: tuvastab võitja väärtuse osalevatele valdkondadele määratud tähtsusastme alusel. See on vaikeühendamissuvand. Valige järjekoha prioritiseerimiseks **Nihuta üles/alla**.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Tähtsuse valik ühendamisväljade dialoogis."::: 
    - **Viimased**: tuvastab võitja väärtuse kõige hiljutisema aja järgi. Nõuab kuupäeva või arvvälja iga koosteväljade osalemisolemi jaoks, et määrata olemi aega.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Hiljutisuse valik ühendamisväljade dialoogis.":::
    - **Hiljutine**: tuvastab võitja väärtuse kõige kaugema aja järgi. Nõuab kuupäeva või arvvälja iga koosteväljade osalemisolemi jaoks, et määrata olemi aega.

1.  Saate ühendamise protsessi lisada veel välju.

1.  Ühendatud välja saate ümber nimetada.

1. Muudatuse rakendamiseks valige **Tehtud**.

1. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** . 

## <a name="manually-combine-fields"></a>Kombineeri välju käsitsi

Määrake ühendatud atribuut käsitsi. 

1. Lehel **Ühenda** valige **Ühenda väljad**.

1. Määrake ripploendis **Väljade ühendamine** koostevõitja poliitika.

1. Valige väli lisamiseks. Valige **Lisa välju** et ühendada rohkem välju.

1. Sisestage **Nimi** ja **Väljundvälja nimi**.

1. Muudatuse rakendamiseks valige **Tehtud**.

1. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** . 

## <a name="change-the-order-of-fields"></a>Väljade järjekorra muutmine

Mõned olemid sisaldavad rohkem üksikasju kui teised. Kui olem sisaldab välja kohta värskeid andmeid, saate väärtusi ühendades prioriseerida selle teiste olemite suhtes.

1. Valige ühendatud väli.
  
1. Valige **Kuva veel** ja valige **Redigeeri**.

1. Valige paanil **Väljade ühendamine** suvand **Nihutage üles/alla** et paika panna järjekord või nihutada ja asetada need soovitud kohale.

1. Kinnitage muudatus.

1. Muudatuste töötlemiseks valige **Salvesta** ja **Käivita** .

## <a name="configure-customer-id-generation"></a>Kliendi ID loomise konfigureerimine 

Pärast väljade ühendamist saate määratleda, kuidas luua CustomerId väärtusi ja kordumatuid kliendiprofiili identifikaatoreid. Andmete ühendamise protsessi ühendamissamm loob kordumatu kliendiprofiili identifikaatori. Identifikaator on *kliendi* olemi CustomerId, mis on saadud andmete ühendamise protsessist. 

Kliendi olemi CustomerId põhineb mittetühiväärtusega võitja primaarvõtmete esimese väärtuse räsil. Need klahvid on pärit vastetes ja ühendamises kasutatavatest olemitest ning neid mõjutab sobitamisjärjestus.Seega saab genereeritud CustomerID muutuda, kui vastetellimuse esmases olemis muudetakse primaarvõtme väärtust. Seega ei pruugi esmase võtme väärtus alati sama klienti tähistada.

Stabiilse kliendi ID konfigureerimine võimaldab teil seda käitumist vältida.

**Kliendi kordumatu ID konfigureerimine**

1. Minge **Ühenda** > **Liitmine**.

1. Valige vahekaart **Võtmed**. 

1. Liikuge kursoriga real **CustomerId** ja valige suvand **Konfigureeri**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Juhtelement ID loomise kohandamiseks.":::

1. Valige kuni viis välja, mille ID on kordumatu ja stabiilsem. Kirjed, mis ei vasta teie konfiguratsioonile, kasutavad selle asemel süsteemi konfigureeritud ID-d.  

1. Muudatuste rakendamiseks tehke valik **Tehtud** ja käivitage koosteprotsess.

## <a name="group-profiles-into-households-or-clusters"></a>Rühmitage profiilid leibkondadesse või klastritesse

Kliendiprofiili loomise konfiguratsiooniprotsessi osana saate määratleda reeglid seotud profiilide rühmitamiseks klastrisse. Praegu on saadaval kahte tüüpi klastrid – Leibkonna ja kohandatud klastrid. Kui *Kliendi* olem sisaldab semantilisi välju *Person.LastName* ja *Location.Address*, valib süsteem eelmääratletud reeglitega subjekti automaatselt. Saate luua klastri ka oma reeglite ja tingimustega, mis sarnanevad [reeglitele](match-entities.md#define-rules-for-match-pairs).

**Määratlege ressurss või klaster**

1. Minge **Ühenda** > **Liitmine**.

1. Vahekaardil **Ühendamine** valige **Täpsem** > **Klastri loomine**.

   :::image type="content" source="media/create-cluster.png" alt-text="Juhtelement uue klastri loomiseks.":::

1. Valige **Leibkonna** või **Kohandatud** klastri vahel. Kui semantilised väljad *Person.LastName* ja *Location.Address* on olemas *Kliendi* olemis, valitakse automaatselt leibkond.

1. Sisestage klastrile nimi ja valige **Valmis**.

1. Loodud klastri leidmiseks valige vahekaart **Klastrid**.

1. Määrake klastri määratlemiseks reeglid ja tingimused.

1. Valige **Käivita**, et käivitada kirjakoosteprotsess ja luua klaster.

Pärast ühendamisprotsessi käivitamist lisatakse klastri identifikaatorid *Kliendi* olemile uute väljadena.

## <a name="run-your-merge"></a>Käivitage kooste

Olenemata sellest, kas liidate atribuute ise või lasete seda teha süsteemil, saate alati käivitada kooste. Toimingu käivitamiseks valige lehel **Liitmine** valik **Käivita**.

> [!div class="mx-imgBorder"]
> ![Andmete liitmine „Salvesta ja Käivita“.](media/configure-data-merge-save-run.png "Andmete liitmine „Salvesta ja Käivita“")

Valige **Käivita ainult ühendamine** juhul, kui soovite näha ainult väljundit ühtses kliendiolemis kajastatuna. Järgnevad protsessid värskendatakse [vastavalt värskendusplaanile](system.md#schedule-tab).

Vaige **Käivita Ühenda ja järgnevad protsessid** et värskendada süsteemi sinu muudatustega. Kõik protsessid, sh rikastamine, segmendid ja mõõtkavad, käivituvad automaatselt. Kui kõik järgnevad protsessid on lõpule jõudnud, kajastavad kliendiprofiilid teie tehtud muudatusi.

Kui soovite teha rohkem muudatusi ja etapi uuesti käivitada, saate tühistada poolelioleva ühendamise. Valige **Värskendamine ...** ja valige nähtavale ilmuva külgpaani suvand **Tühista töö**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

:::image type="content" source="media/process-detail-path.png" alt-text="Süvitsimineku tee et saada protsessi üksikasjad ülesande oleku lingilt.":::

## <a name="next-step"></a>Järgmine etapp

Klientide kohta täiendavate ülevaadete saamiseks seadistage [toiminguid](activities.md), [rikastamist](enrichment-hub.md) või [seosed](relationships.md).

Kui olete tegevused, rikastamine või segmendid juba konfigureerinud, töödeldakse neid automaatselt, et kasutada uusimaid kliendiandmeid.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
