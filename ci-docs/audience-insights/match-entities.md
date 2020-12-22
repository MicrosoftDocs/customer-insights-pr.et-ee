---
title: Olemite vastavusseviimine andmete koondamiseks
description: Viige olemid vastavusse, et luua koondatud kliendiprofiile.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405563"
---
# <a name="match-entities"></a>Olemite vastavusseviimine

Pärast vastendamise etappi olete valmis olemite vastavusse viimiseks. Vastavusse viimise etapp täpsustab, kuidas kombineerida andmekogusid koondatud kliendiprofiilide andmekogusse. Vastendamisetapp vajab vähemalt [kahte kaardistatud olemit](map-entities.md).

## <a name="specify-the-match-order"></a>Vastendamisjärjestuse määramine

Vastendamisetapi käivitamiseks minge **Ühendamine** > **Vastendamine** ja valige **Järjestuse määramine**.

Iga vaste ühendab vähemalt kaks olemit üheks olemiks, samas säilitades iga kordumatu kliendi kirjega. Järgmises näited valisime kolm olemit: **ContactCSV: TestData** **primaarse** olemina, **WebAccountCSV: TestData** **2. olemina** ja **CallRecordSmall: TestData** **3. olemina**. Valikute kohal olev diagramm kirjeldab vastendamisjärjestuse toimimist.

> [!div class="mx-imgBorder"]
> ![Andmete vastendamisjärjestuse muutmine](media/configure-data-match-order-edit-page.png "Andmete vastendamisjärjestuse muutmine")
  
**Primaarne** olem vastendataks **2. olemiga**. Esimesest vastest tulenev andmekogum vastab **3. olemile**.
Selles näites valisime vaid kaks vastet, ent süsteem võimaldab rohkem.

> [!IMPORTANT]
> Olemil, mille valite **primaarseks** olemiks, hakkab põhinema koondpõhiandmekogumil. Sellele olemile lisatakse täiendavad olemid, mis on valitud vastendamisetapis. Samas ei tähenda see, et ühendatud olem hõlmab *kõiki* sellesse olemisse kaasatud andmeid.
>
> Kaks mõtet, mis võivad aidata valida olemite järjestust:
>
> - Milline olem on kõige põhjalikum ja mille kliendiandmed on kõige usaldusväärsemad?
> - Kas äsja tuvastatud olemil on atribuudid, mida jagavad ka teised olemid (näiteks nimi, telefoninumber või e-posti aadress)? Kui ei, siis valige järgmine kõige usaldusväärsem olem.

Valige **valmis**, et salvestada vaste tellimus.

## <a name="define-rules-for-your-first-match-pair"></a>Määratlege esimese vastenduse paari reeglid

Pärast vastendamisjärjestuse määramist näete määratletud vasteid lehel **Vastendamine**. Ekraani ülaosas olevad paanid jäävad tühjaks kuni käivitate vastendamisjärjestuse.

> [!div class="mx-imgBorder"]
> ![Reeglite määratlemine](media/configure-data-match-need-rules.png "Reeglite määratlemine")

Hoiatus **Vajab reegleid** hoiatus viitab sellele, et vastenduse paari jaoks pole määratletud ühtegi vastendusreeglit. Vastendamisreeglid määratlevad loogika, mille alusel vastendatakse kindlat olemite paari.

1. Esimese reegli määratlemiseks avage paan **Reeglimääratlus**, valides vastenduste tabelis (1) vastava vasterea ja seejärel valides **Loo uus reegel** (2).

   > [!div class="mx-imgBorder"]
   > ![Loo uus reegel](media/configure-data-match-new-rule2.png "Loo uus reegel")

