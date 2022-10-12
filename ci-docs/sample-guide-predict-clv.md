---
title: Kliendi eluea väärtuse (CLV) prognoosi näidisjuhend
description: Selle näidisjuhendi abil saate proovida kliendi eluaja väärtuse prognoosi mudelit.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609633"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Kliendi eluea väärtuse (CLV) prognoosi näidisjuhend

Selles juhendis tutvustatakse näidisandmete abil Customer Insightsis prognoos läbivat näidet kliendi eluaegse väärtuse (CLV) kohta. Soovitame proovida seda prognoos [uues keskkonnas](manage-environments.md).

## <a name="scenario"></a>Stsenaarium

Contoso on ettevõte, mis toodab kvaliteetseid kohvi- ja kohvimasinaid. Nad müüvad tooteid oma Contoso Coffee veebisaidi kaudu. Ettevõte soovib mõista väärtust (tulu), mida nende kliendid saavad järgmise 12 kuu jooksul teenida. Teades oma klientide eeldatavat väärtust järgmise 12 kuu jooksul, aitab see neil juhtida oma turundustegevust kõrge väärtusega klientidele.

## <a name="prerequisites"></a>eeltingimused

- Vähemalt [kaasautori õigused](permissions.md).

## <a name="task-1---ingest-data"></a>Ülesanne 1 – andmete valmendamine

Vaadake üle artiklid [andmete allaneelamise](data-sources.md) ja [andmeallikas ühenduse loomise Power Query kohta](connect-power-query.md). Järgmine teave eeldab, et olete andmete allaneelamisega üldiselt tuttav.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>E-kaubanduse platvormist pärit kliendiandmete valmendamine

1. Looge Power Query andmeallikas nimega e-kaubandus **ja valige** tekst/CSV konnektor **.**

1. Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscontacts.

1. Andmete redigeerimise ajal valige **Teisenda ja** seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **DateOfBirth**: kuupäev
   - **CreatedOn**: kuupäev/kellaaeg/ajatsoon

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Sünniaja teisendamine kuupäevaks.":::

1. Nimetage **parempoolse paanil väljal Nimi** oma andmeallikas ümber nimeks **eCommerceContacts**

1. **Salvestage** andmeallikas.

### <a name="ingest-online-purchase-data"></a>Internetiostude andmete valmendamine

1. Lisage samasse andmeallikasse **eCommerce** veel üks andmekogum. Valige uuesti konnektor **Tekst/CSV**.

1. Sisestage **internetiostude** andmete URL https://aka.ms/ciadclassonline.

1. Andmete redigeerimise ajal valige **Teisenda ja** seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **PurchasedOn**: kuupäev/kellaaeg
   - **TotalPrice**: valuuta

1. Nimetage **külgpaani väljal Nimi** oma andmeallikas ümber nimeks **eCommercePurchases**.

1. **Salvestage** andmeallikas.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliendiandmete valmendamine lojaalsusskeemi kaudu

1. Looge andmeallikas nimega **LoyaltyScheme** ja valige **tekst-/CSV-konnektor**.

1. Sisestage püsikliendi https://aka.ms/ciadclasscustomerloyalty URL.

1. Andmete redigeerimise ajal valige **Teisenda ja** seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **DateOfBirth**: kuupäev
   - **RewardsPoints**: täisarv
   - **CreatedOn**: kuupäev/kellaaeg

1. Nimetage **parempoolse paanil väljal Nimi** oma andmeallikas ümber **loyCustomersiks**.

1. **Salvestage** andmeallikas.

### <a name="ingest-customer-data-from-website-reviews"></a>Kliendiandmete valmendamine veebisaidiarvustustest

1. Looge andmeallikas nimega **Veebisait** ja valige **teksti-/CSV-konnektor**.

1. Sisestage veebisaidi arvustuste https://aka.ms/CI-ILT/WebReviews URL.

1. Andmete redigeerimise ajal valige **Teisenda ja** seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **ReviewRating**: kümnendarv
   - **ReviewDate**: kuupäev

1. Nimetage **parempoolse paani väljal Nimi** andmeallikas **ümber arvustusteks**.

1. **Salvestage** andmeallikas.

## <a name="task-2---data-unification"></a>Ülesanne 2 – andmete koondamine

Vaadake üle artikkel [andmete ühendamise](data-unification.md) kohta. Järgmine teave eeldab, et olete andmete ühendamisega üldiselt tuttav.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>3. ülesanne – tehingute ajalooga seotud tegevuse loomine

Vaadake üle artikkel [klienditegevuste](activities.md) kohta. Järgnev teave eeldab, et olete tegevuste loomisega üldiselt tuttav.

1. Looge tegevus nimega **eCommercePurchases** koos *eCommercePurchases:eCommerce* olem ja selle primaarvõti **PurchaseId**.

