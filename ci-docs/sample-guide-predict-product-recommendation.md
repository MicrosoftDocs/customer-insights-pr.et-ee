---
title: Tootesoovituste prognoosimise näidisjuhend
description: Kasutage seda näidisjuhendit, et proovida kasutamiseks valmis tootesoovituste prognoosi mudelit.
ms.date: 05/16/2022
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
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762681"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Tootesoovituste prognoosimise näidisjuhend

Selles juhendis näidatakse teile otsast lõpuni, kuidas kasutada tootesoovituste prognoosi funktsiooni koos alltoodud näidisandmetega.

## <a name="scenario"></a>Stsenaarium

Contoso on ettevõte, mis toodab kvaliteetset kohvi ja kohvimasinaid, mida müüakse veebisaidi Contoso Coffee kaudu. Nende eesmärk on mõista, milliseid tooteid nad peaksid püsiklientidele soovitama. Teades, millised kliendid **tõenäoliselt ostavad**, aitab ettevõttel nendele toodetele keskendudes turundusvõtteid säästa.

## <a name="prerequisites"></a>Eeltingimused

- Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.
- Soovitame teil järgmisi samme rakendada [uues keskkonnas](manage-environments.md).

## <a name="task-1---ingest-data"></a>Ülesanne 1 – andmete valmendamine

Vaadake üle artiklid [andmete allaneelamise](data-sources.md) ja [andmeallikate importimise kohta, kasutades Power Query konkreetselt konnektoreid](connect-power-query.md). Järgmises teabes eeldatakse, et olete andmete valmendamisega üldiselt tuttav.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>E-kaubanduse platvormist pärit kliendiandmete valmendamine

1. Looge andmeallikas nimega **eCommerce**, valige importimise suvand ja valige konnektor **Tekst/CSV**.

1. Sisestage e-kaubanduse kontaktide URL: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **DateOfBirth**: kuupäev
   - **CreatedOn**: kuupäev/kellaaeg/ajatsoon

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Sünniaja teisendamine kuupäevaks.":::

1. Muutke parempoolsel paanil väljal „Nimi“ oma andmeallika praegune nimi **Päring** nimeks **eCommerceContacts**

1. **Salvestage** andmeallikas.

### <a name="ingest-online-purchase-data"></a>Internetiostude andmete valmendamine

1. Lisage samasse andmeallikasse **eCommerce** veel üks andmekogum. Valige uuesti konnektor **Tekst/CSV**.

