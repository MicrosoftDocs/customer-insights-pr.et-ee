---
title: Tellimusevoolavuse prognoosi näidisjuhend
description: Kasutage seda näidisjuhendit, et proovida kasutamiseks valmis tellimusevoolavuse prognoosi mudelit.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610001"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Tellimusevoolavuse prognoosi näidisjuhend

Selles juhendis selgitatakse teile otspunktnäitu tellimuste prognoos näidisandmete abil. Soovitame proovida seda prognoos [uues keskkonnas](manage-environments.md).

## <a name="scenario"></a>Stsenaarium

Contoso on ettevõte, mis toodab kvaliteetseid kohvi- ja kohvimasinaid. Nad müüvad tooteid oma Contoso Coffee veebisaidi kaudu. Hiljuti hakkasid nad pakkuma kordustellimusi, et kliendid saaksid kohvi regulaarselt. Nende eesmärk on mõista, millised tellitud kliendid võivad oma tellimuse järgmise paari kuu jooksul tühistada. Teadmine, milline nende klientidest **tõenäoliselt trügib**, võib aidata neil turundustegevust kokku hoida, keskendudes nende hoidmisele.

## <a name="prerequisites"></a>eeltingimused

- Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.

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

1. Salvestage andmeallikas.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliendiandmete valmendamine lojaalsusskeemi kaudu

1. Looge andmeallikas nimega **LoyaltyScheme** ja valige **tekst-/CSV-konnektor**.

1. Sisestage püsikliendi https://aka.ms/ciadclasscustomerloyalty URL.

1. Andmete redigeerimise ajal valige **Teisenda ja** seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **DateOfBirth**: kuupäev
   - **RewardsPoints**: täisarv
   - **CreatedOn**: kuupäev/kellaaeg

1. Nimetage **parempoolse paanil väljal Nimi** oma andmeallikas ümber **loyCustomersiks**.

1. Salvestage andmeallikas.

### <a name="ingest-subscription-information"></a>Tellimuste teabe valmendamine

1. Looge andmeallikas nimega **SubscriptionHistory** ja valige **tekst-/CSV-konnektor**.

1. Sisestage tellimuste URL https://aka.ms/ciadchurnsubscriptionhistory.

1. Andmete redigeerimise ajal valige **Teisenda ja** seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **SubscriptioID**: täisarv
   - **SubscriptionAmount**: valuuta
   - **SubscriptionEndDate**: kuupäev/kellaaeg
   - **SubscriptionStartDate**: kuupäev/kellaaeg
   - **TransactionDate**: kuupäev/kellaaeg
   - **IsRecurring**: tõene/väär
   - **Is_auto_renew**: tõene/väär
   - **RecurringFrequencyInMonths**: täisarv

1. Nimetage **parempoolse paani väljal Nimi** oma andmeallikas ümber subscriptionhistory’ks **·**.

1. Salvestage andmeallikas.

### <a name="ingest-customer-data-from-website-reviews"></a>Kliendiandmete valmendamine veebisaidiarvustustest

1. Looge andmeallikas nimega **Veebisait** ja valige **teksti-/CSV-konnektor**.

1. Sisestage veebisaidi arvustuste https://aka.ms/ciadclasswebsite URL.

1. Andmete redigeerimise ajal valige **Teisenda ja** seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **ReviewRating**: täisarv
   - **ReviewDate**: kuupäev

1. Nimetage **parempoolse paanil väljal Nimi** oma andmeallikas ümber nimeks **WebReviews**.

## <a name="task-2---data-unification"></a>Ülesanne 2 – andmete koondamine

Vaadake üle artikkel [andmete ühendamise](data-unification.md) kohta. Järgmine teave eeldab, et olete andmete ühendamisega üldiselt tuttav.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>3. ülesanne – tehingute ajalooga seotud tegevuse loomine

Vaadake üle artikkel [klienditegevuste](activities.md) kohta. Järgnev teave eeldab, et olete tegevuste loomisega üldiselt tuttav.

1. Looge tegevus nimega **SubscriptionHistory** koos *tellimuse* olemi ja selle primaarvõtmega **CustomerID**.

1. Looge seos SubscriptionHistory:Subscription *ja eCommerceContacts*:eCommerce *, kus* KliendiID **on välisvõti kahe olemi ühendamiseks**.

