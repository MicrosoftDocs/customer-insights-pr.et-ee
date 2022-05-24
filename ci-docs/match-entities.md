---
title: Olemite vastavusseviimine andmete koondamiseks
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
ms.openlocfilehash: bc470dd932c2c981adc5840bb52d60f8dfe0de61
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740944"
---
# <a name="match-conditions"></a>Sobitamise tingimused

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

See ühendamise etapp määratleb vaste järjestuse ja reeglid olemiüleseks sobitamiseks. See samm nõuab vähemalt kahte olemit.

> [!NOTE]
> Kui olete loonud vastetingimused ja valinud **Edasi**, ei saa te valitud olemit või atribuuti eemaldada. Vajadusel valige **enne jätkamist valitud olemite ja atribuutide ülevaatamiseks tagasi**.

## <a name="include-enriched-entities-preview"></a>Kaasa rikastatud olemid (eelvaade)

Kui rikastasite olemeid andmeallikas tasemel, et aidata oma ühinemistulemusi parandada, valige need. Lisateavet leiate teemast [Andmeallikate rikastamine](data-sources-enrichment.md). Kui valisite lehel Duplikaatkirjed **rikastatud olemid**, ei pea te neid uuesti valima.

1. **Valige lehel Sobitamistingimused** lehe ülaosas suvand **Kasuta rikastatud olemeid**.

1. Valige paanil **Rikastatud olemite** kasutamine üks või mitu rikastatud olemit.

1. Valige nupp **Valmis**.

## <a name="specify-the-match-order"></a>Vastendamisjärjestuse määramine

Iga vaste ühendab kaks või enam olemit üheks, konsolideeritud olemiks. Samal ajal säilitab see kordumatud kliendikirjed. Vastejärjestus näitab, millises järjekorras süsteem püüab kirjetele vastata.

> [!IMPORTANT]
> Loendi esimest olemit nimetatakse esmaseks olemiks. Esmane olem on teie ühtse profiilide andmestiku aluseks. Sellele olemile lisatakse täiendavad valitud olemid.
>
> Olulised kaalutlused:
>
> - Valige esmase olemina olem, millel on kõige täielikumad ja usaldusväärsemad profiiliandmed oma klientide kohta.
> - Valige olem, millel on teiste olemitega (nt nimi, telefoninumber või meiliaadress) mitu ühist atribuuti (nt nimi, telefoninumber või meiliaadress).

1. **Kasutage lehel Kattuvad tingimused** üles- ja allanoolt, et teisaldada olemid soovitud järjestuses või lohistada neid. Näiteks valige **esmaseks olemiks Kontaktid:e-kaubandus** ja **teiseks olemiks kliendilojaalsus: lojaalsus**.

1. Kui soovite, et iga olemi kirje oleks kordumatu klient, olenemata sellest, kas vaste leitakse, valige **Kaasa kõik kirjed**. Kõik selle olemi kirjed, mis ei ühti ühegi teise olemi kirjega, kaasatakse ühtsesse profiili. Kirjeid, millel pole vastet, nimetatakse singletoniteks.
  
Esmane olem *Kontaktid:e-kaubandus* sobitatakse järgmise olemiga *Kliendilojaalsus:Lojaalsus*. Esimese vasteetapi tulemusel saadud andmestik sobitatakse järgmise olemiga, kui teil on rohkem kui kaks olemit.

:::image type="content" source="media/m3_match.png" alt-text="Kuvatõmmis olemite valitud vastetellimusest." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Vastepaaride reeglite määratlemine

Vastendamisreeglid määratlevad loogika, mille alusel vastendatakse kindlat olemite paari. Reegel koosneb ühest või mitmest tingimusest.

Olemi nime kõrval olev hoiatus tähendab, et vastepaari jaoks pole vastereeglit määratletud.

1. Vastereeglite määratlemiseks valige **Olemipaari jaoks lisareegel**.

