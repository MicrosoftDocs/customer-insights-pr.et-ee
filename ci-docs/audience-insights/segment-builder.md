---
title: Segmentide loomine ja haldamine
description: Looge klientide segmente, et rühmitada neid vastavalt eri atribuutidele.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064932"
---
# <a name="create-and-manage-segments"></a>Segmentide loomine ja haldamine

Määratlege keerukad filtrid ühendatud kliendiolemi ümber ja sellega seotud olemid. Pärast töötlemist loob iga segment hulga kliendi kirjeid, mille saate eksportida ja nendega toiminguid teha. Segmente saab hallata lehel **Segmendid**. 

Järgmine näide illustreerib segmenteerimise võimalust. Oleme määratlenud segmendi klientidele, kes on tellinud vähemalt 500 USD eest kaupu viimase 90 päeva jooksul *ja* kes olid seotud klienditeeninduse kõnega, mida eskaleeriti.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Segmendi meisterdamis kasutajaliidese kuvatõmmis kahe kliendisegmendiga rühmaga.":::

## <a name="create-a-new-segment"></a>Looge uus segment

Uue segmendi loomiseks on mitu võimalust. Selles jaotises kirjeldatakse, kuidas luua *tühja segmenti*. Samuti saate luua olemasolevatel olemitel põhineva *kiirsegmendi* või kasutada Masinõpe mudeleid et saada *soovitatud segmente*. Lisateave: [Segmentide ülevaade](segments.md).

Segmenti luues saate mustandi salvestada. See salvestatakse passiivse segmendina ja seda ei saa kehtiva konfiguratsiooniga aktiveeritud olla.

1. Minge lehele **Segmendid**.

1. Valige **Uus** > **Tühi segment**.

