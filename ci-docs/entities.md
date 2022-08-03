---
title: Rakenduse Customer Insights olemid
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
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183540"
---
# <a name="entities-in-customer-insights"></a>Rakenduse Customer Insights olemid

Pärast [andmeallikate konfigureerimist](data-sources.md)minge lehele **Olemid**, et hinnata sisestatud andmete kvaliteeti. Olemeid käsitletakse andmekogumitena. Nende olemite põhjal on loodud mitu Dynamics 365 Customer Insightsi funktsiooni. Nende lähedasem läbivaatamine aitab teil nende võimaluste väljundit valideerida.

Kui töötate Customer Insightsis, rikastades oma andmeid või luues segmente, mõõtühikuid ja tegevusi, kuvatakse **nendest toimingutest loodud olemid lehel Olemid**.

## <a name="view-a-list-of-entities"></a>Olemite loendi kuvamine

Olemite **loendi kuvamiseks avage** > **Andmeüksused**. Iga olemi kohta kuvatakse järgmine teave.

- **Nimi**: andmeüksuse nimi. Kui olemi nime kõrval kuvatakse hoiatuse sümbol, tähendab see, et selle olemi andmeid ei laaditud edukalt.
- **Allikas**: olemi allaneelanud andmeallikas tüüp.
- **Värskendatud** aeg: olemi viimase värskendamise aeg.
- **Olek**: üksikasjad olemi viimase värskenduse kohta.

## <a name="explore-a-specific-entitys-data"></a>Avasta kindlat andmeüksust

1. Avage **Jaotis Andmeüksused** > **·**.
1. Üksikasjade lehe avamiseks valige olem.  
1. Uurige selle olemi erinevaid välju ja kirjeid.

- Vahekaart **Atribuudid** on vaikimisi valitud ja kuvab valitud olemi üksikasjad, nagu väljanimed, andmetüübid ja tüübid. Veerus **Tüüp** kuvatakse ühise andmemudeli seostatavad tüübid, mis on süsteemi poolt automaatselt tuvastatud või mille on kasutajad [käsitsi vastendanud](map-entities.md). Need tüübid on semantilised tüübid, mis võivad atribuutide andmetüüpidest erineda. Näiteks alloleval väljal *Meil* on andmetüüp *String*, kuid selle (semantiline) tüüp Common Data Model võib olla *Email*, *EmailAddress* või *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Väljade tabel.":::

   > [!NOTE]
   > Sellel lehel kuvatakse ainult teie olemi andmete näidis. Täieliku andmekogumi vaatamiseks minge **lehele Andmeallikad**, valige olem, valige **Redigeeri** ja seejärel vaadake selle olemi andmeid Power Query redaktoriga, nagu on selgitatud jaotises [Andmeallikad](data-sources.md).

   Olemis **allaneelatud andmete kohta lisateabe saamiseks leiate veerust Kokkuvõte** mõned olulised andmeomadused, nagu nullid, puuduvad väärtused, kordumatud väärtused, loendused ja jaotused, olenemata sellest, mis teie andmetele rakendub. Andmete kokkuvõtte kuvamiseks valige diagrammi ikoon.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Andmete kokkuvõtlik tabel.":::

- Vahekaardil **Andmed** kuvatakse üksikasjad olemi üksikute kirjete kohta. Loetletud üksikasjad sõltuvad olemi andmetüübist.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Valige olem.":::

- Vahekaart **Aruanded** (saadaval mõne olemi jaoks) võimaldab teil oma andmeid visualiseerida, luues aruande, mis sisaldab järgmisi veerge.

  - **Aruande nimi**: aruande nimi.
  - **Loodud**: olemi loonud isiku nimi.
  - **Loodud**: olemi loomise kuupäev ja kellaaeg.
  - **Toimetanud**: Olemit muutnud isiku nimi.
  - **Redigeeritud**: olemi muutmise kuupäev ja kellaaeg.

## <a name="entity-specific-information"></a>Olemipõhine teave

Järgmine jaotis sisaldab teavet mõne süsteemi loodud olemi kohta.

### <a name="corrupted-data-sources"></a>Andmeallikas on rikutud

sisse võetud andmeallikast pärinevad väljad võivad sisaldada rikutud andmeid. Rikutud väljadega kirjed kuvatakse süsteemi loodud olemitel. Teades rikutud kirjete kohta, saate tuvastada, milliseid andmeid lähtesüsteemis läbi vaadata ja värskendada. Pärast järgmise andmeallikas värskendamist antakse parandatud kirjed customer Insights'ile üle ja edastatakse järgmistele protsessidele. 

Näiteks veeru "sünnipäev" andmetüübiks on seatud "kuupäev". Kliendikirjel on sisestatud sünnipäev "01/01/19777". Süsteem märgib selle kirje rikutuks. Keegi saab nüüd muuta lähtesüsteemis sünnipäeva "1977". Pärast andmeallikate automaatset värskendamist on väljal nüüd kehtiv vorming ja kirje eemaldatakse rikutud olemist.

Minge **Andme** > **Üksused** jaotisse ja otsige rikutud olemeid jaotises **Süsteem** . Rikutud olemite skeemi nimetamine: "DataSourceName_EntityName_corrupt". Valige rikutud olem, et tuvastada rikutud väljad ja põhjus individuaalse kirje tasemel.

   :::image type="content" source="media/corruption-reason.png" alt-text="Korruptsiooni põhjus.":::

Customer Insights töötleb endiselt rikutud kirjeid. Kuid need võivad põhjustada probleeme ühendatud andmetega töötamisel.

Vigaste kirjete näitamiseks käitatakse ülevaatatud andmete puhul järgmised kontrollid:

- Välja väärtus ei ühti selle veeru andmetüübiga.
- Väljad sisaldavad märke, mille puhul veerud ei vasta eeldatud skeemile. Näiteks: valesti vormindatud hinnapakkumised, sisestamata hinnapakkumised või uued tekstimärgid.
- Kui on olemas datetime/date/dateoffset veerud, tuleb nende vorming mudelis täpsustada, kui see ei järgi standardset ISO-vormingut.

[!INCLUDE [footer-include](includes/footer-banner.md)]
