---
title: Sündmuste loomine ja muutmine
description: Kuidas sündmusi luua ja muuta.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: dbafa2231daa82c34ee2ec8292111575e95af675
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228198"
---
# <a name="create-and-modify-events"></a>Sündmuste loomine ja muutmine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Sündmus on andmed, mis tähistab kasutaja käitumist, nt tegevusi veebisaidil.

- *Põhi* sündmuse kirjed, kui kasutaja vaatab lehte (vaata sündmust) või suhtleb sisuga (toimingusündmus).
- *Täpsustatud* sündmus on baassündmuse virtuaalvaade. Sündmuste määratlemiseks eemaldage ja lisage atribuudid või filtreerige sündmused atribuudiväärtuste põhjal.

## <a name="prerequisites"></a>eeltingimused

Sündmuste hankimiseks peavad teie veebisaidi andmed olema koodilõigendi abil esmalt seotud kaasavuse ülevaadetega. Lisateavet leiate teemast [Veebi-SDK installimine veebisaidile](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Esmalt ühendage oma andmed.":::

## <a name="create-refined-events"></a>Täpsemate sündmuste loomine

Kasutage nende sündmuste funktsiooni, et vähendada [eksporti](export-events.md) või eemaldada atribuute, mis pole eksportimiseks vajalikud.

> [!NOTE]
> Kui olete veebi-SDK oma veebisaidile salvestatud, saate vaadata oma baassündmusi ja luua täpsustatud sündmused. 

Baassündmuste vaatamiseks:

1. Valige vasakpoolsel navigeerimispaanil suvand **Andmed**.

1. Valige **Sündmused**, et näha tööruumis kõigi sündmuste loendit.

    :::image type="content" source="media/data-events.png" alt-text="Vaadake sündmusi.":::

Põhisündmusest täpsustatud sündmuse loomiseks toimige järgmiselt: 

1. Minge **Andmed** > **Sündmused** ja valige ekraani ülaosast **+ Uued sündmused**.

1. Tehke dialoogis **Uued sündmused** valik **Täpsustatud sündmuste loomine** ja seejärel klõpsake nuppu **Edasi**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Uute sündmuste viisard.":::
     
1. Sisestage dialoogi **Uued sündmused** järgnev teave:

   - Valige sündmus **Baassündmuste** ripploendist.
   - Sisestage **Täpsustatud sünmuse kuvatav nimi** väljale.
   - Soovi korral värskendage **Tegelikku nime** tühikuid kasutamata.

1. Valige **Loo** sätete kuvamiseks.

Täpsustatud sündmus kuvatakse nüüd teie loendis **Sündmused**.

### <a name="edit-event-name"></a>Redigeeri sündmuse nime

Saate muuta baas- või täpsustatud sündmuse nime ja atribuute.

1. Mine **Andmed** > **Sündmused**. 

1. Valige **Veel [...]** sündmuse jaoks ja valige **Redigeeri nime**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Suvandid loomaks rafineeritud sündmuseid.":::

3. Värskendage sündmuse nime ja valige **Muuda nime**.

### <a name="view-the-details-of-a-refined-event"></a>Vaadake täpsustatud sündmuse üksikasju:

1. Valige loendis **Sündmus** oma baas- või täpsustatud sündmus. 

1. Paani **Redigeeri atribuute** avamiseks valige kuva ülaosast **Lisa ja eemalda atribuute**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Atribuutide lisamine ja eemaldamine.":::

1. Märkige ruudud, mida soovite kuvada, ja atribuudid, mida soovite peita. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Täpsustatud sündmuste atribuutide redigeerimine.":::

1. Valiku rakendamiseks valige **Kinnita** ja seejärel klõpsake nuppu **Salvesta**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Täpsustatud sündmuse valitud atribuutide redigeerimine

1. Minge **Andmed** > **Sündmused** ja valige täpsustatud sündmused et avada üksikasjalikum vaade.
1. Valige **Lisa ja eemalda atribuudid**. 
1. Muutke märkeruute.
1. Valige **Kinnita** ja seejärel **Salvesta** muudatuste rakendamiseks.

Lisateavet sündmuste eksportimise kohta leiate teemast [Sündmuste eksportimine](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
