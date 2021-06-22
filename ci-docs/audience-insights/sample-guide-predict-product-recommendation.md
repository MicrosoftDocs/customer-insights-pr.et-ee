---
title: Tootesoovituste prognoosimise näidisjuhend
description: Kasutage seda näidisjuhendit, et proovida kasutamiseks valmis tootesoovituste prognoosi mudelit.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b136084316da5ae17a8428236381f69e5c21f9ea
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129894"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>Toote soovituste prognoosimise (eelvaate) näidisjuhend

Selles juhendis näidatakse teile otsast lõpuni, kuidas kasutada tootesoovituste prognoosi funktsiooni koos alltoodud näidisandmetega.

## <a name="scenario"></a>Stsenaarium

Contoso on ettevõte, mis toodab kvaliteetseid kohvi- ja kohvimasinaid, mida nad müüvad oma Contoso Coffee veebisaidi kaudu. Nende eesmärk on mõista, milliseid tooteid nad peaksid püsiklientidele soovitama. Teades, millised kliendid **tõenäoliselt ostavad**, aitab ettevõttel nendele toodetele keskendudes turundusvõtteid säästa.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Sünniaja teisendamine kuupäevaks.":::

5. Muutke parempoolsel paanil väljal „Nimi“ oma andmeallika praegune nimi **Päring** nimeks **eCommerceContacts**

6. **Salvestage** andmeallikas.

### <a name="ingest-online-purchase-data"></a>Internetiostude andmete valmendamine

1. Lisage samasse andmeallikasse **eCommerce** veel üks andmekogum. Valige uuesti konnektor **Tekst/CSV**.

1. Sisestage **internetiostude** andmete URL https://aka.ms/ciadclassonline.

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **PurchasedOn**: kuupäev/kellaaeg
   - **TotalPrice**: valuuta

1. Muutke küljepaanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **eCommercePurchases**.

1. **Salvestage** andmeallikas.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Kliendiandmete valmendamine lojaalsusskeemi kaudu

1. Looge andmeallikas nimega **LoyaltyScheme**, valige importimise suvand ja valige konnektor **Tekst/CSV**.

1. Sisestage e-kaubanduse kontaktide URL https://aka.ms/ciadclasscustomerloyalty.

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **DateOfBirth**: kuupäev
   - **RewardsPoints**: täisarv
   - **CreatedOn**: kuupäev/kellaaeg

1. Muutke parempoolsel paanil väljal **Nimi** oma andmeallika praegune nimi **Päring** nimeks **loyCustomers**.

1. **Salvestage** andmeallikas.

## <a name="task-2---data-unification"></a>Ülesanne 2 – andmete koondamine

Pärast andmete sisestamist alustame andmete ühendamise protsessi, et luua ühtne kliendiprofiil. Lisateavet leiate teemast [Andmete koondamine](data-unification.md).

### <a name="map"></a>Vastendus

1. Pärast andmete valmendamist vastendage e-kaubanduse ja lojaalsusandmete kontaktid harilike andmetüüpidega. Liikuge **Andmed** > **Koondamine** > **Vastendamine**.

2. Valige olemid, mis esindavad kliendiprofiili: **eCommerceContacts** ja **loyCustomers**.

   ![E-kaubanduse ja lojaalsuse andmeallikad vahekaardil „Koondamine“.](media/unify-ecommerce-loyalty.png)

3. Valige andmeallika **eCommerceContacts** peamiseks võtmeks **ContactId** ja andmeallika **loyCustomers** peamiseks võtmeks **LoyaltyID**.

   ![LoyaltyId peamise võtmena vahekaardil „Koondamine“.](media/unify-loyaltyid.png)

### <a name="match"></a>Vastenda

1. Liikuge vahekaardile **Vastavusseviimine** ja valige **Määra järjekord**.

2. Valige ripploendis **Peamine** peamiseks andmeallikaks **eCommerceContacts: eCommerce** ja kaasake kõik kirjed.

3. Valige ripploendist **Olem 2** **loyCustomers: LoyaltyScheme** ja kaasake kõik kirjed.

   ![E-kaubanduse ja lojaalsuse vastavusseviimine vahekaardil „Koondamine“.](media/unify-match-order.png)

4. Valige **Loo uus reegel**

5. Lisage esimene tingimus suvandi FullName abil.

   - Valige andmeallika eCommerceContacts jaoks ripploendist **FullName**.
   - Valige andmeallika loyCustomers jaoks ripploendist **FullName**.
   - Valige ripploend **Normaliseerimine** ja valige **Tüüp (telefon, nimi, aadress, ...)**.
   - Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.

