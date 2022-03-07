---
title: Segmentide loomine ja haldamine
description: Looge klientide segmente, et rühmitada neid vastavalt eri atribuutidele.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597046"
---
# <a name="create-and-manage-segments"></a>Segmentide loomine ja haldamine

Segmentide abil saate oma kliente rühmitada demograafiliste, tehingupõhiste või käitumuslike atribuutide põhjal. Segmentide abil saate sihtida reklaamikampaaniaid, müügitegevusi ja klienditoe ttoiminguid oma ärieesmärkide saavutamiseks.

Saate kliendiprofiili olemile ja sellega seotud olemitele luua keerukaid filtreid. Pärast töötlemist loob iga segment hulga kliendi kirjeid, mille saate eksportida ja nendega toiminguid teha. Kehtivad [teenusepiirangud](service-limits.md).

Kui ei ole teisiti öeldud, on kõik segmendid **dünaamilised segmendid**, mida värskendatakse korduva ajakava alusel.

Järgmine näide illustreerib segmenteerimise võimalust. Oleme määratlenud segmendi klientidele, kes on tellinud vähemalt 500 USD eest kaupu viimase 90 päeva jooksul *ja* kes olid seotud klienditeeninduse kõnega, mida eskaleeriti.

> [!div class="mx-imgBorder"]
> ![Mitu rühma](media/segmentation-group1-2.png "Mitu rühma")

## <a name="create-a-new-segment"></a>Looge uus segment

Segmente saab hallata lehel **Segmendid**.

1. Avage sihtrühmaülevaadetes leht **Segmendid**.

1. Valige **Uus** > **Tühi segment**.

1. Valige paanis **Uus segment** segmendi tüüp ja sisestage **nimi**.

   Soovi korral sisestage segmendi tuvastamist hõlbustav näidatav nimi ja kirjeldus.

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

8. Kui olem on ühtlustatud kliendi olemiga seotud läbi [seoste](relationships.md), peate määratlema seose tee kehtiva segmendi loomiseks. Lisage olemid seose teest, kuni saate valida ripploendist olemi vormi **Klient: CustomerInsights**. Seejärel valige iga tingimuse jaoks **Kõik kirjed**.

   > [!div class="mx-imgBorder"]
   > ![Seose tee segmendi loomise ajal](media/segments-multiple-relationships.png "Seose tee segmendi loomise ajal")

1. Vaikimisi genereerivad segmendid väljundolemi, mis sisaldab määratletud filtritele vastavaid kliendiprofiilide kõiki atribuute. Kui segment põhineb muudel olemitel kui olem *Klient*, saate väljundolendisse lisada rohkem atribuute nendest olemitest. Valige **Projekti tribuudid**, et valida väljundolemile lisatavad atribuudid.  

   
   Näide: segment põhineb olemil, mis sisaldab klienditegevuse andmeid, mis on seotud olemiga *Klient*. Segment otsib kõiki kliente, kes on viimase 60 päeva jooksul klienditoele helistanud. Saate valida kõne kestuse ja kõnede arvu lisamise kõigile väljundolemi vastavatele kliendikirjeile. See teave võib kasulik olla meili saatmiseks koos kasulike linkidega võrgus asuvatele spikriartiklitele ja KKK-dele klientidele, kes sageli helistasid.

1. Segmendi salvestamiseks valige nupp **Salvesta**. Segment salvestatakse ja töödeldakse, kui kõik nõuded on kinnitatud. Vastasel juhul salvestatakse see mustandina.

1. Valige **Tagasi segmentidesse**, et naasta lehele **Segmendid**.

## <a name="manage-existing-segments"></a>Olemasolevate segmentide haldamine

Lehel **Segmendid** näete kõiki salvestatud segmente ja saate neid hallata.

Igat segmenti esindab rida, mis sisaldab segmendi kohta täiendavat teavet.

Saate veeru segmente sorteerida, valides veerupäise.

Kasutage segmentide filtreerimiseks paremas ülanurgas asuvat välja **Otsing**.

> [!div class="mx-imgBorder"]
> ![Olemasoleva segmendi haldamise võimalused](media/segments-selected-segment.png "Olemasoleva segmendi haldamise võimalused")