2. Seadistage paanis **Reegli muutmine** selle reegli tingimused. Tingimusi väljendatakse kohustuslike valikutega kahe reaga.

   > [!div class="mx-imgBorder"]
   > ![Uue reegli paan](media/configure-data-match-new-rule-condition.png "Uue reegli paan")

   Olem/väli (esimene) – esimese vastendamise paari olemi vastendamiseks kasutatav atribuut. Näidete hulgas võib olla telefoninumber või e-postiaadress. Valige atribuut, mis tõenäoliselt on kliendile ainulaadne.

   > [!TIP]
   > Vältige toimingu tüüpi atribuutidel põhinevat vastendamist. Teisisõnu, kui atribuut tundub olevat tegevus, võib see olla vastendamiseks halb kriteerium.  

   Olem/väli (teine) – teise vastendamise paari olemi vastendamiseks kasutatav atribuut.

   Normaliseerimine – **Normaliseerimismeetod**: valitud atribuutide jaoks on saadaval erinevad normaliseerimisvalikud. Näiteks kirjavahemärkide või tühikute eemaldamine

   Ettevõtte nime normaliseerimise (eelvaade) puhul saate valida ka **Tüüp (telefon, nimi, ettevõte)**

   > [!div class="mx-imgBorder"]
   > ![Normaliseerimine – B2B](media/match-normalization-b2b.png "Normaliseerimine – B2B")

   Täpsuse tase – selle tingimuse puhul kasutatav täpsuse tase. Vaste tingimuse täpsuse taset on kaht tüüpi: **põhiline** ja **Kohandatud**.  
   - Põhiline: võimaldab valida nelja valikut: madal, keskmine, kõrge ja täpne. Vaid 100 protsendiliste kirjete vastendamiseks valige **Täpne**. Alla 100 protsendiliste kirjete vastendamiseks valige üks neljast tasemest.
   - Kohandatud: liuguriga määratlete kohandatud protsenti, mida kirjed peavad vastendama või sisestage väärtus välja **Kohandatud**. Süsteem vastendab vaid kirjeid, mis ületavad seda läve ühendatud vastenduse paaridena. Liuguri väärtused on vahemikus 0-1. Seega 0,64 tähendab 64 protsenti.

3. Reegli salvestamiseks valige **Valmis**.

### <a name="add-multiple-conditions"></a>Mitme tingimuse lisamine

Olemite vastendamiseks vaid siis, kui täidetud on mitu tingimust, lisage veel tingimusi, mis on seotud tehtemärgiga AND.

1. Valige paanil **Reegli muutmine** valik **Tingimuse lisamine**. Soovi korral saate ka kustutada, valides olemasoleva tingimuse kõrval eemaldamisnuppu.

2. Reegli salvestamiseks valige **Valmis**.

## <a name="add-multiple-rules"></a>Mitme reegli lisamine

Kõik tingimused kehtivad ühele atribuutide paarile, kuid reeglid tähendavad tingimuste kogumeid. Olemite vastendamiseks eri atribuutide komplektiga saate lisada veel reegleid.

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Koondamine** > **Vastavusseviimine**.

2. Valige uuendatav olem ja **Lisa reeglid**.

