---
title: Avaleht sihtrühmaülevaadetes
description: Alustage rakendusega tutvumist avalehel.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597230"
---
# <a name="create-a-new-environment"></a>Loo uus keskkond

## <a name="create-a-trial-environment"></a>Loo proovikeskkond

Saate prooviversiooni saamiseks registreeruda [prooviversiooni registreerimislehel](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> Prooviversioonid aeguvad 30 päeva pärast.

1. Valige suvand **Registreeruge tasuta prooviversiooni saamiseks** ja seejärel suvand **Registreeru kohe**.

1. Sisestage oma töökoha või kooli meiliaadress, rääkige meile endast rohkem ja valige suvand **Edasi**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Prooviversiooni eksemplari kasutajaks registreerumise dialoog":::

1. Sisestage oma uue keskkonna jaoks **Nimi**. 

1. Valige prooviversiooni tüüp.

1. Valige oma keskkonna jaoks **Regioon**.

1. Soovi korral Dynamics 365 organisatsiooni administraatoritele: valige suvand **Täpsemad sätted** ja sisestage oma organisatsiooni URL, et kasutada prognoosi funktsioone, nagu kliendivoolavus.

1. Valige käsk **Loo**. 

Pärast keskkonna loomist näete **demokeskkonda**, mis võimaldab teil väljamõeldud andmetega rakendust avastada. Saate näidisandmeid oma valdkonna järgi muuta. Valige päisest suvand **Sätted** ja seejärel suvand **Demo sätted**. Peale selle saate muuta ka visuaalset kujundust. 

Valige [keskkond](#switch-environments), mille registreerimistoimingu käigus lõite, et töötada oma andmetega.

## <a name="create-a-new-production-or-sandbox-environment"></a>Uue töö- või liivakastikeskkonna loomine

Valige oma keskkonna rakenduse päises **Keskkondade** valija ja seejärel valige **Uus**.

Järgige etappe samamoodi, nagu [proovikeskkonna loomisel](#create-a-trial-environment). Vaikimisi salvestatakse andmed Customer Insightsi hallatavasse andmejärve. Kui valite suvandi **Täpsemad sätted**, kuvatakse lisasuvand, mis võimaldab teil andmed oma Azure Data Lake’i salvestada. Sisestage oma konto nimi ja konto võti, et luua oma Azure Data Lake’iga ühendus. 

> [!IMPORTANT]
> Andmete salvestamisel teenusesse Azure Data Lake Storage nõustute, et andmed edastatakse selle Azure’i salvestusruumi konto asjakohasesse geograafilisse asukohta ja need talletatakse seal, ning et see võib erineda rakendusse Dynamics 365 Customer Insights talletatud andmete salvestuskohast. [Lisateavet leiate Microsofti usalduskeskusest.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Avalehe avastamine

[Pääsete oma sihtrühmaülevaadetele juurde Dynamics 365 Customer Insightsist](https://home.ci.ai.dynamics.com/) järgmise URL-i kaudu: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
**Avalehel** kuvatakse segmentide, mõõtude ja rikastamisandmete (kui need on konfigureeritud) ülevaade pärast etappide [kaardistamine](map-entities.md), [vastendamine](match-entities.md) ja [koondamine](merge-entities.md) lõpuleviimist.

> [!div class="mx-imgBorder"] 
> ![Avalehe ülevaated](media/home-page-insights.png "Avalehe ülevaated")

Jaotises **Viimatised segmendid** näete klientide rühmi vastavalt teie määratletud demograafilistele, käitumuslikele või ülekande atribuutidele. [Segmentide loomine](segments.md) aitab teil rühmitada oma kliendibaasi ja oma äritegevusi paremini sihtida.

**Viimastes mõõtudes** kuvatakse paanid teie määratletud [juhtimismõõdikutega (KPI-dega)](measures.md). Näiteks keskmine kliendivoolavuse tõenäosus või kliendi keskmine kulutamine veebis.

Jaotises **Viimased rikastamised** loetletakse rikastamise käitamise tulemused, mis hiljuti lõpetati. [Rikastamised](enrichment-hub.md) lisavad teie kliendibaasi kohta teavet. Näiteks mõistes huvisid ja kaubamärke millele neil on külgetõmme.

## <a name="switch-environments"></a>Vaheta keskkondasid

Keskkondade vahetamiseks valige juhtelement **Keskkond** lehe paremas ülanurgas.

> [!div class="mx-imgBorder"] 
> ![Keskkondade vahetamine](media/home-page-environment-switcher.png "Keskkondade vahetamine")

Administraatorid saavad luua ja hallata [mitut keskkonda](manage-environments.md). Mitme keskkonna haldamine võib olla kasulik näiteks juhul, kui teie organisatsioon tegutseb rahvusvaheliselt ning teil tuleb andmeid ja ülevaateid erinevatel viisidel eraldada.

## <a name="next-step"></a>Järgmine etapp

Avalehel oma ülevaadete kuvamiseks, tuleb esmalt [lisada andmeallikad](data-sources.md) ja [ühendada](data-unification.md) andmed kliendiprofiilide loomiseks.


[!INCLUDE[footer-include](../includes/footer-banner.md)]