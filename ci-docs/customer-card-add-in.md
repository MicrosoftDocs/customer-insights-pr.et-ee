---
title: Kliendikaardi lisandmoodul Dynamics 365 rakendustele (sisaldab videot)
description: Saate selle lisandmooduli abil kuvada Kliendiprofiili andmed Customer Insightsist Dynamics 365 rakendustes.
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
ms.openlocfilehash: 8508880bb3274bb491a314a043a5222d4d381073
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755631"
---
# <a name="customer-card-add-in-preview"></a>Kliendikaardi lisandmoodul (eelvaade)

Saate oma klientide kohta täieliku ülevaate otse Dynamics 365 rakendustes. Kui kliendikaardi lisandmoodul on installitud toetatud Dynamics 365 rakendusse, saate valida kliendiprofiili väljade, ülevaadete ja tegevuse ajaskaala kuvamise. Lisandmoodul toob andmed Customer Insights -i kaudu, mõjutamata ühendatud Dynamics 365 rakenduse andmeid.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Eeltingimused

- Lisandmoodul töötab ainult Dynamics 365 mudelipõhiste rakendustega (nt Müük või Klienditeenindus, versioon 9.0 ja uuemad).
- Selleks et teie Dynamics 365 andmed vastendataks Customer Insightsi [kliendiprofiilidega, soovitame need konnektori abil Microsoft Dataverse Dynamics 365 rakendusest alla neelata](connect-power-query.md). Kui kasutate Dynamics 365 kontaktide (või ettevõtete) allaneelamiseks mõnda muud meetodit, peate veenduma, et `contactid` väli (või`accountid`) on määratud [selle andmeallikas esmaseks võtmeks andmete ühendamise protsessi vastendamise etapis](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- Kõik kliendikaardi lisandmooduli Dynamics 365 kasutajad tuleb [andmete nägemiseks lisada Customer Insightsi kasutajatena](permissions.md).
- [Andmete otsimiseks on vaja konfigureeritud otsingu- ja filtreerimisvõimalusi](search-filter-index.md) Customer Insightsis.
- Iga lisandmooduli juhtelement tugineb Customer Insightsis kindlatele andmetele. Teatud andmed ja juhtelemendid on saadaval ainult mingit kindlat tüüpi keskkondades. Lisandmooduli konfiguratsioon teavitab teid, kui juhtelement pole valitud keskkonnatüübi tõttu saadaval. Lisateave [keskkondade kasutamise kohta](work-with-business-accounts.md).
  - **Mõõtühiku juhtelement**: Nõuab [konfigureeritud mõõtmetega](measures.md) kliendi atribuutide tüüpe.
  - **Luurekontroll**: nõuab ennustuste või kohandatud mudelite [abil](predictions-overview.md) loodud andmeid.
  - **Kliendi üksikasjade juhtelement**: Kõik profiili väljad on saadaval ühendatud kliendiprofiilis.
  - **Rikastamise juhtelement**: Nõuab kliendiprofiilile aktiivsete [rikastamiste](enrichment-hub.md) rakendamist. Kaardi lisandmoodul toetab neid rikastamisi: [Microsofti pakutavad kaubamärgid](enrichment-microsoft.md), [Microsofti pakutavad huvid ja](enrichment-microsoft.md) Microsofti pakutavad [Office'i kaasamise andmed](enrichment-office.md).
  - **Kontaktide juhtelement**: Vaja on semantilise kontaktitüübi olemi määratlust.
  - **Ajaskaala juhtelement**: Nõuab [konfigureeritud tegevusi](activities.md).

## <a name="install-the-customer-card-add-in"></a>Kliendikaardi lisandmooduli installimine

Kliendikaardi lisandmoodul on rakenduste Customer engagement lahendus Dynamics 365-s. Lahenduse installimiseks avage AppSource ja otsige jaotist **Dynamicsi kliendikaart**. Valige [AppSource'is kliendikaardi lisandmoodul](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ja valige **Hangi kohe**.

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

Sõltuvalt stsenaariumist saate lisada juhtelemente vormidele **Kontakt** või **Konto**. Kui teie Customer Insightsi keskkond on mõeldud ärikontodele, soovitame juhtelemendid lisada vormile Konto. Sellisel juhul asendage allolevate toimingute seas sõna „kontakt” sõnaga „konto”.

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

Isegi õigesti konfigureeritud ID-väljade puhul ei leia juhtelemendid ühegi kliendi andmeid.  

**Lahendus.**

1. Veenduge, et konfigureerisite kaardi lisandmooduli vastavalt juhistele: [Kliendikaardi lisandmooduli konfigureerimine](#configure-the-customer-card-add-in)

1. Vaadake üle andmete allaneelamise konfiguratsioon. Redigeerige kontakti ID GUID-d sisaldava Dynamics 365 süsteemi andmeallikas. Kui kontakti ID GUID kuvatakse redaktoris Power Query suurtähtedega, proovige järgmisi juhiseid.
    1. Redigeerige andmeallikas andmeallikas avamiseks redaktoris Power Query.
    1. Valige kontakti ID veerg.
    1. Saadaolevate toimingute vaatamiseks valige **päiseribal Teisenda**.
    1. Valige **väiketäht**. Kinnitage, kas tabelis olevad GUID-id on nüüd väiketähtsad.
    1. Salvestage andmeallikas.
    1. Käivitage GUID-i muudatuste levitamiseks andmete allaneelamine, ühendamine ja järgmise etapi protsessid.

Pärast seda, kui süsteem on täieliku värskendamise lõpetanud, peaksid kliendikaardi lisandmooduli juhtelemendid kuvama eeldatavad andmed.

[!INCLUDE [footer-include](includes/footer-banner.md)]
