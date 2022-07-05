---
title: Looge meetme koostajaga uusi meetmeid
description: Koostage nullist meetmed, et analüüsida oma ettevõtte peamisi mõõdikuid.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: f3ec86806074a12c1107648303ed2d65e97ebc69
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9083013"
---
# <a name="create-new-measures-with-the-measure-builder"></a>Looge meetme koostajaga uusi meetmeid

Selles artiklis selgitatakse, kuidas luua uus [meede](measures.md) nullist. Mõõtkoosturi võimaldab arvutusi määratleda matemaatikatehtemärkide, liitmisfunktsioonide ja filtrite abil. Saate luua mõõdu koos atribuutidega olemitest, mis on seotud ühtse *kliendiolemiga*.

Meetmete loomine B-C ja B-B keskkonnas toimib samamoodi. Kui aga B-B keskkond [kasutab hierarhiatega](relationships.md#set-up-account-hierarchies) kontosid, saate valida, kas liita mõõt seotud alamkontode vahel.

Samuti saate kiiresti luua meetme, valides tavaliselt kasutatavate ja eelnevalt määratletud meetmete hulgast. Lisateavet leiate teemast [Malli kasutamine mõõdu loomiseks](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

Saate luua meetmeid üksikute klientide tasandil (kliendi atribuut, kliendimõõt) või ettevõtte/organisatsiooni tasandil (ärimeede). Kliendi atribuut ja kliendimõõt on kahte tüüpi, mis võimaldavad teil jälgida jõudlust kliendi kohta. Näiteks iga kliendi kogukulutused. Ärimeetmed võimaldavad teil jälgida tulemuslikkust ettevõtte kohta. Näiteks ettevõtte kogutulu.

- Kliendi atribuut: loob väljundi uue atribuudina, mis salvestatakse uue veeruna süsteemi loodud olemis nimega *Customer_Measure*. Kliendi atribuudi värskendamisel värskendatakse samaaegselt kõiki teisi kliendi atribuute *Customer_Measure*. Lisaks kuvatakse kliendi profiilikaardil kliendi atribuute. Kui see on käivitatud või salvestatud, ei saa kliendi atribuuti muuta seda kliendi mõõduks.

- Kliendi mõõt: loob väljundi oma olemina ja te ei saa seda pärast käivitamist või salvestamist kliendi atribuudiks muuta. Kliendi mõõte kliendi profiilikaardil ei kuvata.

- Ärimeede: loob väljundi oma olemina ja kuvatakse teie Customer Insightsi keskkonna avalehel.

1. Minge meetmete **juurde**.

1. Valige **Uus** ja valige **Looge ise**.

   :::image type="content" source="media/measure-b2c.png" alt-text="B-C-mõõtmise jaoks on tühi konfiguratsiooniekraan." lightbox="media/measure-b2c.png":::

1. Äritaseme jõudluse jälgimiseks lülitage **mõõdu tüüp** üle **äritasemele**. **Kliendi tase** on vaikimisi valitud. **Klienditase** lisab *atribuudi CustomerId* automaatselt dimensioonidele, samas kui **äritase** eemaldab selle automaatselt.

1. Valige konfigureerimisalal rippmenüüst **Funktsiooni Vali väärtus** liitmisfunktsioon. Koondamisfunktsioonid on järgmised.
   - **Sum**
   - **Keskmine**
   - **Loenda**
   - **Kordumatu arv**
   - **Maks.**
   - **Min**
   - **Esimene**: võtab andmekirje esimese väärtuse
   - **Viimane**: võtab andmekirjesse lisatud viimase väärtuse
   - **ArgMax**: leiab andmekirje, mis annab sihtfunktsioonist maksimaalse väärtuse
   - **ArgMin**: leiab andmekirje, mis annab sihtfunktsioonist minimaalse väärtuse

1. Valige **Lisa atribuut**, et valida andmed, mida selle näitaja loomiseks vajate.

   1. Valige vaheleht **Attribuudid**.
   1. Andmeolem: valige olem, mis sisaldab mõõdetavat atribuuti.
   1. Andmeatribuut: valige atribuut, mida soovite näitaja arvutamiseks koondamisfunktsioonis kasutada. Korraga saate valida ainult ühe atribuudi.
   1. Olemasolevast näitajast andmeatribuudi valimiseks klõpsake vahekaarti **Näitajad** või otsige olemi või näitaja nime.
   1. Valige **Lisa**, et lisada atribuut näitajale.

1. Keerukamate näitajate loomiseks võite lisada mõõtmisfunktsioonile rohkem atribuute või kasutada matemaatilisi tehtemärke.

1. Filtrite lisamiseks valige konfiguratsiooniala **Filtreeri**. Filtrite rakendamine kasutab mõõtmise arvutamiseks ainult filtritele vastavaid kirjeid.
  
   1. Valige paani **Filtrid** jaotises **Atribuudi lisamine** atribuut, mida soovite filtrite loomiseks kasutada.
   1. Määrake filtritehted iga valitud atribuudi filtri määratlemiseks.
   1. Valige **Rakenda**, et lisada filtrid näitajale.

1. Valige **Dimensioon**, et valida rohkem välju, mis lisatakse mõõtväljundiolemi veergudena.

   1. Valige **Redigeeri dimensioonid**, et lisada andmeatribuute, mille järgi soovite näitaja väärtusi rühmitada. Näiteks linn või sugu.
   > [!TIP]
   > Kui valisite **tüübiks** Mõõt **klienditaseme**, *on atribuut CustomerId* juba lisatud. Kui eemaldate atribuudi, **lülitab** tüüp mõõtmine **ettevõtte tasemele**.
   1. Valige **Valmis**, et lisada dimensioonid näitajale.

1. Kui teie andmetes on väärtused, mida peate täisarvuga asendama, valige **Reeglid**. Konfigureerige reegel ja veenduge, et valite asendusena ainult täisnumbrid. Asendage *null* näiteks väärtusega *0*.

1. Kui vastendatud andme- ja olemi *Klient* vahel on mitu teed, peate valima ühe tuvastatud [olemi suhte teedest](relationships.md). Näitaja tulemused võivad sõltuvalt valitud teest erineda.

   1. Valige **Seosetee** ja valige olemitee, mida tuleks kasutada teie mõõtmete tuvastamiseks. Kui olemi *Klient* juurde on ainult üks tee, siis seda juhtelementi ei näidata.
   1. Valiku rakendamiseks valige suvand **Valmis**.

1. Kui soovite näitajat veel arvutada, valige **Uus arvutus**. Uute arvutuste jaoks saate kasutada ainult samal olemiteel olevaid üksusi. Täiendavad arvutused kuvatakse näitaja väljundolemis uute veergudena.

1. Valige arvutuses vertikaalne kolmikpunkt (&vellip;) väärtuseks **Duplikaat**, **Ümbernimetamine** või **Arvutuse eemaldamine** mõõdust.

1. **Eelvaatealal** näete näitaja väljundolemi andmeskeemi (sh filtreid ja dimensioone). Eelvaade reageerib dünaamiliselt konfiguratsiooni muudatustele.

1. Valige **Redigeeri üksikasju** välja Sidumata mõõt kõrval. Esitage meetmele nimi. Soovi korral lisage [mõõdule sildid](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoogiboksi Üksikasjade redigeerimine.":::

1. Konfigureeritud näitaja tulemuste arvutamiseks valige **Käivita**. Kui soovite praeguse konfiguratsiooni säilitada ja näitajat hiljem käitada, valige **Salvesta ja sule**.

1. Vastloodud näitaja nägemiseks loendis, valige **Näitajad**.

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

Saate luua meetmeid üksikute kontode tasemel (kliendimõõt) või kõigi kontode tasemel (ärimeede).

- Kliendi mõõt: loob väljundi oma olemina. Kliendi mõõte kliendi profiilikaardil ei kuvata.

- Ärimeede: loob väljundi oma olemina ja kuvatakse teie Customer Insightsi keskkonna avalehel.

1. Minge meetmete **juurde**.

1. Tehke valik **Uus**.

   :::image type="content" source="media/measure-b2b.png" alt-text="B-B-mõõdu jaoks on tühi konfiguratsiooniekraan.":::

1. Valige konfigureerimisalal rippmenüüst **Funktsiooni Vali väärtus** liitmisfunktsioon. Koondamisfunktsioonid on järgmised.
   - **Sum**
   - **Keskmine**
   - **Loenda**
   - **Kordumatu arv**
   - **Maks.**
   - **Min**
   - **Esimene**: võtab andmekirje esimese väärtuse
   - **Viimane**: võtab andmekirjesse lisatud viimase väärtuse

1. Valige **Lisa atribuut**, et valida andmed, mida selle näitaja loomiseks vajate.

   1. Valige vaheleht **Attribuudid**.
   1. Andmeolem: valige olem, mis sisaldab mõõdetavat atribuuti.
   1. Andmeatribuut: valige atribuut, mida soovite näitaja arvutamiseks koondamisfunktsioonis kasutada. Korraga saate valida ainult ühe atribuudi.
   1. Olemasolevast näitajast andmeatribuudi valimiseks klõpsake vahekaarti **Näitajad** või otsige olemi või näitaja nime.
   1. Valige **Lisa**, et lisada atribuut näitajale.

1. Keerukamate näitajate loomiseks võite lisada mõõtmisfunktsioonile rohkem atribuute või kasutada matemaatilisi tehtemärke.

1. Filtrite lisamiseks valige konfiguratsiooniala **Filtreeri**. Filtrite rakendamine kasutab mõõtmise arvutamiseks ainult filtritele vastavaid kirjeid.
  
   1. Valige paani **Filtrid** jaotises **Atribuudi lisamine** atribuut, mida soovite filtrite loomiseks kasutada.
   1. Määrake filtritehted iga valitud atribuudi filtri määratlemiseks.
   1. Valige **Rakenda**, et lisada filtrid näitajale.

1. Valige **Dimensioon**, et valida rohkem välju, mis lisatakse mõõtväljundiolemi veergudena.

   1. Valige **Redigeeri dimensioonid**, et lisada andmeatribuute, mille järgi soovite näitaja väärtusi rühmitada. Näiteks linn või sugu.
      > [!TIP]
      > Kui valisite **tüübiks** Mõõt **klienditaseme**, *on atribuut CustomerId* juba lisatud. Kui eemaldate atribuudi, **lülitub mõõtmistüüp** äritasemele **·**.
   1. Valige **Valmis**, et lisada dimensioonid näitajale.

1. Kui teie andmetes on väärtused, mida peate täisarvuga asendama, valige **Reeglid**. Konfigureerige reegel ja veenduge, et valite asendusena ainult täisnumbrid. Asendage *null* näiteks väärtusega *0*.

1. Saate kasutada **Ettevõtte allüksuste koondamist**, kui te [kasutate hierarhiaga kontosid](relationships.md#set-up-account-hierarchies).
   - Kui väärtuseks on seatud **Väljas**, arvutatakse iga konto mõõtmed. Iga konto saab oma tulemuse.
   - Kui väärtuseks on määratud **Sees**, siis valige **Redigeeri**, et valida kontohierarhia vastavalt sisestatud hierarhiatele. Mõõde annab ainult ühe tulemuse, kuna see on koondatud alamkontodega.

1. Kui vastendatud andme- ja olemi *Klient* vahel on mitu teed, peate valima ühe tuvastatud [olemi suhte teedest](relationships.md). Näitaja tulemused võivad sõltuvalt valitud teest erineda.

   1. Valige **Seosetee** ja valige olemitee, mida tuleks kasutada teie mõõtmete tuvastamiseks. Kui olemi *Klient* juurde on ainult üks tee, siis seda juhtelementi ei näidata.
   1. Valiku rakendamiseks valige suvand **Valmis**.

1. Valige arvutuses vertikaalne kolmikpunkt (&vellip;) väärtuseks **Duplikaat**, **Ümbernimetamine** või **Arvutuse eemaldamine** mõõdust.

1. **Eelvaatealal** näete näitaja väljundolemi andmeskeemi (sh filtreid ja dimensioone). Eelvaade reageerib dünaamiliselt konfiguratsiooni muudatustele.

1. Valige **Redigeeri üksikasju** välja Sidumata mõõt kõrval. Esitage meetmele nimi. Soovi korral lisage [mõõdule sildid](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoogiboksi Üksikasjade redigeerimine.":::

1. Konfigureeritud näitaja tulemuste arvutamiseks valige **Käivita**. Kui soovite praeguse konfiguratsiooni säilitada ja näitajat hiljem käitada, valige **Salvesta ja sule**.

1. Vastloodud näitaja nägemiseks loendis, valige **Näitajad**.
