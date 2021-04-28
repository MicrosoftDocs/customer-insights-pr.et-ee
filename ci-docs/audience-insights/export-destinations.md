---
title: Andmete eksportimine Customer Insights
description: Andmete jagamiseks hallake eksporti.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896138"
---
# <a name="exports-preview-overview"></a>Eksportimine (eelversioon) ülevaade

Lehel **Ekspordid** näete kõiki konfigureeritud eksporte. Ekspordid jagavad erinevate rakendustega konkreetseid andmeid. Need võivad sisaldada kliendiprofiile või olemeid, skeeme ja kaardistamise üksikasju. Iga ekspordi jaoks on vaja [ühendust, mille on seadistanud administraator, et hallata autentimist ja juurdepääsu](connections.md).

> [!NOTE]
> Kuni 2021. aasta märtsini lõi eksport ühenduse vastava teenusega automaatselt. Ekspordiks on nüüd vaja [ühendust, mille administraator on loonud ja ühiskasutusse andnud](connections.md) enne kui saate neid luua.

Minge **Andmed** > **Ekspordid**, et näha ekspordilehte. Kõigil kasutajarollidel on juurdepääs konfigureeritud ekspordi vaatamiseks. Kasutage käsuriba otsinguvälja, et leida eksport nende nime, ühenduse nime või ühenduse tüübi järgi.

## <a name="set-up-a-new-export"></a>Uue ekspordi seadistamine

Ekspordi seadistamiseks või redigeerimiseks peavad teil olema saadaval ühendused. Ühendused sõltuvad teie [kasutajarollist](permissions.md):
- Administraatoritel on juurdepääs kõigile ühendustele. Nad saavad ekspordi seadistamisel luua ka uusi ühendusi.
- Kaastöötajatel on juurdepääs kindlatele ühendustele. Nad sõltuvad administraatoritest, et ühendusi konfigureerida ja jagada. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Vaatajad saavad vaadata ainult olemasolevaid eksporte, kuid ei loo neid.

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi sihtkoha loomiseks **Lisa eksport**.

1. Valige **Ekspordi loomine** paanil ühendus, mida kasutada. [Ühendusi](connections.md) haldavad administraatorid. 

1. Sisestage nõutavad üksikasjad ja valige **Salvesta** eksportimise loomiseks.

### <a name="edit-an-export"></a>Ekspordi redigeerimine

1. Valige redigeeritava ekspordi sihtkoha vertikaalsed kolm punkti.

1. Valige ripploendist **Redigeeri**.

1. Muutke värskendatavad väärtused ja valige **Salvesta**.

## <a name="view-exports-and-export-details"></a>Ekspordi ja ekspordi üksikasjade kuvamine

Pärast ekspordi sihtkoha loomist on need ära toodud **Andmed** > **Ekspordid** loendis. Kõik kasutajad saavad vaadata, milliseid andmeid jagatud on ning nende värskeimat olekut.

1. Minge **Andmed** > **Ekspordid**.

1. Redigeerimisõiguseta kasutajad valivad **Vaade** eksportimise üksikasjade vaatamiseks **Redigeeri** asemel.

1. Sellel kõrvalpaanil kuvatakse ekspordi seadistus. Ilma redigeerimisõiguseta ei saa väärtusi muuta. Valige **Sulge** ekspordilehele naasmiseks.

## <a name="run-exports-on-demand"></a>Käita ekspordid nõudmisel

Pärast ekspordi konfigureerimist käitatakse see iga [kavandatud värskendusega](system.md#schedule-tab) kui on olemas töötav ühendus.

Andmete eksportimiseks ilma ajastatud värskendamist ootamata minge **Andmed** > **Eksport**. Teil on kaks varianti.

- Kõigi ekspordite käivitamiseks valige **Käivita kõik** käsuribalt. 
- Üksikekspordi käivitamiseks valige loendiüksuses vertikaalsed kolm punkti (...) ja valige siis **Käivita**.

## <a name="remove-an-export"></a>Ekspordi eemaldamine

1. Minge **Andmed** > **Ekspordid**.

1. Klõpsake eemaldatava ekspordi juures kolmel vertikaalsel punktil.

1. Valige rippmenüüst **Eemalda**.

1. Eemaldamise kinnitamiseks valige kinnitusekraanil **Eemalda**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