1. Looge seos e-kaubanduse vahelOstmised *:e-kaubandus* ja *e-kaubandusKontaktid:e-kaubandus*, mille **puhul kontaktID** on võõrvõti kahe olemi ühendamiseks.

1. Valige **EventActivity** jaoks **TotalPrice** ja ajatempli **jaoks** **BuydOn**.

1. Valige **tegevuse tüübi** jaoks **SalesOrderLine** ja vastendage tegevuse andmed semantiliselt.

1. Käivitage tegevus.

1. Lisage veel üks tegevus ja vastendage selle väljade nimed vastavate väljadega.
   - **Tegevuse olem**: Arvustused:Veebisait
   - **Primaarvõti**: ReviewId
   - **Ajatempel**: ülevaatekuupäev
   - **Sündmuse tegevus**: ActivityTypeDisplay
   - **Lisateave**: ReviewRating
   - **Tegevuse tüüp**: ülevaade

1. Käivitage tegevus.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>4. ülesanne – kliendi eluea prognoosi konfigureerimine

Kui ühtsed kliendiprofiilid on paigas ja tegevus loodud, käivitage kliendi eluaegne väärtus (CLV) prognoos. Üksikasjalikud juhised leiate teemast [Kliendi eluaegne väärtus prognoos](predict-customer-lifetime-value.md).

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil** Loo **paanil Kliendi eluaegne väärtus** suvand Kasuta **mudelit**.

1. Seejärel valige suvand **Alustamine**.

1. Pange mudeli nimeks **OOB eCommerce CLV prognoos** ja väljundolemi nimeks **OOBeCommerceCLVPrediction**.

1. Määratlege mudeli eelistused.
   - **prognoos ajavahemik**: **12 kuud või 1 aasta**, et määratleda, kui kaugele tulevikku CLV ennustada.
   - **Aktiivsed kliendid**: **laske mudelil arvutada ostuintervall**, mis on ajavahemik, mille jooksul kliendil peab olema olnud vähemalt üks tehing aktiivseks lugemiseks.
   - **Kõrge väärtusega klient**: määratlege käsitsi kõrge väärtusega kliendid kui **30% aktiivsetest klientidest**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Eelistused, etapp CLV mudeli juhendatud kogemuses.":::

1. Tehke valik **Edasi**.

1. Tehinguajaloo andmete lisamiseks valige **nõutavate andmete** sammus **Lisa andmed**.

    :::image type="content" source="media/clv-model-required.png" alt-text="Lisage CLV-mudeli juhendatud kogemusse nõutavad andmed.":::

1. Valige **SalesOrderLine** ja olem eCommercePurchases ning valige **Edasi**. Nõutavad andmed täidetakse tegevusest automaatselt. Valige **Salvesta** ja seejärel **Edasi**.

1. Etapp Täiendavad **andmed (valikuline)** võimaldab teil lisada rohkem kliendi tegevuse andmeid, et saada rohkem teavet kliendisuhtluse kohta. Selle näite puhul valige **Lisa andmed** ja lisage veebiülevaate tegevus.

1. Tehke valik **Edasi**.

1. Andmevärskenduste **etapis** valige **mudeli ajakava jaoks Igakuine**.

1. Tehke valik **Edasi**.

1. Pärast kõigi üksikasjade läbivaatamist valige **Salvesta ja käivita**.

## <a name="task-5---review-model-results-and-explanations"></a>Ülesanne 5 – mudeli tulemuste ja selgituste läbivaatamine

Laske mudelil treenimine ja andmete hindamine lõpule viia. [Vaadake üle CLV mudeli tulemused ja selgitused](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>6. ülesanne – suure väärtusega klientide segmendi loomine

Mudeli käivitamine loob uue olemi, mis on loetletud asukohas **Andmed** > **Olemid** loendis. Saate luua mudeli loodud olemi põhjal uue kliendisegmendi.

1. Klõpsake tulemustelehel käsku **Loo segment**.

1. Looge olemi OOBeCommerceCLVPrediction **abil** reegel ja määratlege segment.
   - **Valdkond**: CLVScore
   - **Operaator**: suurem kui
   - **Väärtus**: 1500

1. Valige **Salvesta** ja **käivita** segment.

Teil on nüüd segment, mis tuvastab kliendid, kes prognooside kohaselt teenivad järgmise 12 kuu jooksul rohkem kui 1500 dollarit tulu. Kui kasutatakse rohkem andmeid, värskendatakse see segment dünaamiliselt. Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).

> [!TIP]
> Samuti saate luua segmendi prognoos mudeli jaoks lehelt Segmendid, valides **Suvandi Uus** ja käsk **Loo luureandmetest** **.** > **·** Lisateavet leiate teemast [Kiirsegmentidega](segment-quick.md) uue segmendi loomine.

[!INCLUDE [footer-include](includes/footer-banner.md)]
