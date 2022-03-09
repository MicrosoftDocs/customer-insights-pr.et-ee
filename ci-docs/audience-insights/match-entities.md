---
title: Olemite vastavusseviimine andmete koondamiseks
description: Viige olemid vastavusse, et luua koondatud kliendiprofiile.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: 3c0dd9c417e569ed37d8122c637072893732418a
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/02/2022
ms.locfileid: "8372622"
---
# <a name="match-entities"></a>Olemite vastavusseviimine

Vastavusse viimise etapp täpsustab, kuidas kombineerida andmekogusid koondatud kliendiprofiilide andmekogusse. Pärast [vastendusetapi](map-entities.md) lõpuleviimist andmete koondamisel olete valmis olemeid vastendama. Vastendamisetapp vajab vähemalt kahte kaardistatud olemit.

Vastete leht koosneb kolmest jaotisest: 
- Põhimõõdikud, mis summeerivad vastendatud kirjete arvu
- Olemiülese vastendamise vastenduste järjekord ja reeglid
- Vastendusolemite duplikaadieemalduse reeglid

## <a name="specify-the-match-order"></a>Vastendamisjärjestuse määramine

Iga vaste ühendab kaks või enam olemit üheks, konsolideeritud olemiks. Samal ajal säilitab see kordumatud kliendikirjed. Vaste järjekord näitab, millises järjekorras süsteem püüab kirjeid sobitada.

> [!IMPORTANT]
> Olem, mille valite primaarseks olemiks, saab koondatud profiilide andmekomplekti aluseks. Sellele olemile lisatakse täiendavad olemid, mis on valitud vastendamisetapis. See ei tähenda, et koondatud olem sisaldaks *kõiki* selles olemis sisalduvaid andmeid.
>
> Kaks mõtet, mis võivad aidata valida olemite järjestust:
>
> - Esmaseks olemiks valige olem, mille profiiliandmed teie kliendi kohta on kõige täielikumad ja usaldusväärsemad.
> - Valige olem, millel on primaarolemiks mitu muu olemiga ühist atribuuti (nt nimi, telefoninumber või meiliaadress).

1. Vastandamise faasi alustamiseks minge asukohta **Andmed** > **Ühilda** > **Sobita** ja valige **Määra tellimus**.
1. Valige **Olemi tellimus**. Näiteks valige **esmase olemina eCommerce:eCommerceContacts** ja **teise olemina LoyaltyScheme:loyCustomers**. 
1. Kui soovite, et iga olemi kirje oleks kordumatu klient ja see vastaks igale järgmisele olemile, valige **Kaasa kõik**.
1. Valige nupp **Valmis**. 

Pärast vastejärjekorra määramist kuvatakse **määratletud vastepaarid DataUnifyMatchi** **·** > **jaotises** > **Sobitatud kirjete üksikasjad.** Peamised mõõdikud on tühjad, kuni mänguprotsess on lõpule viidud.

:::image type="content" source="media/match-page.png" alt-text="Andmete koondamise koondamisala vastete lehe kuvatõmmis.":::
  
Esmane olem *eCommerce:eCommerceContacts* vastendatakse järgmise olemiga *LoyaltyScheme:loyCustomers*. Esimese vasteetapist tulenev andmestik sobitatakse järgmise olemiga, kui teil on rohkem kui kaks olemit.

## <a name="define-rules-for-match-pairs"></a>Vastepaaride reeglite määratlemine

Vastendamisreeglid määratlevad loogika, mille alusel vastendatakse kindlat olemite paari.

Olemi nime kõrval kuvatav hoiatus **Vajab reeglit** viitab sellele, et vastepaari jaoks pole vastendusreeglit määratud. 

:::image type="content" source="media/match-rule-add.png" alt-text="Esiletõstetud reeglite lisamise juhtelemendiga vastendatud kirje üksikasjade jaotise kuvatõmmis.":::

1. Vastereeglite määratlemiseks valige **jaotises Vastendatud kirjete üksikasjad** olemi **all käsk Lisa reegel**.

