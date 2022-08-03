---
title: Vastendamistingimused andmete ühendamiseks
description: Viige olemid vastavusse, et luua koondatud kliendiprofiile.
recommendations: false
ms.date: 05/05/2022
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
ms.openlocfilehash: e3e4e37d5b4c9caf2520a789d5f78ef33b491793
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139693"
---
# <a name="match-conditions-for-data-unification"></a>Vastendamistingimused andmete ühendamiseks

See ühendamise etapp määratleb vastejärjekorra ja olemiülese vastendamise reeglid. See etapp nõuab vähemalt kahte olemit.

> [!NOTE]
> Kui olete vastendustingimused loonud ja valite suvandi **Edasi**, ei saa te valitud olemit või atribuuti eemaldada. Vajadusel valige **Tagasi**, et vaadata valitud olemid ja atribuudid enne jätkamist üle.

## <a name="include-enriched-entities-preview"></a>Rikastatud olemite kaasamine (eelvaade)

Kui rikastasite olemeid andmeallikas tasemel, et aidata ühendamise tulemusi parandada, valige need. Lisateavet leiate teemast [Andmeallikate rikastamine](data-sources-enrichment.md). Kui valisite rikastatud olemid **lehel Kirjete** dubleerimine, ei pea te neid uuesti valima.

1. **Valige lehel Vastavusse viimise tingimused** lehe ülaosas suvand **Kasuta rikastatud olemeid**.

1. **Valige paanilt Rikastatud olemite** kasutamine üks või mitu rikastatud olemit.

1. Valige nupp **Valmis**.

## <a name="specify-the-match-order"></a>Vastendamisjärjestuse määramine

Iga vaste ühendab kaks või enam olemit üheks, konsolideeritud olemiks. Samal ajal säilitab see kordumatud kliendikirjed. Vastete järjekord näitab järjekorda, milles süsteem üritab kirjeid sobitada.

> [!IMPORTANT]
> Loendi esimest olemit nimetatakse esmaseks olemiks. Esmane olem on teie ühtse profiiliandmestiku aluseks. Sellele olemile lisatakse täiendavad valitud olemid.
>
> Olulised kaalutlused:
>
> - Valige peamiseks olemiks olem, millel on teie klientide kohta kõige täielikumad ja usaldusväärsemad profiiliandmed.
> - Valige esmaseks olemiks olem, millel on mitu teiste olemitega ühist atribuuti (nt nimi, telefoninumber või meiliaadress).

1. **Kasutage lehel Tingimuste sobitamine** olemite teisaldamiseks soovitud järjestuses üles- ja allanooli või lohistage neid. Näiteks valige **esmaseks olemiks Contacts:eCommerce** ja **teiseks olemiks CustomerLoyalty:Loyalty**.

1. Kui soovite, et iga olemi kirje oleks kordumatu klient, olenemata sellest, kas vaste leitakse, valige **Kaasa kõik kirjed**. Kõik selle olemi kirjed, mis ei ühti ühegi teise olemi kirjega, kaasatakse ühtsesse profiili. Kirjeid, millel pole vastet, nimetatakse singletoniteks.
  
Esmane olem *Kontaktid:e-kaubandus* vastendatakse järgmise olemiga *CustomerLoyalty:Loyalty*. Esimesest vastendusetapist tulenev andmekogum vastendatakse järgmise olemiga, kui teil on rohkem kui kaks olemit.

:::image type="content" source="media/m3_match.png" alt-text="Olemite valitud vastendusjärjestuse kuvatõmmis." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Vastepaaride reeglite määratlemine

Vastendamisreeglid määratlevad loogika, mille alusel vastendatakse kindlat olemite paari. Reegel koosneb ühest või mitmest tingimusest.

Olemi nime kõrval olev hoiatus tähendab, et vastepaari jaoks pole vastereeglit määratletud.

1. Vastendusreeglite **määratlemiseks valige** olemipaari jaoks lisa reegel.

