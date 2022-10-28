---
title: Andmete ühendamise tingimuste vastendamine
description: Viige olemid vastavusse, et luua koondatud kliendiprofiile.
recommendations: false
ms.date: 10/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bbd2c5f441b85460250c11f02358ea67260278d6
ms.sourcegitcommit: 52ea58c872b10f1e6f9d120be93df93cca1a12dd
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 10/26/2022
ms.locfileid: "9721516"
---
# <a name="match-conditions-for-data-unification"></a>Andmete ühendamise tingimuste vastendamine

See ühtlustamise etapp määratleb vastendusjärjestuse ja olemiülese vastendamise reeglid. See samm nõuab vähemalt kahte üksust.

> [!NOTE]
> Kui olete vastetingimused loonud ja valinud **Edasi**, ei saa te valitud olemit ega atribuuti eemaldada. Vajadusel valige **Tagasi**, et valitud olemid ja atribuudid enne jätkamist üle vaadata.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Rikastatud olemite kaasamine (eelvaade)

Kui rikastasite üksusi andmeallikas tasemel, et aidata ühtlustamise tulemusi parandada, valige need. Lisateavet leiate teemast [Andmeallikate rikastamine](data-sources-enrichment.md). Kui valisite rikastatud olemid **lehel Kirjete** dubleerimine, ei pea te neid uuesti valima.

1. Lehel **Sobivad tingimused** valige **lehe ülaosas käsk Kasuta rikastatud olemeid**.

1. Valige paanil **Kasuta rikastatud olemeid üks või mitu rikastatud olemit**.

1. Valige nupp **Valmis**.

## <a name="specify-the-match-order"></a>Vastendamisjärjestuse määramine

Iga vaste ühendab kaks või enam olemit üheks, konsolideeritud olemiks. Samal ajal säilitab see kordumatud kliendikirjed. Vastendusjärjestus näitab järjekorda, milles süsteem üritab kirjeid sobitada.

> [!IMPORTANT]
> Esimest olemit nimetatakse esmaseks olemiks, mis on aluseks teie ühendatud profiilidele. Sellele olemile lisatakse täiendavad valitud olemid.
>
> Olulised kaalutlused:
>
> - Valige olem, millel on kõige täielikumad ja usaldusväärsemad profiiliandmed teie klientide kui peamise olemi kohta.
> - Valige olem, millel on teiste olemitega mitu ühist atribuuti (nt nimi, telefoninumber või meiliaadress), mis on peamine olem.

1. Kasutage **lehel Sobivad tingimused** üles- ja allaliigutamise nooli, et teisaldada olemid soovitud järjestuses või lohistada neid. Näiteks valige **peamiseks olemiks eCommerceCustomers** ja **teiseks olemiks püsikliendid**.

1. Kui soovite, et olemis oleks iga kirje kordumatu klient, olenemata sellest, kas vaste leitakse, valige **Kaasa kõik kirjed**. Kõik selle olemi kirjed, mis ei ühti ühegi teise olemi kirjetega, kaasatakse ühtsesse profiili. Kirjeid, millel pole vastet, nimetatakse singletonsiks.
  
Peamine olem Kontaktid:e-kaubandus *vastendatakse järgmise olemiga* *CustomerLoyalty:Loyalty*. Esimesest vasteetapist tulenev andmekogum vastendatakse järgmise olemiga, kui teil on rohkem kui kaks olemit.

:::image type="content" source="media/m3_match.png" alt-text="Olemite jaoks valitud vastendusjärjestuse kuvatõmmis." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Vastepaaride reeglite määratlemine

Vastendamisreeglid määratlevad loogika, mille alusel vastendatakse kindlat olemite paari. Reegel koosneb ühest või mitmest tingimusest.

Olemi nime kõrval olev hoiatus tähendab, et vastepaari jaoks pole vaste reeglit määratletud.

1. Vastereeglite määratlemiseks valige **Olemipaari jaoks käsk Lisa reegel**.

