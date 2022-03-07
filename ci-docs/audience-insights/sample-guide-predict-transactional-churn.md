---
title: Tehinguvoolavuse prognoosi näidisjuhend
description: Kasutage seda näidisjuhendit, et proovida kasutamiseks valmis tehinguvoolavuse prognoosi mudelit.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 93841358d110bd16c7b7f8beb079bed704b22260
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354596"
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

Pärast andmete valmendamist alustame protsessi **Vastenda, vii vastavusse, ühenda**, et luua koondatud kliendiprofiil. Lisateavet leiate teemast [Andmete koondamine](data-unification.md).

### <a name="map"></a>Vastendus

1. Pärast andmete valmendamist vastendage e-kaubanduse ja lojaalsusandmete kontaktid harilike andmetüüpidega. Liikuge **Andmed** > **Koondamine** > **Vastendamine**.

1. Valige olemid, mis esindavad kliendiprofiili: **eCommerceContacts** ja **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="E-kaubanduse ja lojaalsuse andmeallikad vahekaardil „Koondamine“.":::

1. Valige andmeallika **eCommerceContacts** peamiseks võtmeks **ContactId** ja andmeallika **loyCustomers** peamiseks võtmeks **LoyaltyID**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="LoyaltyId peamise võtmena vahekaardil „Koondamine“.":::

### <a name="match"></a>Vastenda

1. Liikuge vahekaardile **Vastavusseviimine** ja valige **Määra järjekord**.

1. Valige **Esmane** ripploendist **eCommerceContacts: eCommerce** kui esmane allikas ja kaasake kõik kirjed.

1. Valige **Olem 2** ripploendist väärtus **loyCustomers: LoyaltyScheme** ja kaasake kõik kirjed.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="E-kaubanduse ja lojaalsuse vastavusseviimine vahekaardil „Koondamine“.":::

1. Valige **Loo uus reegel**

1. Lisage esimene tingimus suvandi FullName abil.

   * eCommerceContacts jaoks valige **Täisnimi** rippmenüüst.
   * loyCustomers jaoks valige **Täisnimi** rippmenüüst.
   * Valige ripploend **Normaliseerimine** ja valige **Tüüp (telefon, nimi, aadress, ...)**.
   * Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.

1. Sisestage uuele reeglile nimi **FullName, Email**.

   * Lisage meiliaadressi jaoks teine tingimus, valides suvandi **Lisa tingimus**
   * Olemi eCommerceContacts jaoks valige **EKiri** rippmenüüst.
   * Olemi loyCustomers jaoks valige **EKiri** rippmenüüst. 
   * Jätke suvand „Normaliseerimine“ tühjaks. 
   * Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Reegli vastavusseviimine nime ja meili korral vahekaardil „Koondamine“.":::

7. Valige **Salvesta** ja **Käivita**.

### <a name="merge"></a>Ühendamine

1. Avage vahekaart **Ühendamine**.

1. Määrake olemi **loyCustomers** üksuse **ContactId** kuvatavaks nimeks **ContactIdLOYALTY**, et eristada seda muudest valmendatud ID-dest.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="contactid nime vahetamine lojaalsuse ID-s.":::

1. Valige **Salvesta** ja **Käivita**, et käivitada ühendamisprotsess.



## <a name="task-3---configure-transaction-churn-prediction"></a>Ülesanne 3 – tehinguvoolavuse prognoosi konfigureerimine

Kui kliendiprofiilid on koondatud, saame käivitada tellimusevoolavuse prognoosi. Üksikasjalike juhiste leiate artiklist [Tellimuse prognoos](predict-subscription-churn.md). 

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