1. Sisestage veebiostude **andmete URL**[https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **PurchasedOn**: kuupäev/kellaaeg
   - **TotalPrice**: valuuta

1. Muutke küljepaanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **eCommercePurchases**.

1. **Salvestage** andmeallikas.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliendiandmete valmendamine lojaalsusskeemi kaudu

1. Looge andmeallikas nimega **LoyaltyScheme**, valige importimise suvand ja valige konnektor **Tekst/CSV**.

1. Sisestage e-kaubanduse kontaktide URL [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **DateOfBirth**: kuupäev
   - **RewardsPoints**: täisarv
   - **CreatedOn**: kuupäev/kellaaeg

1. Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **loyCustomers**.

1. **Salvestage** andmeallikas.

## <a name="task-2---data-unification"></a>Ülesanne 2 – andmete koondamine

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>3. toiming – tootesoovituse prognoosi konfiguratsioon

Kui ühtsed kliendiprofiilid on paigas, saame nüüd tootesoovituse prognoos käivitada.

1. Minge **Intelligents** > **Prognoos** ja valige **Tootesoovitus**.

1. Seejärel valige suvand **Alustamine**.

1. Nimetage mudeli **OOB tootesoovituse mudeli prognoos** ja väljundolemi **OOBProductRecommendationPrediction**.

1. Määratlege mudeli jaoks kolm järgmist tingimust.

   - **Toodete arv**: määrake selle väärtuseks **5**. See säte määratleb mitu toodet soovite oma klientidele soovitada.

   - **Eeldatud kordusostud**: valige **Jah** näitamaks, et soovite tooteid kaasata soovitusesse, mille teie kliendid on varem ostnud.

   - **Tagasivaate aken:** valige vähemalt **365 päeva**. See säte määtatleb, kui kaugele mudel vaatab kliendi aktiivsuse ajas tagasi, et seda kasutada oma soovituste sisendina.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Toote soovitusmudeli mudeli eelistused.":::

1. Valige toimingus **Nõutavate** andmete **lisamine väärtus Lisa andmed**.

1. Valige paanil **Andme** **lisamine olemiks ostuajaloo olemik SalesOrderLine**. Praegu pole see tõenäoliselt veel konfigureeritud. Avage paanil link, et luua tegevus järgmiste juhistega.
   1. **Sisestage tegevuse nimi** ja valige *olemina* **e-kaubanduse ostutellimused:e-kaubandus**. Esmane **võti** on *PurchaseId*.
   1. Määratlege ja nimetage seos olemiga *eCommerceContacts*:eCommerce ja valige **välisvõtmeks ContactId**.
   1. Tegevuse ühendamiseks seadke **sündmuse tegevuseks** väärtuseks *TotalHind* ja Ajatempel väärtuseks *BoughtOn*. Saate määrata rohkem välju, nagu on kirjeldatud kliendi [tegevustes](activities.md).
   1. Valige **tegevuse tüübi** puhul *SalesOrderLine*. Vastendage järgmised tegevusväljad.
      - Tellimuse rea ID: PurchaseId
      - Tellimuse ID: PurchaseId
      - Tellimuse andmed: OstetudOn
      - Toote kood: ProductId
      - Summa: Hind kokku
   1. Enne mudelikonfiguratsiooni naasmist vaadake tegevus üle ja lõpetage see.

1. Valige juhises **Tegevuste** valimine jaotises Tegevused **äsja loodud tegevus**. Valige **Edasi** ja atribuudivastendus on juba täidetud. Valige **Salvesta**.

1. Selles näidisjuhendis jätame komplekti Tooteteabe **ja** tootefiltrite **lisamine vahele**, kuna meil pole tooteteabe andmeid.

1. Määrake **jaotises Andmevärskendused** mudeli ajakava.

   Mudelit on vaja regulaarselt treenida, et see õpiks uusi mustreid uute andmete valmendamisel. Selle näite puhul valige **Iga kuu**.

1. Pärast kõigi üksikasjade läbivaatamist valige **Salvesta ja käivita**. Mudeli esmakordseks käivitamiseks kulub paar minutit.

## <a name="task-4---review-model-results-and-explanations"></a>Ülesanne 4 – mudeli tulemuste ja selgituste läbivaatamine

Laske mudelil treenimine ja andmete hindamine lõpule viia. Nüüd saate üle vaadata tootesoovituste mudeli selgitused. Lisateavet leiate teemast [Prognoos oleku ja tulemuste läbivaatamine](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tööülesanne 5 – rohkelt ostetud toodete segmendi loomine

Tootmismudeli käitamisel luuakse uus olem, mida näete, kui liigute **Andmed** > **Olemid**.

Saate luua mudeli loodud olemi põhjal uue segmendi.

1. Liikuge jaotisse **Segmendid**. Valige **Uus** ja valige **Loo intelligentsusest**.

   ![Segmendi loomine mudeli väljundiga.](media/segment-intelligence.png)

1. Valige lõpp-punkt **OOBProductRecommendationModelPrediction** ja määratlege segment.

   - Väli: ProductID
   - Väärtus: valige kolm peamist toote ID-d

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Saate mudelitulemitest luua segmendi.":::

Nüüd on teil dünaamiliselt värskendatud segment, mis tuvastab kliendid, kes võivad olla huvitatud kolme kõige soovitatavama toote ostmisest.

Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
