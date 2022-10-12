---
title: Tootesoovituste prognoosimise näidisjuhend
description: Kasutage seda näidisjuhendit, et proovida kasutamiseks valmis tootesoovituste prognoosi mudelit.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610139"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Tootesoovituste prognoosimise näidisjuhend

Selles juhendis tutvustatakse tootesoovituste prognoos näidisandmete abil. Soovitame proovida seda prognoos [uues keskkonnas](manage-environments.md).

## <a name="scenario"></a>Stsenaarium

Contoso on ettevõte, mis toodab kvaliteetseid kohvi- ja kohvimasinaid. Nad müüvad tooteid oma Contoso Coffee veebisaidi kaudu. Nende eesmärk on mõista, milliseid tooteid nad peaksid püsiklientidele soovitama. Teadmine, mida kliendid tõenäolisemalt **ostavad**, aitab neil turundustegevust säästa, keskendudes konkreetsetele üksustele.

## <a name="prerequisites"></a>eeltingimused

- Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.

## <a name="task-1---ingest-data"></a>Ülesanne 1 – andmete valmendamine

Vaadake üle artiklid [andmete allaneelamise](data-sources.md) ja [andmeallikas ühenduse loomise Power Query kohta](connect-power-query.md). Järgmine teave eeldab, et olete andmete allaneelamisega üldiselt tuttav.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>E-kaubanduse platvormist pärit kliendiandmete valmendamine

1. Looge Power Query andmeallikas nimega e-kaubandus **ja valige** tekst/CSV konnektor **.**

1. Sisestage e-kaubanduse kontaktide URL:https://aka.ms/ciadclasscontacts.

1. Andmete redigeerimise ajal valige **Teisenda ja** seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **DateOfBirth**: kuupäev
   - **CreatedOn**: kuupäev/kellaaeg/ajatsoon

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Sünniaja teisendamine kuupäevaks.":::

1. Nimetage **parempoolse paanil väljal Nimi** oma andmeallikas ümber nimeks **eCommerceContacts**.

1. **Salvestage** andmeallikas.

### <a name="ingest-online-purchase-data"></a>Internetiostude andmete valmendamine

1. Lisage samasse andmeallikasse **eCommerce** veel üks andmekogum. Valige uuesti konnektor **Tekst/CSV**.

1. Sisestage veebiostude andmete URL https://aka.ms/ciadclassonline.

1. Andmete redigeerimise ajal valige **Teisenda ja** seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **PurchasedOn**: kuupäev/kellaaeg
   - **TotalPrice**: valuuta

1. Nimetage **külgpaani väljal Nimi** oma andmeallikas ümber nimeks **eCommercePurchases**.

1. **Salvestage** andmeallikas.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliendiandmete valmendamine lojaalsusskeemi kaudu

1. Looge andmeallikas nimega **LoyaltyScheme** ja valige **tekst-/CSV-konnektor**.

1. Sisestage püsiklientide URL https://aka.ms/ciadclasscustomerloyalty.

1. Andmete redigeerimise ajal valige **Teisenda ja** seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **DateOfBirth**: kuupäev
   - **RewardsPoints**: täisarv
   - **CreatedOn**: kuupäev/kellaaeg

1. Nimetage **parempoolse paanil väljal Nimi** oma andmeallikas ümber **loyCustomersiks**.

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

## <a name="task-4---configure-product-recommendation-prediction"></a>4. toiming – tootesoovituse prognoosi konfiguratsioon

Kui ühtsed kliendiprofiilid on paigas ja tegevus loodud, käivitage tootesoovitus prognoos.

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil** Loo **paanil Tootesoovitused (eelvaade)** suvand Kasuta **mudelit**.

1. Seejärel valige suvand **Alustamine**.

1. Nimetage mudeli **OOB tootesoovituse mudeli prognoos** ja väljundolemi **OOBProductRecommendationPrediction**.

1. Tehke valik **Edasi**.

1. Määratlege mudeli eelistused.
   - **Toodete** arv: **5**, et määratleda, kui palju tooteid soovite oma klientidele soovitada.
   - **Eeldatavad** korduvad ostud: **jah**, et lisada soovitusesse varem ostetud tooted.
   - **Tagasivaade:** **365 päeva**, et määratleda, kui kaugele mudel tagasi vaatab, enne kui toote uuesti soovitate.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Toote soovitusmudeli mudeli eelistused.":::

1. Tehke valik **Edasi**.

1. **Valige etapis Ostuajaloo** lisamine käsk **Lisa andmed**.

1. Valige **SalesOrderLine** ja olem eCommercePurchases ning valige **Edasi**. Nõutavad andmed täidetakse tegevusest automaatselt. Valige **Salvesta** ja seejärel **Edasi**.

1. **Jätke vahele etapid Tooteteabe** lisamine ja **Tootefiltrid**, kuna meil pole tooteteabe andmeid.

1. Andmevärskenduste **etapis** valige **mudeli ajakava jaoks Igakuine**.

1. Tehke valik **Edasi**.

1. Pärast kõigi üksikasjade läbivaatamist valige **Salvesta ja käivita**.

## <a name="task-5---review-model-results-and-explanations"></a>Ülesanne 5 – mudeli tulemuste ja selgituste läbivaatamine

Laske mudelil treenimine ja andmete hindamine lõpule viia. [Vaadake üle tootesoovituse mudeli selgitused](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Tööülesanne 6 – rohkelt ostetud toodete segmendi loomine

Mudeli käivitamine loob uue olemi, mis on loetletud asukohas **Andmed** > **Olemid** loendis. Saate luua mudeli loodud olemi põhjal uue segmendi.

1. Klõpsake tulemustelehel käsku **Loo segment**.

1. Looge reegel olemi OOBProductRecommendationModelPrediction **abil** ja määratlege segment.
   - **Väli**: ProductID
   - **Väärtus**: valige toote ID-de esikolmik

1. Valige **Salvesta** ja **käivita** segment.

Nüüd on teil dünaamiliselt värskendatav segment, mis tuvastab kliendid, kes võivad olla huvitatud viie kõige soovitatavama toote ostmisest. Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).

> [!TIP]
> Samuti saate luua segmendi prognoos mudeli jaoks lehelt Segmendid, valides **Suvandi Uus** ja käsk **Loo luureandmetest** **.** > **·** Lisateavet leiate teemast [Kiirsegmentidega](segment-quick.md) uue segmendi loomine.

[!INCLUDE [footer-include](includes/footer-banner.md)]