1. Konfigureerige paanil **Reegli loomine** reegli tingimused.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Lisatud tingimustega avatud vastendusreegli kuvatõmmis.":::

   - **Olem/väli (esimene rida)**: valige seotud olem ja atribuut kliendi jaoks tõenäoliselt kordumatu kirjeatribuudi määramiseks. Näiteks telefoninumber või meiliaadress. Vältige vastendamist tegevustüübi atribuutide järgi. Näiteks ei leia ostu ID tõenäoliselt teiste kirjetüüpide puhul vasteid.

   - **Olem/väli (teine rida)**: valige atribuut, mis on seotud esimeses reas määratud olemi atribuudiga.

   - **Normaliseeri**: valige valitud atribuutide puhul mõni järgmistest normaliseerimissuvanditest. 
     - Numbrid: teisendab muud numbrisüsteemid (nt rooma numbrid) araabia numbriteks. *VIII* asemel on kasutusel *8*.
     - Sümbolid: eemaldab kõik sümbolid ja erimärgid. Tekstist *Head&Shoulder* saab tekst *HeadShoulder*.
     - Tekst väiketäheliseks: teisendab kõik märgid väiketäheliseks. Tekstist *ALL CAPS ja Title Case* saab *all caps ja title case*.
     - Tüüp (telefon, nimi, aadress, organisatsioon): standardiseerib nimed, pealkirjad, telefoninumbrid, aadressid jne. 
     - Unicode ASCII-ks: teisendab Unicode'i tähistuse ASCII-märkideks. */u00B2* asemel on kasutusel *2*.
     - Tühik: eemaldab kõik tühikud. Tekstist *Hello   World* saab tekst *HelloWorld*.

   - **Täpsus**: saate määrata selle tingimuse jaoks rakendatava täpsustaseme. 
     - **Põhiline**: valikualus: *väike*, *keskmine*, *suur* ja *täpne*. Valige **Täpne**, et sobitada ainult 100 protsendile vastavad kirjed. Alla 100 protsendiliste kirjete vastendamiseks valige üks neljast tasemest.
     - **Kohandatud**: saate määrata protsendi, millele kirjed peavad vastama. Süsteem vastendab ainult seda läve ületavad kirjed.

1. Sisestage reegli **Nimi**.