1. Paanil **Uus segment** valige segmendi tüüp.

   - **Dünaamilised segmendid** [värskenda](segments.md#refresh-segments) korduva ajakava puhul.
   - **Staatilisi segmente** käitatakse üks kord selle loomisel.

1. Sisestage **Väljundi olemi nimi** segmendi jaoks. Soovi korral sisestage segmendi tuvastamist hõlbustav näidatav nimi ja kirjeldus.

1. Rühma määramise lehele **Segmendikoostur** minemiseks valige **Järgmine**. Rühm on hulk kliente.

1. Valige olem, mis sisaldab segmenteeritavat atribuuti.

1. Valige atribuut, mille järgi segmenteerida. Atribuudil võib olla üks neljast väärtuse tüübist: arvuline, string, kuupäev või Boolean.

1. Valige valitud atribuudi tehtemärk ja väärtus.

   > [!div class="mx-imgBorder"]
   > ![Kohandatud rühma filter](media/customer-group-numbers.png "Kliendi rühma filter")

   |Number |Määratlus  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atribuut          |
   |3    |Operaator         |
   |4    |Väärtus         |

   1. Rühmale täiendavate tingimuste lisamiseks saate kasutada kaht loogikatehet:

      - **AND** tehtemärk: mõlemad tingimused tuleb täita segmenteerimise võimaldamiseks. See valik on kõige kasulikum juhul, kui määratlete eri olemite tingimusi.

      - **VÕI** tehtemärk: üks tingimus tuleb täita segmenteerimise võimaldamiseks. See valik on kõige kasulikum juhul, kui määratlete sama olemi mitu tingimusi.

      > [!div class="mx-imgBorder"]
      > ![OR tehtemärk, kus tuleb täita üks tingimustest](media/segmentation-either-condition.png "OR tehtemärk, kus tuleb täita üks tingimustest")

      Praegu saab pesastada tehtemärki **OR** tehtemärgi **AND** põhjal, ent mitte vastupidi.

   1. Iga rühm vastab klientide komplektile. Saate ühendada rühmad, et kaasata teie ärijuhtumi jaoks nõutavad kliendid.    
   Valige **Lisa rühm**.

      > [!div class="mx-imgBorder"]
      > ![Kliendirühma lisamine](media/customer-group-add-group.png "Kliendirühma lisamine")

   1. Valige üks tehingukomplekt: **Liit**, **Lõikuv** või **Välja arvatud**.

   > [!div class="mx-imgBorder"]
   > ![Kliendirühma ühendi lisamine](media/customer-group-union.png "Kliendirühma ühendi lisamine")

   - **ühend** ühendab kaks rühma.

   - **Ühisosa** kattub kahe rühmaga. Koondatud rühma jäetakse alles ainult andmed, mis on mõlemas rühmas *ühised*.

   - **Välja arvatud** kombineerib kaks rühma. Alles jäetakse ainult sellised rühma A andmed, mida *ei leidu* rühmas B.

1. Kui olem on ühtlustatud kliendi olemiga seotud läbi [seoste](relationships.md), peate määratlema seose tee kehtiva segmendi loomiseks. Lisage olemid seose teest, kuni saate valida ripploendist olemi vormi **Klient: CustomerInsights**. Seejärel valige **Kõik kirjed** iga etapi jaoks.

   > [!div class="mx-imgBorder"]
   > ![Seose tee segmendi loomise ajal](media/segments-multiple-relationships.png "Seose tee segmendi loomise ajal")

1. Vaikimisi genereerivad segmendid väljundolemi, mis sisaldab määratletud filtritele vastavaid kliendiprofiilide kõiki atribuute. Kui segment põhineb muudel olemitel kui olem *Klient*, saate väljundolendisse lisada rohkem atribuute nendest olemitest. Valige **Projekti tribuudid**, et valida väljundolemile lisatavad atribuudid.  
  
   Näide: segment põhineb olemil, mis sisaldab klienditegevuse andmeid, mis on seotud olemiga *Klient*. Segment otsib kõiki kliente, kes on viimase 60 päeva jooksul klienditoele helistanud. Saate valida kõne kestuse ja kõnede arvu lisamise kõigile väljundolemi vastavatele kliendikirjeile. See teave võib kasulik olla meili saatmiseks koos kasulike linkidega võrgus asuvatele spikriartiklitele ja KKK-dele klientidele, kes sageli helistasid.

   > [!NOTE]
   > - Prognoositud atribuudid töötavad ainult olemitega, kellel on üks-mitmele-seos kliendiolemiga. Näiteks võib ühel kliendil olla mitu tellimust.
   > - Saate luua ainult selle olemi projektiatribuute, mida kasutatakse igas teie kasutatava segmendipäringu rühmas.
   > - Prognoositud atribuudid on teguriks seatud kasutades tehete kogumeid.

1. Segmendi salvestamiseks valige nupp **Salvesta**. Segment salvestatakse ja töödeldakse, kui kõik nõuded on kinnitatud. Vastasel juhul salvestatakse see mustandina.

1. Valige **Tagasi segmentidesse**, et naasta lehele **Segmendid**.



## <a name="quick-segments"></a>Kiirsegmendid

Kiirsegmendid lasevad teil luua lihtsaid segmente ühe tehtega kiiresti, et saada kiiremaid ülevaateid.

1. Lehel **Segmendid** klõpsake **Uus** > **Loo vorm**.

   - Valige suvand **Profiilid** etehitada segment, mis põhineb *ühendatud kliendi* olemil.
   - Valige suvand **Mõõtmised**, et luua segment juba loodud segmentide ümber.
   - Valige suvand **Ärianalüüs**, et luua segment ümber ühe väljundi olemi, mille olete loonud, kasutades kas **Prognooside** või **Kohandatud mudelite** võimalusi.

2. Valige dialoogiboksis **Uus kiirsegment** atribuut ripploendist **Väli**.

3. Süsteem esitab paar täiendavat ülevaadet, mis aitavad luua klientidest paremad segmendid.
   - Kategooria väljade puhul näitame 10 peamist kliendi arvu. Valige **Väärtus** ja **Ülevaatamine**.

   - Süsteem näitab numbrilise atribuudi puhul, mis atribuudi väärtus langeb iga kliendi protsendiili alla. Valige **Tehtemärk**, **Väärtus** ja **Ülevaatamine**.

4. Süsteem esitab **hinnangulise segmendi mahu**. Saate valida, kas luua määratletud segment või esmalt vaadata seda uuesti, et hankida muus mahus segment.

    > [!div class="mx-imgBorder"]
    > ![Kiirsegmendi nimi ja hinnang](media/quick-segment-name.png "Kiirsegmendi nimi ja hinnang")

5. Sisestage segmendi **nimi**. Soovi korral sisestage **Kuvatav nimi**.

6. Segmendi loomiseks valige käsk **Salvesta**.

7. Pärast segmendi töötlust saate seda vaadata nagu kõiki teisi loodud segmente.

## <a name="next-steps"></a>Järgmised etapid

Kliendi taseme ülevaadete hankimiseks [eksportige segment](export-destinations.md) ja tutvuge [kliendikaardiga](customer-card-add-in.md) ning [ühendajatega](export-power-bi.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
