---
title: Tehinguvoolavuse prognoosi näidisjuhend
description: Kasutage seda näidisjuhendit, et proovida kasutamiseks valmis tehinguvoolavuse prognoosi mudelit.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609679"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Tehinguvoolavuse prognoosi näidisjuhend

Selles juhendis selgitatakse teile otspunktnäite tehingute prognoos näidisandmete abil. Soovitame proovida seda prognoos [uues keskkonnas](manage-environments.md).

## <a name="scenario"></a>Stsenaarium

Contoso on ettevõte, mis toodab kvaliteetseid kohvi- ja kohvimasinaid. Nad müüvad tooteid oma Contoso Coffee veebisaidi kaudu. Nende eesmärk on teada saada, millised kliendid, kes tavaliselt nende tooteid regulaarselt ostavad, pole enam järgmise 60 päeva jooksul aktiivsed. Teades, millised nende kliendid **tõenäoliselt loobuvad**, aitab ettevõttel nende säilitamisele keskendudes turundusvõtteid säästa.

## <a name="prerequisites"></a>eeltingimused

- Vähemalt [kaasautori õigused](permissions.md).

## <a name="task-1---ingest-data"></a>Ülesanne 1 – andmete valmendamine

Vaadake üle artiklid [andmete allaneelamise](data-sources.md) ja [andmeallikas ühenduse loomise Power Query kohta](connect-power-query.md). Järgmine teave eeldab, et olete andmete allaneelamisega üldiselt tuttav.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>E-kaubanduse platvormist pärit kliendiandmete valmendamine

1. Looge andmeallikas nimega e-kaubandus **ja valige** tekst/ CSV konnektor **.**

1. Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscontacts.

1. Andmete redigeerimise ajal valige **Teisenda ja** seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.

   - **DateOfBirth**: kuupäev
   - **CreatedOn**: kuupäev/kellaaeg/ajatsoon

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Teisenda DoB kuupäevaks.":::

1. Nimetage **parempoolse paanil väljal Nimi** oma andmeallikas ümber nimeks **eCommerceContacts**

1. Salvestage andmeallikas.

### <a name="ingest-online-purchase-data"></a>Internetiostude andmete valmendamine

1. Lisage samasse andmeallikasse **eCommerce** veel üks andmekogum. Valige uuesti konnektor **Tekst/CSV**.

1. Sisestage veebiostude andmete URL https://aka.ms/ciadclassonline.

1. Andmete redigeerimise ajal valige **Teisenda ja** seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.

   - **PurchasedOn**: kuupäev/kellaaeg
   - **TotalPrice**: valuuta

1. Nimetage **parempoolse paanil väljal Nimi** oma andmeallikas ümber nimeks **eCommercePurchases**.

1. Salvestage andmeallikas.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliendiandmete valmendamine lojaalsusskeemi kaudu

1. Looge andmeallikas nimega **LoyaltyScheme** ja valige **tekst-/CSV-konnektor**.

1. Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscustomerloyalty.

1. Andmete redigeerimise ajal valige **Teisenda ja** seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.

   - **DateOfBirth**: kuupäev
   - **RewardsPoints**: täisarv
   - **CreatedOn**: kuupäev/kellaaeg

1. Nimetage **parempoolse paanil väljal Nimi** oma andmeallikas ümber **loyCustomersiks**.

1. Salvestage andmeallikas.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Ülesanne 4 – tehinguvoolavuse prognoosi konfigureerimine

Kui ühtsed kliendiprofiilid on paigas ja tegevus paigas, käivitage tehingumaht prognoos.

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil** Loo **suvand Kasuta mudelit** kliendiüksuse **mudelis**.

1. Valige **kandetüübi jaoks Transactional** ja seejärel **Alustage**.

1. Pange mudelile nimi **OOB e-kaubanduse tehinguvoolavuse prognoos** ja väljundolemile nimi **OOBeCommerceChurnPrediction**.

1. Tehke valik **Edasi**.

1. Määratlege mudeli eelistused.

   - **prognoos aken**: **60** päeva, et määratleda, kui kaugele tulevikku tahame ennustada.

   - **Churn definitsioon**: **60** päeva, et näidata ostuta kestust, mille järel klient loetakse kokkusurutuks.

     :::image type="content" source="media/model-levers.PNG" alt-text="Valige mudelieelistused prognoos Window ja Churn Definition.":::

1. Tehke valik **Edasi**.

1. Valige **Ostuajalugu (nõutav)** ja valige ostuajaloo jaoks **Lisa andmeid**.

1. Valige **SalesOrderLine** ja olem eCommercePurchases ning valige **Edasi**. Nõutavad andmed täidetakse tegevusest automaatselt. Valige **Salvesta** ja seejärel **Edasi**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="E-kaubanduse olemite ühendamine.":::

1. **Jätke samm Lisaandmed (valikuline)** vahele.

1. Andmevärskenduste **etapis** valige **mudeli ajakava jaoks Igakuine**.

1. Pärast kõigi üksikasjade läbivaatamist valige **Salvesta ja käivita**.

## <a name="task-5---review-model-results-and-explanations"></a>Ülesanne 5 – mudeli tulemuste ja selgituste läbivaatamine

Laske mudelil treenimine ja andmete hindamine lõpule viia. Vaadake üle churn-mudeli selgitused. Lisateavet leiate teemast [prognoos tulemuste](predict-transactional-churn.md#view-prediction-results) vaatamine.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Ülesanne 6 – suure voolavusriskiga klientide segmendi loomine

Tootmismudeli käitamisel luuakse uus olem, mis on loetletud **andmeüksustes** > **·**. Saate luua mudeli loodud olemi põhjal uue segmendi.

1. Klõpsake tulemustelehel käsku **Loo segment**.

1. Looge olemi OOBeCommerceChurnPrediction **abil** reegel ja määratlege segment.
   - **Väli**: ChurnScore
   - **Operaator**: suurem kui
   - **Väärtus**: 0,6

1. Valige **Salvesta** ja **käivita** segment.

Nüüd on teil segment, mida värskendatakse dünaamiliselt ja mis tuvastab kõrge riskiga kliendid. Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).

> [!TIP]
> Samuti saate luua segmendi prognoos mudeli jaoks lehelt Segmendid, valides **Suvandi Uus** ja käsk **Loo luureandmetest** **.** > **·** Lisateavet leiate teemast [Kiirsegmentidega](segment-quick.md) uue segmendi loomine.

[!INCLUDE [footer-include](includes/footer-banner.md)]
