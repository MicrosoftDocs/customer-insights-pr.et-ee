---
title: Uute meetmete loomine meetme koostajaga
description: Koostage meetmed nullist, et analüüsida oma ettevõtte peamisi mõõdikuid.
ms.date: 02/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 5329aea240ba40ec8698b3ddeb67fb5f21c62bbd
ms.sourcegitcommit: cf6a0ed44915908a44c70889a2dd199a9d0d4798
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/28/2022
ms.locfileid: "8359946"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Mõõdukoosturi kasutamine meetmete loomiseks nullist

Selles artiklis selgitatakse, kuidas luua uus [meede](measures.md) nullist. Mõõte koostaja võimaldab arvutusi määratleda matemaatikatehtemärkide, koondamisfunktsioonide ja filtrite abil. Saate luua mõõdu, mille atribuudid on olemitest, mis on seotud ühendatud *kliendiolemiga*. 

Meetmete loomine B-C ja B-to-B keskkonnas toimib samamoodi. Kui aga olete B-to-B keskkond [kasutab hierarhiatega kontosid](relationships.md#set-up-account-hierarchies), saate meetme koondada seotud alamkontode vahel.

Samuti saate kiiresti luua meetme, valides laialdaselt kasutatavate ja eelnevalt määratletud meetmete hulgast. Lisateavet leiate teemast [Malli kasutamine mõõdu loomiseks](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

Saate luua meetmeid üksikute klientide tasemel (kliendi atribuut, kliendi mõõt) või ettevõtte/organisatsiooni tasemel (ärimeede). Kliendi atribuut ja kliendi mõõt on kahte tüüpi, mis võimaldavad teil jälgida jõudlust kliendi kohta. Näiteks iga kliendi kogukulu. Ärimeetmed võimaldavad teil jälgida tulemuslikkust ettevõtte kohta. Näiteks ettevõtte kogutulu.

- Kliendi atribuut: loob väljundi uue atribuudina, mis salvestatakse uue veeruna süsteemi loodud olemis nimega *Customer_Measure*. Kliendiatribuudi värskendamisel värskendavad kõik teised olemi Customer_Measure *kliendi atribuudid* samaaegselt. Lisaks kuvatakse kliendiprofiili kaardil kliendi atribuudid. Kui see on käivitatud või salvestatud, ei saa kliendi atribuut seda kliendimõõtmiseks muuta.

- Kliendi mõõt: loob väljundi oma olemina ja te ei saa seda pärast käivitamist või salvestamist kliendi atribuudiks muuta. Kliendi mõõdud ei kuvata kliendiprofiili kaardil.

- Ärimeede: loob väljundi oma olemina ja kuvatakse customer Insightsi keskkonna avalehel.

1. Minge meetmete **juurde**.

1. Valige **Uus** ja valige **Looge ise**.

   :::image type="content" source="media/measure-b2c.png" alt-text="B-C-mõõdu tühi konfiguratsiooniekraan.":::

1. Valige **Redigeeri nimi** ja sisestage näitaja **Nimi**. 

1. Valige konfiguratsioonialal koondamisfunktsioon rippmenüüst **Vali funktsioon**. Koondamisfunktsioonid on järgmised. 
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

1. Valige **Dimensioon**, et valida veel välju, mis lisatakse dimensiooni väljundolemi veergudena.
 
   1. Valige **Redigeeri dimensioonid**, et lisada andmeatribuute, mille järgi soovite näitaja väärtusi rühmitada. Näiteks linn või sugu. *Klienditaseme näitajate loomiseks* valitakse vaikimisi *CustomerID* dimensioon. Kui soovite luua *äritaseme näitajaid*, saate vaikeeelise eemaldada.
   1. Valige **Valmis**, et lisada dimensioonid näitajale.

1. Kui teie andmetes on väärtused, mida peate täisarvuga asendama, valige **Reeglid**. Konfigureerige reegel ja veenduge, et valite asendusena ainult täisnumbrid. Asendage *null* näiteks väärtusega *0*.

1. Kui vastendatud andme- ja olemi *Klient* vahel on mitu teed, peate valima ühe tuvastatud [olemi suhte teedest](relationships.md). Näitaja tulemused võivad sõltuvalt valitud teest erineda. 
   
   1. Valige **Seosetee** ja valige olemitee, mida tuleks kasutada teie mõõtmete tuvastamiseks. Kui olemi *Klient* juurde on ainult üks tee, siis seda juhtelementi ei näidata.
   1. Valiku rakendamiseks valige suvand **Valmis**. 

1. Kui soovite näitajat veel arvutada, valige **Uus arvutus**. Uute arvutuste jaoks saate kasutada ainult samal olemiteel olevaid üksusi. Täiendavad arvutused kuvatakse näitaja väljundolemis uute veergudena.

1. Valige näitajast arvutuse **Duplitseerimiseks**, **Ümber nimetamiseks** või **Eemaldamiseks** **...**.

1. **Eelvaatealal** näete näitaja väljundolemi andmeskeemi (sh filtreid ja dimensioone). Eelvaade reageerib dünaamiliselt konfiguratsiooni muudatustele.

1. Konfigureeritud näitaja tulemuste arvutamiseks valige **Käivita**. Kui soovite praeguse konfiguratsiooni säilitada ja näitajat hiljem käitada, valige **Salvesta ja sule**.

1. Vastloodud näitaja nägemiseks loendis, valige **Näitajad**.

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)


Saate luua meetmeid üksikute kontode tasemel (kliendi mõõt) või kõigi kontode tasemel (ärimeede). 

- Kliendi mõõt: loob väljundi oma olemina. Kliendi mõõdud ei kuvata kliendiprofiili kaardil.

- Ärimeede: loob väljundi oma olemina ja kuvatakse customer Insightsi keskkonna avalehel.

1. Minge meetmete **juurde**.

1. Tehke valik **Uus**.

   :::image type="content" source="media/measure-b2b.png" alt-text="B-B-mõõdu tühi konfiguratsioonikuva.":::

1. Valige **Redigeeri nimi** ja sisestage näitaja **Nimi**. 

1. Valige konfiguratsioonialal koondamisfunktsioon rippmenüüst **Vali funktsioon**. Koondamisfunktsioonid on järgmised. 
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

1. Valige **Dimensioon**, et valida veel välju, mis lisatakse dimensiooni väljundolemi veergudena.
 
   1. Valige **Redigeeri dimensioonid**, et lisada andmeatribuute, mille järgi soovite näitaja väärtusi rühmitada. Näiteks linn või sugu. *Klienditaseme näitajate loomiseks* valitakse vaikimisi *CustomerID* dimensioon. Kui soovite luua *äritaseme näitajaid*, saate vaikeeelise eemaldada.
   1. Valige **Valmis**, et lisada dimensioonid näitajale.

1. Kui teie andmetes on väärtused, mida peate täisarvuga asendama, valige **Reeglid**. Konfigureerige reegel ja veenduge, et valite asendusena ainult täisnumbrid. Asendage *null* näiteks väärtusega *0*.

1. Saate kasutada **Ettevõtte allüksuste koondamist**, kui te [kasutate hierarhiaga kontosid](relationships.md#set-up-account-hierarchies).
   - Kui väärtuseks on seatud **Väljas**, arvutatakse iga konto mõõtmed. Iga konto saab oma tulemuse.
   - Kui väärtuseks on määratud **Sees**, siis valige **Redigeeri**, et valida kontohierarhia vastavalt sisestatud hierarhiatele. Mõõde annab ainult ühe tulemuse, kuna see on koondatud alamkontodega.

1. Kui vastendatud andme- ja olemi *Klient* vahel on mitu teed, peate valima ühe tuvastatud [olemi suhte teedest](relationships.md). Näitaja tulemused võivad sõltuvalt valitud teest erineda. 
   
   1. Valige **Seosetee** ja valige olemitee, mida tuleks kasutada teie mõõtmete tuvastamiseks. Kui olemi *Klient* juurde on ainult üks tee, siis seda juhtelementi ei näidata.
   1. Valiku rakendamiseks valige suvand **Valmis**. 

1. Valige näitajast arvutuse **Duplitseerimiseks**, **Ümber nimetamiseks** või **Eemaldamiseks** **...**.

1. **Eelvaatealal** näete näitaja väljundolemi andmeskeemi (sh filtreid ja dimensioone). Eelvaade reageerib dünaamiliselt konfiguratsiooni muudatustele.

1. Konfigureeritud näitaja tulemuste arvutamiseks valige **Käivita**. Kui soovite praeguse konfiguratsiooni säilitada ja näitajat hiljem käitada, valige **Salvesta ja sule**.

1. Vastloodud näitaja nägemiseks loendis, valige **Näitajad**.

---