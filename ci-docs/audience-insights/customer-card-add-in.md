---
title: Dynamics 365 rakenduste kliendikaardi lisandmoodul (sisaldab videot)
description: Saate selle lisandmooduliga kuvada Dynamics 365 rakenduste sihtrühma ülevaadete andmeid.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: ce6c8fab84fd4c5dfc9f78b91dde3483a1d358c1
ms.sourcegitcommit: 11308ed275b4b25a35576eccfcae9dda9e2c2784
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/02/2022
ms.locfileid: "8085210"
---
# <a name="customer-card-add-in-preview"></a>Kliendikaardi lisandmoodul (eelvaade)



Saate oma klientide kohta täieliku ülevaate otse Dynamics 365 rakendustes. Kui kliendikaardi lisandmoodul on installitud toetatud Dynamics 365 rakendusse, saate valida kliendiprofiili väljade, ülevaadete ja tegevuse ajaskaala kuvamise. Lisandmoodul toob andmed Customer Insights -i kaudu, mõjutamata ühendatud Dynamics 365 rakenduse andmeid.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Eeltingimused

- Lisandmoodul töötab ainult Dynamics 365 mudelipõhiste rakendustega (nt Müük või Klienditeenindus, versioon 9.0 ja uuemad).
- Kui teie Dynamics 365 andmed vastendavad vaatajaskonna ülevaate kliendiprofiilidega, soovitame need [konnektori abil Microsoft Dataverse alla neelata Rakendusest Dynamics 365](connect-power-query.md). Kui kasutate Dynamics 365 kontaktide (või kontode) allaneelamiseks mõnda muud meetodit, peate `contactid` veenduma, et väli (või `accountid`) on andmete ühendamise protsessi kaardietapis seatud [selle andmeallikas esmaseks võtmeks](map-entities.md#select-primary-key-and-semantic-type-for-attributes). 
- Kõik Dynamics 365 kliendikaardi lisandmooduli kasutajad peavad andmete nägemiseks olema [lisatud kasutajatena](permissions.md) publiku ülevaadetes.
- [Konfigureeritud otsing ja võimekuste filtreerimine](search-filter-index.md) on publiku ülevaadetes nõutud andmete otsingu töötamise jaoks.
- Iga lisandmooduli juhtelement kasutab sihtrühma ülevaadetes teatud andmeid. Teatud andmed ja juhtelemendid on saadaval ainult mingit kindlat tüüpi keskkondades. Lisandmooduli konfiguratsioon annab teile teada, kui juhtelement pole valitud keskkonnatüübi tõttu saadaval. Lisateave [keskkondade kasutamise kohta](work-with-business-accounts.md).
  - **Mõõtühiku juhtelement**: Nõuab [konfigureeritud mõõtmetega](measures.md) kliendi atribuutide tüüpe.
  - **Luurekontroll**: nõuab ennustuste või kohandatud mudelite [abil](predictions-overview.md) loodud andmeid.
  - **Kliendi üksikasjade juhtelement**: Kõik profiili väljad on saadaval ühendatud kliendiprofiilis.
  - **Rikastamise juhtelement**: Nõuab kliendiprofiilile aktiivsete [rikastamiste](enrichment-hub.md) rakendamist. Kaardi lisandmoodul toetab neid rikastumiseid: [Microsofti pakutavad kaubamärgid](enrichment-microsoft.md), [Microsofti pakutavad](enrichment-microsoft.md) huvid ja [Microsofti esitatud Office'i kaasamise andmed](enrichment-office.md).
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

Sõltuvalt stsenaariumist saate lisada juhtelemente vormidele **Kontakt** või **Konto**. Kui teie sihtrühma ülevaadete keskkond on seotud ärikontoga, on soovitatav juhtelemendid lisada Konto vormile. Sellisel juhul asendage allolevate toimingute seas sõna „kontakt” sõnaga „konto”.

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

Isegi õigesti konfigureeritud ID-väljade puhul ei leia juhtelemendid andmeid ühegi kliendi kohta.  

**Lahendus.**

1. Veenduge, et konfigureerisite kaardi lisandmooduli vastavalt juhistele: [Kliendikaardi lisandmooduli konfigureerimine](#configure-the-customer-card-add-in) 

1. Vaadake üle andmete allaneelamise konfiguratsioon. Redigeerige dynamics 365 süsteemi andmeallikas, mis sisaldab kontakti ID GUID-d. Kui kontakti ID GUID kuvatakse redaktoris Power Query suurtähtedega, proovige järgmist. 
    1. Redigeerige andmeallikas, et avada andmeallikas redaktoris Power Query.
    1. Valige kontakti ID veerg.
    1. Saadaolevate toimingute kuvamiseks valige **päiseribal Teisenda**.
    1. Valige **väiketäht**. Kinnitage, kas tabelis olevad GUID-d on nüüd väiketähed.
    1. Salvestage andmeallikas.
    1. Käivitage andmete allaneelamine, ühendamine ja järgnevad protsessid GUID muudatuste levitamiseks. 

Pärast täieliku värskendamise lõpetamist peaksid kliendikaardi lisandmooduli juhtelemendid näitama oodatud andmeid. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
