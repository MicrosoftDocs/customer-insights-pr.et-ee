---
title: Kliendi eluea väärtuse prognoosi näidisjuhend
description: Selle näidisjuhendi abil saate proovida kliendi eluaja väärtuse prognoosi mudelit.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129940"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Kliendi eluea väärtuse (CLV) prognoosi näidisjuhend

Selles juhendis selgitatakse teile lõppnäidet kliendi eluea väärtuse (CLV) prognoosi kohta teenuses Customer Insights näidisandmete abil.

## <a name="scenario"></a>Stsenaarium

Contoso on ettevõte, mis toodab kvaliteetseid kohvi- ja kohvimasinaid. Nad müüvad tooteid oma Contoso Coffee veebisaidil. Ettevõte soovib mõista väärtust (tulu), mida nende kliendid saavad järgmise 12 kuu jooksul teenida. Teades oma klientide eeldatavat väärtust järgmise 12 kuu jooksul, aitab see neil juhtida oma turundustegevust kõrge väärtusega klientidele.

## <a name="prerequisites"></a>Eeltingimused

- Vähemalt [kaasautori õigused](permissions.md) sihtrühma ülevaates.
- Soovitame teil järgmisi samme rakendada [uues keskkonnas](manage-environments.md).

## <a name="task-1---ingest-data"></a>Ülesanne 1 – andmete valmendamine

Vaadake üle artiklid [andmete rakendamise](data-sources.md) ja [andmeallikate importimise kohta Power Query konnektorite](connect-power-query.md) abil. Järgmises teabes eeldatakse, et olete andmete valmendamisega üldiselt tuttav.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>E-kaubanduse platvormist pärit kliendiandmete valmendamine

1. Looge andmeallikas nimega **eCommerce**, valige importimise suvand ja valige konnektor **Tekst/CSV**.