Segmendi valimisel on saadaval järgmised tegevused.

- Segmendi üksikasjade **Vaatamine**, sealhulgas liikmete arvu suundumist, segmendi liikmete ülevaadet.
- Segmendi **Redigeerimine** atribuutide muutmiseks.
- Segmendi **Duplikaadi loomine**. Saate selle atribuute kohe redigeerida või lihtsalt duplikaadi salvestada.
- Segmendi **Värskendamine** viimaste andmete kaasamiseks.
- Segmendi **Aktiveerimine** või **Desaktiveerimine**. Segmentidel on kaks võimalikku olekut – aktiivne või passiivne. Nendest olekutest on kasu segmendi redigeerimise ajal. Passiivsete segmentide puhul segmendi määratlus on olemus, kuid see ei sisalda ühtegi klienti. Kui aktiveerite segmendi, siis selle olekuks muutub valikult passiivne valikule aktiivne ja see hakkab otsima kliente, mis vastavad segmendi määratlusele. Kui [plaanitud värskendus](system.md#schedule-tab) on konfigureeritud, on passiivsete segmentide **olekuks** **Vahele jäetud**, mis näitab, et värskendamist isegi ei proovitud. Kui passiivne segment aktiveeritakse, värskendatakse seda ja lisatakse plaanitud värskendustesse.
  Teise võimalusena saate kasutada ripploendi **Aktiveeri/desaktiveeri** funktsiooni **Ajasta hiljem**, et määrata kindla segmendi aktiveerimise ja desaktiveerimise tulevane kuupäev ja kellaaeg.
- Segmendi **Ümbernimetamine**.
- Liikmete loendi **Allalaadimine** CSV-failina.
- Suvand **Lisa** saadab segmendi kliendi ID-de loendi teises rakenduses töötlemiseks.
- Segmendi **Kustutamine**.

## <a name="refresh-segments"></a>Segmentide värskendamine

Saate kõiki segmente korraga värskendada, valides lehel **Segmendid** suvandi **Värskenda kõik** või saate ühte või mitut segmenti värskendada, kui valite need ja valite suvandite hulgast **Värskenda**. Teise võimalusena saate konfigureerida korduva värskendamise, valides **Administraator** > **Süsteem** > **Ajasta**.

> [!TIP]
> Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types). Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies). Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku. Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.

## <a name="download-and-export-segments"></a>Segmentide allalaadimine ja eksportimine

Saate oma segmendid kas CSV-faili alla laadida või eksportida need rakendusse Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Segmentide allalaadimine CSV-faili

1. Avage sihtrühmaülevaadetes leht **Segmendid**.

2. Valige konkreetse segmendi paanil kolmikpunkt.

3. Valige ripploendi toimingutest käsk **Laadi alla CSV-vormingus**.

### <a name="export-segments-to-dynamics-365-sales"></a>Segmentide eksportimine rakendusse Dynamics 365 Sales

Enne segmentide eksportimist rakendusse Dynamics 365 Sales peab administraator [looma ekspordi sihtkoha](export-destinations.md) rakendusele Dynamics 365 Sales.

1. Avage sihtrühmaülevaadetes leht **Segmendid**.

2. Valige konkreetse segmendi paanil kolmikpunkt.

3. Valige toimingute ripploendist **Lisa** ja valige ekspordi sihtkoht, kuhu soovite andmed saata.

## <a name="draft-mode-for-segments"></a>Segmentide mustandi režiim

Kui kõik segmendi töötlemise nõuded pole täidetud, saate salvestada segmendi mustandina ja pääsete sellele juurde lehelt **Segmendid**.

See salvestatakse passiivse segmendina ja seda ei saa aktiveerida enne, kui see on kehtiv.

## <a name="add-more-conditions-to-a-group"></a>Lisage rühma täiendavaid tingimusi

Rühmale täiendavate tingimuste lisamiseks saate kasutada kaht loogikatehet:

- **AND** tehtemärk: mõlemad tingimused tuleb täita segmenteerimise võimaldamiseks. See valik on kõige kasulikum juhul, kui määratlete eri olemite tingimusi.

