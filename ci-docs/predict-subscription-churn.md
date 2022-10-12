---
title: Ennusta tellimust (sisaldab videot)
description: Saate prognoosida, kas on oht, et klient ei kasuta enam teie ettevõtte kordustellimuse tooteid või teenuseid.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610231"
---
# <a name="predict-subscription-churn"></a>Kordustellimuste voolavuse prognoosimine

Saate prognoosida, kas on oht, et klient ei kasuta enam teie ettevõtte kordustellimuse tooteid või teenuseid. Tellimuse andmed sisaldavad aktiivseid ja passiivseid tellimusi iga kliendi kohta, nii et kliendi ID kohta on mitu kirjet.

Teil peavad olema äriteadmised, et mõista, mida churn teie ettevõtte jaoks tähendab. Toetame ajapõhiseid tünnide definitsioone, mis tähendab, et klient loetakse pärast tellimuse lõppemist teatud aja jooksul kokku kukkunuks.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Proovige tellimustöid prognoos näidisandmete abil: [tellimuse churn prognoos näidisjuhend](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>eeltingimused

- Vähemalt [kaasautori õigused](permissions.md).
- Vähemalt 10 kliendiprofiili, eelistatavalt rohkem kui 1,000 unikaalset klienti.
- Kliendiidentifikaator – kordumatu identifikaator tellimuste vastavusse viimiseks teie klientidega.
- Tellimuse andmed vähemalt kahekordse valitud ajaakna kohta. Eelistatavalt kahe kuni kolme aasta tellimisandmed. Tellimuse ajalugu peab sisaldama järgmist.
  - **Tellimuse ID:** tellimuse kordumatu identifikaator.
  - **Tellimuse lõppkuupäev:** kuupäev, mil tellimus kliendi jaoks aegub.
  - **Tellimuse alguskuupäev:** kuupäev, mil tellimus kliendi jaoks algab.
  - **Kande kuupäev:** tellimuse muutmise kuupäev. Näiteks klient ostab või tühistab kordustellimuse.
  - **Kas tegemist on korduva tellimusega:** kahendjärjestuse tõene/vale väli, mis määrab, kas tellimust uuendatakse sama tellimuse ID-ga ilma kliendi sekkumiseta.
  - **Korduste sagedus (kuudes):** korduvate tellimuste puhul kuu, mil tellimust uuendatakse. Näiteks aastane kordustellimus, mis uueneb kliendi jaoks automaatselt igal aastal, selle väärtuseks on 12.
  - **Tellimuse summa**: valuuta summa, mille klient maksab tellimuse uuendamise eest. See võib aidata tuvastada erinevate kordustellimuste tasemete mustreid.
- Vähemalt kaks tegevuskirjet 50% klientide kohta, kelle kohta soovite arvutada. Kliendi tegevused peavad hõlmama järgmist:
  - **Primaarvõti:** tegevuse kordumatu identifikaator. Näiteks veebisaidi külastus või kasutuse kirje, mis näitab, et klient vaatas teleseriaali osa.
  - **Ajatempel:** primaarvõtmega tuvastatud sündmuse kuupäev ja kellaaeg.
  - **Sündmus:** sündmuse nimi, mida soovite kasutada. Näiteks nimega „UserAction” video voogesituse teenuse väljal võiks olla väärtus „Vaadatud”.
  - **Üksikasjad:** sündmuse üksikasjalik teave. Näiteks nimega „ShowTitle” video voogesituse teenuse väljal võiks olla kliendi vaadatud video väärtus.
- Esitatud olemi andmeväljal puuduvad väärtused vähem kui 20%.

## <a name="create-a-subscription-churn-prediction"></a>Kordustellimuse voolavuse prognoosi loomine

Valige **Salvesta mustand** igal ajal, et salvestada prognoos mustandina. Mustand prognoos kuvatakse vahekaardil **Minu ennustused**.

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil** Loo **paanil Kliendituuma mudel** **suvand Kasuta mudelit**.

1. Valige **tükitüübi jaoks Tellimus** ja seejärel **Alustage**.

1. **Nimeta see mudel** ja **Väljundi olemi nimi**, et neid muudest mudelitest või olemitest eristada.

1. Tehke valik **Edasi**.

### <a name="define-customer-churn"></a>Määratlege kliendi teenusest loobumine

1. Sisestage arv **Päevi möödunud kordustellimuse lõppemisest**, mida teie ettevõte peab olekuks, mil kliendivoolavus on toimunud. See periood on tavaliselt seotud äritegevusega, nagu pakkumised või muud turundustegevused, mis püüavad vältida kliendi kaotamist.

1. Sisestage päevade arv **, et uurida tulevikku, et ennustada trügimist**. Näiteks ennustage oma klientide voolavusriski järgmise 90 päeva jooksul, et kohandada oma klientide säilitamise jõupingutusi. Pöördumisriski ennustamine pikemaks või lühemaks perioodiks võib muuta pöördumisriski profiili tegurite käsitlemise keerulisemaks, sõltuvalt teie konkreetsetest ärinõuetest.

1. Tehke valik **Edasi**.

### <a name="add-required-data"></a>Lisage nõutud andmed

1. Valige **Tellimuse ajaloo** jaoks **Lisa andmed**.

1. Valige semantilise tegevuse tüüp **Tellimus**, mis sisaldab nõutavat tellimuse ajaloo teavet. Kui tegevust pole seadistatud, valige **siin** ja looge see.

1. Kui tegevuste atribuudid olid tegevuse loomisel semantiliselt vastendatud, valige jaotises **Tegevused** konkreetsed atribuudid või olem, millele soovite arvutuses keskenduda. Kui semantilist vastendamist ei toimunud, valige Redigeeri **ja** vastendage oma andmed.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Nõutavate andmete lisamine subscription churn mudeli jaoks":::

1. Valige **Edasi** ja vaadake üle selle mudeli jaoks vajalikud atribuudid.

1. Valige **Salvesta**.

1. Valige **Lisa andmed** kliendi tegevuste **jaoks**.

1. Valige semantilise tegevuse tüüp, mis annab kliendi tegevuse teabe. Kui tegevust pole seadistatud, valige **siin** ja looge see.

1. Kui tegevuste atribuudid olid tegevuse loomisel semantiliselt vastendatud, valige jaotises **Tegevused** konkreetsed atribuudid või olem, millele soovite arvutuses keskenduda. Kui semantilist vastendamist ei toimunud, valige Redigeeri **ja** vastendage oma andmed.

1. Valige **Edasi** ja vaadake üle selle mudeli jaoks vajalikud atribuudid.

1. Valige **Salvesta**.

1. Lisage veel tegevusi või valige **Edasi**.

### <a name="set-update-schedule"></a>Värskendusajakava määratlemine

1. Valige mudeli ümberõppe sagedus. See säte on oluline prognooside täpsuse värskendamiseks, kuna Customer Insightsis kasutatakse uusi andmeid. Suur osa ettevõtteid saavad teha ümberõpet kord kuus ja saavutavad täpsed prognoosid.

1. Tehke valik **Edasi**.

### <a name="review-and-run-the-model-configuration"></a>Mudeli konfiguratsiooni läbivaatamine ja käitamine

Etapp **Läbivaatus ja käivitamine** näitab konfiguratsiooni kokkuvõtet ja annab võimaluse teha muudatusi enne prognoos loomist.

1. Valige **redigeeri mis** tahes juhis, mida soovite üle vaadata ja teha muudatusi.

1. Kui olete oma valikutega rahul, valige mudeli käitamise alustamiseks Salvesta **ja käivita**. Valige nupp **Valmis**. Vahekaart Minu **ennustused** kuvatakse prognoos loomise ajal. Selle protsessi lõpule viimiseks võib kuluda mitu tundi, olenevalt prognoosis kasutatud andmete hulgast.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Prognoos tulemuste vaatamine

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil Minu ennustused** prognoos soovite vaadata.

Tulemuste lehel on kolm peamist andmete jaotist.

- **Koolitusmudeli toimivus**: hinded A, B või C näitavad prognoos toimivust ja aitavad teil teha otsuse väljundolemisse salvestatud tulemuste kasutamise kohta.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Mudeli punktisumma teabevälja kujutis koos A-klassiga.":::

  Astmed määratletakse vastavalt järgmistele reeglitele.
  - **A** kui mudel ennustas täpselt vähemalt 50% kogu ennustustest ja kui täpsete prognooside protsent klientide kohta, kes kükitasid, on suurem kui ajalooline keskmine churn rate vähemalt 10%.
  - **B**, kui mudel ennustas täpselt vähemalt 50% kogu ennustustest ja kui täpsete prognooside protsent klientide kohta, kes kükitasid, on kuni 10% suurem kui ajalooline keskmine churn rate.
  - **C**, kui mudel ennustas täpselt vähem kui 50% kogu ennustustest või kui täpsete prognooside protsent klientide kohta, kes kükitasid, on väiksem kui ajalooline keskmine churn rate.
  
- **Voolavuse tõenäosus (klientide arv)**: Kliendirühmad nende prognoositud voolavuse riski põhjal. Valikuliselt [looge kõrge riskiga klientide](prediction-based-segment.md) segmendid. Sellised segmendid aitavad mõista, kus segmendi liikmelisuse sulgemiskuupäev peaks olema.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Graafik, mis kuvab voolavuse tulemuste jaotust, jagatuna vahemikeks 0–100% vahel":::

- **Kõige mõjukamad tegurid:** prognoosi loomisel võetakse arvesse paljusid tegureid. Mudeli loodavate koondprognooside jaoks arvutatakse iga teguri olulisus. Kasutage neid tegureid oma prognoos tulemuste valideerimiseks. Või kasutage seda teavet hiljem segmentide [loomiseks](.//prediction-based-segment.md), mis võivad aidata mõjutada klientide riski.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Loend mõjukate teguritega ja nende olulisus voolavuse tulemuse prognoosimisel.":::

> [!NOTE]
> Selle mudeli väljundüksuses on ChurnScore *churn’i prognoositud tõenäosus ja* IsChurn *on Binaarne silt,* mis põhineb ChurnScore’il *0*.5 lävendiga. Kui see vaikelävi teie stsenaariumi puhul ei tööta, [looge eelistatud lävega uus segment](segments.md). Tünni skoori vaatamiseks minge jaotisse **Andmeüksused** > **ja** vaadake selle mudeli jaoks määratletud väljundolemi andmete vahekaarti.

[!INCLUDE [footer-include](includes/footer-banner.md)]
