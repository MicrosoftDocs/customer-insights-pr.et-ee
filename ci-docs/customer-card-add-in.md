---
title: Dynamics 365 rakenduste kliendikaardi lisandmoodul (eelvaade) (sisaldab videot)
description: Selle lisandmooduliga saate dynamics 365 rakendustes Customer Insightsi kliendiprofiili andmeid kuvada.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8b3b6a0d54b80d7df454e9dc925f14cc3c39684c
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9194918"
---
# <a name="customer-card-add-in-for-dynamics-365-apps-preview"></a>Dynamics 365 rakenduste kliendikaardi lisandmoodul (eelvaade)

Saate oma klientide kohta täieliku ülevaate otse Dynamics 365 rakendustes. Kui kliendikaardi lisandmoodul on installitud toetatud Dynamics 365 rakendusse, saate valida kliendiprofiili väljade, ülevaadete ja tegevuse ajaskaala kuvamise. Lisandmoodul toob andmed Customer Insights -i kaudu, mõjutamata ühendatud Dynamics 365 rakenduse andmeid.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>eeltingimused

- Dynamics 365 mudelipõhised rakendused, näiteks Sales või klienditeenindus, versioon 9.0 ja uuemad.
- Dynamics 365-i andmete vastendamiseks Customer Insightsi [kliendiprofiilidega soovitame need alla neelata Dynamics 365 rakendusest konnektori Microsoft Dataverse abil](connect-power-query.md). Kui kasutate Dynamics 365-i kontaktide (või kontode) allaneelamiseks mõnda muud meetodit, veenduge, `contactid` et väli (või`accountid`) oleks andmete ühendamise protsessi ajal määratud selle andmeallikas [primaarvõtmeks](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Andmete nägemiseks tuleb [kõik Dynamics 365-i kliendikaardi lisandmooduli kasutajad lisada Customer Insightsi kasutajatena](permissions.md).
- [Konfigureeritud otsingu-ja filtreerimise võimalused](search-filter-index.md) rakenduses Customer Insights.
- Iga lisandmooduli juhtelement tugineb Customer Insightsi konkreetsetele andmetele. Teatud andmed ja juhtelemendid on saadaval ainult mingit kindlat tüüpi keskkondades. Lisandmooduli konfiguratsioon teavitab teid, kui juhtelement pole valitud keskkonnatüübi tõttu saadaval. Lisateave [keskkondade kasutamise kohta](work-with-business-accounts.md).
  - **Mõõtude juhtimine** nõuab [konfigureeritud kliendiatribuutide mõõtusid](measures.md).
  - **Teabeturbe juhtimiseks** on vaja andmeid, mis on loodud prognooside või kohandatud mudelite [abil](predictions-overview.md).
  - **Kliendiandmete juhtelement** kuvab kõik ühtses kliendiprofiilis saadaoleva profiili väljad.
  - **Rikastamise juhtimine** nõuab kliendiprofiilidele rakendatud aktiivset [rikastamist](enrichment-hub.md). Kaardi lisandmoodul toetab neid rikastamisi: [Microsofti pakutavad kaubamärgid](enrichment-microsoft.md), [Microsofti pakutavad](enrichment-microsoft.md) huvid ja [Microsofti pakutavad Office'i kaasamisandmed](enrichment-office.md).
  - **Kontaktide juhtelement** nõuab kontakti semantilise olemi tüüpi.
  - **Ajaskaala juhtimine** nõuab [konfigureeritud tegevusi](activities.md).

## <a name="install-the-customer-card-add-in"></a>Kliendikaardi lisandmooduli installimine

Kliendikaardi lisandmoodul on rakenduste Customer engagement lahendus Dynamics 365-s. Lahenduse installimiseks toimige järgmiselt.

1. Minge rakendusse AppSource Dynamics Customer Card (Dynamicsi kliendikaart **) ja otsige seda**.

1. Valige [AppSource'is kliendikaardi lisandmoodul](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ja valige **Hangi kohe**.

Lahenduse installimiseks võib olla vajalik rakenduse Dynamics 365 administraatori mandaadiga sisse logida. Lahenduse installimiseks teie keskkonda võib kuluda pisut aega.

## <a name="configure-the-customer-card-add-in"></a>Kliendikaardi lisandmooduli konfigureerimine

1. Administraatorina minge teenuses Dynamics 365 jaotisesse **Sätted** ja valige **Lahendused**.

1. Valige link **Kuvatav nimi** lahendusele **Dynamics 365 Customer Insightsi kliendikaardi lisandmoodul (eelvaade)**.

   > [!div class="mx-imgBorder"]
   > ![Vali kuvanimi.](media/select-display-name.png "Valige kuvatav nimi.")

1. Valige **Logi sisse** ja sisestage administraatori konto mandaat, mida kasutate rakenduse Customer Insights konfigureerimiseks.

   > [!NOTE]
   > Kontrollige, et brauseri hüpikakende blokeerija ei blokeeriks autentimise akent, kui valite nupu **Logi sisse**.

1. Valige Customer Insights -i keskkond, kust soovite andmeid tuua.

1. Määratlege väljavastendus Dynamics 365 rakenduses kirjete jaoks. Customer Insights'i andmetest olenevalt saate valida järgmiste suvandite vastendamise:
   - Kontaktiga vastendamiseks valige kliendiolemi väli, mis vastab teie kontaktiolemi ID-le.
   - Kontoga vastendamiseks valige kliendiolemi väli, mis vastab teie kontoolemi ID-le.

   > [!div class="mx-imgBorder"]
   > ![Ühendu ID väljaga.](media/contact-id-field.png "Kontakti ID väli.")

1. Sätete salvestamiseks valige **Salvesta konfiguratsioon**.

1. Järgmisena peate määrama rakenduses Dynamics 365 turberollid, et kasutajad saaksid kliendikaarti kohandada ja näha. Avage lahenduses Dynamics 365 **Sätted** > **Turvalisus** > **Kasutajad**. Valige kasutajarollide redigeerimiseks kasutajad ja valige **Halda rolle**.

1. Määrake roll **Customer Insightsi kaardikohandaja** nendele kasutajatele, kes kohandavad kogu ettevõtte kaardil kuvatavat sisu.

## <a name="add-customer-card-controls-to-forms"></a>Kliendikaardi juhtelementide lisamine vormidele

Sõltuvalt stsenaariumist saate lisada juhtelemente vormidele **Kontakt** või **Konto**. Kui teie Customer Insightsi keskkond on mõeldud ärikontodele, soovitame lisada juhtelemendid vormile Konto. Sellisel juhul asendage allolevate toimingute seas sõna „kontakt” sõnaga „konto”.

1. Kliendikaardi juhtelementide lisamiseks kontaktivormile avage lahenduses Dynamics 365 **Sätted** > **Kohandused**.

1. Valige **Süsteemi kohandamine**.

1. Sirvige olemi **Kontakt** juurde, laiendage see ja valige **Vormid**.

1. Valige kontakti vorm, kuhu soovite kliendikaardi juhtelemendid lisada.

    > [!div class="mx-imgBorder"]
    > ![Kontaktivormi valimine.](media/contact-active-forms.png "Kontaktivormi valimine.")

1. Juhtelemendi lisamiseks lohistage väljaredaktoris mistahes väli **Väljauurijast** sinna, kuhu soovite juhtelemendi paigutada.

1. Valige äsja lisatud vormi väli ja seejärel valige **Muuda atribuute**.

1. Minge vahekaardile **Juhtelemendid** ja valige **Lisa juhtelement**. Valige üks saadaolevatest kohandatud juhtelementidest ja valige **Lisa**.

1. **Välja atribuutide** dialoogis tühjendage märkeruut **Kuva vormil silt**.

1. Valige juhtelemendi jaoks suvand **Veeb**. Valige rikastamise juhtelemendi jaoks, millist rikastamise tüüpi soovite kuvada, konfigureerides välja **enrichmentType**. Lisage igale rikastamistüübile eraldi rikastamise juhtelement.

1. Värskendatud kontaktivormi avaldamiseks valige **Salvesta** ja **Avalda**.

1. Minge avaldatud kontakti vormile. Näete äsja lisatud juhtelementi. Võimalik, et peate esmakordsel kasutusel sisse logima.

1. Selleks et kohandada seda, mida soovite kohandatud juhtelemendil kuvada, valige paremas ülanurgas redigeerimise nupp.

## <a name="upgrade-customer-card-add-in"></a>Kliendikaardi lisandmooduli täiendamine

Kliendikaardi lisandmoodulit ei täiendata automaatselt. Uusimale versioonile täiendamiseks järgige neid juhiseid Dynamics 365 rakenduses, kus on installitud lisandmoodul.

1. Avage Dynamics 365 rakenduse jaotises **Sätted** > **Kohandamine** ja valige **Lahendused**.

1. Otsige lisandmoodulite tabelist **CustomerInsightsCustomerCard** ja valige see rida.

1. Valige tegumiribalt **Rakenda lahenduse täiendus**.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Lahenduse täiendamine Dynamics 365 rakenduste kohandamisalal.":::

1. Pärast täiendamisprotsessi käivitamist kuvatakse laadimisnäidik kuni täienduse lõpuleviimiseni. Kui uuemat versiooni pole, kuvab täiendus tõrketeate.

## <a name="troubleshooting"></a>Tõrkeotsing

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Kliendikaardi lisandmooduli juhtelemendid ei leia andmeid

**Probleem:**

Isegi õigesti konfigureeritud ID-väljade korral ei leia juhtelemendid ühegi kliendi kohta andmeid.  

**Lahendus.**

1. Veenduge, et konfigureerisite kaardi lisandmooduli vastavalt juhistele: [Kliendikaardi lisandmooduli konfigureerimine](#configure-the-customer-card-add-in)

1. Vaadake üle andmete allaneelamise konfiguratsioon. Redigeerige kontakti ID GUID-i sisaldava Dynamics 365-i süsteemi andmeallikas. Kui kontakti ID GUID kuvatakse redaktoris Power Query suurtähtedega, proovige järgmisi samme.
    1. Redigeerige andmeallikas, et avada andmeallikas redaktoris Power Query.
    1. Valige kontakti ID veerg.
    1. Valige **päiseribal teisendamine**, et näha saadaolevaid toiminguid.
    1. Valige **väiketähed**. Kontrollige, kas tabelis olevad GUID-id on nüüd väiketähed.
    1. Salvestage andmeallikas.
    1. Käivitage GUID-i muudatuste levitamiseks andmete allaneelamine, ühendamine ja allavoolu protsessid.

Kui süsteem on täieliku värskendamise lõpetanud, peaksid kliendikaardi lisandmooduli juhtelemendid näitama eeldatavaid andmeid.

[!INCLUDE [footer-include](includes/footer-banner.md)]