1. **Konfigureerige paanil Lisa reegel** reegli tingimused.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Paani Lisa reegel kuvatõmmis.":::

   - **Valige Olem/väli (esimene rida)**: valige olem ja atribuut, mis on tõenäoliselt kliendile ainuomane. Näiteks telefoninumber või meiliaadress. Vältige vastendamist tegevustüübi atribuutide järgi. Näiteks ei leia ostu ID tõenäoliselt teiste kirjetüüpide puhul vasteid.

   - **Valige Olem/väli (teine rida):** valige atribuut, mis on seotud esimesel real määratud olemi atribuudiga.

   - **Normaliseeri**: valige valitud atribuutide puhul mõni järgmistest normaliseerimissuvanditest.
     - **Numbrid: teisendab muud numbrisüsteemid, näiteks rooma numbrid**, araabia numbriteks. *VIII* asemel on kasutusel *8*.
     - **Sümbolid: eemaldab kõik sümbolid** ja erimärgid. Tekstist *Head&Shoulder* saab tekst *HeadShoulder*.
     - **Tekst väiketähtedeks: teisendab kõik märgid väiketähtedeks**. Tekstist *ALL CAPS ja Title Case* saab *all caps ja title case*.
     - **Tüüp (telefon, nimi, aadress, organisatsioon)**: standardiseerib nimed, tiitlid, telefoninumbrid, aadressid ja organisatsioonid.
     - **Unicode to ASCII: teisendab Unicode’i märke ASCII** märkideks. */u00B2* asemel on kasutusel *2*.
     - **Tühik**: eemaldab kõik tühikud. Tekstist *Hello   World* saab tekst *HelloWorld*.

   - **Täpsus**: saate määrata selle tingimuse jaoks rakendatava täpsustaseme.
     - **Põhiline**: valige madala (30%), *keskmise* (60%)*,* kõrge (80%) ja *täpse (100%)* *vahel*. Valige **Täpne**, et vastendada ainult 100 protsendile vastavaid kirjeid.
     - **Kohandatud**: saate määrata protsendi, millele kirjed peavad vastama. Süsteem vastendab ainult seda läve ületavad kirjed.

   - **Nimi**: reegli nimi.

1. Olemite vastendamiseks ainult siis, kui atribuudid vastavad mitmele tingimusele, valige **Lisa** > **tingimus,** et lisada vastereeglile rohkem tingimusi. Tingimused on ühendatud loogika tehtemärkiga AND ja käivitatakse seega ainult juhul, kui kõik tingimused on täidetud.

