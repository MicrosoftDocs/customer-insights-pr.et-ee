---
title: Tööruumide ja keskkondade haldamine
description: Tööruumide ja keskkondade loomine, ümbernimetamine ja kustutamine.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486030"
---
# <a name="manage-environments-and-workspaces"></a>Keskkondade ja tööruumide haldamine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Ülevaade

Tööruum on ruum sündmuste ja aruannete talletamiseks ning haldamiseks. Siin saate kasutajategevust reaalajas vaadata. Tööruumi loomisel valite tööruumi saatmiseks soovitud andmetüübi. Praegu toetatakse veebiandmeid ja mobiilirakendusi.

Keskkond on koht, kus te oma tööruume ja ühendusi haldate. Keskkondade kasutamine sõltub teie asutusest ja teie kasutusjuhtumist. Näiteks saate luua:

-   Üksik keskkond.
-   Eraldi keskkond katsetamise ja tootmise jaoks.
-   Eraldage keskkonnad oma organisatsiooni konkreetsetele meeskondadele või osakondadele, mis sisaldavad iga vaatajaskonna jaoks asjakohaseid sündmusi.
-   Eraldage keskkonnad oma ettevõtte erinevate globaalsete harude jaoks.
-   Ühendused Customer Insights vaatajaskonna statistikaga.

## <a name="choose-an-environment-and-create-a-workspace"></a>Valige keskkond ja looge tööruum 

Iga tööruum peab olema keskkonnas. Saate valida olemasoleva keskkonna või luua tööruumi loomisel uue keskkonna. Seejärel saate lisada tööruumi liikmeid ja alustada andmete kogumist.

**Oma esimese tööruumi loomine**

1. Valige kaasamisülevaadetes **Uus** tööruumi vahetaja suvandist. 

   :::image type="content" source="media/New-workspace.png" alt-text="Customer Insights lehe tööruumi valija.":::

1. Valige loendist soovitud keskkond või valige **Loo uus keskkond**.

1. Sisestage nimi jaotisesse **Tööruumi nimi**. 

1. Valige, millist tüüpi keskkonda soovite luua, olenevalt sellest, kas soovite mõõta veebisaidil või mobiilirakenduses toimumis toimumist. 

1. Liikmeid ja nende õigusetasemeid saate lisada **Roll** loendist. Seejärel valige **Valmis** et luua tööruum või **Järgmine** et installida kood. 

1. Installige koodilõigend, et alustada andmete saatmist ja seejärel valige **Valmis**. 

## <a name="manage-a-workspace"></a>Tööruumi haldamine

Keskkonnas saate samaaegselt hooldada mitut tööruumi. Teie [roll](user-roles.md) määratleb, kuidas saate nendega töötada. 

 - Tööruumi haldamiseks peate olema keskkonna administraator või tööruumi administraator.
 - Tööruumi administraatorina saate olemasolevad tööruumid ümber nimetada või need kustutada. 

### <a name="edit-a-workspace-name"></a>Tööruumi nime haldamine

1. Avage **Administraator** > **Tööruum** ja **Sätted**.

1. Väljale **Tööruumi nimi** sisestage uus nimi.

1. Vajutage nuppu **Salvesta**, et muudatused rakendada.

### <a name="delete-a-workspace"></a>Tööruumi kustutamine

Tööruumi kustutamisel eemaldatakse jäädavalt kogu selle sisu, andmed, sätted ja õigused. Seda ei saa tagasi võtta.

1. Avage **Administraator** > **Tööruum** ja **Sätted**.

1. Valige **Kustuta tööruum**. 

1. Jaotises **Kustuta tööruum** valige **KINNITA KUSTUTAMINE**. 

1. Valige **Kustuta** tööruumi jäädavalt kustutamiseks.

### <a name="manage-workspace-members"></a>Tööruumi liikmete haldamine

1. Avage **Administraator** > **Tööruum** ja valige **Sätted**.

1. Valige **Liikmete lisamine** et anda juurdepääs ja [määrata rollid](user-roles.md). Praegu on ainult **Tööruumi administraator** saadaval.

1. Valige **Lisa liikmed**, et lisada nad oma tööruumi.

## <a name="manage-an-environment"></a>Halda keskkonda

Keskkonna administraatorina pääsete keskkonnale ligi vasakpoolselt navigeerimispaanilt. Saate konfigureerida keskkonnasätteid, muid keskkonnaadministraatoreid ja tööruume. Valige halduskeskuse erinevate alade vahel liikumiseks vahekaardid.

:::image type="content" source="media/New-environment.png" alt-text="Keskkonna halduskeskus.":::

### <a name="create-an-environment"></a>Keskkonna loomine

1. Tööruumi valijas valige **+Uus**.

1. Juhendavas kogemuses avage ripploendist **Keskkond** ja valige käsk **Loo uus keskkond**. 

1. Sisestage **Keskkonna nimi**.

   :::image type="content" source="media/create-environment.png" alt-text="Astuge juhendatavasse keskkonda, et täpsustada keskkonna üksikasju.":::

1. Valige **Piirkond** ja seejärel **Edasi**. 

1. Sisestage Tööruumi nimi ja valige, millist tüüpi tööruumi soovite luua. 

1.  Soovi korral võite liikmeid lisada ja koodilõigendi koopia teha loomisprotsessi lõpuleviimiseks.

### <a name="rename-an-environment"></a>Keskkonna ümbernimetamine

1. Avage **Administraator** > **Tööruum** ja **Sätted**.

1. Värskendage **Keskkonna nimi** ja valige **Salvesta** muudatuste rakendamiseks.

### <a name="manage-environment-members"></a>Keskkonna liikmete haldamine

1. Avage **Administraator** > **Keskkond** ja valige **Liikmed**.

1. Valige **Liikmete lisamine** et värskendada liikmeid ja [määrata rollid](user-roles.md). Praegu on ainult **Keskkonna administraator** saadaval.

1. Valige **Lisa liikmed**, et lisada nad oma tööruumi.

### <a name="delete-an-environment"></a>Keskkonna kustutamine

Keskkonnaadministraatorid saavad keskkondi kustutada. Enne keskkonna kustutamist peate selle all kõik tööruumid eemaldama.

1. Avage **Administraator** > **Tööruum** ja **Sätted**.

1. Valige **Kustuta keskkond**. 

1. Jaotises **Kustuta tööruum** valige **KINNITA KUSTUTAMINE**. 

1. Valige **Kustuta** keskkonna lõplikuks kustutamiseks.

## <a name="manage-connections"></a>Halda ühendusi

Sihtrühma ülevaadete ühenduste loomine võimaldab näha aruandeid kaasamisülevaadetes, mis põhinevad ühendatud kliendiprofiilidel. 

Lisateavet vt: [Sihtrühma ülevaadete ja kaasamisülevaadete vahelise lingi loomine](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Isikuandmete haldamine

Kliendi isikuandmete kaitsmiseks saate kustutada või eksportida lõppkasutajat tuvastada võimaldavaid andmeid.

Lisateavet leiate teemast [Isikuandmeid sisaldavate sündmuseandmete kustutamine ja eksportimine](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