1. Konfigureerige reegli **tingimused paanil Reegli lisamine**.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Reegli lisamise paani kuvatõmmis.":::

   - **Valige Olem/väli (esimene rida):**: valige seotud olem ja atribuut, et määrata kirje atribuut, mis on tõenäoliselt kliendile ainuomane. Näiteks telefoninumber või meiliaadress. Vältige vastendamist tegevustüübi atribuutide järgi. Näiteks ei leia ostu ID tõenäoliselt teiste kirjetüüpide puhul vasteid.

   - **Valige Olem/väli (teine rida):**: valige atribuut, mis on seotud esimesel real määratud olemi atribuudiga.

   - **Normaliseeri**: valige valitud atribuutide puhul mõni järgmistest normaliseerimissuvanditest.
     - **Numbrid**: teisendab muud numbrisüsteemid (nt rooma numbrid) araabia numbriteks. *VIII* asemel on kasutusel *8*.
     - **Sümbolid**: eemaldab kõik sümbolid ja erimärgid. Tekstist *Head&Shoulder* saab tekst *HeadShoulder*.
     - **Tekst väiketähtedeks**: teisendab kõik märgid väiketähtedeks. Tekstist *ALL CAPS ja Title Case* saab *all caps ja title case*.
     - **Tüüp (telefon, nimi, aadress, organisatsioon):**: standardiseerib nimed, tiitlid, telefoninumbrid, aadressid ja organisatsioonid.
     - **Unicode ascii-ks**: teisendab unicode'i märke ASCII-märkideks. */u00B2* asemel on kasutusel *2*.
     - **Tühik**: eemaldab kõik tühikud. Tekstist *Hello   World* saab tekst *HelloWorld*.

   - **Täpsus**: saate määrata selle tingimuse jaoks rakendatava täpsustaseme.
     - **Põhiline**: valige *madala (30%)*, *keskmise (60%)*, *kõrge (80%)* ja *täpse (100%) vahel*. Valige **Täpne**, et vastendada ainult kirjeid, mis vastavad 100 protsendile.
     - **Kohandatud**: saate määrata protsendi, millele kirjed peavad vastama. Süsteem vastendab ainult seda läve ületavad kirjed.

   - **Nimi**: reegli nimi.

1. Olemite vastendamiseks ainult siis, kui atribuudid vastavad mitmele tingimusele, valige **Lisa** > **tingimus**, et lisada vastendusreeglile rohkem tingimusi. Tingimused on ühendatud loogika tehtemärkiga AND ja käivitatakse seega ainult juhul, kui kõik tingimused on täidetud.

