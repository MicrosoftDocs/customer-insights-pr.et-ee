---
title: Olemid ja andmekomplektid
description: Saate vaadata andmeid olemite lehel.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: ac8b0671b20123091bef64e672fc53398fe8955a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 07/13/2021
ms.locfileid: "6553970"
---
# <a name="entities-in-audience-insights"></a>Olemid sihtrühmaülevaadetes

Pärast [andmeallikate konfigureerimist](data-sources.md)minge lehele **Olemid**, et hinnata sisestatud andmete kvaliteeti. Olemeid käsitletakse andmekogumitena. Nende olemite põhjal on loodud mitu Dynamics 365 Customer Insightsi funktsiooni. Nende lähedasem läbivaatamine aitab teil nende võimaluste väljundit valideerida.

**Olemite** lehel loetletakse olemid ja see sisaldab mitut veergu.

- **Nimi**: teie andmete olemi nimi. Kui olemi nime kõrval kuvatakse hoiatuse sümbol, tähendab see, et selle olemi andmeid ei laaditud edukalt.
- **Allikas**: andmeallika tüüp, mis olemisse sisestati
- **Looja**: olemi loonud inimese nimi
- **Loodud**: olemi loomise kuupäev ja kellaaeg
- **Värskendaja**: olemit värskendanud inimese nimi
- **Viimati värskendatud**: olemi viimase värskendamise kuupäev ja kellaaeg
- **Viimane värskendatud**: viimase andmete värskendamise kuupäev ja kellaaeg

## <a name="explore-a-specific-entitys-data"></a>Avasta kindlat andmeüksust

Valige olem, et avastada selles olemis sisalduvaid erinevaid välju ja kirjeid.

> [!div class="mx-imgBorder"]
> ![Valige olem.](media/data-manager-entities-data.png "Olemi valimine")

- Vahekaardil **Andmed** kuvatakse olemin üksikkirjete tabeli analüüsimise üksikasjad.

> [!div class="mx-imgBorder"]
> ![Väljade tabel.](media/data-manager-entities-fields.PNG "Väljade tabel")

- Vahekaart **Atribuudid** on vaikimisi valitud ja kuvab tabeli et vaadata üle valitud olemi üksikasjad nagu välja nimed, andmetüübid ja tüübid. Veerus **Tüüp** kuvatakse ühise andmemudeli seostatavad tüübid, mis on süsteemi poolt automaatselt tuvastatud või mille on kasutajad [käsitsi vastendanud](map-entities.md). Need tüübid on semantilised tüübid, mis võivad atribuutide andmetüüpidest erineda. Oletagem näiteks, et allpool oleval väljal *Meil* on andmetüüp *Tekst*, kuid selle (semantilise) Common Data Modeli tüüp võib *Meil* või *Meiliaadress*.

> [!NOTE]
> Mõlemad tabelid näitavad ainult teie olemi andmete näidiseid. Täieliku andmekogumise vaatamiseks minge lehele **Andmeallikad**, valige olem, valige **Redigeeri** ja seejärel vaadake selle olemi andmeid Power Query redaktoriga, nagu on selgitatud [andmeallikates](data-sources.md).

Kui soovite lisateavet olemisse sisestatud andmete kohta, on **Kokkuvõtte** veerus toodud teie jaoks olulised kohaldatavad andmed, nt nullid, puuduvad väärtused, kordumatud väärtused, arvud ja jaotused.

Andmete kokkuvõtte kuvamiseks valige diagrammi ikoon.

> [!div class="mx-imgBorder"]
> ![Kokkuvõtte sümbol.](media/data-manager-entities-summary.png "Andmete kokkuvõtte tabel")

## <a name="entity-specific-information"></a>Olemipõhine teave

Järgmine jaotis sisaldab teavet mõne süsteemi loodud olemi kohta.

### <a name="corrupted-data-sources"></a>Andmeallikas on rikutud

sisse võetud andmeallikast pärinevad väljad võivad sisaldada rikutud andmeid. Rikutud väljadega kirjed kuvatakse süsteemi loodud olemitel. Teades rikutud kirjete kohta, saate tuvastada, milliseid andmeid lähtesüsteemis läbi vaadata ja värskendada. Pärast järgmise andmeallikas värskendamist antakse parandatud kirjed customer Insights'ile üle ja edastatakse järgmistele protsessidele. 

Näiteks veeru "sünnipäev" andmetüübiks on seatud "kuupäev". Kliendikirjel on sisestatud sünnipäev "01/01/19777". Süsteem märgib selle kirje rikutuks. Keegi saab nüüd muuta lähtesüsteemis sünnipäeva "1977". Pärast andmeallikate automaatset värskendamist on väljal nüüd kehtiv vorming ja kirje eemaldatakse rikutud olemist. 

Minge **Andme** > **Üksused** jaotisse ja otsige rikutud olemeid jaotises **Süsteem** . Rikutud olemite skeemi nimetamine: "DataSourceName_EntityName_corrupt".

Customer Insights töötleb endiselt rikutud kirjeid. Kuid need võivad põhjustada probleeme ühendatud andmetega töötamisel.

Vigaste kirjete näitamiseks käitatakse ülevaatatud andmete puhul järgmised kontrollid: 

- Välja väärtus ei ühti selle veeru andmetüübiga.
- Väljad sisaldavad märke, mille puhul veerud ei vasta eeldatud skeemile. Näiteks: valesti vormindatud hinnapakkumised, sisestamata hinnapakkumised või uued tekstimärgid.
- Kui veerud datetime/date/datetimeoffset on olemas, tuleb nende vorming mudelis määrata, kui need ei järgi standartset ISO vormingut.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