1. Valige **ajatempli** eventactivity **jaoks SubscriptionType** ja **SubscriptionEndDate** **·**.

1. Valige **Tegevuse tüübi** jaoks **Tellimus** ja vastendage tegevuse andmed semantiliselt.

1. Käivitage tegevus.

1. Lisage veel üks tegevus ja vastendage selle väljade nimed vastavate väljadega.
   - Klienditegevuse olem: Reviews:Website
   - Esmane võti: Website.Reviews.ReviewId
   - Ajatempel: Website.Reviews.ReviewDate
   - Sündmus (tegevuse nimi): Website.Reviews.ActivityTypeDisplay
   - Üksikasjad (summa või väärtus): Website.Reviews.ReviewRating

1. Käivitage tegevus.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Ülesanne 4 – tellimusevoolavuse prognoosi konfigureerimine

Kui ühtsed kliendiprofiilid on paigas ja tegevus loodud, käivitage tellimus prognoos. Täpsemad juhised leiate teemast [Prognoos](predict-subscription-churn.md).

1. Minge **luureprognooside** > **juurde**.

1. **Valige vahekaardil** Loo **paanil Kliendituuma mudel** **suvand Kasuta mudelit**.

1. Valige **tükitüübi jaoks Tellimus** ja seejärel **Alustage**.

1. Pange mudelile nimi **OOB tellimusevoolavuse prognoos** ja väljundolemile nimi **OOBSubscriptionChurnPrediction**.

1. Määratlege mudeli eelistused.
   - **Päevad pärast tellimuse lõppu**: **60** päeva, et näidata, et klient loetakse katkestatuks, kui ta ei uuenda tellimust selle aja jooksul pärast tellimuse lõppu.
   - **Päevad tuleviku uurimiseks, et ennustada churn**: **93** päeva, mis on kestus, mille jooksul mudel ennustab, millised kliendid võivad churn. Mida suurem on ajavahemik, seda ebatäpsemad on tulemused.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Valige mudeli eelistused ja churn definitsioon.":::

1. Tehke valik **Edasi**.

1. **Valige etapis** Nõutavad andmed **tellimuse ajaloo pakkumiseks Lisa andmeid**.

1. Valige **Tellimus** ja olem SubscriptionHistory ning valige **Edasi**. Nõutavad andmed täidetakse tegevusest automaatselt. Valige **Salvesta**.

1. Tehke jaotises Klienditegevused valik **Lisa andmed**.

1. Selle näite puhul lisage veebiülevaate tegevus.

1. Tehke valik **Edasi**.

1. Andmevärskenduste **etapis** valige **mudeli ajakava jaoks Igakuine**.

1. Pärast kõigi üksikasjade läbivaatamist valige **Salvesta ja käivita**.

## <a name="task-5---review-model-results-and-explanations"></a>Ülesanne 5 – mudeli tulemuste ja selgituste läbivaatamine

Laske mudelil treenimine ja andmete hindamine lõpule viia. Vaadake üle tellimusmudeli selgitused. Lisateavet leiate teemast [prognoos tulemuste](predict-subscription-churn.md#view-prediction-results) vaatamine.

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Ülesanne 6 – suure voolavusriskiga klientide segmendi loomine

Mudeli käivitamine loob uue olemi, mis on loetletud asukohas **Andmed** > **Olemid** loendis. Saate luua mudeli loodud olemi põhjal uue segmendi.

1. Klõpsake tulemustelehel käsku **Loo segment**.

1. Looge reegel olemi **OOBSubscriptionChurnPrediction** abil ja määratlege segment.
   - **Väli**: ChurnScore
   - **Operaator**: suurem kui
   - **Väärtus**: 0,6

1. Valige **Salvesta** ja **käivita** segment.

Teil on nüüd segment, mida värskendatakse dünaamiliselt ja mis tuvastab selle tellimusäri jaoks suure voolavusriskiga kliente. Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).

> [!TIP]
> Samuti saate luua segmendi prognoos mudeli jaoks lehelt Segmendid, valides **Suvandi Uus** ja käsk **Loo luureandmetest** **.** > **·** Lisateavet leiate teemast [Kiirsegmentidega](segment-quick.md) uue segmendi loomine.

[!INCLUDE [footer-include](includes/footer-banner.md)]
