---
title: Olemid ja andmekomplektid
description: Saate vaadata andmeid olemite lehel.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 1e1abdf49a3c1fe6f9fdd2cf5353a7723454f47b
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355293"
---
# <a name="entities-in-audience-insights"></a>Olemid sihtrühmaülevaadetes

Pärast [andmeallikate konfigureerimist](data-sources.md)minge lehele **Olemid**, et hinnata sisestatud andmete kvaliteeti. Olemeid käsitletakse andmekogumitena. Nende olemite põhjal on loodud mitu Dynamics 365 Customer Insightsi funktsiooni. Nende lähedasem läbivaatamine aitab teil nende võimaluste väljundit valideerida.

Lehel **Olemid** loetletakse olemid ja need veerud.

- **Nimi**: andmeolemi nimi. Kui olemi nime kõrval kuvatakse hoiatuse sümbol, tähendab see, et selle olemi andmeid ei laaditud edukalt.
- **Allikas**: olemi neelanud andmeallikas tüüp.
- **Värskendatud**: olemi viimase värskendamise aeg.
- **Olek**: olemi viimase värskenduse üksikasjad.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Avasta kindlat andmeüksust

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Olemid**.
1. **Valige lehel Olemid** üksus üksikasjade lehe avamiseks.  
1. Tutvuge selle olemi erinevate väljade ja kirjetega.

- Vahekaart **Atribuudid** on vaikimisi valitud ja kuvab tabeli et vaadata üle valitud olemi üksikasjad nagu välja nimed, andmetüübid ja tüübid. Veerus **Tüüp** kuvatakse ühise andmemudeli seostatavad tüübid, mis on süsteemi poolt automaatselt tuvastatud või mille on kasutajad [käsitsi vastendanud](map-entities.md). Need tüübid on semantilised tüübid, mis võivad atribuutide andmetüüpidest erineda. Oletagem näiteks, et allpool oleval väljal *Meil* on andmetüüp *Tekst*, kuid selle (semantilise) Common Data Modeli tüüp võib *Meil* või *Meiliaadress*.

> [!div class="mx-imgBorder"]
> ![Väljade tabel.](media/data-manager-entities-fields.PNG "Väljade tabel")

> [!NOTE]
> Sellel lehel kuvatakse ainult teie olemi andmete näidis. Täieliku andmekogumi vaatamiseks **minge lehele Andmeallikad**, valige olem, valige **Redigeeri** ja seejärel vaadake selle olemi andmeid koos redaktoriga Power Query, nagu on selgitatud [andmeallikates](data-sources.md).

Kui soovite lisateavet olemisse sisestatud andmete kohta, on **Kokkuvõtte** veerus toodud teie jaoks olulised kohaldatavad andmed, nt nullid, puuduvad väärtused, kordumatud väärtused, arvud ja jaotused. Andmete kokkuvõtte kuvamiseks valige diagrammi ikoon.

> [!div class="mx-imgBorder"]
> ![Kokkuvõtte sümbol.](media/data-manager-entities-summary.png "Andmete kokkuvõtte tabel")

- Vahekaardil **Andmed** kuvatakse olemin üksikkirjete tabeli analüüsimise üksikasjad. Loetletud üksikasjad sõltuvad olemi andmetüübist.

> [!div class="mx-imgBorder"]
> ![Valige olem.](media/data-manager-entities-data.png "Olemi valimine")

- Vahekaart **Aruanded** (saadaval mõne olemi puhul) võimaldab teil oma andmeid visualiseerida aruande loomise teel ja sisaldab 2004.

  - **Aruande nimi**: aruande nimi.
  - **Loodud**: Olemi loonud isiku nimi.
  - **Loodud**: olemi loomise kuupäev ja kellaaeg.
  - **Redigeerinud**: Olemit muutnud isiku nimi.
  - **Redigeeritud**: olemi muutmise kuupäev ja kellaaeg. 

## <a name="entity-specific-information"></a>Olemipõhine teave

Järgmine jaotis sisaldab teavet mõne süsteemi loodud olemi kohta.

### <a name="corrupted-data-sources"></a>Andmeallikas on rikutud

sisse võetud andmeallikast pärinevad väljad võivad sisaldada rikutud andmeid. Rikutud väljadega kirjed kuvatakse süsteemi loodud olemitel. Teades rikutud kirjete kohta, saate tuvastada, milliseid andmeid lähtesüsteemis läbi vaadata ja värskendada. Pärast järgmise andmeallikas värskendamist antakse parandatud kirjed customer Insights'ile üle ja edastatakse järgmistele protsessidele. 

Näiteks veeru "sünnipäev" andmetüübiks on seatud "kuupäev". Kliendikirjel on sisestatud sünnipäev "01/01/19777". Süsteem märgib selle kirje rikutuks. Keegi saab nüüd muuta lähtesüsteemis sünnipäeva "1977". Pärast andmeallikate automaatset värskendamist on väljal nüüd kehtiv vorming ja kirje eemaldatakse rikutud olemist. 

Minge **Andme** > **Üksused** jaotisse ja otsige rikutud olemeid jaotises **Süsteem** . Rikutud olemite skeemi nimetamine: "DataSourceName_EntityName_corrupt". Valige rikutud olem, et tuvastada kõik rikutud väljad ja põhjus üksikul kirjetasemel.
> [!div class="mx-imgBorder"]
> ![Korruptsiooni põhjus.](media/corruption-reason.png "Korruptsiooni põhjus")

Customer Insights töötleb endiselt rikutud kirjeid. Kuid need võivad põhjustada probleeme ühendatud andmetega töötamisel.

Vigaste kirjete näitamiseks käitatakse ülevaatatud andmete puhul järgmised kontrollid: 

- Välja väärtus ei ühti selle veeru andmetüübiga.
- Väljad sisaldavad märke, mille puhul veerud ei vasta eeldatud skeemile. Näiteks: valesti vormindatud hinnapakkumised, sisestamata hinnapakkumised või uued tekstimärgid.
- Kui veerge on kuupäeva-/kuupäeva-/kuupäeva-kellaajaoffset, tuleb nende vorming mudelis määrata, kui see ei järgi iso standardvormingut.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
