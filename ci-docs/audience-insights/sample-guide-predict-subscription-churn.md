---
title: Tellimusevoolavuse prognoosi näidisjuhend
description: Kasutage seda näidisjuhendit, et proovida kasutamiseks valmis tellimusevoolavuse prognoosi mudelit.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2537cfb5dde0d1ce1af16f585f0bf91d15ea1870
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653975"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Tellimusevoolavuse prognoosi (eelversioon) näidisjuhend

Selles juhendis näidatakse teile otsast lõpuni, kuidas kasutada tellimusevoolavuse prognoosi funktsiooni koos alltoodud näidisandmetega. 

## <a name="scenario"></a>Stsenaarium

Contoso on ettevõte, mis toodab kvaliteetset kohvi ja kohvimasinaid, mida müüakse veebisaidi Contoso Coffee kaudu. Hiljuti hakkasid nad pakkuma kordustellimusi, et kliendid saaksid kohvi regulaarselt. Nende eesmärk on mõista, millised tellimusega liitunud kliendid võivad järgmise paari kuu jooksul tellimuse tühistada. Teades, millised nende kliendid **tõenäoliselt loobuvad**, aitab ettevõttel nende säilitamisele keskendudes turundusvõtteid säästa.

## <a name="prerequisites"></a>Eeltingimused

- Vähemalt [Kaasautori õigused](permissions.md) Customer Insightsis.
- Soovitame teil järgmisi samme rakendada [uues keskkonnas](manage-environments.md).

## <a name="task-1---ingest-data"></a>Ülesanne 1 – andmete valmendamine

Vaadake üle artiklid [andmete valmendamise](data-sources.md) ja [Power Query konnektorite abil andmete importimise](connect-power-query.md) kohta. Järgmises teabes eeldatakse, et olete andmete valmendamisega üldiselt tuttav. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>E-kaubanduse platvormist pärit kliendiandmete valmendamine

1. Looge andmeallikas nimega **eCommerce**, valige importimise suvand ja valige konnektor **Tekst/CSV**.

1. Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscontacts.

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.

   - **DateOfBirth**: kuupäev
   - **CreatedOn**: kuupäev/kellaaeg/ajatsoon

   [!div class="mx-imgBorder"]
   ![Sünniaja teisendamine kuupäevaks](media/ecommerce-dob-date.PNG "sünniaja teisendamine kuupäevaks")

1. Muutke parempoolsel paanil väljal „Nimi“ oma andmeallika praegune nimi **Päring** nimeks **eCommerceContacts**

1. Salvestage andmeallikas.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliendiandmete valmendamine lojaalsusskeemi kaudu

1. Looge andmeallikas nimega **LoyaltyScheme**, valige importimise suvand ja valige konnektor **Tekst/CSV**.

1. Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscustomerloyalty.

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.

   - **DateOfBirth**: kuupäev
   - **RewardsPoints**: täisarv
   - **CreatedOn**: kuupäev/kellaaeg

1. Muutke parempoolsel paanil väljal „Nimi“ oma andmeallika praegune nimi **Päring** nimeks **loyCustomers**.

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

1. Muutke parempoolsel paanil väljal „Nimi“ oma andmeallika praegune nimi **Päring** nimeks **SubscriptionHistory**.

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

Pärast andmete valmendamist alustame protsessi **Vastenda, vii vastavusse, ühenda**, et luua koondatud kliendiprofiil. Lisateavet leiate teemast [Andmete koondamine](data-unification.md).

### <a name="map"></a>Vastendus

1. Pärast andmete valmendamist vastendage e-kaubanduse ja lojaalsusandmete kontaktid harilike andmetüüpidega. Liikuge **Andmed** > **Koondamine** > **Vastendamine**.

1. Valige olemid, mis esindavad kliendiprofiili: **eCommerceContacts** ja **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="E-kaubanduse ja lojaalsuse andmeallikad vahekaardil „Koondamine“.":::

1. Valige andmeallika **eCommerceContacts** peamiseks võtmeks **ContactId** ja andmeallika **loyCustomers** peamiseks võtmeks **LoyaltyID**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId peamise võtmena vahekaardil „Koondamine“.":::

### <a name="match"></a>Vastenda

1. Liikuge vahekaardile **Vastavusseviimine** ja valige **Määra järjekord**.

1. Valige ripploendis **Peamine** peamiseks andmeallikaks **eCommerceContacts: eCommerce** ja kaasake kõik kirjed.

1. Valige ripploendist **Olem 2** **loyCustomers: LoyaltyScheme** ja kaasake kõik kirjed.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="E-kaubanduse ja lojaalsuse vastavusseviimine vahekaardil „Koondamine“.":::

1. Valige **Loo uus reegel**

1. Lisage esimene tingimus suvandi FullName abil.

   * Valige andmeallika eCommerceContacts jaoks ripploendist **FullName**.
   * Valige andmeallika loyCustomers jaoks ripploendist **FullName**.
   * Valige ripploend **Normaliseerimine** ja valige **Tüüp (telefon, nimi, aadress, ...)**.
   * Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.

1. Sisestage uuele reeglile nimi **FullName, Email**.

   * Lisage meiliaadressi jaoks teine tingimus, valides suvandi **Lisa tingimus**
   * Valige olemi eCommerceContacts jaoks ripploendist **Meil**.
   * Valige olemi loyCustomers jaoks ripploendist **Meil**. 
   * Jätke suvand „Normaliseerimine“ tühjaks. 
   * Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Reegli vastavusseviimine nime ja meili korral vahekaardil „Koondamine“.":::

7. Valige **Salvesta** ja **Käivita**.

### <a name="merge"></a>Ühendamine

1. Avage vahekaart **Ühendamine**.

1. Määrake olemi **loyCustomers** üksuse **ContactId** kuvatavaks nimeks **ContactIdLOYALTY**, et eristada seda muudest valmendatud ID-dest.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="contactid nime vahetamine lojaalsuse ID-s.":::

1. Valige **Salvesta** ja **Käivita**, et käivitada ühendamisprotsess.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Ülesanne 3 – tellimusevoolavuse prognoosi konfigureerimine

Kui kliendiprofiilid on koondatud, saame käivitada tellimusevoolavuse prognoosi. Üksikasjalikud juhised leiate artiklist [Tellimusevoolavuse prognoos (eelversioon)](predict-subscription-churn.md). 

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
