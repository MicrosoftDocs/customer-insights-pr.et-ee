---
title: Mõõdikute loomine ja haldamine
description: Määratleda ettevõtte äritegevuse analüüsimiseks ja kajastamiseks vajalikud näitajad.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9a94a32a04f2a8beb661c27271fe96f23d998722
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887935"
---
# <a name="define-and-manage-measures"></a>Meetmete määratlemine ja haldamine

See aitab teil paremini mõista kliendi käitumist ja äritegevust. Nad vaatavad asjakohaseid [ühendatud profilide](data-unification.md) väärtusi. Näiteks soovib ettevõte näha *kogukulu kliendile*, et mõista üksikkliendi ostuajalugu või mõõta *ettevõtte kogumüüki*, et saada aru kogu ettevõtte müügituludest.  

Näitajad luuakse meetmete ehitaja abil, mis on erinevate tehtemärkide ja lihtsate vastendussuvanditega andmepäringu platvorm. See võimaldab filtreerida andmeid, rühmitada tulemusi, tuvastada [olemite seoseteid](relationships.md) ja kuvada väljundi eelvaadet.

Kasutage äritegevuste plaanimiseks näitaja ehitajat, pärides kliendiandmeid ja väljastades ülevaateid. Näiteks *kogukulu ühe kliendi kohta* ja *kogutulu ühe kliendi kohta* loomine aitab tuvastada suure kulutamise, kuid suure tootlusega klientide rühm. Saate [luua segmendi](segments.md), mis aitab teil teha järgmist. 

## <a name="build-your-own-measure-from-scratch"></a>Isikliku voo loomine puhtalt lehelt

Selles jaotises tutvustatakse uue näitaja loomist nullist. Saate ehitada näitaja andmeatribuutidega andmeüksustelt, millel on kliendi olemiga ühenduse loomiseks suhe loodud. 

1. Avage sihtrühmaülevaadetes jaotis **Näitajad**.

1. Valige **Uus** ja valige **Looge ise**.

1. Valige **Redigeeri nimi** ja sisestage näitaja **Nimi**. 
   > [!NOTE]
   > Kui teie uuel näitaja konfiguratsioonil on ainult kaks välja– näiteks CustomerID ja üks arvutus, lisatakse väljund uue veeruna süsteemi genereeritud olemile nimega Customer_Measure. Näete näitaja väärtust ühtses kliendiprofiilis. Muud näitajad loovad oma olemeid.

1. Valige konfiguratsioonialas koondamisfunktsioon ripploendist **Vali funktsioon**. Koondamisfunktsioonid on järgmised. 
   - **Sum**
   - **Keskmine**
   - **Loenda**
   - **Kordumatu arv**
   - **Maks.**
   - **Min**
   - **Esimene**: võtab andmekirje esimese väärtuse
   - **Viimane**: võtab andmekirjesse lisatud viimase väärtuse

   :::image type="content" source="media/measure-operators.png" alt-text="Tehtemärgid näitaja arvutamiseks.":::

1. Valige **Lisa atribuut**, et valida andmed, mida selle näitaja loomiseks vajate.
   
   1. Valige vaheleht **Attribuudid**. 
   1. Andmeolem: valige olem, mis sisaldab mõõdetavat atribuuti. 
   1. Andmeatribuut: valige atribuut, mida soovite näitaja arvutamiseks koondamisfunktsioonis kasutada. Korraga saate valida ainult ühe atribuudi.
   1. Olemasolevast näitajast andmeatribuudi valimiseks klõpsake vahekaarti **Näitajad** või otsige olemi või näitaja nime. 
   1. Valige **Lisa**, et lisada atribuut näitajale.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Valige arvutuses soovitud atribuut.":::

1. Keerukamate näitajate loomiseks võite lisada mõõtmisfunktsioonile rohkem atribuute või kasutada matemaatilisi tehtemärke.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Keerukama näitaja loomine tehtemärkidega.":::

1. Filtrite lisamiseks valige konfiguratsiooniala **Filtreeri**. 
  
   1. Valige paani **Filtrid** jaotisest **Lisa atribuut** atribuut, mida soovite filtrite loomiseks kasutada.
   1. Määrake filtritehted iga valitud atribuudi filtri määratlemiseks.
   1. Valige **Rakenda**, et lisada filtrid näitajale.

1. Dimensioonide lisamiseks valige konfiguratsioonialas **Dimensioon**. Dimensioonid kuvatakse näitaja väljundolemis veergudena.
   1. Valige **Redigeeri dimensioonid**, et lisada andmeatribuute, mille järgi soovite näitaja väärtusi rühmitada. Näiteks linn või sugu. *Klienditaseme näitajate loomiseks* valitakse vaikimisi *CustomerID* dimensioon. Kui soovite luua *äritaseme näitajaid*, saate vaikeeelise eemaldada.
   1. Valige **Valmis**, et lisada dimensioonid näitajale.

1. Kui teie andmetes on väärtusi, mida peate täisarvuga asendama , nt pange *null* asemel *0*, valige **Reeglid**. Konfigureerige reegel ja veenduge, et valite asendusena ainult täisnumbrid.

1. Kui vastendatud andme- ja olemi *Klient* vahel on mitu teed, peate valima ühe tuvastatud [olemi suhte teedest](relationships.md). Näitaja tulemused võivad sõltuvalt valitud teest erineda. 
   1. Valige **andmeelistused** ja seejärel olemi tee, mida tuleks oma näitaja tuvastamiseks kasutada. Kui olemi *Klient* juurde on ainult üks tee, siis seda juhtelementi ei näidata.
   1. Valiku rakendamiseks valige suvand **Valmis**. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Saate valida näitajale olemi tee.":::

