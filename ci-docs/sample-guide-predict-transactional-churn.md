---
title: Tehinguvoolavuse prognoosi näidisjuhend
description: Kasutage seda näidisjuhendit, et proovida kasutamiseks valmis tehinguvoolavuse prognoosi mudelit.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741314"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Tehinguvoolavuse prognoosi näidisjuhend

Selles juhendis näidatakse teile otsast lõpuni, kuidas kasutada Customer Insightsis tehinguvoolavuse prognoosi funktsiooni koos alltoodud andmetega. Kõik selles juhendis kasutatud andmed ei ole tegelikud kliendiandmed ja need kuuluvad Contoso andmekogumi hulka, mis asub teie Customer Insightsi tellimuse keskkonnas *Demo*.

## <a name="scenario"></a>Stsenaarium

Contoso on ettevõte, mis toodab kvaliteetset kohvi ja kohvimasinaid, mida müüakse veebisaidi Contoso Coffee kaudu. Nende eesmärk on teada saada, millised kliendid, kes tavaliselt nende tooteid regulaarselt ostavad, pole enam järgmise 60 päeva jooksul aktiivsed. Teades, millised nende kliendid **tõenäoliselt loobuvad**, aitab ettevõttel nende säilitamisele keskendudes turundusvõtteid säästa.

## <a name="prerequisites"></a>Eeltingimused

- Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.
- Soovitame teil järgmisi samme rakendada [uues keskkonnas](manage-environments.md).

## <a name="task-1---ingest-data"></a>Ülesanne 1 – andmete valmendamine

Vaadake üle artiklid [andmete allaneelamise](data-sources.md) ja [andmeallikate importimise kohta, kasutades Power Query konkreetselt konnektoreid](connect-power-query.md). Järgmises teabes eeldatakse, et olete andmete valmendamisega üldiselt tuttav. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>E-kaubanduse platvormist pärit kliendiandmete valmendamine

1. Looge andmeallikas nimega **eCommerce**, valige importimise suvand ja valige konnektor **Tekst/CSV**.

1. Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscontacts.

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.

   - **DateOfBirth**: kuupäev
   - **CreatedOn**: kuupäev/kellaaeg/ajatsoon

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Teisenda DoB kuupäevaks.":::

1. Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **eCommerceContacts**

1. Salvestage andmeallikas.

### <a name="ingest-online-purchase-data"></a>Internetiostude andmete valmendamine

1. Lisage samasse andmeallikasse **eCommerce** veel üks andmekogum. Valige uuesti konnektor **Tekst/CSV**.

1. Sisestage **internetiostude** andmete URL https://aka.ms/ciadclassonline.

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.

   - **PurchasedOn**: kuupäev/kellaaeg
   - **TotalPrice**: valuuta
   
1. Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **eCommercePurchases**.

1. Salvestage andmeallikas.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliendiandmete valmendamine lojaalsusskeemi kaudu

1. Looge andmeallikas nimega **LoyaltyScheme**, valige importimise suvand ja valige konnektor **Tekst/CSV**.

1. Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscustomerloyalty.

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.

   - **DateOfBirth**: kuupäev
   - **RewardsPoints**: täisarv
   - **CreatedOn**: kuupäev/kellaaeg

1. Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **loyCustomers**.

1. Salvestage andmeallikas.

## <a name="task-2---data-unification"></a>Ülesanne 2 – andmete koondamine

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Ülesanne 3 – tehinguvoolavuse prognoosi konfigureerimine

Kui ühtsed kliendiprofiilid on paigas, saame nüüd käivitada tehingulõigu prognoos. Üksikasjalikke juhiseid leiate artiklist [Kanne prognoos](predict-transactional-churn.md). 

1. Minge jaotisse **Ärianalüüs** > **Avastamine** ja valige kasutamiseks **Kliendivoolavuse mudel**.

1. Valige suvand **Tehingupõhine** ja valige **Alusta**.

1. Pange mudelile nimi **OOB e-kaubanduse tehinguvoolavuse prognoos** ja väljundolemile nimi **OOBeCommerceChurnPrediction**.

1. Määratlege voolavuse mudeli jaoks kaks tingimust.

   * **Prognoosiajavahemik**: **vähemalt 60** päeva. See säte määratleb, kui kaugel tulevikus tahame kliendivoolavust ennustada.

   * **Voolavuse määratlus**: **vähemalt 60** päeva. Ostudeta aeg, pärast mida loetakse klient loobunuks.

     :::image type="content" source="media/model-levers.PNG" alt-text="Mudeli suvandite „Prognoosiajavahemik“ ja „Voolavuse määratlus“ valimine.":::

1. Valige **Ostuajalugu (nõutav)** ja valige ostuajaloo jaoks **Lisa andmeid**.

1. Lisage olem **eCommercePurchases: eCommerce** ja vastendage e-kaubandusest pärit väljad asjaomaste mudelile vajalike väljadega.

1. Ühendage olem **eCommercePurchases: eCommerce** olemiga **eCommerceContacts: eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="E-kaubanduse olemite ühendamine.":::

1. Valige **Järgmine**, et määratleda mudeli ajakava.

   Mudelit on vaja regulaarselt treenida, et see õpiks uusi mustreid uute andmete valmendamisel. Selle näite puhul valige **Iga kuu**.

1. Pärast kõigi üksikasjade läbivaatamist valige **Salvesta ja käivita**.

## <a name="task-4---review-model-results-and-explanations"></a>Ülesanne 4 – mudeli tulemuste ja selgituste läbivaatamine

Laske mudelil treenimine ja andmete hindamine lõpule viia. Nüüd saate vaadata churn mudeli selgitusi. Lisateavet leiate teemast [Prognoos oleku ja tulemuste läbivaatamine](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Ülesanne 5 – suure voolavusriskiga klientide segmendi loomine

Tootmismudeli käitamisel luuakse uus olem, mida näete, kui liigute **Andmed** > **Olemid**.   

Saate luua mudeli loodud olemi põhjal uue segmendi.

1.  Liikuge jaotisse **Segmendid**. Valige **Uus** ja seejärel **Loo üksusest** > **Ärianalüüs**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Segmendi loomine mudeli väljundiga.":::

1. **Valige lõpp-punkt OOBeCommerceChurnPrediction** ja määratlege segment. 
   - Väli: ChurnScore
   - Tehtemärk: suurem kui
   - Väärtus: 0,6

Nüüd on teil dünaamiliselt värskendatud segment, mis tuvastab kõrge suurusega riskiga kliendid.

Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
