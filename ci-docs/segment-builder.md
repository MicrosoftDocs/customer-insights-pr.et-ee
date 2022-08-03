---
title: Keerukate segmentide loomine segmendiehitajaga
description: Kasutage segmendiehitajat keerukate kliendisegmentide loomiseks, rühmitades need erinevate atribuutide põhjal.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170630"
---
# <a name="create-complex-segments-with-segment-builder"></a>Keerukate segmentide loomine segmendiehitajaga

Määratlege keerukad filtrid ühendatud kliendiolemi ümber ja sellega seotud olemid. Pärast töötlemist loob iga segment hulga kliendi kirjeid, mille saate eksportida ja nendega toiminguid teha.

> [!TIP]
> **Üksikklientidel** põhinevad segmendid sisaldavad automaatselt segmendi liikmete jaoks saadaolevat kontaktteavet. **Ärikontode** keskkondades põhinevad segmendid kontodel (ettevõtetel või tütarettevõtetel). Kontaktteabe kaasamiseks segmenti kasutage segmendi meisterdamisfunktsiooni **Projekti atribuudid**. Veenduge, et kontakti andmeallikad oleks [semantselt vastendatud olemiga ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Segmentide koostamine

Järgmine pilt illustreerib segmendikoosturi erinevaid aspekte. Sellel kuvatakse segment, mille tulemuseks on klientide rühm. Kliendid tellisid kaupa kindla aja jooksul ja kogusid punkte või kulutasid teatud rahasumma.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Segmendi ehitaja elemendid." lightbox="media/segment-builder-overview.png":::

1. Korraldage oma segment reeglite ja alamreeglitega. Iga reegel või alamreegel koosneb tingimustest. Ühendage tingimused loogiliste tehtemärkidega.

1. Valige reeglile rakenduvate olemite vaheline [seosetee](relationships.md). Seosetee määratleb, milliseid atribuute saab tingimuses kasutada.

1. Reeglite ja alamreeglite haldamine. Saate muuta reegli positsiooni või selle kustutada.

1. Lisage alamreeglite abil tingimused ja looge õige hargnemine alamreeglite abil.

1. Saate rakendada ühendatud reeglitele salvestatud toiminguid.

1. Kasutage atribuudipaani, et lisada saadaolevaid olemiatribuute või luua atribuutidel põhinevad tingimused. Paanil kuvatakse valitud seoseteel põhinevate olemite ja atribuutide loend, mis on valitud reegli jaoks saadaval.

1. Lisage olemasolevatele reeglitele ja alamreeglitele atribuutidel põhinevad tingimused või lisage see uude reeglisse.

1. Saate segmendi loomise ajal muudatusi tagasi võtta ja uuesti teha.

Ülaltoodud näites on kirjeldatud segmentimisvõimalust. Oleme määratlenud segmenti klientidele, kes koguvad vähemalt $500 veebikaupu *ja* on huvitatud tarkvara arendamisest.

## <a name="create-a-new-segment-with-segment-builder"></a>Uue segmendi loomine segmendiehitajaga

1. Liikuge jaotisse **Segmendid**.

1. Valige **Uus** > **Ehita enda oma**. Segmendi osade lehel saate määratleda või koostada reegleid. Reegel koosneb ühest või mitmest tingimusest mis määratleb klientide komplekti.

1. Valige **Lõigu Pealkirjata kõrval käsk Redigeeri üksikasju**. Andke oma segmendile nimi ja värskendage segmendile soovitatud **Väljundolemi nime**. Soovi korral saate segmendile lisada kirjelduse ja [sildid](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/segments_edit_details.png" alt-text="Dialoogiboks Üksikasjade redigeerimine.":::

1. **Valige jaotises Reegel1** selle olemi atribuut, mille alusel soovite kliente filtreerida. Atribuutide valimiseks on kaks viisi.
   - Vaadake paanil **Lisa reeglile** saadaolevad olemid ja atribuudid läbi ja valige lisamisatribuudi kõrval soovitud **+** ikoon. Valige, kas soovite lisada atribuudi olemasolevale reeglile või kasutada seda uue reegli loomiseks.
   - Kui soovite näha kattuvate soovituste kuvamist, tippige atribuudi nimi reegli jaotisesse.

1. Valige tingimuse kattuvate väärtuste määramiseks tehtemärgid. Atribuudil võib olla üks neljast andmetüübist: arv, string, kuupäev või tõeväärtus. Sõltuvalt atribuudi andmetüübist on tingimuse määramiseks saadaval erinevad tehtemärgid. Ärikontodega segmentide puhul on saadaval kaks eritehtet, et kaasata allaneetud ettevõtete potentsiaalsed hierarhiad. Kasutage seotud kontode kaasamiseks tehteid *laps* ja *vanem*.

1. Kui soovite reeglile lisada veel tingimusi, valige **Lisa tingimus**. Praeguse reegli alla reegli loomiseks valige käsk **Lisa alamreegel**.

1. Kui reegel kasutab muid olemeid peale *kliendi* olemi, valige **suvand Määra seosetee**, et vastendada valitud olem ühtse kliendi olemiga. Kui on ainult üks võimalik seosetee, valib süsteem selle automaatselt. Erinevad [suhteteed](relationships.md#relationship-paths) võivad anda erinevaid tulemusi. Igal reeglil võib olla oma seosetee.

   :::image type="content" source="media/relationship-path.png" alt-text="Potentsiaalne seosetee ühtse kliendiolemiga vastendatud olemil põhineva reegli loomisel.":::

1. Kui teil on reeglis mitu tingimust, valige, milline loogiline tehtemärk need ühendab.  
   - **JA** tehtemärk: kirje segmenti kaasamiseks peavad olema täidetud kõik tingimused. Kasutage seda suvandit, kui määratlete tingimusi erinevates olemites.
   - **VÕI** tehtemärk: kirje segmenti kaasamiseks peab olema täidetud üks tingimustest. Kasutage seda suvandit, kui määratlete sama olemi jaoks mitu tingimust.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Reegel kahe JA tingimustega.":::

   VÕI tehtemärki kasutades peavad kõik tingimused põhinema seoseteel kaasatud olemitel.

1. Erinevate kliendikirjete kogumite loomiseks looge mitu reeglit. Teie ärijuhtumi jaoks vajalike klientide kaasamiseks ühendage rühmad. Täpsemalt, kui te ei saa olemit reeglisse kaasata määratud seosetee tõttu, looge sellest atribuutide valimiseks uus reegel.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Lisage segmendile uus reegel ja valige seatud tehtemärk.":::

   1. Valige **Lisa reegel**.
   1. Valige üks tehingukomplekt: **Liit**, **Lõikuv** või **Välja arvatud**.

      - **ühend** ühendab kaks rühma.
      - **Ühisosa** kattub kahe rühmaga. Ühtsesse rühma jäävad ainult need andmed, mis on mõlema rühma jaoks *ühised*.
      - **Välja arvatud** kombineerib kaks rühma. Säilitatakse ainult rühma A andmed, mis *ei ole ühised* rühma B andmetele.

1. Vaikimisi sisaldab väljundolem automaatselt kõiki kliendiprofiilide atribuute, mis vastavad määratletud filtritele. Kui segment põhineb muudel olemitel kui *kliendi* olem, valige **Projekti atribuudid**, et lisada nende olemite atribuute väljundolemile rohkem.

   > [!IMPORTANT]
   > Ärikontodel põhinevate segmentide puhul tuleb segmenti kaasata iga konto ühe või mitme kontakti üksikasjad üksusest *ContactProfile*, et võimaldada selle segmendi aktiveerimist või eksportimist sihtkohtadesse, mis nõuavad kontaktteavet. Olemi *ContactProfile* kohta leiate lisateavet teemast [Semantilised vastendused](semantic-mappings.md).
   > Kontaktide prognoositud atribuutidega ärikontodel põhineva segmendi näidisväljund võiks välja näha järgmine:
   >
   > |ID  |Konto nimi  |Tulu  |Kontaktisiku nimi  | Kontakti roll|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100K | [Abbie Moss, Ruth Soto]  | [tegevjuht, hankejuht]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Näide väljundolemile lisatava küljepaanil valitud projitseeritud atribuutidest.":::
  
   Näiteks: Segment põhineb olemil, mis sisaldab *Kliendi* olemiga seotud ostuandmeid. Segmendis otsitakse kõiki Hispaaniast pärit kliente, kes on praeguse aasta jooksul oma kaupa ostnud. Saate valida, kas lisada atribuudid, nagu kauba hind või ostukuupäev, kõigile väljundolemi vastavatele kliendikirjetele. See teave võib olla kasulik, et analüüsida hooajalist korrelatsiooni kogukuludega.

   > [!NOTE]
   > - **Projektiatribuudid** töötavad ainult olemitele, mille seos kliendiolemiga on üks-mitmele. Näiteks võib ühel kliendil olla mitu tellimust.
   > - Kui atribuut, mida soovite projekti jaoks kasutada, on *Kliendi* olemist rohkem kui ühe hüppe kaugusel, nagu see on seoses määratletud, tuleks seda atribuuti kasutada igas teie ettevõttes kasutatava segmendipäringu reeglis.
   > - Kui atribuut, mida soovite projekti jaoks kasutada, on *Kliendi* olemist ühe hüppe kaugusel, siis seda atribuuti ei pea kasutama igas teie ettevõttes kasutatava segmendipäringu reeglis.
   > - **Prognoositud atribuudid** on seatud teguriks kasutades tehete kogumeid.

1. Segmendi loomiseks valige **Käivita**. Valige **Salvesta,** kui soovite praeguse konfiguratsiooni säilitada ja segmendi hiljem käivitada. Kuvatakse **leht Segmendid**.

### <a name="segment-builder-tips"></a>Segmendiehitaja näpunäited

Segmendi loomisel segmendikoosturiga pidage meeles järgmisi näpunäiteid.

- Segmendi tehtemärgid ei soovita tingimuste jaoks tehtemärkide seadmisel olemite kehtivaid väärtusi. Minge **Andmed** > **Olemid** ja laadige alla olemi andmed, et näha, millised väärtused on saadaval.
- Kuupäevadel põhinevad tingimused võimaldavad teil vahetada fikseeritud kuupäevade ja ujutatud kuupäevavahemiku vahel.
- Kui teil on oma segmendi jaoks mitu reeglit, on redigeeritud reegli kõrval vertikaalne sinine joon.
- Reegleid ja tingimusi saate segmendi määratluses teisaldada ka muudesse kohtadesse. Valige reegli või tingimuse kõrval vertikaalne kolmikpunkt (&vellip;) ja valige, kuidas ja kuhu seda teisaldada.
- Käsuribal juhtelementide **Võta tagasi** ja **Tee uuesti** abil saate muudatusi tagasi võtta.
- Pärast segmendi loomist võimaldavad [mõned segmendid jälgida segmendi](segments.md#track-usage-of-a-segment) kasutamist.

## <a name="next-steps"></a>Järgmised toimingud

[Eksportige segment](export-destinations.md) ja tutvuge [kliendikaardi integratsiooniga](customer-card-add-in.md), et kasutada segmente muudes rakendustes.

[!INCLUDE [footer-include](includes/footer-banner.md)]