1. Soovi korral kaaluge täpsemaid valikuid, nagu [erandid](#add-exceptions-to-a-rule) või [kohandatud vastetingimused](#specify-custom-match-conditions).

1. Reegli lõpetamiseks valige **Valmis**.

1. Võite ka [rohkem reegleid lisada](#add-rules-to-a-match-pair).

1. Klõpsake valikut **Edasi**.

> [!div class="nextstepaction"]
> [Järgmine etapp: väljade ühendamine](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Reeglite lisamine vastepaarile

Vastendusreeglid esindavad tingimuste kogumeid. Olemite vastendamiseks mitmel atribuudil põhinevate tingimustega lisage veel reegleid.

1. Valige **Lisa reegel** olemi kohta, millele soovite reegleid lisada.

1. Järgige teema [Vastepaaride reeglite määratlemine](#define-rules-for-match-pairs) juhiseid.

> [!NOTE]
> Reeglite järjekorda on oluline. Sobitamisalgoritm proovib sobitada antud kliendikirjet teie esimese reegli alusel ja jätkab teise reegliga ainult siis, kui esimese reegliga ei tuvastatud ühtegi vastet.

## <a name="advanced-options"></a>Täpsemad suvandid

### <a name="add-exceptions-to-a-rule"></a>Reeglile erandite lisamine

Enamikul juhtudel viib olemi vastendamine konsolideeritud andmetega kordumatute kliendiprofiilideni. Harvaesinevate valepositiivsete ja valenegatiivsete juhtumite lahendamiseks määratlege vastereegli erandid. Erandid rakendatakse pärast vastendamisreeglite töötlemist ja välditakse kõigi erandikriteeriumidele vastavate kirjete vastendamist.

Näiteks kui teie vaste reegel ühendab perekonnanimi, linna ja sünnikuupäeva, tuvastab süsteem sama perekonnanimi kaksikud, kes elavad sama profiiliga samas linnas. Saate määrata profiilidele mittevastava erandi, kui ühendatavate olemite eesnimi pole samad.

1. **Valige paanil Reegli** redigeerimine käsk **Lisa** > **erand**.

1. Määrake erandi kriteeriumid.

1. Reegli salvestamiseks valige **Valmis**.

### <a name="specify-custom-match-conditions"></a>Kohandatud vastetingimuste määramine

Määrake tingimused, mis alistavad vaste vaikeloogika. Saadaval on neli võimalust:

|Variant  |Kirjeldus |Näide  |
|---------|---------|---------|
|Ühtib alati     | – saate määratleda alati vastendatud primaarvõtmete väärtused.         |  Sobitage primaarvõtmega 12345 *rida alati primaarvõtmega* *54321 reaga*.       |
|Ei ühti kunagi     | – saate määratleda primaarvõtmete väärtused, mis kunagi ei ühti.        | Ärge kunagi sobitage primaarvõtmega 12345 *rida primaarvõtmega* *54321* reaga.        |
|Möödu            | Määratleb väärtused, mida süsteem peaks vastefaasis alati ignoreerima. |  Ignoreerige vaste ajal väärtusi *11111* ja *Tundmatu.*        |
|Pseudonüümi vastendus    | Väärtuste määratlemine, mida süsteem peaks pidama samaks väärtuseks.         | Arvake, *et Joe* on Josephiga *võrdne*.        |

1. Valige **Kohandatud**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Nupp Kohandatud":::

1. Valige kohandatud **tüüp ja valige** Laadi mall **alla**. Nimetage mall ümber tühikuid kasutamata. Kasutage iga vaste valiku jaoks eraldi malli.

1. Avage allalaaditud mallifail ja sisestage üksikasjad. Mall sisaldab välju, et täpsustada kohandatud vastendamise olemit ja olemi primaarvõtme väärtusi. Olemite nimed on tõstutundlikud. Näiteks kui soovite, et esmane võti *12345* olemist *Müük* vastaks alati esmasele võtmele *34567* olemist *Kontakt*, täitke järgmine mall.
   - Entity1: Sales
   - Entity1Key: 12345
   - Entity2: Contact
   - Entity2Key: 34567

   Sama malli fail suudab määratleda mitme olemi kohandatud vastendamiskirjeid.

   > [!NOTE]
   > Kui soovite olemi pöördduplitseerimise määrata kohandatud sobitamisega, sisestage Entity1 ja Entity2 sama olem ja määrake erinevad primaarvõtmed. Kohandatud vastendamise kasutamiseks peate olemile määratlema vähemalt ühe duplikaadieemaldusreegli.

1. Pärast kõigi alistamiste lisamist salvestage mallifail.

1. Minge jaotisse **Andmed** > **Andmeallikad** ja valmendage mallifailid uute olemitena.

1. Pärast failide üleslaadimist valige **uuesti suvand Kohandatud**. Valige rippmenüüst vajalikud olemid ja valige **Valmis**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Dialoogi kuvatõmmis, mis näitab, kuidas valida kohandatud vastendusstsenaariumi alistamised.":::

1. Kohandatud vaste rakendamine sõltub vastesuvandist, mida soovite kasutada.

   - Funktsiooni Alati **vaste** või **Mitte kunagi sobitamiseks** jätkake järgmise juhisega.
   - Möödaviigu **või** pseudonüümi vastendamiseks **valige** Redigeeri **olemasoleval vastereeglil või** loo uus reegel. Valige **ripploendis Normaliseerimised suvand Kohandatud ümbersõit** või **Pseudonüümi vastendamine** ja valige **Valmis**.

1. Kohandatud vaste konfiguratsiooni rakendamiseks valige paanil **Kohandatud** **suvand Valmis**.

   Igal allaneelatud mallifailil on oma andmeallikas. Kui avastatakse kirjeid, mis vajavad spetsiaalset sobitamist, värskendage sobivat andmeallikas. Värskendust kasutatakse järgmise ühendamisprotsessi ajal. Näiteks tuvastate peaaegu sama nimega kaksikud, kes elavad samal aadressil, mis oli liidetud üheks inimeseks. Värskendage andmeallikas, et tuvastada kaksikud eraldi unikaalsete kirjetena.

> [!div class="nextstepaction"]
> [Järgmine etapp: väljade ühendamine](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
