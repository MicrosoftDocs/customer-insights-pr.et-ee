---
title: Tööruumide ja keskkondade haldamine
description: Tööruumide ja keskkondade loomine, ümbernimetamine ja kustutamine.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ded9e98f06109b7cdc27f449455b7f58d633722f
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350632"
---
# <a name="manage-environments-and-workspaces"></a>Keskkondade ja tööruumide haldamine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Ülevaade

Käesolevas teemas käsitletakse, kuidas hallata tööruume ja keskkondi pärast nende loomist. 

- *Tööruum* on ruum sündmuste ja aruannete talletamiseks ning haldamiseks. Siin saate kasutajategevust reaalajas vaadata. Tööruumi loomisel valite tööruumi saatmiseks soovitud andmetüübi. Praegu toetatakse veebiandmeid ja mobiilirakendusi. Lisateavet leiate teemast [Uue tööruumi loomine ja liikmete lisamine](create-workspace.md).

- *Keskkond* on koht, kus te oma tööruume ja ühendusi haldate. Lisateavet leiate teemast [Uue keskkonna loomine](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Hallake olemasolevat tööruumi

Keskkonnas saate samaaegselt hooldada mitut tööruumi. Teie [roll](user-roles.md) määratleb, kuidas saate nendega töötada. 

 - Tööruumi haldamiseks peate olema keskkonna administraator või tööruumi administraator.
 - Tööruumi administraatorina saate olemasolevad tööruumid ümber nimetada või need kustutada. 

:::image type="content" source="media/workspace-edit.png" alt-text="Tööruumi administraatori keskus.":::

### <a name="edit-a-workspace-name"></a>Tööruumi nime haldamine

1. Avage **Administraator** > **Tööruum** ja **Sätted**.

1. Väljale **Tööruumi nimi** sisestage uus nimi.

1. Vajutage nuppu **Salvesta**, et muudatused rakendada.

### <a name="delete-a-workspace"></a>Tööruumi kustutamine

Tööruumi kustutamine eemaldab jäädavalt kogu selle sisu, andmed, sätted ja õigused. Seda ei saa tagasi võtta.

1. Avage **Administraator** > **Tööruum** ja **Sätted**.

1. Valige **Kustuta tööruum**. 

1. Sisestage **Tööruumi kustutamise** dialoogi **KINNITA KUSTUTAMINE** suurtes tähtedes. 

1. Valige **Kustuta** tööruumi jäädavalt kustutamiseks.

### <a name="manage-workspace-members"></a>Tööruumi liikmete haldamine

1. Avage **Administraator** > **Tööruum** ja valige **Sätted**.

1. Valige **Liikmete lisamine** et anda juurdepääs ja [määrata rollid](user-roles.md). Praegu on ainult **Tööruumi administraator** saadaval.

1. Valige **Lisa liikmed**, et lisada nad oma tööruumi.

## <a name="manage-an-existing-environment"></a>Olemasoleva keskkonna haldamine

Keskkonna administraatorina pääsete keskkonnale ligi vasakpoolselt navigeerimispaanilt. Saate konfigureerida keskkonnasätteid, muid keskkonnaadministraatoreid ja tööruume. Valige halduskeskuse erinevate alade vahel liikumiseks vahekaardid.

:::image type="content" source="media/environment-edit.png" alt-text="Keskkonna halduskeskus.":::

### <a name="edit-an-environment-name"></a>Keskkonnanime redigeerimine

1. Avage **Administraator** > **Tööruum** ja **Sätted**.

1. Värskendage **Keskkonna nimi** ja valige **Salvesta** muudatuste rakendamiseks.

### <a name="delete-an-environment"></a>Keskkonna kustutamine

Keskkonnaadministraatorid saavad keskkondi kustutada. Enne keskkonna kustutamist peate selle all kõik tööruumid eemaldama.

1. Avage **Administraator** > **Tööruum** ja **Sätted**.

1. Valige **Kustuta keskkond**. 

1. Sisestage **Tööruumi kustutamise** dialoogi **KINNITA KUSTUTAMINE** suurtes tähtedes. 

1. Valige **Kustuta** keskkonna lõplikuks kustutamiseks.

### <a name="manage-environment-members"></a>Keskkonna liikmete haldamine

1. Avage **Administraator** > **Keskkond** ja valige **Liikmed**.

1. Valige **Liikmete lisamine** et värskendada liikmeid ja [määrata rollid](user-roles.md). Praegu on ainult **Keskkonna administraator** saadaval.

1. Valige **Lisa liikmed**, et lisada nad oma tööruumi.

## <a name="manage-connections"></a>Halda ühendusi

Sihtrühma ülevaadete ühenduste loomine võimaldab näha aruandeid kaasamisülevaadetes, mis põhinevad ühendatud kliendiprofiilidel. 

Lisateavet vt: [Sihtrühma ülevaadete ja kaasamisülevaadete vahelise lingi loomine](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Isikuandmete haldamine

Kliendi isikuandmete kaitsmiseks saate kustutada või eksportida lõppkasutajat tuvastada võimaldavaid andmeid.

Lisateavet leiate teemast [Isikuandmeid sisaldavate sündmuseandmete kustutamine ja eksportimine](../dsr-rights-requests.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