3. Järgige teema [Määratlege esimese vastenduse paari reeglid](#define-rules-for-your-first-match-pair) juhiseid.

> [!NOTE]
> Reegli järjekord on oluline. Vastendamise algoritm proovib vastendada esimese reegli alusel ja jätkab teise reegliga vaid siis, kui esimese reegli korral ei tuvastatud vasteid.

## <a name="define-deduplication-on-a-match-entity"></a>Vastendatud olemis duplikaadieemalduse määratlemine

Lisaks ülaltoodud jaotistes kirjeldatud olemitevahelistele vastavusseviimise reeglite määramisele saate määrata ka duplikaadieemalduse reeglid. *Duplikaadieemaldus* on protsess. See tuvastab duplikaatkirjed, ühendab need üheks kirjeks ja lingib kõik lähtekirjed selle ühendatud kirjega koos alternatiivsete ID-dega.

Pärast eemaldatud duplikaatidega kirje tuvastamist kasutatakse seda olemitevahelises vastavusseviimise protsessis. Duplikaadieemaldust rakendatakse olemi tasemel ja seda saab rakendada iga olemi korral, mida kasutatakse vastavusseviimise protsessis.

### <a name="add-deduplication-rules"></a>Duplikaadieemalduse reeglite lisamine

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Koondamine** > **Vastavusseviimine**.

1. Valige jaotises **Ühendatud duplikaadid** suvand **Sea olemid**.

1. Valige jaotises **Ühendamise eelistused** olemid, mille korral soovite duplikaadieemaldust rakendada.

1. Määrake duplikaatkirjete ühendamise viis ja valige üks kolmest ühendamissuvandist.
   - *Enim täidetud*: tuvastab võitjana kirje, millel on kõige rohkem täidetud atribuute. See on vaikeühendamissuvand.
   - *Kõige hiljutisem*: tuvastab võitjana kirje, millega tegeleti kõige viimasena. Hiljutisuse määratlemiseks on vaja kuupäeva- või numbrilist välja.
   - *Kõige vanem*: tuvastab võitjana kirje, millega tegeleti kõige varem. Hiljutisuse määratlemiseks on vaja kuupäeva- või numbrilist välja.
 
   > [!div class="mx-imgBorder"]
   > ![Duplikaadieemalduse reeglite samm 1](media/match-selfconflation.png "Duplikaadieemalduse reeglite samm 1")
 
1. Kui olemid on valitud ja nende ühendamiseelistus on seatud, valige **Loo uus reegel**, et määratleda duplikaadieemalduse reeglid olemi tasemel.
   - Suvand **Vali väli** loetleb kõik selle olemi saadaolevad väljad, mille lähteandmetest soovite eemaldada duplikaadid.
   - Määrake normaliseerimis- ja täpsussätted sarnasel viisil, nagu kirjeldati olemitevahelises vastavusseviimises.
   - Lisatingimuste määratlemiseks valige **Lisa tingimus**.
 
   > [!div class="mx-imgBorder"]
   > ![Duplikaadieemalduse reeglite samm 2](media/match-selfconflation-rules.png "Duplikaadieemalduse reeglite samm 2")

  Võite olemi jaoks luua mitu duplikaadieemalduse reeglit. 

1. Vastavusseviimise protsessi käitamise korral rühmitatakse kirjed nüüd duplikaadieemalduse reeglites määratletud tingimuste alusel. Pärast kirjete rühmitamist rakendatakse ühendamispoliitikat, et tuvastada võitjast kirje.

1. Seejärel kasutatakse seda võitjast kirjet olemitevahelises vastavusseviimises.

1. Kõik kohandatud vastavusseviimise reeglid, mis on määratletud „alati vastavusseviimise“ ja „mitte kunagi vastavusseviimise“ jaoks, alistavad duplikaadieemalduse reeglid. Kui duplikaadieemalduse reegel tuvastab ühtivad kirjed ja kohandatud vastavusseviimise reegel on seatud neid kirjeid mitte kunagi vastavusse viima, siis neid kahte kirjet ei viida vastavusse.

1. Pärast vastavusseviimise protsessi käivitamist näete duplikaadieemalduse andmeid.
   
> [!NOTE]
> Duplikaadieemalduse reeglite määramine pole kohustuslik. Kui selliseid reegleid pole konfigureeritud, rakendatakse süsteemi määratletud reegleid. Need ahendavad kõik kirjed, millel on sama primaarvõtme ja vastendusreeglite väljade väärtuskombinatsiooni (täpne vaste) ühte kirjesse, pärast mida edastatakse olemiandmed olemitevaheliseks vastavusseviimiseks, et jõudlus ja süsteem oleksid paremad.

## <a name="run-your-match-order"></a>Käivitage vaste järjestus

Pärast vastavusseviimise reeglite (sh olemitevahelise vastavusseviimise ja duplikaadieemalduse reeglite) määratlemist saate käivitada vastavusseviimise korralduse. Toimingu käivitamiseks valige lehel **Vastendamine** valik **Käivita**. Vastendamisalgoritm võib aega võtta. Lehel **Vastendamine** ei saa muuta atribuute kuni vastendamine on lõppenud. Leiate ühendatud kliendiprofiili olemi, mis loodi lehel **Olemid**. Ühendatud kliendiolemit nimetatakse **ConflationMatchPairs : CustomerInsights**.

Täiendavate muudatuste tegemiseks ja etapi uuesti käivitamiseks saate poolelioleva vaste tühistada. Valige tekst **Värskendamine ...** ja valige nähtavale ilmuva külgpaani allosast suvand **Tühista töö**.

Kui vastendamise protsess on lõpule viinud, muutub tekst **Värskendamine ...** tekstiks **Õnnestus**, ja te saate jälle kasutada kõiki lehe funktsioone.

Esimene vastendamine loob koondpõhiolemit. Kõik järgnevad vastendamised laiendavad seda olemit.

> [!TIP]
> Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types). Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies). Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku. Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.

