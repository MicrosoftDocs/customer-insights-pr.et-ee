---
title: Andmete eksportimine Customer Insights
description: Andmete jagamiseks hallake eksporti.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253035"
---
# <a name="exports-preview-overview"></a>Eksportimine (eelversioon) ülevaade

Lehel **Ekspordid** näete kõiki konfigureeritud eksporte. Ekspordid jagavad erinevate rakendustega konkreetseid andmeid. Need võivad sisaldada kliendiprofiile või olemeid, skeeme ja kaardistamise üksikasju. Iga ekspordi jaoks on vaja [ühendust, mille on seadistanud administraator, et hallata autentimist ja juurdepääsu](connections.md).

Minge **Andmed** > **Ekspordid**, et näha ekspordilehte. Kõigil kasutajarollidel on juurdepääs konfigureeritud ekspordi vaatamiseks. Kasutage käsuriba otsinguvälja, et leida eksport nende nime, ühenduse nime või ühenduse tüübi järgi.

## <a name="set-up-a-new-export"></a>Uue ekspordi seadistamine

Ekspordi seadistamiseks või redigeerimiseks peavad teil olema saadaval ühendused. Ühendused sõltuvad teie [kasutajarollist](permissions.md):
- Administraatoritel on juurdepääs kõigile ühendustele. Nad saavad ekspordi seadistamisel luua ka uusi ühendusi.
- Kaastöötajatel on juurdepääs kindlatele ühendustele. Nad sõltuvad administraatoritest, et ühendusi konfigureerida ja jagada. Ekspordiloendis kuvatakse kaastöötajad, kes saavad veergu **Teie õigused** eksportimist muuta või ainult vaadata. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Vaatajad saavad vaadata ainult olemasolevaid eksporte, kuid ei loo neid.

### <a name="define-a-new-export"></a>Uue ekspordi määratlemine

1. Minge **Andmed** > **Ekspordid**.

1. Uue ekspordi loomiseks valige **Lisa eksport**.

1. Valige **Ekspordi loomine** paanil ühendus, mida kasutada. [Ühendusi](connections.md) haldavad administraatorid. 

1. Sisestage nõutavad üksikasjad ja valige **Salvesta** eksportimise loomiseks.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Uue ekspordi määratlemine olemasoleva ekspordi põhjal

1. Minge **Andmed** > **Ekspordid**.

1. Valige eksportide loendis eksport, mille soovite duplitseerida.

1. Valitud ekspordi üksikasjadega paani **Defineeri eksport** avamiseks valige käsuribal **Loo duplikaat**.

1. Vaadake eksportimine läbi ja kohandage seda ning valige uue ekspordi loomiseks käsk **Salvesta**.

### <a name="edit-an-export"></a>Ekspordi redigeerimine

1. Minge **Andmed** > **Ekspordid**.

1. Valige eksportide loendis eksport, mille soovite redigeerida.

1. Valige käsuribal käsk **Redigeeri**.

1. Muutke värskendatavad väärtused ja valige **Salvesta**.

## <a name="view-exports-and-export-details"></a>Ekspordi ja ekspordi üksikasjade kuvamine

Pärast ekspordi sihtkoha loomist on need ära toodud **Andmed** > **Ekspordid** loendis. Kõik kasutajad saavad vaadata, milliseid andmeid jagatud on ning nende värskeimat olekut.

1. Minge **Andmed** > **Ekspordid**.

1. Redigeerimisõiguseta kasutajad valivad **Vaade** eksportimise üksikasjade vaatamiseks **Redigeeri** asemel.

1. Kõrvalpaanil kuvatakse ekspordi konfiguratsioon. Ilma redigeerimisõiguseta ei saa väärtusi muuta. Valige **Sulge** ekspordilehele naasmiseks.

## <a name="schedule-and-run-exports"></a>Ajasta ja käivita ekspordid

Igal konfigureeritud ekspordil on värskendusgraafik. Värskendamise ajal otsib süsteem uusi või värskendatud andmeid, mida eksporti kaasata. Vaikimisi käitatakse eksport iga [kavandatud süsteemivärskenduse](system.md#schedule-tab) osana. Saate värskendamise ajakava kohandada või selle käsitsi eksportimise käivitamiseks välja lülitada.

Ekspordigraafikud sõltuvad teie keskkonna olekust. Kui plaanitud eksportimisel on [sõltuvuste](system.md#refresh-policies) värskendusi juba tehtud, viib süsteem esmalt sõltuvused lõpule ja käivitab seejärel ekspordi. Näete, millal eksporti viimati veerus **Värskendati**.

### <a name="schedule-exports"></a>Eksportide ajastamine

Kohandatud värskendusgraafikuid saab määratleda nii üksiku ekspordi kui ka mitme ekspordi jaoks korraga. Praegu määratletud ajakava on ära toodud ekspordiloendi veerus **Ajakava**. Ajakava muutmise õigus on sama, mis [eksportide redigeerimise ja määratlemise](export-destinations.md#set-up-a-new-export) õigus. 

1. Minge **Andmed** > **Ekspordid**.

1. Valige eksport, mille soovite ajastada.

1. Valige käsuribal käsk **Ajasta**.

1. Määrake paanil **Ajasta eksportimine**, et muuta suvandi **Ajasta käivitus** väärtuseks **Sees** käitamisel automaatselt. Käsitsi värskendamiseks seadke selle väärtuseks **Väljas**.

1. Valige automaatselt värskendatud ekspordi korral väärtus **Korduvus** ja määrake selle üksikasjad. Määratletud aeg kehtib kõigile korduvuse eksemplaridele. On aeg, mil eksport peaks käivituma värskendamisel.

1. Muudatuste rakendamiseks ja aktiveerimiseks klõpsake nuppu **Salvesta**.

Mitme ekspordi ajakava redigeerimisel peate tegema valiku jaotises **Säilita või kirjuta graafikud üle**.
- **Säilitage üksikud ajakavad**. Saate säilitada valitud ekspordi jaoks varem määratletud ajakava ja ainult keelata või lubada neid.
- **Kõigi valitud ekspordite jaoks uue ajakava määratlemine**: valitud ekspordi olemasolevate graafikute ülekirjutamine.

### <a name="run-exports-on-demand"></a>Käita ekspordid nõudmisel

Andmete eksportimiseks ilma ajastatud värskendamist ootamata minge **Andmed** > **Eksport**.

- Kõigi ekspordite käivitamiseks valige **Käivita kõik** käsuribalt. Selle toiminguga käitatakse ainult aktiivse ajakavaga eksport.
- Ühe ekspordi käivitamiseks valige see loendist ja valige käsuribalt **Käivita**. Nii käitate eksportimist ilma aktiivse ajakavata. 

## <a name="remove-an-export"></a>Ekspordi eemaldamine

1. Minge **Andmed** > **Ekspordid**.

1. Valige eksport, mille soovite eemaldada.

1. Valige käsuribal käsk **Eemalda**.

1. Eemaldamise kinnitamiseks valige kinnitusekraanil **Eemalda**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