6. Sisestage uuele reeglile nimi **FullName, Email**.

   - Lisage meiliaadressi jaoks teine tingimus, valides suvandi **Lisa tingimus**
   - Valige olemi eCommerceContacts jaoks ripploendist **Meil**.
   - Valige olemi loyCustomers jaoks ripploendist **Meil**.
   - Jätke suvand „Normaliseerimine“ tühjaks.
   - Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.

   ![Reegli vastavusseviimine nime ja meili korral vahekaardil „Koondamine“.](media/unify-match-rule.png)

7. Valige **Salvesta** ja **Käivita**.

### <a name="merge"></a>Ühendamine

1. Avage vahekaart **Ühendamine**.

1. Määrake olemi **loyCustomers** üksuse **ContactId** kuvatavaks nimeks **ContactIdLOYALTY**, et eristada seda muudest valmendatud ID-dest.

   ![contactid nime vahetamine lojaalsuse ID-s.](media/unify-merge-contactid.png)

1. Valige **Salvesta** ja **Käivita**, et käivitada ühendamisprotsess.

## <a name="task-3---configure-product-recommendation-prediction"></a>3. toiming – tootesoovituse prognoosi konfiguratsioon

Kui kliendiprofiilid on koondatud, saame käivitada tellimusevoolavuse prognoosi.

1. Minge **Intelligents** > **Prognoos** ja valige **Tootesoovitus**.

1. Seejärel valige suvand **Alustamine**.

1. Nimetage mudeli **OOB tootesoovituse mudeli prognoos** ja väljundolemi **OOBProductRecommendationPrediction**.

1. Määratlege mudeli jaoks kolm järgmist tingimust.

   - **Toodete arv**: määrake selle väärtuseks **5**. See säte määratleb mitu toodet soovite oma klientidele soovitada.

   - **Eeldatud kordusostud**: valige **Jah** näitamaks, et soovite tooteid kaasata soovitusesse, mille teie kliendid on varem ostnud.

   - **Tagasivaate aken:** valige vähemalt **365 päeva**. See säte määtatleb, kui kaugele mudel vaatab kliendi aktiivsuse ajas tagasi, et seda kasutada oma soovituste sisendina.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Toote soovitusmudeli mudeli eelistused.":::

1. Valige **Nõutavad andmed** ja valige ostuajaloo jaoks **Lisa andmeid**.

1. Lisage olem **eCommercePurchases: eCommerce** ja vastendage e-kaubandusest pärit väljad asjaomaste mudelile vajalike väljadega.

1. Ühendage olem **eCommercePurchases: eCommerce** olemiga **eCommerceContacts: eCommerce**.

   ![E-kaubanduse olemite ühendamine.](media/model-purchase-join.png)

1. Valige **Järgmine**, et määratleda mudeli ajakava.

   Mudelit on vaja regulaarselt treenida, et see õpiks uusi mustreid uute andmete valmendamisel. Selle näite puhul valige **Iga kuu**.

1. Pärast kõigi üksikasjade läbivaatamist valige **Salvesta ja käivita**.


## <a name="task-4---review-model-results-and-explanations"></a>Ülesanne 4 – mudeli tulemuste ja selgituste läbivaatamine

Laske mudelil treenimine ja andmete hindamine lõpule viia. Nüüd saate üle vaadata tootesoovituste mudeli selgitused. Lisateavet leiate teemast [Prognoos oleku ja tulemuste läbivaatamine](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tööülesanne 5 – rohkelt ostetud toodete segmendi loomine

Tootmismudeli käitamisel luuakse uus olem, mida näete, kui liigute **Andmed** > **Olemid**.

Saate luua mudeli loodud olemi põhjal uue segmendi.

1. Liikuge jaotisse **Segmendid**. Valige **Uus** ja seejärel **Loo üksusest** > **Ärianalüüs**.

   ![Segmendi loomine mudeli väljundiga.](media/segment-intelligence.png)

1. Valige lõpp-punkt **OOBProductRecommendationModelPrediction** ja määratlege segment.

   - Väli: ProductID
   - Tehtemärk: väärtus
   - Väärtus: valige kolm peamist toote ID-d

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Saate mudelitulemitest luua segmendi.":::

Teil on nüüd dünaamiliselt uuendatud segment, mis tuvastab kliendid, kes on valmis ostma kolme kõige soovitatavamat toodet 

Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
