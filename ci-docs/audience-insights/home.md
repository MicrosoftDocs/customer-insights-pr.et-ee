---
title: Avaleht sihtrühmaülevaadetes
description: Alustage rakendusega tutvumist avalehel.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405552"
---
# <a name="create-a-new-environment"></a>Loo uus keskkond

## <a name="create-a-trial-environment"></a>Loo proovikeskkond

Saate prooviversiooni saamiseks registreeruda [prooviversiooni registreerimislehel](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Prooviversioonid aeguvad 30 päeva pärast.

1. Valige suvand **Registreeruge tasuta prooviversiooni saamiseks** ja seejärel suvand **Registreeru kohe**.

1. Sisestage oma töökoha või kooli meiliaadress, rääkige meile endast rohkem ja valige suvand **Edasi**.

1. Sisestage oma uue keskkonna jaoks **Nimi**. 

1. Valige prooviversiooni tüüp.

1. Valige oma keskkonna jaoks **Regioon**.

1. Soovi korral Dynamics 365 organisatsiooni administraatoritele: valige suvand **Täpsemad sätted** ja sisestage oma organisatsiooni URL, et kasutada prognoosi funktsioone, nagu kliendivoolavus.

1. Valige käsk **Loo**. 

Pärast keskkonna loomist näete **demokeskkonda**, mis võimaldab teil väljamõeldud andmetega rakendust avastada. Saate näidisandmeid oma valdkonna järgi muuta. Valige päisest suvand **Sätted** ja seejärel suvand **Demo sätted**. Peale selle saate muuta ka visuaalset kujundust. 

Valige [keskkond](#change-between-environments), mille registreerimistoimingu käigus lõite, et töötada oma andmetega.

## <a name="create-a-new-production-or-sandbox-environment"></a>Uue töö- või liivakastikeskkonna loomine

Valige oma keskkonnas päises olev ikoon **Sätted** ja seejärel suvand **Uus keskkond**.

Järgige etappe samamoodi, nagu [proovikeskkonna loomisel](#create-a-trial-environment). Kui valite suvandi **Täpsemad sätted**, kuvatakse lisasuvand, mis võimaldab teil andmed oma Azure Data Lake’i salvestada. Sisestage oma konto nimi ja konto võti, et luua oma Azure Data Lake’iga ühendus. Vaikimisi salvestatakse andmed Customer Insightsi hallatavasse andmejärve.

> [!IMPORTANT]
> Andmete salvestamisel teenusesse Azure Data Lake Storage nõustute, et andmed edastatakse selle Azure’i salvestusruumi konto asjakohasesse geograafilisse asukohta ja need talletatakse seal, ning et see võib erineda rakendusse Dynamics 365 Customer Insights talletatud andmete salvestuskohast. [Lisateavet leiate Microsofti usalduskeskusest.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Avalehe avastamine

Pääsete [oma Customer Insightsi keskkonnale juurde](https://home.ci.ai.dynamics.com/) järgmise URL-i kaudu: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Avalehel** kuvatakse teie kliendibaasi ja põhinäitajate ülevaade teie ettevõtte seisukorra jälgimiseks.

> [!div class="mx-imgBorder"] 
> ![Avalehe ülevaated](media/home-page-insights.png "Avalehe ülevaated")

Jaotises **Viimatised segmendid** näete klientide rühmi vastavalt teie määratletud demograafilistele, käitumuslikele või ülekande atribuutidele. [Segmentide loomine](segments.md) aitab teil oma äritegevust paremini sihtida.

Suvand **Viimatised meetmed** kuvab [meetmetega](measures.md) paanid. Meetmed on juhtimismõõdustikud (KPId), mille teie olete määratlenud. Näiteks kliendivoolavuse keskmine tõenäosus või keskmine veebis kulutatud summa kliendi kohta.

Jaotises **Viimased rikastamised** loetletakse rikastamise käitamise tulemused, mis hiljuti lõpetati. Rikastamine lisab teie kliendibaasi kohta teavet. Näiteks mõistes huvisid ja kaubamärke millele neil on külgetõmme. Seda teavet saab avada [rikastamise](enrichment-microsoft-graph.md) võimaluste abil, kui olete lõpule viinud [kaardistamise](map-entities.md), [vastendamise](match-entities.md) ja [ühendamise](merge-entities.md) etapid.

## <a name="change-between-environments"></a>Keskkondade vahetamine

Pärast [andmeallikate](data-sources.md)seadistamist ja konfigureerimist, peaksite demokeskkonnast reaalajas keskkonnale üle minema. Tootmiskeskkonna kasutamine võimaldab teil töötada oma kliendiandmetega. Keskkondade vahetamiseks valige juhtelement **Keskkond** lehe paremas ülanurgas.

> [!div class="mx-imgBorder"] 
> ![Keskkondade vahetamine](media/home-page-environment-switcher.png "Keskkondade vahetamine")

Administraatorid saavad luua ja hallata [mitut keskkonda](manage-environments.md). Mitme keskkonna haldamine võib olla kasulik näiteks juhul, kui teie organisatsioon tegutseb rahvusvaheliselt ning teil tuleb andmeid ja ülevaateid erinevatel viisidel eraldada.

## <a name="next-step"></a>Järgmine etapp

Avalehel oma ülevaadete kuvamiseks, tuleb esmalt [lisada andmeallikad](data-sources.md) ja [ühendada](data-unification.md) andmed kliendiprofiilide loomiseks.