- **VÕI** tehtemärk: üks tingimus tuleb täita segmenteerimise võimaldamiseks. See valik on kõige kasulikum juhul, kui määratlete sama olemi mitu tingimusi.

   > [!div class="mx-imgBorder"]
   > ![OR tehtemärk, kus tuleb täita üks tingimustest](media/segmentation-either-condition.png "OR tehtemärk, kus tuleb täita üks tingimustest")

Praegu saab pesastada tehtemärki **OR** tehtemärgi **AND** põhjal, ent mitte vastupidi.

## <a name="combine-multiple-groups"></a>Mitme rühma kombineerimine

Iga rühm toodab kindla klientide kogumi. Neid rühmi saate kombineerida, et kaasata teie ärimudeli jaoks vajalikud kliendid.

1. Minge sihtrühmaülevaadetes lehele **Segmendid** ja valige segment.

2. Valige **Lisa rühm**.

   > [!div class="mx-imgBorder"]
   > ![Kliendirühma lisamine](media/customer-group-add-group.png "Kliendirühma lisamine")

3. Valige üks järgmistest määramistehetest: **Ühend**, **Ühisosa** või **Välja arvatud**.

   > [!div class="mx-imgBorder"]
   > ![Kliendirühma ühendi lisamine](media/customer-group-union.png "Kliendirühma ühendi lisamine")

   Valige uue rühma määratlemiseks tehtemärk. Salvestage eri rühmad, et teha kindlaks säilitatavad andmed.

   - **ühend** ühendab kaks rühma.

   - **Ühisosa** kattub kahe rühmaga. Koondatud rühma jäetakse alles ainult andmed, mis on mõlemas rühmas *ühised*.

   - **Välja arvatud** kombineerib kaks rühma. Alles jäetakse ainult sellised rühma A andmed, mida *ei leidu* rühmas B.

## <a name="view-processing-history-and-segment-members"></a>Vaadake töötlemise ajalugu ja segmendi liikmeid

Segmendi koondandmete nägemiseks vaadake üle selle üksikasjad.

Lehel **Segmendid** valige ülevaadatav segment.

Lehe ülaosa sisaldab suundumuse trendigraafikut, mis visualiseerib liikmete arvu muudatused. Hoidke kursorit andmepunktide kohal, et näha liikmete arvu kindlal kuupäeval.

Saate uuendada visualiseerimise ajavahemikku.

> [!div class="mx-imgBorder"]
> ![Segmendi ajavahemik](media/segment-time-range.png "Segmendi ajavahemik")

Alaosa sisaldab segmendi liikmete loendit.

> [!NOTE]
> Selle loendi väljad põhinevad segmendi olemite atribuutidel.
>
>Loend on eelvaade kattuvatest segmendi liikmetest ja näitab segmendi 100 esimest kirjet, et saaksite vajadusel kiiresti seda hinnata ja kontrollida selle määratlusi. Kõikide kattuvate kirjete nägemiseks peate [eksportima segmendi](export-destinations.md).

## <a name="quick-segments"></a>Kiirsegmendid

Lisaks segmendikujundajale on veel üks võimalus segmentide loomiseks. Kiirsegmendid võimaldavad teil luua lihtsaid segmente (ühe operaatoriga) kiiresti ja koheste ülevaadetega.

1. Valige lehel **Segmendid** jaotis **Uus** > **Kiirloomise vorm**.

   - Ühendatud kliendiprofiilil põhineva segmendi loomiseks valige valik **Profiilid**.
   - Valige valik **Mõõtmed**, et luua varem lehel **Mõõtmed** loodud iga mõõtme kliendiatribuudi tüübi ümber segment.
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

Järgmistes olukordades soovitame kasutada segmendikoosturit, mitte soovitatavat segmentide võimalust:

- Segmentide loomine filtritega kategooriliselt väljadel, kus tehtemärgiks pole **Is**
- Segmentide loomine filtritega numbriliselt väljadel, kus tehtemärkideks pole **Between**, **Greater than** ja **Less than**
- Filtritega segmentide loomine kuupäeva tüüpi väljadel

## <a name="next-steps"></a>Järgmised etapid

Kliendi taseme ülevaadete hankimiseks [eksportige segment](export-destinations.md) ja tutvuge [kliendikaardiga](customer-card-add-in.md) ning [ühendajatega](export-power-bi.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]