## <a name="review-and-validate-your-matches"></a>Vastenduste ülevaatamine ja valideerimine

Hinnake vastepaaride kvaliteeti ja täiustage seda:

- Lehel **Vastendamine** leiate kaks paani, kus näidatakse esmaseid ülevaateid teie andmetest.

  - **Kordumatud kliendid**: näitab süsteemi tuvastatud kordumatute profiilide arvu.
  - **Vastendatud kirjed**: näidatakse vastendamispaaride vastete arvu.

- Tabelis **Vaste järjestus** pääsete juurde iga vastendamispaari tulemustele, selleks võrrelge vastepaari olemi kirjete arvu edukalt vastendatud kirjete protsendiga.

- Tabeli **Vaste järjestus** olemi jaotises **Reeglid** leiate edukalt vastendatud kirjete protsendi reegli tasemel. Reegli kõrval asuva tabeli sümboli valimisel näete kõiki neid kirjeid reegli tasemel. Soovitame üle vaadata kirjete alamhulka, et kinnitada nende õiget vastendamist.

- Optimaalse väärtuse tuvastamiseks katsetage tingimuste ümber eri täpsusega lävedega.

  1. Valige katsetatava vastendamispaari reegli puhul kolme punkti ikooni (...) ja valige **Muuda**.

  2. Valige tingimus, millega soovite katsetada. Iga kriteerium asub paanis **Vastendusreegel** ühes reas.

  3. Lehel **Kriteeriumi eelvaade** nähtu sõltub tingimuse täpsuse taset. Leidke valitud tingimuse vastendatud ja vastendamata kirjete arv.

     Hankige põhjalikke teadmisi eri läve tasemete mõjudest. Saate võrrelda, mitu kirjet vastendataks iga lävetaseme puhul ja vaadake iga valiku kirjeid. Valige kõik paanid ja vaadake üle tabeli jaotise andmed.

## <a name="optimize-your-matches"></a>Vastete optimeerimine

Parandage kvaliteeti, selleks seadistage uuesti paar vaste näitajat:

- **Muutke vastendamisjärjestust**, selleks valige **Muuda** ja muutke vastendamisjärjekorra välju.

  > [!div class="mx-imgBorder"]
  > ![Andmete vastendamisjärjestuse muutmine](media/configure-data-match-order-edit.png "Andmete vastendamisjärjestuse muutmine")

- **Muutke reeglite järjestust**, kui määratlesite mitu reeglit. Saate muuta vastendamisreeglite järjestust, selleks valige vastendamisreeglite ruudustikus **Liigu üles** ja **Liigu alla**.

  > [!div class="mx-imgBorder"]
  > ![Muutke reegli järjestust](media/configure-data-change-rule-order.png "Muutke reegli järjestust")