1. Kui soovite näitajat veel arvutada, valige **Uus arvutus**. Uute arvutuste jaoks saate kasutada ainult samal olemiteel olevaid üksusi. Täiendavad arvutused kuvatakse näitaja väljundolemis uute veergudena.

1. Valige näitajast arvutuse **Duplitseerimiseks**, **Ümber nimetamiseks** või **Eemaldamiseks** **...**.

1. **Eelvaatealal** näete näitaja väljundolemi andmeskeemi (sh filtreid ja dimensioone). Eelvaade reageerib dünaamiliselt konfiguratsiooni muudatustele.

1. Konfigureeritud näitaja tulemuste arvutamiseks valige **Käivita**. Kui soovite praeguse konfiguratsiooni säilitada ja näitajat hiljem käitada, valige **Salvesta ja sule**.

1. Vastloodud näitaja nägemiseks loendis, valige **Näitajad**.

## <a name="use-a-template-to-build-a-measure"></a>Malli abil mõõdu loomine

Nende loomiseks võite kasutada tavaliselt kasutatavate meetmete ettemääratud malle. Mallide üksikasjalik kirjeldus ja juhendatud kogemused aitavad teil luua tõhusa mõõtmissüsteemi. Mallid põhinevad olemi *Ühendatud tegevus* kaardistatud andmetele. Seega veenduge, et olete konfigureerinud [klienditegevused](activities.md) enne malli põhjal mõõtühiku loomist.

Saadaval mõõdumallid: 
- Keskmine tehingu väärtus (ATV)
- Tehingu väärtus kokku
- Päeva keskmine tulu
- Aasta keskmine tulu
- Kannete arv
- Teenitud püsikliendipunktid
- Lunastatud püsikliendipunktid
- Püsikliendipunktide saldo
- Aktiivse kliendi eluiga
- Püsikliendi liikmestaatuse kestus
- Aega viimasest ostust

Järgmine protseduur kirjeldab etappe uue meetme loomiseks malli abil.

1. Avage sihtrühmaülevaadetes jaotis **Näitajad**.

1. Valige **Uus** ja seejärel **Vali mall**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Rippmenüü ekraanipilt, kui luuakse mallil esiletõstetud uus mõõt.":::

1. Leidke teie vajadusele sobiv mall ja valige **Valige mall**.

1. Vaadake nõutavad andmed läbi ja valige **Alustamine**, kui kõik andmed on olemas.

1. Määrake **Nime muutmine** paanil oma mõõtühiku ja väljundi olemi nimi. 

1. Valige nupp **Valmis**.

1. Määrake **Sea ajaperiood** jaotises ajavahemikud andmete kasutamiseks. Valige, kas soovite, et uus mõõt hõlmaks kogu andmekogumit, valides suvandi **Kogu aeg**. Või kui soovite, et mõõtühiku valikuks oleks **Kindel ajaperiood**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Kuvatõmmis ajavahemiku jaotisest, kui konfigureerite malli põhjal mõõtmise.":::

1. Järgmises jaotises valige **Lisa andmed**, et valida tegevused ja kaardistada oma olemi *Ühendatud tegevus* vastavad andmed.

    1. 1. etapp: valige jaotises **Tegevuse tüüp** selle olemi tüüp, mida soovite kasutada. Valige **Tegevused** jaoks olemid, mida soovite kaardistada.
    1. 2. etapp: valige atribuut olemist *Ühendatud Tegevus* valemiga nõutava komponendi jaoks. Näiteks keskmise tehingu väärtuse puhul on see atribuut, mis tähistab tehingu väärtust. Valige **Tegevuse ajatempli** jaoks atribuut olemist Ühendatud tegevus, mis tähistab tegevuse kuupäeva ja kellaaega.
   
1. Kui andmete kaardistamine õnnestub, näete olekut **Lõpule viidud** ning kaardistatud tegevuste ja atribuutide nime.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Lõpuleviidud mõõtühikumalli konfiguratsiooni kuvatõmmis.":::

1. Nüüd saate valida suvandi **Käita**, et arvutada mõõtmise tulemused. Hiljem viimistlemiseks valige **Salvesta mustand**.

## <a name="manage-your-measures"></a>Meetmete haldamine

Meetmete loendi leiate lehelt **Meetmed**.

Leiate teavet näidiku tüübi, autori, loomise kuupäeva, staatuse ja oleku kohta. Kui valite loendist näitaja, saate väljundit eelvaadata ja .CSV-faili alla laadida.

Kõigi oma meetmete korraga värskendamiseks valige **Värskenda kõik** ilma kindlat meedet valimata.

> [!div class="mx-imgBorder"]
> ![Toimingud üksikute meetmete haldamiseks](media/measure-actions.png "Toimingud üksikute meetmete haldamiseks")

Valige loendist soovitud näitaja järgmiste suvandite jaoks.

- Valige meetme nimi, et näha selle üksikasju.
- Meetme konfiguratsiooni **Redigeerimine**.
- **Värskendage** näitajat, võttes aluseks värskeimad andmed.
- Meetme **Ümbernimetamine**.
- Meetme **Kustutamine**.
- **Aktiveeri** või **Inaktiveeri**. Passiivseid näitajad ei värskendata [kavandatud värskenduse](system.md#schedule-tab) ajal.

> [!TIP]
> Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types). Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies). Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku. Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.

## <a name="next-step"></a>Järgmine etapp

[Kliendisegmendi loomiseks](segments.md) saate kasutada olemasolevaid näitajaid.


[!INCLUDE[footer-include](../includes/footer-banner.md)]