1. **Konfigureerige reegli** lisamine paanil reegli tingimused.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Reegli lisamise paani kuvatõmmis.":::

   - **Valige olem/väli (esimene rida)**: valige seotud olem ja atribuut, et määrata kirjeatribuut, mis on tõenäoliselt kliendile ainuomane. Näiteks telefoninumber või meiliaadress. Vältige vastendamist tegevustüübi atribuutide järgi. Näiteks ei leia ostu ID tõenäoliselt teiste kirjetüüpide puhul vasteid.

   - **Valige olem/väli (teine rida)**: valige atribuut, mis on seotud esimeses reas määratud olemi atribuudiga.

   - **Normaliseeri**: valige valitud atribuutide puhul mõni järgmistest normaliseerimissuvanditest.
     - **Numbrid**: teisendab teised numbrisüsteemid, näiteks Rooma numbrid, araabia numbriteks. *VIII* asemel on kasutusel *8*.
     - **Sümbolid**: eemaldab kõik sümbolid ja erimärgid. Tekstist *Head&Shoulder* saab tekst *HeadShoulder*.
     - **Tekst väiketähtedeks**: teisendab kogu märgi väiketähtedeks. Tekstist *ALL CAPS ja Title Case* saab *all caps ja title case*.
     - **Tüüp (telefon, nimi, aadress, organisatsioon)**: standardiseerib nimed, pealkirjad, telefoninumbrid, aadressid ja organisatsioonid.
     - **Unicode väärtuseks ASCII**: teisendab unicode'i märke ASCII märkideks. */u00B2* asemel on kasutusel *2*.
     - **Tühimik**: eemaldab kõik tühikud. Tekstist *Hello   World* saab tekst *HelloWorld*.

   - **Täpsus**: saate määrata selle tingimuse jaoks rakendatava täpsustaseme.
     - **Põhiline**: valige *madal (30%),*, *keskmine (60%)*, *kõrge (80%)* ja *täpne (100%)*. Valige **Täpne**, et sobitada ainult kirjed, mis vastavad 100 protsendile.
     - **Kohandatud**: saate määrata protsendi, millele kirjed peavad vastama. Süsteem vastendab ainult seda läve ületavad kirjed.

   - **Nimi**: reegli nimi.

1. Olemite vastendamiseks ainult siis, kui atribuudid vastavad mitmele tingimusele, valige **Lisa** > **tingimus**, et lisada vastereeglile rohkem tingimusi. Tingimused on ühendatud loogika tehtemärkiga AND ja käivitatakse seega ainult juhul, kui kõik tingimused on täidetud.