1. [Lisage veel tingimusi](#add-conditions-to-a-rule) või valige reegli vormistamiseks **Valmis**.

1. Võite ka [rohkem reegleid lisada](#add-rules-to-a-match-pair).

1. Vajutage nuppu **Salvesta**, et muudatused rakendada.

### <a name="add-conditions-to-a-rule"></a>Tingimuste lisamine reeglile

Kui soovite olemeid vastendada ainult juhul, kui atribuudid vastavad mitmele tingimusele, lisage vastendusreeglile veel tingimusi. Tingimused on ühendatud loogika tehtemärkiga AND ja käivitatakse seega ainult juhul, kui kõik tingimused on täidetud.

1. Avage **Andmed** > **Koondamine** > **Vastendamine** ja valige **Redigeeri** reegli jaoks millele soovite tingimusi lisada.

1. Valige paanil **Reegli muutmine** valik **Tingimuse lisamine**.

1. Reegli salvestamiseks valige **Valmis**.

### <a name="add-rules-to-a-match-pair"></a>Reeglite lisamine vastepaarile

Vastendusreeglid esindavad tingimuste kogumeid. Olemite sobitamiseks mitme atribuudi alusel tingimustega lisage veel reegleid.

1.  Avage **Andmed** > **Koondamine** > **Vastendamine** ja valige **Lisa reegel** olemi jaoks millele soovite reegleid lisada.

2. Järgige teema [Vastepaaride reeglite määratlemine](#define-rules-for-match-pairs) juhiseid.

> [!NOTE]
> Reeglite järjekorda on oluline. Vastendamise algoritm proovib vastendada esimese reegli alusel ja jätkab teise reegliga vaid siis, kui esimese reegli korral ei tuvastatud vasteid.

### <a name="change-the-entity-order-in-match-rules"></a>Olemi järjestuse muutmine reeglite vastendamises

Saate olemeid mängureeglite jaoks ümber tellida, et muuta nende töötlemise järjekorda. Reeglid, mis on muudetud tellimuse tõttu vastuolulised, eemaldatakse. Värskendatud konfiguratsiooniga eemaldatud reeglid tuleb uuesti luua.

1. Minge **Andmed** > **Unify** > **Vaste** ja valige **Redigeeri**.

1. Paanil **Reegli redigeerimine** valige juhtelement **Nihuta üles/alla** või lohistage olemid tellimuse muutmiseks.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Suvandid tellimuse olemite sobitamise ajal töötlemise suvandite muutmiseks.":::

1. Reegli salvestamiseks valige **Valmis**.

## <a name="define-deduplication-on-a-match-entity"></a>Vastendatud olemis duplikaadieemalduse määratlemine

Lisaks [olemiülestele vastendusreeglitele](#define-rules-for-match-pairs) saate määrata ka duplikaadieemalduse reeglid. *Duplikaadieemaldus* on veel üks kirjete vastendamise toiming. See tuvastab duplikaatkirjed ja ühendab need ühte kirjesse. Lähtekirjed lingitakse alternatiivsete ID-dega ühendatud kirjega.

Likvideeritud kirjeid kasutatakse olemiüleses sobitamisprotsessis. Deduplication toimub üksikutel olemitel ja seda saab konfigureerida iga mängupaarides kasutatava olemi jaoks.

Duplikaadieemalduse reeglite määramine pole kohustuslik. Kui selliseid reegleid pole konfigureeritud, rakendatakse süsteemi määratletud reegleid. Nad kombineerivad kõik kirjed ühte kirjesse enne olemi andmete edastamist olemiüleseks vastendamiseks täiustatud jõudluse tagamiseks.

### <a name="add-deduplication-rules"></a>Duplikaadieemalduse reeglite lisamine

1. Avage **Andmed** > **Koondamine** > **Vastendamine**.

1. **Valige jaotises Deduplicated Records Details** (**Määra olemid).** Juhul, kui duplikaadieemaldusreeglid on juba loodud, valige **Redigeeri**.

1. Valige paanil **Ühendamise eelistused** olemid, mille jaoks soovite duplikaadieemaldust käitada.

   1. Määrake duplikaatkirjete kombineerimisviis ja valige üks kolmest ühendamissuvandist.
      - **Enim täidetud**: tuvastab võitjana kirje, millel on kõige rohkem asustatud atribuudivälju. See on vaikeühendamissuvand.
      - **Kõige hiljutisem**: tuvastab võitjana kirje, millega tegeleti kõige viimasena. Hiljutisuse määratlemiseks on vaja kuupäeva- või numbrilist välja.
      - **Kõige vanem**: tuvastab võitjana kirje, millega tegeleti kõige varem. Hiljutisuse määratlemiseks on vaja kuupäeva- või numbrilist välja.

   1. Soovi korral valige **olemi üksikute atribuutide deduplatsioonireeglite määratlemiseks Suvand Täpsemalt**. Näiteks saate säilitada kõige uuema e-kirja JA kõige täielikuma aadressi erinevatest kirjetest. Laiendage olemit, et näha kõiki selle atribuute ja määratleda, millist suvandit üksikute atribuutide puhul kasutada. Kui valite recency-põhise suvandi, peate määrama ka kuupäeva/kellaaja välja, mis määratleb recency. 
 
      > [!div class="mx-imgBorder"]
      > ![Duplikaadieemalduse reeglite samm 1.](media/match-selfconflation.png "Duplikaadieemalduse reeglite samm 1")

   1. Koosteelistuste rakendamiseks deduplatsiooni jaoks valige **Valmis**.
 
1. Kui olemid on valitud ja nende ühendamiseelistus on seatud, valige **Lisa reegel**, et määratleda duplikaadieemalduse reeglid olemi tasemel.
   - **Välja valimine** loetleb kõik sellest olemist pärit saadaolevad väljad. Valige väli, mille duplikaate soovite otsida. Valige väljad, mis on tõenäoliselt iga kliendi jaoks kordumatud. Näiteks meiliaadress või nime, linna ja telefoninumbri kombinatsioon.
   - Määrake normaliseerimis- ja täpsusesätted.
   - Lisatingimuste määratlemiseks valige **Lisa tingimus**.
 
   > [!div class="mx-imgBorder"]
   > ![Duplikaadieemalduse reeglite samm 2.](media/match-selfconflation-rules.png "Duplikaadieemalduse reeglite samm 2")

  Võite olemi jaoks luua mitu duplikaadieemalduse reeglit. 

1. Vastavusseviimise protsessi käitamise korral rühmitatakse kirjed nüüd duplikaadieemalduse reeglites määratletud tingimuste alusel. Pärast kirjete rühmitamist rakendatakse ühendamispoliitikat, et tuvastada võitjast kirje.

1. Võitja kirje antakse seejärel üle olemitevahelisele sobitamisele koos kaotaja kirjetega (nt alternatiivsed ID-d), et parandada sobitamiskvaliteeti.

1. Kõik määratletud kohandatud vastendusreeglid kirjutavad üle duplikaadieemaldusreeglid. Kui duplikaadieemalduse reegel tuvastab ühtivad kirjed ja kohandatud vastavusseviimise reegel on seatud neid kirjeid mitte kunagi vastavusse viima, siis neid kahte kirjet ei viida vastavusse.

1. Pärast [mänguprotsessi](#run-the-match-process) käivitamist näete põhimõõdikute paanidel deduplatsiooni statistikat.

### <a name="deduplication-output-as-an-entity"></a>Pöördduplitseerimise väljund olemina

Duplikaadieemaldusega luuakse uus olem iga olemi olemi jaoks vastepaaridest, et tuvastada duplikaadieemaldusega kirjed. Neid olemeid võib leida koos suvandiga **ConflationMatchPairs:CustomerInsights** jaotises **Süsteem** leheküljel **Olemid** nimega **Deduplication_Datasource_Entity**.

Pöördduplitseeritava väljundi olem sisaldab järgmist teavet:
- ID-d/võtmed
  - Primaarvõtme väli ja selle alternatiivsed ID väljad. Alternatiivsed ID-d on kõik kirje tuvastatud alternatiivsed ID-d.
  - Deduplication_GroupId väli näitab olemi sees tuvastatud rühma või klastrit, mis rühmitab kõik sarnased kirjed määratud pöördduplitseerimise väljade põhjal. Seda kasutatakse süsteemi töötlemise eesmärkidel. Kui pole määratud pole manuaalseid pöördduplitseerimise reegleid ja süsteemi määratletud pöördduplitseerimise väljade subjektireeglid kehtivad, ei pruugi te seda välja pöördduplitseerimise väljundi olemist leida.
  - Deduplication_WinnerId: see väli sisaldab tuvastatud rühma või klastri võitja ID-d. Kui Deduplication_WinnerId on sama, mis kirje primaarvõtme väärtus, tähendab see, et kirje on võitja kirje.
- Väljad, mida kasutatakse pöördduplitseerimise reeglite määratlemiseks.
- Reeglid ja punktisumma väljad, mis tähistavad rakendatavaid pöördduplitseerimise reegleid ja millist punktisummat tagastas sobitusalgoritm.
 
## <a name="include-enriched-entities-preview"></a>Kaasa rikastatud olemid (eelvaade)

Kui rikastasite andmeallikas tasemel olemeid, valige need enne mänguprotsessi käivitamist. Rikastatud üksused võivad parandada teie ühendamise tulemusi. Lisateavet vt teemast [Enrichment for Data sources](data-sources-enrichment.md). 

1. **Avage dataUnifyMatch** > **·** > **ja** valige lehe ülaosas suvand **Kasuta rikastatud olemeid.**

1. Valige paanil **Kasuta rikastatud olemeid** üks või mitme rikastatud olemit.

1. Valige nupp **Valmis**. Kui kasutatakse lähteolemit (nt vastejärjestus või reeglid), muudetakse see automaatselt rikastatud olemiks.
  
## <a name="run-the-match-process"></a>Vastenduse käivitamine

Konfigureeritud vastendusreeglitega (sh olemitevahelise vastavusseviimise ja duplikaadieemalduse reeglite) saate käivitada vastavusseviimise. 

Toimingu käivitamiseks valige **Andmed** > **Koondamine** > **Vastendamine** ja valige **Käivita**. Vastendusalgoritmil kulub lõpuleviimiseks veidi aega ja te ei saa konfiguratsiooni muuta ennem kui see on lõpule viidud. Muudatuste tegemiseks saate töötamise tühistada. Valige töö olek ja tehke paanil **Edenemise üksikasjad** valik **Tühista töö**.

Lõpuleviidud käituse tulemuse, koondatud kliendiprofiili olemi leiate lehelt **Olemid**. Kliendi koondolemi nimeks on **Kliendid** jaotises **Profiilid**. Esimene õnnestunud vastekäitus loob koondolemi *Klient*. Kõik järgnevad vastekäitused laiendavad seda olemit.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Vastenduste ülevaatamine ja valideerimine

Vastepaaride kvaliteedi hindamiseks ja vajaduse korral nende täpsustamiseks avage **Andmed** > **Koondamine** > **Vastendamine**.

Lehe ülaosas asuvad paanid kuvavad põhimõõdikuid, summeerides vastendatud kirjete ja duplikaatide arvu.

:::image type="content" source="media/match-KPIs.png" alt-text="Numbrite ja üksikasjadega vastete lehe põhimõõdikute kärbitud kuvatõmmis.":::

- **Kordumatud lähtekirjed** näitab viimases vastekäituses töödeldud üksikute lähtekirjete arvu.
- **Vastendatud ja vastendamata kirjed** tõstab esile, mitu kordumatut kirjet on alles pärast vastendusreeglite töötlemist.
- **Ainult vastendatud kirjed** näitab ainult vastete arvu kõigis vastepaarides.

Iga vastepaari tulemusi ja selle reegleid saate hinnata tabelis **Vastendatud kirjete üksikasjad**. Võrrelge vastepaarist saadud kirjete arvu edukalt vastendatud kirjete protsendiga.

Vaadake üle vastepaari reeglid, et näha edukalt vastendatud kirjete protsenti reeglite tasemel. Valige kolmikpunkt (...) ja seejärel valige **Vastete eelversioon**, et näha kõiki neid kirjeid reegli tasemel. Soovitame mõnda kirjet vaadata, et kontrollida, kas need on õigesti vastendatud.

Optimaalse väärtuse leidmiseks proovige tingimustes erinevaid täpsuslävesid.

  1. Valige selle reegli kolmikpunkt (...), millega soovite katseid teha, ja valige **Redigeeri**.

  2. Muutke täpsuse väärtusi tingimustes, mida soovite muuta.

  3. Valige **Eelversioon**, et näha valitud tingimusega vastendatud ja vastendamata kirjete arvu.

## <a name="manage-match-rules"></a>Vastendusreeglite haldamine

Enamuse vasteparameetritest saate ümber konfigureerida ja peenhäälestada.

:::image type="content" source="media/match-rules-management.png" alt-text="Ripploendi menüü kuvatõmmis koos vastetusreegli suvanditega.":::

- **Muutke reeglite järjestust**, kui määratlesite mitu reeglit. Vastendusreeglite ümberjärjestamiseks saate valida suvandid **Nihuta üles** ja **Nihuta alla** või reegleid pukseerida.

- **Reegli tingimuste muutmiseks** valige **Redigeeri** ja valige muud väljad.

- **Inaktiveerige reegel**, et säilitada sobitusreegel eraldades seda sobitusprotsessist.

- Kui olete vastendusreegli määratlenud, **dubleerige reeglid** ja kui soovite luua sarnase reegli muudatustega, valige **Dubleeri**.

- **Reegli kustutamiseks** valige sümbol **Kustuta**.

## <a name="advanced-options"></a>Täpsemad suvandid

### <a name="add-exceptions-to-a-rule"></a>Reeglile erandite lisamine

Enamikul juhtudel toob olemi sobitamine kaasa unikaalsed kasutajaprofiilid konsolideeritud andmetega. Harvaesinevate valepositiivsete ja valenegatiivsete juhtumite dünaamiliseks käsitlemiseks saate määratleda vastereegli erandid. Erandeid rakendatakse pärast mängureeglite töötlemist ja vältige kõigi erandikriteeriumidele täitvate kirjete sobitamist.

Näiteks kui teie mängureegel ühendab perekonnanimi, linna ja sünnikuupäeva, tuvastaks süsteem sama perekonnanimi kaksikud, kes elavad samas linnas kui sama profiil. Saate määrata erandi, mis ei vasta profiilidele, kui teie ühendatud olemite eesnimi pole samad.

1. Avage **Andmed** > **Koondamine** > **Vastendamine** ja valige **Redigeeri** reegli jaoks millele soovite tingimusi lisada.

1. **Valige reegli** redigeerimispaanil **Lisa erand**.

1. Määrake erandikriteeriumid. 

1. Reegli salvestamiseks valige **Valmis**.

### <a name="specify-custom-match-conditions"></a>Kohandatud vastetingimuste määramine

Saate määrata tingimused, mis alistavad vaikevaste loogika. Saadaval on neli võimalust. 

|Variant  |Kirjeldus |Näide  |
|---------|---------|---------|
|Ühtib alati     | Määratleb väärtused, mis on alati sobitatud.         |  Alati sobivad *Mike'i* ja *MikeR-iga*.       |
|Ei ühti kunagi     | Määratleb väärtused, mis kunagi ei ühti.        | Ära kunagi sobi *Johni* ja *Jonathaniga*.        |
|Kohandatud möödumine     | Määratleb väärtused, mida süsteem peaks mängufaasis alati ignoreerima. |  Ignoreerige väärtusi *11111* ja *Tundmatut* matši ajal.        |
|Pseudonüümi vastendus    | Väärtuste määratlemine, mida süsteem peaks sama väärtusena kaaluma.         | Mõtle *, et Joe* on Josephiga *võrdne*.        |

1. Avage **Andmed** > **Koondamine** > **Vastendamine** ja tehke jaotises **Vastendatud kirjete üksikasjad** valik **Kohandatud vaste**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Esiletõstetud kohandatud vaste kontrolliga vastendusreeglite kuvatõmmis.":::

1. Avage paanil **Kohandatud** **vahekaart Kirjed**.

1. Valige ripploendist **Kohandatud vaste suvand Kohandatud** ja valige **Laadi mall** alla. Iga mängusuvandi jaoks on vaja eraldi malli.

1. Avage allalaaditud mallifail ja täitke üksikasjad. Mall sisaldab välju, et täpsustada kohandatud vastendamise olemit ja olemi primaarvõtme väärtusi. Näiteks kui soovite, et esmane võti *12345* olemist *Müük* vastaks alati esmasele võtmele *34567* olemist *Kontakt*, täitke järgmine mall.
    - Entity1: Sales
    - Entity1Key: 12345
    - Entity2: Contact
    - Entity2Key: 34567

   Sama malli fail suudab määratleda mitme olemi kohandatud vastendamiskirjeid.
   
   Kui soovite olemi pöördduplitseerimise määrata kohandatud sobitamisega, sisestage Entity1 ja Entity2 sama olem ja määrake erinevad primaarvõtmed.

1. Pärast kõigi alistamiste lisamist salvestage mallifail.

1. Minge jaotisse **Andmed** > **Andmeallikad** ja valmendage mallifailid uute olemitena.

1. Pärast failide üleslaadimist ja olemite avalikustamist valige uuesti valik **Kohandatud vaste**. Näete valikuid, et täpsustada kaasatavad olemid. Valige rippmenüüst vajalikud olemid ja valige **Valmis**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Dialoogi kuvatõmmis, mis näitab, kuidas valida kohandatud vastendusstsenaariumi alistamised.":::

1. Kohandatud vaste rakendamine sõltub mängusuvandist, mida soovite kasutada. 

   - Kui **mäng on alati sobiv** või **mitte kunagi sobitatud**, jätkake järgmise sammuga.
   - Kohandatud ümbersõidu **või** pseudonüümi vastendamise **puhul** valige **Redigeeri** olemasoleva mängureegli alusel või looge uus reegel. Valige **ripploendis Normaliseerimised suvand Kohandatud ümbersõidu** - või **pseudonüümi vastendamine** ja valige **Valmis**.

1. Kohandatud vastekonfiguratsiooni rakendamiseks tehke lehel **Match** valik **Salvesta**.

1. Vastendusprotsessi käivitamiseks tehke lehel **Match** valik **Käivita**. Muud määratud vastendusreeglid alistatakse kohandatud vastenduskonfiguratsiooniga.

#### <a name="known-issues"></a>Teadaolevad probleemid

- Enesesketseerimine ei näita normaliseeritud andmeid deduplatsiooniolemites. Kuid see rakendab normaliseerimist sisemiselt deduplatsiooni ajal. See on disaini järgi kõigi normaliseerimiste jaoks. 
- Kui semantiline tüübisäte eemaldatakse **kaardifaasis**, kui vastereegel kasutab pseudonüümi vastendust või kohandatud ümbersõitu, siis normaliseerimist ei rakendata. See juhtub ainult siis, kui tühjendate semantilise tüübi pärast normaliseerimise konfigureerimist mängureeglis, kuna semantiline tüüp on teadmata.


## <a name="next-step"></a>Järgmine etapp

Pärast vähemalt ühe matšipaari matšiprotsessi lõpetamist jätkake [**sammu Ühenda**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
