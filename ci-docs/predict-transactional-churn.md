---
title: Tehingute prognoos (sisaldab videot)
description: Prognoosige, kas on oht, et klient ei osta enam teie ettevõtte tooteid või teenuseid.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610507"
---
# <a name="predict-transaction-churn"></a>Tehinguvoolavuse prognoos

Tehinguvoolavuse prognoos aitab ennustada, kas klient on lõpetanud kindlal perioodil teie toodete või teenuste ostmise.

Teil peavad olema äriteadmised, et mõista, mida churn teie ettevõtte jaoks tähendab. Toetame ajapõhiseid voolavuse määratlusi, mis tähendab, et klient loetakse loobunuks, kui ta pole mingi perioodi jooksul oste teinud.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Ärikontodel põhinevate keskkondade puhul võime ennustada ettevõtte jaoks tehinguvoolavust, samuti ettevõtte ja muu taseme teabe nagu tootekategooria kombinatsiooni. Näiteks võib dimensiooni lisamine aidata kindlaks teha, kui tõenäoline on, et konto "Contoso" lõpetab tootekategooria "kontori kirjatarbed" ostmise. Lisaks võime ärikontode puhul kasutada AI-d ka potentsiaalsete põhjuste loendi loomiseks, miks ettevõte võib teise taseme teabe kategoorias tõenäoliselt liikuda.