1. Soovi korral kaaluge täpsemaid suvandeid, näiteks [erandeid](#add-exceptions-to-a-rule) või [kohandatud vastetingimusi](#specify-custom-match-conditions).

1. Reegli lõpuleviimiseks valige **Valmis**.

1. Võite ka [rohkem reegleid lisada](#add-rules-to-a-match-pair).

1. Klõpsake valikut **Edasi**.

> [!div class="nextstepaction"]
> [Järgmine samm: Väljade ühendamine](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Reeglite lisamine vastepaarile

Vastendusreeglid esindavad tingimuste kogumeid. Olemite sobitamiseks tingimustega, mis põhinevad mitmel atribuudil, lisage rohkem reegleid.

1. Valige **Lisa reegel** olemi kohta, millele soovite reegleid lisada.

1. Järgige teema [Vastepaaride reeglite määratlemine](#define-rules-for-match-pairs) juhiseid.

> [!NOTE]
> Reeglite järjekorda on oluline. Sobitamisalgoritm püüab teie esimese reegli alusel sobitada antud kliendikirjet ja jätkab teise reegliga ainult siis, kui esimese reegliga vasteid ei tuvastatud.

## <a name="advanced-options"></a>Täpsemad suvandid

### <a name="add-exceptions-to-a-rule"></a>Erandite lisamine reeglile

Enamikul juhtudel viib olemi sobitamine konsolideeritud andmetega unikaalsete kliendiprofiilideni. Harvaesinevate valepositiivsete ja valenegatiivsete juhtumite dünaamiliseks käsitlemiseks saate määratleda vastereegli erandid. Erandid rakendatakse pärast mängureeglite töötlemist ja välditakse kõigi erandikriteeriumidele vastavate kirjete sobitamist.

Näiteks kui teie mängureeglis on ühendatud perekonnanimi, linn ja sünniaeg, tuvastaks süsteem kaksikud, kellel on samad perekonnanimi kes elavad samas linnas sama profiiliga. Saate määrata erandi, mis ei vasta profiilidele, kui ühendatavate olemite eesnimi pole samad.

1. **Valige reegli** redigeerimise paanil **Lisa** > **erand**.

1. Määrake erandikriteeriumid.

1. Reegli salvestamiseks valige **Valmis**.

### <a name="specify-custom-match-conditions"></a>Kohandatud vastetingimuste määramine

Saate määrata tingimused, mis alistavad vaikimisi vasteloogika. Saadaval on neli võimalust:

|Variant  |Kirjeldus |Näide  |
|---------|---------|---------|
|Ühtib alati     | Määratleb väärtused, mis on alati sobitatud.         |  Sobib alati Mike'i *ja* *MikeR-iga*.       |
|Ei ühti kunagi     | Määratleb väärtused, mis kunagi ei ühti.        | Ära kunagi sobi *Johni* ja *Jonathaniga*.        |
|Kohandatud möödumine     | Määratleb väärtused, mida süsteem peaks vastefaasis alati ignoreerima. |  Ignoreerige vaste ajal väärtusi *11111* ja *Teadmata*.        |
|Pseudonüümi vastendus    | Väärtuste määratlemine, mida süsteem peaks pidama samaks väärtuseks.         | Mõtle *, et Joe* on Josephiga *võrdne*.        |

1. Valige **Kohandatud**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Nupp Kohandatud":::

1. **Valige kohandatud tüüp** ja valige **Laadi mall Alla**. Iga vastesuvandi jaoks on vaja eraldi malli.

1. Avage allalaaditud mallifail ja täitke üksikasjad. Mall sisaldab välju, et täpsustada kohandatud vastendamise olemit ja olemi primaarvõtme väärtusi. Näiteks kui soovite, et esmane võti *12345* olemist *Müük* vastaks alati esmasele võtmele *34567* olemist *Kontakt*, täitke järgmine mall.
    - Entity1: Sales
    - Entity1Key: 12345
    - Entity2: Contact
    - Entity2Key: 34567

   Sama malli fail suudab määratleda mitme olemi kohandatud vastendamiskirjeid.

   Kui soovite olemi pöördduplitseerimise määrata kohandatud sobitamisega, sisestage Entity1 ja Entity2 sama olem ja määrake erinevad primaarvõtmed.

1. Pärast kõigi alistamiste lisamist salvestage mallifail.

1. Minge jaotisse **Andmed** > **Andmeallikad** ja valmendage mallifailid uute olemitena.

1. Pärast failide üleslaadimist valige **uuesti suvand Kohandatud**. Valige rippmenüüst nõutavad olemid ja valige **Valmis**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Dialoogi kuvatõmmis, mis näitab, kuidas valida kohandatud vastendusstsenaariumi alistamised.":::

1. Kohandatud vaste rakendamine sõltub vaste valikust, mida soovite kasutada.

   - Sest **alati sobitada** või **mitte kunagi sobitada**, jätkake järgmise sammuga.
   - Valige **ümbersõidu**- või **pseudonüümivaste vastendamiseks** **redigeeri** olemasolevas vastereeglis või looge uus reegel. Valige ripploendis **Normaliseerimised suvand Kohandatud ümbersõidu** või **Pseudonüümi vastendus** ja valige **Valmis**.

1. Kohandatud vastekonfiguratsiooni rakendamiseks valige **kohandatud** paanil **Valmis**.

> [!div class="nextstepaction"]
> [Järgmine samm: Väljade ühendamine](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
