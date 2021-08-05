---
title: Loo ja konfigureeri Customer Insights -i prooviversioon
description: Juhised selle prooviversiooni tellimuse toomiseks Dynamics 365 Customer Insights -i ja konfigureerimiseks.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f80654f03252142ce08241ff3ca3606be4595740
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650461"
---
# <a name="set-up-a-trial-environment"></a>Seadistage proovikeskkond 

Prooviversioon Dynamics 365 Customer Insights võimaldab teil vaadata põhifunktsioone ja saada lisateavet mitmesuguste funktsioonide kohta. Proovitellimus kustutatakse pärast aegumist. Proovikeskkonnad loovad üksikkasutajad, kes saavad oma proovikeskkonna administraatoriks. Nad saavad kutsuda prooviversiooni rohkem kasutajaid ja konfigureerida mitmesuguseid funktsioone.

## <a name="create-a-trial-environment"></a>Loo proovikeskkond

Saate prooviversiooni saamiseks registreeruda [prooviversiooni registreerimislehel](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Valige suvand **Registreeruge tasuta prooviversiooni saamiseks** ja seejärel suvand **Registreeru kohe**.

1. Sisestage oma töö või kooli meiliaadress, rääkige meile endast ja valige **Alustamine**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Prooviversiooni eksemplari kasutajaks registreerumise dialoog":::

1. Vaadake üle tingimused ja kinnitamiseks valige suvand **Jätka**.

1. Sisestage oma uue keskkonna jaoks **Nimi**. 

1. Määrake keskkonna **tüübiks** **Prooviversioon**.

1. **Valdkonna demo valimise** väljal võite soovi korral valida valdkonnapõhise andmekomplekti. Võite ka [valdkonna demo muuta](#use-industry-specific-demo-data-sets-in-audience-insights) hiljem ja alustada vaikeandmekomplektiga.

1. Valige oma keskkonna jaoks **Regioon**.

1. Kui olete Dynamics 365 organisatsiooni administraator, valige **Täpsemad sätted** ja sisestage oma organisatsiooni URL, kus saate kasutada prognoosi funktsioone nagu kliendivoolavus prognoosi. 

1. Valige käsk **Loo**. 

Keskkonna seadistamiseks kulub mõni hetk. Pärast lõpetamist suunatakse teid demokeskkonda või valdkonna demosse, mille valite ülaltoodud etapis. Nüüd saate rakendusega tutvuda koos kirjutuskaitstud demoandmetega. Oma andmete keskkonda lisamiseks vaadake teemat [Stsenaariumipõhise demoandmete loomine oma keskkonnas](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Äsja loodud proovikeskkonna kuvatõmmis.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Valdkonnapõhise demoandmekomplektide kasutamine publiku ülevaadetes

Tõeliste andmeallikate ühendamine on üks oluline etapp Customer Insights -i võimu kasutamisel. Funktsioonide proovimiseks ilma oma andmeid segamata saate soovi korral kasutada valdkonnapõhiseid demoandmeid. Järgmistes valdkondades on saadaval paar demoandmekomplekti. 

-   Autotööstus
-   Pangandus
-   Tarbekaubad
-   Riigiasutus
-   Tervishoiuteenus
-   Majutus
-   Kindlustus
-   Tootmine
-   Professionaalsed teenused
-   Jaemüük

### <a name="see-industry-specific-demo-data-in-trials"></a>Valdkonnapõhise demoandmete vaatamine prooviversioonis

Customer Insights -i kirjutuskaitstud versiooni puhul, mis on kohandatud konkreetsele valdkonnale või stsenaariumile, alustage Demokeskkonnast. 
 
1.  Valige sihtrühma ülevaadetest **Demo** keskkond keskkonnavalijast.

2.  **Avalehel** valige Vali valdkonna demo ripploendi menüüst suvand.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Valige proovikeskkonna jaoks valdkond.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Stsenaariumipõhise demoandmete loomine oma keskkonnas

Administraatorina valige keskkonna loomiseks rakendusepäises keskkonnavalija. Uues keskkonnas saate konfigureerida oma andmeallikaid ja seadistada rakenduse vastavalt oma nõuetele. 

1.  Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2.  Oma andmeallikate importimiseks minge [andmetoomise juhendisse](data-sources.md).     
   Kui eelistate töötada näidisandmetega, mis lubavad teil kasutada andmete toomist, võite kasutada valdkonna demoandmeid oma keskkonnas. Valige suvand **Impordi Datahub-ist** ja järgige allolevaid juhiseid.

3.  Valige valdkonnakaart, mis sobib teie stsenaariumiga. 

4.  Vaadake ülee ja soovi korral värskendage andmeallika nime. 

5.  Valige **Järgmine** näidisandmete sissetoomiseks. 

Nüüd saab kasutada sissetoodud andmeid, et kohandada Customer Insights oma stsenaariumile. Kui soovite vaadata allaneetud demoandmetele omast keskkonda, valige keskkonnavalijas **<Industry> Demo** suvand.

## <a name="limitations-in-trials"></a>Prooviversiooni piirangud

- Vaikimisi prooviversioon aktiivne 30 päeva. Siiski saate laiendada neid 23 päeva pärast prooviversiooni sisselogimist.
- Te ei saa kasutada oma Azure Data Lake Storage'i kontot väljundandmete talletuseks prooviversiooni ajal. Siiski saate andmeid tuua Data Lake Storage -i kontolt.
- Saate talletada kuni 3 GB andmeid Dataverse -i keskkonnas, mis luuakse automaatselt Customer Insights -i prooviversiooni käivitamisel.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Andmete kopeerimine prooviversioonist tasulisele kordustellimusele

Üldiselt soovitame Customer Insights tasulisele versioonile üleminekul alustada värskelt oma andmetega. 

Soovi korral saate oma andmed kopeerida proovikeskkonnast, kui ostate Customer Insights -i. Sätete migreerimiseks proovikeskkonnast tasulisesse keskkonda peate olema Customer Insights -i prooviversiooni ja Microsoft 365 rentniku globaalse administraatori või Dynamics 365 administraatori administraator. 

Pärast esmakordset Customer Insights -i tasulisesse eksemplari sisselogimist palutakse teil luua uus keskkond. Selle protsessi käigus saate kopeerida konfiguratsiooni olemasolevast keskkonnast ja migreerida enamiku sätetest. Kui teil on ülal nimetatud õigused, kuvatakse selles loendis proovikeskkond. Lisateavet leiate teemast [Keskkonna konfiguratsiooni kopeerimine](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Järgmised etapid

Vaadake läbi järgmised artiklid, mis aitavad teil Customer Insights -i konfigureerimisega algust teha. 

- [Lisage veel kasutajaid ja määrake õiguseid](permissions.md)i.
- [Tooge sisse oma andmeallikaid](data-sources.md) ja käivitage need [andmete ühendamise protsessis](data-unification.md) , et [saada ühtseid kliendiprofiile](customer-profiles.md).
- [Rikastage ühendatud kliendiprofiile](enrichment-hub.md) või [käivitage ennetavad mudeleid](predictions-overview.md).
- Looge [segmente](segments.md) klientide rühmitamiseks ja [mõõdikuid](measures.md) KPI-de ülevaatamiseks.
- Seadistage [ühendused](connections.md) ja [eksport](export-destinations.md) andmete alamhulkade töötlemiseks muudes rakendustes.