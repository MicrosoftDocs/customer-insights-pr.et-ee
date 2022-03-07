---
title: Uue keskkonna loomine
description: Keskkonna eesmärk ja kuidas uut luua.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 1f82ff588c2ffbe82c3ee7df2498ac2cca2bad31
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225418"
---
# <a name="create-a-new-environment"></a>Uue keskkonna loomine 

## <a name="overview"></a>Ülevaade

Keskkond on koht, kus te oma tööruume ja ühendusi haldate. Keskkondade kasutamine sõltub teie asutusest ja teie kasutusjuhtumist. Näiteks saate luua:

- Üksik keskkond.
- Eraldi keskkond katsetamise ja tootmise jaoks.
- Eraldage keskkonnad oma organisatsiooni konkreetsetele meeskondadele või osakondadele, mis sisaldavad iga vaatajaskonna jaoks asjakohaseid sündmusi.
- Eraldage keskkonnad oma ettevõtte erinevate globaalsete harude jaoks.
- Ühendused Customer Insights vaatajaskonna statistikaga.

## <a name="create-a-new-environment"></a>Uue keskkonna loomine

1. Valige põhib banneri aknas paremalt keskkonnavalija ja seejärel **+Uus**.

   :::image type="content" source="media/environment-picker.png" alt-text="Valige keskkonnavalija.":::

1. Tippige **Häälestus** paanile **Keskkonna nimi**.

1. Valige sõltuvalt plaani tüübist konto **Tüüp**.

1. Valige **Piirkond** ja seejärel **Edasi**. 

1. Tippige **tööruumi nimi**, mis võimaldab teil koguda andmeid konkreetsete veebisaitide või rakenduste jaoks. Lisateavet vaadake teemast [Tööruumi loomine](create-workspace.md) .

1. Valige tööruumi **tüüp** (veeb või mobiil), mida soovite luua. 

1. Valikuliste sätete lubamiseks või keelamiseks tehke valik **Kuva täpsemad sätted**.

   - Lülitage **Tundmatu teada** „lubatud” peale, et siduda veebisündmused varem autentinud kasutajatega. Lisateavet leiate teemast [Varem autenditud külastajate veebisündmuste tuvastamine](unknown-to-known.md).
   - Lülitage **Filtreerige robotiliiklus** olekusse „lubatud”, et eemaldada selle tööruumi veebiliiklus robotite kaupa. 

1. Kui olete lõpetanud, valige **Lõpeta**. 

1. Installige koodilõigend, et alustada andmete saatmist, ja klõpsake tööruumi loomiseks nuppu **Valmis**. Lisateavet leiate [Arendaja ressursside ülevaade](developer-resources.md).

> [!NOTE]
> Nüüd saate lisada liikmeid ja määrata nende õigusetasemeid loendis **Roll**. Lisateavet leiate teemast [Rollid ja õigused](user-roles.md). 

Lisateavet leiate teemast [Keskkondade ja tööruumide haldamine](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Uue keskkonnaga töötamine

- [Looge tööruum](../engagement-insights/create-workspace.md) ja lisage liikmeid.
- [Lisage kood oma veebisaidile](../engagement-insights/instrument-website.md) või [mobiilirakendusele](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Vaadake [reaalajaaruannet](../engagement-insights/view-reports.md) või looge [kohandatud aruanded](../engagement-insights/custom-reports.md).
- [Luua täpsustatud sündmused](../engagement-insights/refined-events.md) ekspordiks.
- [Eksportige andmed](../engagement-insights/export-events.md) Data Lake Storage'i.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