- **Paljundage reegleid**, kui olete määratlenud vastendamisreegli ja soovite luua sarnase, ent muudetud reegli. Selleks valige **Duplikaat**.

  > [!div class="mx-imgBorder"]
  > ![Reegli paljundaminel](media/configure-data-duplicate-rule.png "Reegli paljundamine")

- **Muutke reegleid**, valides sümboli **Muuda**. Saate kasutada järgmisi muudatusi.

  - Muutke tingimuse atribuute: valige kindlas tingimuse read uued atribuudid.
  - Muutke tingimuse läve: reguleerige täpsusliugurit.
  - Muutke tingimuse normaliseerimisviisi: uuendage normaliseerimisviisi.

## <a name="specify-your-custom-match-records"></a>Määrake muudetud vastendamiskirjed.

Saate määrata tingimused, et kindlad kirjed peaksid alati vastama või mitte kunagi vastama. Neid reegleid saab vastendamisel üles laadida korraga.

1. Valige ekraanil **Vastendamisjärjestus** valikut **Kohandatud vaste**.

   > [!div class="mx-imgBorder"]
   > ![Kohandatud vaste loomine](media/custom-match-create.png "Kohandatud vaste loomine")

2. Kui olemeid pole üles laaditud, näete uut dialoogikasti **Kohandatud vaste**, mis nõuab teatud andmete sisestamist. Kui olete need andmed varem esitanud, jätkake kaheksanda etapiga.

   > [!div class="mx-imgBorder"]
   > ![Uus kohandatud vaste dialoogikast](media/custom-match-new-dialog-box.png "Uus kohandatud vaste dialoogikast")

3. Valige **Täida mall**, et hankida malli fail, mis määratleb, mis olemite kirjed peaksid kattuma alati või mitte kunagi. Peate „Vastenda alati“ kirjed ja „Vastenda mitte kunagi“ kirjed sisestama eraldi kahte eri faili.

4. Mall sisaldab välju, et täpsustada kohandatud vastendamise olemit ja olemi primaarvõtme väärtusi. Näiteks, kui soovite, et olemi Sales primaarvõti 12345 ühtiks alati olemi Contact primaarvõtmega 34567, peate täpsustama järgmiselt.
    - Entity1: Sales
    - Entity1Key: 12345
    - Entity2: Contact
    - Entity2Key: 34567

   Sama malli fail suudab määratleda mitme olemi kohandatud vastendamiskirjeid.

5. Pärast kõikide soovitud asenduste lisamist salvestage malli fail.

6. Minge jaotisse **Andmed** > **Andmeallikad** ja valmendage mallifailid uute olemitena. Pärast sisestamist saate nendega määratleda vastendamisseadistust.

7. Pärast failide üleslaadimist ja olemite avalikustamist valige uuesti valik **Kohandatud vaste**. Näete valikuid, et täpsustada kaasatavad olemid. Valige rippmenüüst vajalikud olemid.

   > [!div class="mx-imgBorder"]
   > ![Kohandatud vaste asendused](media/custom-match-overrides.png "Kohandatud vaste asendused")

8. Valige olemid, mida tahate kasutada **Vastenda alati** ja **Vastenda mitte kunagi** puhul, seejärel valige **Valmis**.

9. Valige äsja seadistatud kohandatud vaste seadistuse lehel **Vastendamine** valik **Salvesta**.

10. Vastendamiseks valige lehel **Vastendamine** valik **Käivita** ja kohandatud vaste seadistus läheb kasutusele. Kõik süsteemi vastendatud reeglid asendatakse seadistuskomplektiga.

11. Pärast vastendamist saate kinnitada olemi **ConflationMatchPair**, et kinnitada, kas ühendamisvasted asendati.

## <a name="next-step"></a>Järgmine etapp

Pärast vähemalt ühe vastendamispaari vastendamist võite lahendada andmete võimalikud vastuolud, selleks lugege teemat [**Liitmine**](merge-entities.md).