1. Soovi korral kaaluge täpsemaid suvandeid, nagu [erandid](#add-exceptions-to-a-rule) või [kohandatud vaste tingimused](#specify-custom-match-conditions).

1. Reegli lõpuleviimiseks valige **Valmis**.

1. Võite ka [rohkem reegleid lisada](#add-rules-to-a-match-pair).

1. Klõpsake valikut **Edasi**.

> [!div class="nextstepaction"]
> [Järgmine samm: Väljade ühendamine](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Reeglite lisamine vastepaarile

Vastendusreeglid esindavad tingimuste kogumeid. Olemite vastendamiseks tingimustega, mis põhinevad mitmel atribuudil, lisage veel reegleid.

1. Valige **olemi puhul, millele soovite reegleid lisada, käsk Lisa reegel**.

1. Järgige teema [Vastepaaride reeglite määratlemine](#define-rules-for-match-pairs) juhiseid.

> [!NOTE]
> Reeglite järjekorda on oluline. Sobitamisalgoritm proovib sobitada antud kliendikirjet teie esimese reegli alusel ja jätkab teise reegliga ainult siis, kui esimese reegliga vasteid ei tuvastatud.

## <a name="advanced-options"></a>Täpsemad suvandid

### <a name="add-exceptions-to-a-rule"></a>Reeglile erandite lisamine

Enamikul juhtudel viib olemi vaste kordumatute kliendiprofiilideni konsolideeritud andmetega. Harvaesinevate valepositiivsete ja valenegatiivsete juhtumite dünaamiliseks käsitlemiseks saate vastereegli jaoks määratleda erandid. Erandid rakendatakse pärast vastereeglite töötlemist ja välditakse kõigi erandite kriteeriumidele vastavate kirjete sobitamist.

Näiteks kui teie mängureegel ühendab perekonnanimi, linna ja sünnikuupäeva, tuvastab süsteem sama perekonnanimi kaksikud, kes elavad sama profiiliga samas linnas. Saate määrata erandi, mis ei vasta profiilidele, kui ühendatavate olemite eesnimi pole samad.

1. **Valige reegli** redigeerimise paanil **Lisa** > **erand**.

1. Määrake erandi kriteeriumid.

1. Reegli salvestamiseks valige **Valmis**.

### <a name="specify-custom-match-conditions"></a>Kohandatud vastetingimuste määramine

Saate määrata tingimused, mis alistavad vaste vaikeloogika. Saadaval on neli võimalust:

|Variant  |Kirjeldus |Näide  |
|---------|---------|---------|
|Ühtib alati     | Määratleb väärtused, mis on alati vastendatud.         |  *Sobitage alati Mike* ja *MikeR*.       |
|Ei ühti kunagi     | Määratleb väärtused, mis kunagi ei ühti.        | Ärge kunagi sobitage *Johni* ja *Jonathaniga*.        |
|Kohandatud möödumine     | Määratleb väärtused, mida süsteem peaks vaste faasis alati ignoreerima. |  Ignoreerige vaste ajal väärtusi *11111* ja *Tundmatu*.        |
|Pseudonüümi vastendus    | Väärtuste määratlemine, mida süsteem peaks pidama samaks väärtuseks.         | Arvake *, et Joe* on Josephiga *võrdne*.        |

1. Valige **Kohandatud**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Kohandatud nupp":::

1. Valige **kohandatud tüüp** ja valige **Laadi mall** alla. Iga vastevaliku jaoks on vaja eraldi malli.

1. Avage allalaaditud mallifail ja sisestage üksikasjad. Mall sisaldab välju, et täpsustada kohandatud vastendamise olemit ja olemi primaarvõtme väärtusi. Näiteks kui soovite, et esmane võti *12345* olemist *Müük* vastaks alati esmasele võtmele *34567* olemist *Kontakt*, täitke järgmine mall.
    - Entity1: Sales
    - Entity1Key: 12345
    - Entity2: Contact
    - Entity2Key: 34567

   Sama malli fail suudab määratleda mitme olemi kohandatud vastendamiskirjeid.

   Kui soovite olemi pöördduplitseerimise määrata kohandatud sobitamisega, sisestage Entity1 ja Entity2 sama olem ja määrake erinevad primaarvõtmed.

1. Pärast kõigi alistamiste lisamist salvestage mallifail.

1. Minge jaotisse **Andmed** > **Andmeallikad** ja valmendage mallifailid uute olemitena.

1. Pärast failide üleslaadimist valige **uuesti suvand Kohandatud**. Valige rippmenüüst soovitud olemid ja valige **Valmis**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Dialoogi kuvatõmmis, mis näitab, kuidas valida kohandatud vastendusstsenaariumi alistamised.":::

1. Kohandatud vaste rakendamine sõltub vaste valikust, mida soovite kasutada.

   - Kui **soovite alati sobitada** või **mitte kunagi sobitada**, jätkake järgmise sammuga.
   - Väljal **Ümberminek** või **pseudonüümi vastendamine** valige **Redigeeri** olemasolevas vastereeglis või looge uus reegel. Valige ripploendist Normaliseerimised **suvand Kohandatud ümbersõit** või **Pseudonüümi vastendus** ja valige **Valmis**.

1. Kohandatud vaste **konfiguratsiooni rakendamiseks valige** Kohandatud **paanil Valmis**.

> [!div class="nextstepaction"]
> [Järgmine samm: Väljade ühendamine](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
