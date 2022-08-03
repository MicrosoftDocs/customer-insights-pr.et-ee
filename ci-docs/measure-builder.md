---
title: Mõõtude loomine mõõturiga
description: Koostage meetmed nullist, et analüüsida oma ettevõtte peamisi mõõdikuid.
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
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170844"
---
# <a name="create-measures-with-measure-builder"></a>Mõõtude loomine mõõturiga

Mõõtude koostaja võimaldab teil arvutusi määratleda matemaatika tehtemärkide, liitmisfunktsioonide ja filtrite abil. Määratlege mõõdud, kasutades ühtse *kliendi* olemiga seotud olemite atribuute.

Meetmete loomine keskkondades B-C ja B-B toimib samamoodi. Kui aga teie B-B-keskkond [kasutab hierarhiatega](relationships.md#set-up-account-hierarchies) kontosid, valige, kas mõõt liita seotud alamkontode vahel.

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

Looge mõõdud üksikklientide (kliendi atribuut, kliendi mõõt) või ettevõtte/organisatsiooni (ärimõõt) tasandil. Kliendiatribuut ja kliendi mõõt võimaldavad teil jälgida toimivust kliendi kohta. Näiteks iga kliendi kogukulu. Ärimõõdikud jälgivad tulemuslikkust ettevõtte kohta. Näiteks ettevõtte kogutulu.

- Kliendiatribuut: loob väljundi uue atribuudina, mis salvestatakse uue veeruna süsteemi loodud olemisse nimega *Customer_Measure*. Kliendiatribuudi värskendamisel värskendatakse samaaegselt kõiki teisi Customer_Measure *olemi kliendiatribuute*. Lisaks kuvatakse kliendiprofiili kaardil kliendi atribuudid. Pärast käivitamist või salvestamist ei saa te kliendi atribuuti kliendi mõõduks muuta.

- Kliendi mõõt: loob väljundi oma olemina ja te ei saa seda pärast käitamist või salvestamist kliendiatribuudiks muuta. Kliendi mõõtühikuid kliendiprofiili kaardil ei kuvata.

- Ettevõtte mõõt: loob väljundi oma olemina ja kuvatakse teie Customer Insightsi keskkonna avalehel.

1. Avage **Mõõdud**.

1. Valige **Uus** > **Ehita enda oma**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tühi konfiguratsioonikuva mõõtude B-C jaoks." lightbox="media/measure-b2c.png":::

1. Valige **Redigeeri üksikasju** valiku Untitled measure (Pealkirjata mõõt) kõrval. Sisestage mõõdu nimi. Soovi korral lisage [mõõdule sildid](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoogiboks Üksikasjade redigeerimine.":::

1. Valige nupp **Valmis**.

1. Ettevõttetaseme jõudluse jälgimiseks lülitage **mõõtu tüüp** **ettevõtte tasemele**. **Kliendi tase** on vaikimisi valitud. **Kliendi tase** lisab *atribuudi CustomerId* automaatselt dimensioonidesse, samas kui **ettevõtte tase** eemaldab selle automaatselt.

1. Valige konfiguratsioonialal rippmenüüst **Funktsiooni valimine liitmisfunktsioon**. Koondamisfunktsioonid on järgmised.
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

1. Valige **Lisa atribuut**, et valida selle mõõdu loomiseks vajalikud andmed.

   1. Valige vaheleht **Attribuudid**.
   1. Andmeolem: valige olem, mis sisaldab mõõdetavat atribuuti.
   1. Andmeatribuut: valige atribuut, mida soovite näitaja arvutamiseks koondamisfunktsioonis kasutada. Korraga saate valida ainult ühe atribuudi.
   1. Soovi korral valige andmeatribuut olemasolevast mõõdust, valides **vahekaardi Mõõdud**, või otsige olemi või mõõdu nime.
   1. Valige suvand **Lisa**.

1. Keerukamate mõõtude loomiseks lisage rohkem atribuute või kasutage mõõtfunktsioonis matemaatika tehtemärke.

1. Filtrite lisamiseks valige konfiguratsiooniala **Filtreeri**. Filtrite rakendamisel kasutatakse mõõdu arvutamiseks ainult filtritele vastavaid kirjeid.
  
   1. Valige paani **Filtrid** jaotises **Atribuudi lisamine** atribuut, mida soovite filtrite loomiseks kasutada.
   1. Määrake filtritehted iga valitud atribuudi filtri määratlemiseks.
   1. Valige suvand **Rakenda**.

1. Valige **Dimensioon**, et valida rohkem välju, mida mõõdu väljundolemile veergudena lisada.

   1. Valige **Redigeeri dimensioonid**, et lisada andmeatribuute, mille järgi soovite näitaja väärtusi rühmitada. Näiteks linn või sugu.
      > [!TIP]
      > Kui valisite **mõõdutüübiks** **Kliendi taseme**, *on atribuut CustomerId* juba lisatud. Kui eemaldate atribuudi, **lülitub** mõõtmistüüp **ettevõtte tasemele**.
   1. Valige nupp **Valmis**.

1. Kui teie andmetes on väärtusi, mis tuleb asendada täisarvuga, valige **Reeglid**. Konfigureerige reegel ja veenduge, et valite asendusena ainult täisnumbrid. Asendage *null* näiteks väärtusega *0*.

1. Kui vastendatud andmeolemi ja *kliendi* olemi vahel on mitu teed, valige üks tuvastatud [olemi seose teedest](relationships.md). Näitaja tulemused võivad sõltuvalt valitud teest erineda.

   1. Valige **Seosetee** ja valige olemitee, mida tuleks kasutada teie mõõtmete tuvastamiseks. Kui olemi *Klient* juurde on ainult üks tee, siis seda juhtelementi ei näidata.
   1. Valige nupp **Valmis**.

1. Kui soovite näitajat veel arvutada, valige **Uus arvutus**. Kasutage uute arvutuste tegemiseks ainult samal olemiteel olevaid olemeid. Täiendavad arvutused kuvatakse näitaja väljundolemis uute veergudena. Soovi korral valige **arvutuse jaoks nime loomiseks Redigeeri** nime.

1. Valige arvutusel vertikaalne kolmikpunkt (&vellip;), et arvutust dubleerida **või** **mõõdust eemaldada**.

1. **Eelvaatealal** näete näitaja väljundolemi andmeskeemi (sh filtreid ja dimensioone). Eelvaade reageerib dünaamiliselt konfiguratsiooni muudatustele.

1. Konfigureeritud näitaja tulemuste arvutamiseks valige **Käivita**. Kui soovite praeguse konfiguratsiooni säilitada ja näitajat hiljem käitada, valige **Salvesta ja sule**. Kuvatakse **leht Mõõdud**.

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

Looge mõõdud üksikute kontode (kliendi mõõt) või kõigi kontode (ettevõtte mõõt) tasemel.

- Kliendi mõõt: loob väljundi oma olemina. Kliendi mõõtühikuid kliendiprofiili kaardil ei kuvata.

- Ettevõtte mõõt: loob väljundi oma olemina ja kuvatakse teie Customer Insightsi keskkonna avalehel.

1. Avage **Mõõdud**.

1. Tehke valik **Uus**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tühi konfiguratsioonikuva mõõdu B-B jaoks.":::

1. Valige **Redigeeri üksikasju** valiku Untitled measure (Pealkirjata mõõt) kõrval. Sisestage mõõdu nimi. Soovi korral lisage [mõõdule sildid](work-with-tags-columns.md#manage-tags). 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoogiboks Üksikasjade redigeerimine.":::

1. Valige nupp **Valmis**.

1. Valige konfiguratsioonialal rippmenüüst **Funktsiooni valimine liitmisfunktsioon**. Koondamisfunktsioonid on järgmised.
   - **Sum**
   - **Keskmine**
   - **Loenda**
   - **Kordumatu arv**
   - **Maks.**
   - **Min**
   - **Esimene**: võtab andmekirje esimese väärtuse
   - **Viimane**: võtab andmekirjesse lisatud viimase väärtuse

1. Valige **Lisa atribuut**, et valida selle mõõdu loomiseks vajalikud andmed.

   1. Valige vaheleht **Attribuudid**.
   1. Andmeolem: valige olem, mis sisaldab mõõdetavat atribuuti.
   1. Andmeatribuut: valige atribuut, mida soovite näitaja arvutamiseks koondamisfunktsioonis kasutada. Korraga saate valida ainult ühe atribuudi.
   1. Soovi korral valige andmeatribuut olemasolevast mõõdust, valides **vahekaardi Mõõdud**, või otsige olemi või mõõdu nime.
   1. Valige **Lisa**, et lisada atribuut näitajale.

1. Keerukamate mõõtude loomiseks lisage rohkem atribuute või kasutage mõõtfunktsioonis matemaatika tehtemärke.

1. Filtrite lisamiseks valige konfiguratsiooniala **Filtreeri**. Filtrite rakendamisel kasutatakse mõõdu arvutamiseks ainult filtritele vastavaid kirjeid.
  
   1. Valige paani **Filtrid** jaotises **Atribuudi lisamine** atribuut, mida soovite filtrite loomiseks kasutada.
   1. Määrake filtritehted iga valitud atribuudi filtri määratlemiseks.
   1. Valige **Rakenda**, et lisada filtrid näitajale.

1. Valige **Dimensioon**, et valida rohkem välju, mida mõõdu väljundolemile veergudena lisada.

   1. Valige **Redigeeri dimensioonid**, et lisada andmeatribuute, mille järgi soovite näitaja väärtusi rühmitada. Näiteks linn või sugu.
      > [!TIP]
      > Atribuut *CustomerId* on juba lisatud, mis näitab, et tegemist on klienditaseme mõõdutüübiga. Atribuudi eemaldamisel muutub mõõdu tüüp ettevõtte tasemele.
   1. Valige **Valmis**, et lisada dimensioonid näitajale.

1. Kui teie andmetes on väärtusi, mis tuleb asendada täisarvuga, valige **Reeglid**. Konfigureerige reegel ja veenduge, et valite asendusena ainult täisnumbrid. Asendage *null* näiteks väärtusega *0*.

1. Kui kasutate [hierarhiatega](relationships.md#set-up-account-hierarchies) kontosid, vaadake üle **Alamkontode üleskeeramine**.
   - Kui väärtuseks on seatud **Väljas**, arvutatakse iga konto mõõtmed. Iga konto saab oma tulemuse.
   - Kui väärtuseks on määratud **Sees**, siis valige **Redigeeri**, et valida kontohierarhia vastavalt sisestatud hierarhiatele. Meede annab ainult ühe tulemuse, kuna see on koondatud allkontodega.

1. Kui vastendatud andmeolemi ja *kliendi* olemi vahel on mitu teed, valige üks tuvastatud [olemi seose teedest](relationships.md). Näitaja tulemused võivad sõltuvalt valitud teest erineda.

   1. Valige **Seosetee** ja valige olemitee, mida tuleks kasutada teie mõõtmete tuvastamiseks. Kui olemi *Klient* juurde on ainult üks tee, siis seda juhtelementi ei näidata.
   1. Valiku rakendamiseks valige suvand **Valmis**.

1. Valige arvutusel vertikaalne kolmikpunkt (&vellip;), et arvutust dubleerida **või** **mõõdust eemaldada**.

1. **Eelvaatealal** näete näitaja väljundolemi andmeskeemi (sh filtreid ja dimensioone). Eelvaade reageerib dünaamiliselt konfiguratsiooni muudatustele.

1. Konfigureeritud näitaja tulemuste arvutamiseks valige **Käivita**. Kui soovite praeguse konfiguratsiooni säilitada ja näitajat hiljem käitada, valige **Salvesta ja sule**. Kuvatakse **leht Mõõdud**.

---

## <a name="next-step"></a>Järgmine etapp

Kasutage kliendisegmendi loomiseks [olemasolevaid mõõtühikuid](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