1. Sisestage eCommerce kontaktide URL [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.
   - **DateOfBirth**: kuupäev
   - **CreatedOn**: kuupäev/kellaaeg/ajatsoon

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Sünniaja teisendamine kuupäevaks.":::

1. Muutke parempoolsel paanil väljal „Nimi“ oma andmeallika praegune nimi **Päring** nimeks **eCommerceContacts**

1. **Salvestage** andmeallikas.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Kliendiandmete valmendamine veebisaidiarvustustest

1. Looge andmeallikas nimega **Veebisait**, valige importimise suvand ja valige konnektor **Tekst/CSV**.

1. Sisestage e-kaubanduse kontaktide URL https://aka.ms/CI-ILT/WebReviews.

1. Andmete redigeerimise käigus valige **Teisenda** ja seejärel **Kasuta esimest rida päistena**.

1. Värskendage allpool loetletud veergude andmetüüp.

   - **ReviewRating**: kümnendarv
   - **ReviewDate**: kuupäev

1. Nimetage parempoolse paani väljal 'Nimi' oma andmeallikas ümber **päringust** **arvustusteks**.

1. **Salvestage** andmeallikas.

## <a name="task-2---data-unification"></a>Ülesanne 2 – andmete koondamine

Pärast andmete sisestamist alustame andmete ühendamise protsessi, et luua ühtne kliendiprofiil. Lisateavet leiate teemast [Andmete koondamine](data-unification.md).

### <a name="map"></a>Vastendus

1. Pärast andmete valmendamist vastendage e-kaubanduse ja lojaalsusandmete kontaktid harilike andmetüüpidega. Liikuge **Andmed** > **Koondamine** > **Vastendamine**.

1. Valige olemid, mis esindavad kliendiprofiili: **eCommerceContacts** ja **loyCustomers**. Seejärel valige **Rakenda**.

   ![E-kaubanduse ja lojaalsuse andmeallikad vahekaardil „Koondamine“.](media/unify-ecommerce-loyalty.png)

1. Valige andmeallika **eCommerceContacts** peamiseks võtmeks **ContactId** ja andmeallika **loyCustomers** peamiseks võtmeks **LoyaltyID**.

   ![LoyaltyId peamise võtmena vahekaardil „Koondamine“.](media/unify-loyaltyid.png)

1. Valige **Salvesta**.

### <a name="match"></a>Vastenda

1. Liikuge vahekaardile **Vastavusseviimine** ja valige **Määra järjekord**.

1. Valige ripploendis **Peamine** peamiseks andmeallikaks **eCommerceContacts: eCommerce** ja kaasake kõik kirjed.

1. Valige ripploendist **Olem 2** **loyCustomers: LoyaltyScheme** ja kaasake kõik kirjed.

   ![E-kaubanduse ja lojaalsuse vastavusseviimine vahekaardil „Koondamine“.](media/unify-match-order.png)

1. Valige **Lisa reegel**

1. Lisage esimene tingimus suvandi FullName abil.

   - Valige andmeallika eCommerceContacts jaoks ripploendist **FullName**.
   - Valige andmeallika loyCustomers jaoks ripploendist **FullName**.
   - Valige ripploend **Normaliseerimine** ja valige **Tüüp (telefon, nimi, aadress, ...)**.
   - Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.

1. Sisestage uuele reeglile nimi **FullName, Email**.

   - Lisage meiliaadressi jaoks teine tingimus, valides suvandi **Lisa tingimus**
   - Valige olemi eCommerceContacts jaoks ripploendist **Meil**.
   - Valige olemi loyCustomers jaoks ripploendist **Meil**.
   - Jätke suvand „Normaliseerimine“ tühjaks.
   - Määrake **täpsustasemeks** **põhiline** ja **väärtuseks** **suur**.

   ![Reegli vastavusseviimine nime ja meili korral vahekaardil „Koondamine“.](media/unify-match-rule.png)

1. Valige nupp **Valmis**.

1. Valige **Salvesta** ja **Käivita**.

### <a name="merge"></a>Ühendamine

1. Avage vahekaart **Ühendamine**.

1. Määrake olemi **loyCustomers** üksuse **ContactId** kuvatavaks nimeks **ContactIdLOYALTY**, et eristada seda muudest valmendatud ID-dest.

   ![contactid nime vahetamine lojaalsuse ID-s.](media/unify-merge-contactid.png)

1. Valige **Salvesta** ja **Käivita liitmine ja allavooluprotsessid**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>3. ülesanne – kliendi eluea prognoosi konfigureerimine

Kui ühendatud kliendiprofiilid on paigas, saame nüüd käivitada kliendi eluea väärtuse prognoosi. Üksikasjalikud juhised leiate teemast [Kliendi eluea väärtuse prognoos (eelvaade)](predict-customer-lifetime-value.md).

1. Minge loendisse **Intelligents**  > **Prognoosid** ja valige **Kliendi eluea väärtuse mudel**.

1. Avage külgpaanil soovitud teave ja valige **Alustamine**.

1. Pange mudeli nimeks **OOB eCommerce CLV prognoos** ja väljundolemi nimeks **OOBeCommerceCLVPrediction**.

1. Määratlege CLV mudeli eelistused.
   - **Prognoosi ajavahemik**: **12 kuud või 1 aasta**. Selle sättega määratletakse, kui palju tulevikku prognoositakse kliendi eluea väärtus.
   - **Aktiivsed kliendid**: määrake, mida aktiivsed kliendid teie ettevõtte jaoks tähendab. Saate määrata ajaloolise ajaraami, mille jooksul peab kliendil olema olnud vähemalt üks tehing, mida tuleb aktiivseks lugeda. Mudel prognoosib, ainult aktiivsete klientide CLV-d. Valige kuupäevade vahemik, kas mudel arvutab ajaperioodi varasemate kannete andmete põhjal või tagab kindla ajavahemiku. Selles näidisjuhendis **lubame mudelil arvutada ostuintervalli**, mis on vaikesuvand.
   - **Kõrge väärtusega kliendid**: määratlege kõrge väärtusega kliendid protsentuaalselt kõige paremini tasuvatest klientidest. Mudelis kasutatakse seda sisendit, et pakkuda tulemusi, mis vastaksid teie kõrge väärtusega klientide ärimääratlusele. Võite lasta mudelil määratleda kõrge väärtusega kliente. See kasutab heuristilist reeglit, mis tuletab protsentiili. Saate määratleda ka kõrge väärtusega kliendid tulevaste maksvate klientide protsentiilina. Selles näidisjuhendis määratleme kõrge väärtusega kliendid käsitsi **30% aktiivseimaks ostuklientideks** ja valime suvandi **Edasi**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="Eelistused, etapp CLV mudeli juhendatud kogemuses.":::

1. Tehinguajaloo andmete lisamiseks valige **nõutavate andmete** sammus **Lisa andmed**.

1. Lisage olem **eCommercePurkirjeses: eCommerce** ja vastendage mudeli puhul nõutavad atribuudid.
   - Tehingu ID: eCommerce.eCommercePurchases.PurchaseId
   - Tehingu kuupäev: eCommerce.eCommercePurchases.PurchasedOn
   - Tehingu summa: eCommerce.eCommercePursseses.TotalPrice
   - Toote ID: eCommerce.eCommercePurtooteses.ProductId

1. Tehke valik **Edasi**.

1. Saate seadistada seose olemi **eCommercePursseses: eCommerce** ja **eCommerceContacts: eCommerce** vahel.

1. **Täiendavate andmete (valikuline)** sammuga saate lisada rohkem klienditegevuse andmeid. Need andmed võivad aidata saada rohkem ülevaateid kliendi ja teie ettevõtte vahelisest suhtlusest, mis võib aidata kaasa CLV-le. Klientide peamiste suhtluste, nt veebilogide, klienditeenindus logide või autasude programmiajaloo lisamine võib parandada prognooside täpsust. Kui soovite kaasata rohkem klienditegevuseandmeid, valige **Lisa andmed**.

1. Lisage klienditegevuse olem ja vastendage selle väljade nimed mudelis nõutavatele väljadele.
   - Klienditegevuse olem: Reviews:Website
   - Esmane võti: Website.Reviews.ReviewId
   - Ajatempel: Website.Reviews.ReviewDate
   - Sündmus (tegevuse nimi): Website.Reviews.ActivityTypeDisplay
   - Üksikasjad (summa või väärtus): Website.Reviews.ReviewRating

1. Valige **Edasi** ja konfigureerige tegevus ning kannete ja kliendiandmete vaheline seos.  
   - Tegevuse tüüp: valige olemasolev
   - Tegevuse silt: ülevaade
   - Vastav silt: Website.Reviews.UserId
   - Kliendi olem: eCommerceContacts:eCommerce
   - Seos: WebsiteReviews

1. Valige **Järgmine**, et määratleda mudeli ajakava.

   Mudel peab uute mustrite õppimiseks regulaarselt treenima, kui uusi andmeid sisestatakse. Selle näite puhul valige **Igakuine**.

1. Pärast kõigi üksikasjade läbivaatamist valige **Salvesta ja käivita**.

## <a name="task-4---review-model-results-and-explanations"></a>Ülesanne 4 – mudeli tulemuste ja selgituste läbivaatamine

Laske mudelil treenimine ja andmete hindamine lõpule viia. Järgmiseks saate vaadata CLV mudeli tulemusi ja selgitusi. Lisateavet leiate teemast [Prognoos oleku ja tulemuste läbivaatamine](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>5. ülesanne – suure väärtusega klientide segmendi loomine

Mudeli käivitamine loob uue olemi, mis on loetletud asukohas **Andmed** > **Olemid** loendis. Saate luua mudeli loodud olemi põhjal uue kliendisegmendi.

1. Liikuge jaotisse **Segmendid**. 

1. Valige **Uus** ja seejärel **Loo üksusest** > **Ärianalüüs**.

   ![Segmendi loomine mudeli väljundiga.](media/segment-intelligence.png)

1. Valige olem **OOBeCommerceCLVPrediction** ja määratlege segment.
  - Väli: CLVScore
  - Tehtemärk: suurem kui
  - Väärtus: 1500

1. Valige **Ülevaade** ja **salvestage** segment.

Teil on nüüd segment, mis tuvastab kliendid, kes prognooside kohaselt teenivad järgmise 12 kuu jooksul rohkem kui 1500 dollarit tulu. Kui kasutatakse rohkem andmeid, värskendatakse see segment dünaamiliselt.

Lisateavet vt teemast [Segmentide loomine ja haldamine](segments.md).
