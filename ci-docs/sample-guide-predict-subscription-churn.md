---
title: Tellimusevoolavuse prognoosi näidisjuhend
description: Kasutage seda näidisjuhendit, et proovida kasutamiseks valmis tellimusevoolavuse prognoosi mudelit.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741406"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Tellimusevoolavuse prognoosi näidisjuhend

Selles juhendis näidatakse teile otsast lõpuni, kuidas kasutada tellimusevoolavuse prognoosi funktsiooni koos alltoodud näidisandmetega. 

## <a name="scenario"></a>Stsenaarium

Contoso on ettevõte, mis toodab kvaliteetset kohvi ja kohvimasinaid, mida müüakse veebisaidi Contoso Coffee kaudu. Hiljuti hakkasid nad pakkuma kordustellimusi, et kliendid saaksid kohvi regulaarselt. Nende eesmärk on mõista, millised tellimusega liitunud kliendid võivad järgmise paari kuu jooksul tellimuse tühistada. Teades, millised nende kliendid **tõenäoliselt loobuvad**, aitab ettevõttel nende säilitamisele keskendudes turundusvõtteid säästa.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Sünniaja teisendamine kuupäevaks.":::

1. Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **eCommerceContacts**

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

### <a name="ingest-subscription-information"></a>Tellimuste teabe valmendamine

1. Looge andmeallikas nimega **SubscriptionHistory**, valige importimise suvand ja valige konnektor **Tekst/CSV**.

1. Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadchurnsubscriptionhistory.

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.

   - **SubscriptioID**: täisarv
   - **SubscriptionAmount**: valuuta
   - **SubscriptionEndDate**: kuupäev/kellaaeg
   - **SubscriptionStartDate**: kuupäev/kellaaeg
   - **TransactionDate**: kuupäev/kellaaeg
   - **IsRecurring**: tõene/väär
   - **Is_auto_renew**: tõene/väär
   - **RecurringFrequencyInMonths**: täisarv

1. Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **SubscriptionHistory**.

1. Salvestage andmeallikas.

### <a name="ingest-customer-data-from-website-reviews"></a>Kliendiandmete valmendamine veebisaidiarvustustest

1. Looge andmeallikas nimega **Veebisait**, valige importimise suvand ja valige konnektor **Tekst/CSV**.

1. Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasswebsite.

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.

   - **ReviewRating**: täisarv
   - **ReviewDate**: kuupäev

1. Muutke parempoolsel paanil väljal „Nimi“ oma andmeallika praegune nimi **Päring** nimeks **webReviews**.

## <a name="task-2---data-unification"></a>Ülesanne 2 – andmete koondamine

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>Ülesanne 3 – tellimusevoolavuse prognoosi konfigureerimine

Kui kliendiprofiilid on koondatud, saame käivitada tellimusevoolavuse prognoosi. Üksikasjalikke juhiseid leiate artiklist [Tellimuse prognoos](predict-subscription-churn.md). 

1. Minge jaotisse **Ärianalüüs** > **Avastamine** ja valige kasutamiseks **Kliendivoolavuse mudel**.

1. Valige suvand **Tellimus** ja valige **Alusta**.

1. Pange mudelile nimi **OOB tellimusevoolavuse prognoos** ja väljundolemile nimi **OOBSubscriptionChurnPrediction**.

1. Määratlege voolavuse mudeli jaoks kaks tingimust.

   * **Päevi pärast tellimuse lõppu**: **vähemalt 60** päeva. Kui klient ei uuenda tellimust selle perioodi jooksul pärast tellimuse lõppemist, loetakse ta loobunuks. 

   * **Voolavuse määratlus**: **vähemalt 93** päeva. Aeg, mida mudel kasutab selle prognoosimiseks, millised kliendid võivad loobuda. Mida suurem on ajavahemik, seda ebatäpsemad on tulemused.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Mudeli suvandite „Prognoosiajavahemik“ ja „Voolavuse määratlus“ valimine.":::

1. Valige **Lisa nõutavad andmed** ja valige tellimuseajaloo jaoks **Lisa andmeid**.

1. Lisage olem **eSubscription: SubscriptionHistory** ja vastendage e-kaubandusest pärit väljad asjaomaste mudelile vajalike väljadega.

1. Ühendage olem **Subscription: SubscriptionHistory** olemiga **eCommerceContacts: eCommerce**, pane seosele nimi **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="E-kaubanduse olemite ühendamine.":::

1. Lisage klienditegevuste jaotises olem **webReviews: Website** ja vastendage olemist webReviews pärit väljad asjaomaste mudelile vajalike väljadega. 
   - Primaarvõti: ReviewId
   - Ajatempel: ReviewDate
   - Sündmus: ReviewRating

1. Tegevuse konfigureerimine veebisaidiarvustuste jaoks. Valige tegevus **Ülevaatamine** ja ühendage olem **webReviews: Website** olemiga **eCommerceContacts: eCommerce**.

1. Valige **Järgmine**, et määratleda mudeli ajakava.

   Mudelit on vaja regulaarselt treenida, et see õpiks uusi mustreid uute andmete valmendamisel. Selle näite puhul valige **Iga kuu**.

1. Pärast kõigi üksikasjade läbivaatamist valige **Salvesta ja käivita**.

## <a name="task-4---review-model-results-and-explanations"></a>Ülesanne 4 – mudeli tulemuste ja selgituste läbivaatamine

Laske mudelil treenimine ja andmete hindamine lõpule viia. Nüüd saate üle vaadata tellimusevoolavuse mudeli selgitused. Lisateavet leiate teemast [Prognoos oleku ja tulemuste läbivaatamine](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Ülesanne 5 – suure voolavusriskiga klientide segmendi loomine

Tootmismudeli käitamisel luuakse uus olem, mida näete, kui liigute **Andmed** > **Olemid**.   

Saate luua mudeli loodud olemi põhjal uue segmendi.

1.  Liikuge jaotisse **Segmendid**. Valige **Uus** ja seejärel **Loo üksusest** > **Ärianalüüs**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Segmendi loomine mudeli väljundiga.":::

1. Valige lõpp-punkt **OOBSubscriptionChurnPrediction** ja määratlege segment. 
   - Väli: ChurnScore
   - Tehtemärk: suurem kui
   - Väärtus: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Tellimusevoolavuse segmendi seadistamine.":::

Teil on nüüd segment, mida värskendatakse dünaamiliselt ja mis tuvastab selle tellimusäri jaoks suure voolavusriskiga kliente.

Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]