> [!TIP]
> Proovige tehingut prognoos näidisandmete abil: [Transaction churn prognoos näidisjuhend](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>eeltingimused

- Vähemalt [kaasautori õigused](permissions.md).
- Vähemalt 10 kliendiprofiili, eelistatavalt rohkem kui 1,000 unikaalset klienti.
- Kliendi identifikaator – kordumatu identifikaator tehingute sobitamiseks teie klientidega.
- Tehinguandmed vähemalt kahekordse valitud ajavahemiku kohta, näiteks kahe kuni kolme aasta pikkuse tehingute ajaloo kohta. Ideaalis vähemalt kaks tehingut kliendi kohta. Tehingute ajalugu peab sisaldama järgmist:
  - **Tehingu ID**: ostu või tehingu kordumatu tunnus.
  - **Tehingu kuupäev**: ostu või tehingu kuupäev.
  - **Tehingu väärtus: tehingu** valuuta või arvväärtuse summa.
  - **Kordumatu toote ID**: ostetud toote või teenuse ID, kui teie andmed on rea kauba tasemel.
  - **Kas see kanne oli tagastus**: tõene/vale väli, mis tuvastab, kas kanne oli tagastus või mitte. Kui tehingu **väärtus** on negatiivne, tuletame tootluse.
- Kliendi tegevuse andmed:
  - Kliendiidentifikaator – kordumatu identifikaator tegevuste vastendamiseks klientidega.
  - **Primaarvõti:** tegevuse kordumatu identifikaator. Näiteks veebisaidikülastus või kasutuskirje, mis näitab, et klient proovis teie toote näidist.
  - **Ajatempel:** primaarvõtmega tuvastatud sündmuse kuupäev ja kellaaeg.
  - **Sündmus:** sündmuse nimi, mida soovite kasutada. Näiteks väli nimega „UserAction“ võid toidupoe korral märkida, et klient kasutas kupongi.
  - **Üksikasjad:** sündmuse üksikasjalik teave. Näiteks väli nimega „CouponValue“ võib olla toidupoes kupongi rahaline väärtus.
- Vähem kui 20% esitatud üksuse andmevälja puuduvatest väärtustest

Ärikontode (B-kuni B) puhul lisage kliendiandmed staatilisemate atribuutidega joondatud, et tagada mudeli parim toimivus.
- **CustomerID:** kliendi kordumatu identifikaator.
- **Loomise kuupäev:** kliendi lisamise kuupäev.
- **Osariik või provints:** kliendi asukoht osariigis või provintsis.
- **Riik:** Kliendi riik.
- **Tööstus:** kliendi tööstusharu tüüp. Näiteks kohvi röstkoja väli „Tööstus” võib näidata, kas klient oli jaemüügis.
- **Klassifikatsioon:** kliendi kategoriseerimine teie ettevõtte jaoks. Näiteks kohvi röstkoja väli „ValueSegment” võib olla kliendi tasand kliendi suuruse põhjal.

> [!NOTE]
> Ettevõtte jaoks, kelle klientide ostu sagedus on kõrge (iga paari nädala tagant), on soovitatav valida lühem prognoosiaken ja voolavuse määratlus. Ostude madal sagedus (iga paari kuu tagant või kord aastas) korral valige pikem prognoosiaken ja voolavuse määratlus.

## <a name="create-a-transaction-churn-prediction"></a>Tehinguvoolavuse prgonoosi loomine

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil** Loo **paanil Kliendituuma mudel** **suvand Kasuta mudelit**.

1. Valige **kandetüübi jaoks Kanne** ja seejärel **Alustage**.

1. **Nimeta see mudel** ja **Väljundi olemi nimi**, et neid muudest mudelitest või olemitest eristada.

1. Tehke valik **Edasi**.

### <a name="define-customer-churn"></a>Määratlege kliendi teenusest loobumine

Valige **Salvesta mustand** igal ajal, et salvestada prognoos mustandina. Mustand prognoos kuvatakse vahekaardil **Minu ennustused**.

1. Seadke **prognoos aken**. Näiteks ennustage oma klientide voolavusriski järgmise 90 päeva jooksul, et kohandada oma klientide säilitamise jõupingutusi. Voolavusriski ennustamine pikema või lühema ajavahemiku jooksul võib raskendada voolavusriski tekitavate tegurite käsitlemist, kuid see sõltub teie ettevõtte vajadustest.

1. Sisestage väljale Churn definitsioon **päevade arv, et määratleda churn**. Näiteks kui klient ei ole viimase 30 päeva jooksul ostu sooritanud, võidakse teda pidada teie ettevõtte jaoks ebakvaliteetseks.

1. Tehke valik **Edasi**.

### <a name="add-purchase-history"></a>Lisa ostuajalugu

1. Valige **Lisa andmed** kliendikannete ajaloo **jaoks**.

1. Valige semantilise tegevuse tüüp SalesOrder **või** **SalesOrderLine**, mis sisaldab kandeajaloo teavet. Kui tegevust pole seadistatud, valige **siin** ja looge see.

1. Kui tegevuste atribuudid olid tegevuse loomisel semantiliselt vastendatud, valige jaotises **Tegevused** konkreetsed atribuudid või olem, millele soovite arvutuses keskenduda. Kui semantilist vastendamist ei toimunud, valige Redigeeri **ja** vastendage oma andmed.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Kõrvalpaan, kus kuvatakse kindlate tegevuste valimine semantilise tüübi all.":::

1. Valige **Edasi** ja vaadake üle selle mudeli jaoks vajalikud atribuudid.

1. Valige **Salvesta**.

1. Lisage veel tegevusi või valige **Edasi**.

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Lisage Lisaandmed (valikuline)

1. Valige **Lisa andmed** kliendi tegevuste **jaoks**.

1. Valige semantilise tegevuse tüüp, mis sisaldab andmeid, mida soovite kasutada. Kui tegevust pole seadistatud, valige **siin** ja looge see.

1. Kui tegevuste atribuudid olid tegevuse loomisel semantiliselt vastendatud, valige jaotises **Tegevused** konkreetsed atribuudid või olem, millele soovite arvutuses keskenduda. Kui semantilist vastendamist ei toimunud, valige Redigeeri **ja** vastendage oma andmed.

1. Valige **Edasi** ja vaadake üle selle mudeli jaoks vajalikud atribuudid.

1. Valige **Salvesta**.

1. Vali **Järgmine**

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

### <a name="select-prediction-level"></a>Valige progonoosi tase

Enamik ennustusi luuakse kliendi tasandil. Mõnes olukorras ei pruugi see olla nii suur, et see vastaks teie ärivajadustele. Kasutage seda funktsiooni, et ennustada näiteks kliendi haru, mitte kliendi kui terviku jaoks.

1. Valige **teisese taseme** jaoks olemi valimine. Kui see suvand pole saadaval, veenduge, et olete eelmise jaotise lõpule viinud.

1. Laiendage olemid, millelt soovite teisese taseme valida, või kasutage valitud suvandite filtreerimiseks otsingufiltrivälja.

1. Valige atribuut, mida soovite kasutada teisese tasemena, ja seejärel valige **Lisa**.

1. Tehke valik **Edasi**.

> [!NOTE]
> Selles jaotises saadaolevad olemid kuvatakse seetõttu, et neil on seos eelmises jaotises valitud olemiga. Kui te ei näe olemit, mida lisada soovite, siis veenduge, et sellel oleks seostes kehtiv **Seos**. Konfiguratsiooni puhul sobivad ainult üks-ühele ja mitu-ühele seosed.

### <a name="add-additional-data-optional"></a>Lisage Lisaandmed (valikuline)

1. Valige **Lisa andmed** kliendi tegevuste **jaoks**.

1. Valige semantilise tegevuse tüüp, mis sisaldab andmeid, mida soovite kasutada. Kui tegevust pole seadistatud, valige **siin** ja looge see.

1. Kui tegevuste atribuudid olid tegevuse loomisel semantiliselt vastendatud, valige jaotises **Tegevused** konkreetsed atribuudid või olem, millele soovite arvutuses keskenduda. Kui semantilist vastendamist ei toimunud, valige Redigeeri **ja** vastendage oma andmed.

1. Valige **Edasi** ja vaadake üle selle mudeli jaoks vajalikud atribuudid.

1. Valige **Salvesta**.

1. Vali **Järgmine**

1. Soovi korral tehke valik **Andmete lisamine** **Klientide andmete jaoks**.

1. Vastendage semantilised atribuudid väljadega oma kliendiandmetes vastavalt tuvastatud andmetele. Kasutatud väljade andmeid ei tohiks sageli muuta, et tagada mudeli parim jõudlus. Kui valite näiteks iga kuu muudetud välja „Klassifitseerimine”, oleks prognoosi puhul ainult viimane väärtus, ehkki sama väärtus ei pruugi ajalooliselt kehtida kliendile prognoosi loomise ajal.

1. Tehke valik **Edasi**.

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Esitab valikulise loendi ettevõtetest, mis on seotud kontodega

Lisage loend äriklientidest ja ettevõtetest, mida soovite kasutada kriteeriumite lisana. [Nende võrdluskontode](#view-prediction-results) üksikasjad hõlmavad nende churn-skoori ja kõige mõjukamaid funktsioone, mis mõjutasid nende prognoos.

1. Valige **+ Lisa kliente**.

1. Valige võrdlusalusena tegutsevad kliendid.

1. Tehke valik **Edasi**.

---

### <a name="set-update-schedule"></a>Värskendusajakava määratlemine

1. **Andmete värskendamise** etapis valige mudeli ümberõppe sagedus. See säte on oluline prognooside täpsuse värskendamiseks, kuna Customer Insightsi lisatakse uusi andmeid. Suur osa ettevõtteid saavad teha ümberõpet kord kuus ja saavutavad täpsed prognoosid.

1. Tehke valik **Edasi**.

### <a name="review-and-run-the-model-configuration"></a>Mudeli konfiguratsiooni läbivaatamine ja käitamine

Etapp **Läbivaatus ja käivitamine** näitab konfiguratsiooni kokkuvõtet ja annab võimaluse teha muudatusi enne prognoos loomist.

1. Valige **redigeeri mis** tahes juhis, mida soovite üle vaadata ja teha muudatusi.

1. Kui olete oma valikutega rahul, valige mudeli käitamise alustamiseks Salvesta **ja käivita**. Valige nupp **Valmis**. Vahekaart Minu **ennustused** kuvatakse prognoos loomise ajal. Selle protsessi lõpule viimiseks võib kuluda mitu tundi, olenevalt prognoosis kasutatud andmete hulgast.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prognoos tulemuste vaatamine

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil Minu ennustused** prognoos soovite vaadata.

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

Tulemuste lehel on kolm peamist andmete jaotist.

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

Tulemuste lehel on kolm peamist andmete jaotist.

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Mõjukate **funktsioonide analüüsi** teabeleht sisaldab nelja andmejaotist:

- Valige parempoolsel paanil üksus valikust **Parimad kliendid** või **Võrdluskliendid**. Mõlema loendi tellimisel väheneb voolavusskoori väärtus: kas punktisumma on ainult kliendi jaoks või klientide koondskoor ja teisese taseme väärtus, näiteks tootekategooria. Valitud üksus määrab selle lehe sisu.

  - **Tippkliendid**: Loetelu kümnest kliendist, kellel on nende voolavusskooride põhjal suurim ja väiksem voolavusoht.
  - **Võrdlusalused kliendid**: Loetelu kuni kümnest kliendist, kes valiti mudeli konfigureerimisel.

- **Voolavusskoor:** Kuvab parempoolsel paanil valitud üksuse skoori.

- **Churn-riski jaotus:** näitab churn-riski jaotust klientide vahel ja protsentiili, milles valitud klient on.

- **Peamised funktsioonid, mis suurendavad ja vähendavad padrunite riski:** loetleb viis peamist funktsiooni, mis suurendasid ja vähendasid paremal paanil valitud üksuse padrunite riski. Kuvab selle üksuse funktsiooni väärtuse ja selle mõju iga mõjuka funktsiooni skoorile. Samuti näidatakse iga funktsiooni keskmine väärtus nii madalate, keskmiste kui ka suurte suurustega kliendisegmentidel. See aitab valitud üksuse põhifunktsiooni väärtusi paremini kontekstueerida ja võrrelda seda madala, keskmise ja kõrge voolavusega kliendisegmentide väärtustega.

  - Madal: kontod või konto- ja teise taseme kombinatsioonid, mille skoor on vahemikus 0 kuni 0,33.
  - Keskmine: kontod või kontode kombinatsioonid ja teisesed tasemed, mille skoor jääb vahemikku 0,33–0,66.
  - Kõrge: kontod või kontode kombinatsioonid ja teisesed tasemed, mille skoor on suurem kui 0,66.

  Kui ennustate ettevõtte tasemel voolavust, võetakse kõiki kontosid arvesse voogude segmentide funktsioonide keskmiste väärtuste tuletamisel. Iga konto sekundaarse taseme voolavuse ennustuste puhul sõltub voolavuse segmentide tuletamine külgpaneelil valitud üksuse teisest tasemest. Näiteks kui kaubal on tootekategooria teisene tase (kontoritarbed), siis võetakse kaubasegmentide keskmiste funktsiooniväärtuste tuletamisel arvesse ainult neid kaupu, mille tootekategooriaks on kontoritarbed. Seda loogikat rakendatakse üksuse funktsiooniväärtuste ja keskmise väärtuse õiglase võrdluse tagamiseks nii väikese, keskmise kui ka kõrge voolavusega segmentides.

  Mõnel juhul on madala, keskmise või kõrge voolavusega segmentide keskmine väärtus tühi või pole saadaval, kuna vastavasse voolavuse segmenti pole ülaltoodud määratluse alusel vastavaid üksusi.

  Keskmiselt madalate, keskmiste ja kõrgete veergude all olevate väärtuste tõlgendamine on kategooria tunnuste (nt riik või tööstus) puhul erinev. Kuna tunnuse "keskmise" väärtuse mõiste ei kehti kategooriliste funktsioonide kohta, on nendes veergudes olevad väärtused madala, keskmise või suure kliendihulgaga segmentides olevate klientide osakaal, kellel on üksuse omaga võrreldes sama kategoorilise funktsiooni väärtus külgpaneelil valitud.

---

 > [!NOTE]
 > Selle mudeli väljundüksuses näitab ChurnScore *churni prognoositavat tõenäosust ja* IsChurn *on Binaarne silt,* mis põhineb ChurnScore’il *0*.5 lävendiga. Kui see vaikelävi teie stsenaariumi puhul ei tööta, [looge eelistatud lävega uus segment](segments.md#create-a-segment). Kõik kliendid ei pruugi olla aktiivsed kliendid. Võimalik, et mõnel neist pole pikka aega ühtegi tegevust olnud ja neid peetakse juba "voolanuks", võttes aluseks teie voolavuse määratluse. Ennustamise risk klientide jaoks, kes juba voolasid, ei ole kasulik, kuna nemad ei ole sihtrühmas.
>
> Tünni skoori vaatamiseks minge jaotisse **Andmeüksused** > **ja** vaadake selle mudeli jaoks määratletud väljundolemi andmete vahekaarti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
