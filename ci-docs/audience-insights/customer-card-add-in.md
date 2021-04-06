---
title: Kliendikaardi lisandmooduli installimine ja konfigureerimine
description: Kliendikaardi lisandmooduli installimine ja konfigureerimine teenuse Dynamics 365 Customer Insights jaoks.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597322"
---
# <a name="customer-card-add-in-preview"></a>Kliendikaardi lisandmoodul (eelvaade)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Saate oma klientide kohta täieliku ülevaate otse Dynamics 365 rakendustes. Saate vaadata kliendikaardi lisandmooduliga seotud demograafiat, ülevaateid ja tegevuse ajajooni.

## <a name="prerequisites"></a>Eeltingimused

- Dynamics 365 rakendus (nt müügikeskus või klienditeeninduskeskus), versioon 9.0 ja uuem, kus Unified Interface on lubatud.
- Kliendiprofiilid, [mis on valmendatud Dynamics 365 rakendusest Common Data Service'i abil](connect-power-query.md).
- Kliendikaardi lisandmooduli kasutajad tuleb sihtrühmaülevaadetes [lisada kasutajatena](permissions.md).
- [Konfigureeritud otsingu- ja filtrifunktsioonid](search-filter-index.md).
- Demograafiliste andmete juhtelement: demograafilised väljad (nt vanus või sugu) on saadaval koondatud kliendiprofiilis.
- Rikastamise juhtelement: nõuab kliendiprofiilile aktiivsete [rikastamiste](enrichment-hub.md) rakendamist.
- Ärianalüüsi juhtelement: nõuab Azure'i masinõppe ([prognoosid](predictions.md) või [kohandatud mudelid](custom-models.md)) abil genereeritud andmeid
- Näitajate juhtelement: nõuab [konfigureeritud näitajaid](measures.md).
- Ajaskaala juhtelement: nõuab [konfigureeritud tegevusi](activities.md).

## <a name="install-the-customer-card-add-in"></a>Kliendikaardi lisandmooduli installimine

Kliendikaardi lisandmoodul on rakenduste Customer engagement lahendus Dynamics 365-s. Lahenduse installimiseks avage AppSource ja otsige jaotist **Dynamicsi kliendikaart**. Valige [AppSource'is kliendikaardi lisandmoodul](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ja valige **Hangi kohe**.

Lahenduse installimiseks võib olla vajalik rakenduse Dynamics 365 administraatori mandaadiga sisse logida.

Lahenduse installimiseks teie keskkonda võib kuluda pisut aega.

## <a name="configure-the-customer-card-add-in"></a>Kliendikaardi lisandmooduli konfigureerimine

1. Administraatorina minge teenuses Dynamics 365 jaotisesse **Sätted** ja valige **Lahendused**.

1. Valige link **Kuvatav nimi** lahendusele **Dynamics 365 Customer Insightsi kliendikaardi lisandmoodul (eelvaade)**.

   > [!div class="mx-imgBorder"]
   > ![Valige kuvatav nimi](media/select-display-name.png "Valige kuvatav nimi")

1. Valige **Logi sisse** ja sisestage administraatori konto mandaat, mida kasutate rakenduse Customer Insights konfigureerimiseks.

   > [!NOTE]
   > Kontrollige, et brauseri hüpikakende blokeerija ei blokeeriks autentimise akent, kui valite nupu **Logi sisse**.

1. Valige keskkond, kust soovite andmeid tuua.

1. Määratlege, millised väljad vastendada Dynamics 365 rakenduse kirjetega.
   - Kontaktiga vastendamiseks valige kliendiolemi väli, mis vastab teie kontaktiolemi ID-le.
   - Kontoga vastendamiseks valige kliendiolemi väli, mis vastab teie kontoolemi ID-le.

   > [!div class="mx-imgBorder"]
   > ![Kontakti ID väli](media/contact-id-field.png "Kontakti ID väli")

1. Sätete salvestamiseks valige **Salvesta konfiguratsioon**.

1. Järgmisena peate määrama rakenduses Dynamics 365 turberollid, et kasutajad saaksid kliendikaarti kohandada ja näha. Avage lahenduses Dynamics 365 **Sätted** > **Turvalisus** > **Kasutajad**. Valige kasutajarollide redigeerimiseks kasutajad ja valige **Halda rolle**.

1. Määrake roll **Customer Insightsi kaardikohandaja** nendele kasutajatele, kes kohandavad kogu ettevõtte kaardil kuvatavat sisu.

## <a name="add-customer-card-controls-to-forms"></a>Kliendikaardi juhtelementide lisamine vormidele
  
1. Kliendikaardi juhtelementide lisamiseks kontaktivormile avage lahenduses Dynamics 365 **Sätted** > **Kohandused**.

1. Valige **Süsteemi kohandamine**.

1. Sirvige olemi **Kontakt** juurde, laiendage see ja valige **Vormid**.

1. Valige kontaktivorm, kuhu soovite kliendikaardi juhtelemendid lisada.

    > [!div class="mx-imgBorder"]
    > ![Kontaktivormi valimine](media/contact-active-forms.png "Kontaktivormi valimine")

1. Juhtelemendi lisamiseks lohistage väljaredaktoris mistahes väli **Väljauurijast** sinna, kuhu soovite juhtelemendi paigutada.

1. Valige äsja lisatud vormi väli ja seejärel valige **Muuda atribuute**.

1. Minge vahekaardile **Juhtelemendid** ja valige **Lisa juhtelement**. Valige üks saadaolevatest kohandatud juhtelementidest ja valige **Lisa**.

1. **Välja atribuutide** dialoogis tühjendage märkeruut **Kuva vormil silt**.

1. Valige juhtelemendi jaoks suvand **Veeb**. Valige rikastamise juhtelemendi jaoks, millist rikastamise tüüpi soovite kuvada, konfigureerides välja **enrichmentType**. Lisage igale rikastamistüübile eraldi rikastamise juhtelement.

1. Värskendatud kontaktivormi avaldamiseks valige **Salvesta** ja **Avalda**.

1. Minge avaldatud kontakti vormile. Näete äsja lisatud juhtelementi. Võimalik, et peate esmakordsel kasutusel sisse logima.

1. Selleks et kohandada seda, mida soovite kohandatud juhtelemendil kuvada, valige paremas ülanurgas redigeerimise nupp.

## <a name="upgrade-customer-card-add-in"></a>Kliendikaardi lisandmooduli täiendamine
Kliendikaardi lisandmoodulit ei täiendata automaatselt. Uusimale versioonile täiendamiseks järgige neid juhiseid Dynamics 365 rakenduses, kuhu on installitud lisandmoodul.

1. Avage Dynamics 365 rakenduse jaotises **Sätted** > **Kohandamine** ja valige **Lahendused**.

1. Otsige lisandmoodulite tabelist **CustomerInsightsCustomerCard** ja valige see rida.

1. Valige tegumiribalt **Rakenda lahenduse täiendus**.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Lahenduse täiendamine Dynamics 365 rakenduste kohandamisalal":::

1. Pärast täiendamisprotsessi käivitamist kuvatakse laadimisnäidik kuni täienduse lõpuleviimiseni. Kui uuemat versiooni pole, kuvab täiendus tõrketeate.


[!INCLUDE[footer-include](../includes/footer-banner.md)]