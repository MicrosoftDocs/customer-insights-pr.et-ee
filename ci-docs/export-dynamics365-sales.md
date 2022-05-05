---
title: Customer Insightsi andmete eksportimine rakendusse Dynamics 365 Sales
description: Lugege, kuidas konfigureerida ühendust ja eksportida Dynamics 365 Sales'i.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 987690283090ec83ca75f50bf8f3cd8da9295887
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642635"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>Kasutage segmente rakendusega Dynamics 365 Sales (eelversioon)



Kasutage kliendiandmeid turundusloendite loomiseks, töövoogude järeltegevusteks ja kampaaniate saatmiseks Dynamics 365 Salesi abil.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Eksport Dynamics 365 Salesisse on piiratud 100 000 liikmega segmendi kohta.
- Segmendi eksport Rakendusse Dynamics 365 Sales võib võtta kuni 3 tundi. 

## <a name="prerequisite-for-connection"></a>Ühenduse eeltingimus

1. Enne segmendi eksportimist Customer Insightsist Salesi, peavad kontaktikirjed olema olemas rakenduses Dynamics 365 Sales. Lugege lisateavet selle kohta, kuidas dynamics 365 Salesi [kontakte rakenduses alla neelata Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Segmentide eksportimine Customer Insightsist müüki ei loo müügieksemplarides uusi kontaktikirjeid. Salesi kontaktikirjed tuleb customer Insightsis alla neelata ja kasutada andmeallikas. Need tuleb lisada ka ühendatud kliendi olemisse, et vastendada kliendi ID-d ja kontakti ID-deks, enne kui segmente saab eksportida.

## <a name="set-up-the-connection-to-sales"></a>Ühenduse loomine Sales'iga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Dynamics 365 Sales** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage väljale **Serveri aadress** oma organisatsiooni Salesi URL.

1. Jaotises **Serveri administraatorikonto** valige suvand **Logi sisse** ja valige rakenduse Dynamics 365 Sales konto.

1. Vastendage kliendi ID väli Dynamics 365 kontakti ID-ga.

1. Ühenduse loomiseks valige **Salvesta**. 

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus Dynamics 365 Sales jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Valige üks või mitu segmenti.

1. Valige **Salvesta**

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
