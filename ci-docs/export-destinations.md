---
title: Eksportimine (eelversioon) ülevaade
description: Andmete jagamiseks hallake eksporti.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: d983e84e713003610eb27dc9b3f911b62b01d522
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082908"
---
# <a name="exports-preview-overview"></a>Eksportimine (eelversioon) ülevaade

Lehel **Ekspordid** näete kõiki konfigureeritud eksporte. Ekspordid jagavad erinevate rakendustega konkreetseid andmeid. Need võivad sisaldada kliendiprofiile, olemeid, skeeme ja vastendamise üksikasju. Iga ekspordi jaoks on vaja [ühendust, mille on seadistanud administraator, et hallata autentimist ja juurdepääsu](connections.md).

Minge **Andmed** > **Ekspordid**, et näha ekspordilehte. Kõik kasutajarollid saavad vaadata konfigureeritud eksporti. Kasutage käsuriba otsinguvälja, et leida eksporti nime, ühenduse nime või ühenduse tüübi järgi.

## <a name="export-types"></a>Ekspordi tüübid

Eksporditüüpe on kaks peamist:  

- **Andmevälja eksport** võimaldab eksportida mis tahes tüüpi olemit, mis on saadaval Customer Insightsis. Ekspordiks valitud olemid eksporditakse kõigi andmeväljade, metaandmete, skeemide ja vastendamise üksikasjadega. 
- **Segmendi eksport** võimaldab eksportida segmendiolemeid Customer Insightsist. Segmendid esindavad kliendiprofiilide loendit. Eksportimise konfigureerimisel valite kaasatud andmeväljad, olenevalt sihtsüsteemist, kus andmeid ekspordite. 

### <a name="export-segments"></a>Ekspordi segmendid

**Segmentide eksportimine keskkondades äriettevõtete (B2B) või eratarbijate jaoks (B2C)**  
Enamik ekspordisuvandeid toetab mõlemat tüüpi keskkondi. Segmentide eksportimisel erinevatesse sihtsüsteemidesse on erinõuded. Üldiselt sisaldavad segmendi liige ja kliendiprofiil kontaktteavet. Kuigi see kehtib enamasti eratarbijate (B2C) põhinevate segmentide puhul, ei pruugi see käia ärikontodel (B2B) põhinevate segmentide kohta. 

**Segmendi ekspordikeskkonnad ärikontode jaoks (B2B)**  
- Segmendid ärikontode keskkondades on rajatud *konto* olemile. Konto segmentide eksportimiseks nagu see on, peab sihtsüsteem toetama puhtaid konto segmente. See kehtib [LinkedIn'i](export-linkedin-ads.md) kohta, kui valite ekspordi määratlemisel suvandi **ettevõte**.
- Kõik muud sihtsüsteemid nõuavad kontaktiolemi välju. Tagamaks, et ettevõtte segmendid saavad tuua andmeid seotud kontaktidest, peab teie segmendi määratluses olema kontakti olemi projektiatribuudid. Lisateave [segmentide ja projektiatribuutide konfigureerimise kohta](segment-builder.md).

**Segmentide eksport keskkondades eratarbijatele (B2C)**  
- Segmendid üksikutele klientidele mõeldud keskkondade kontekstis on üles ehitatud olemile *ühendatud kliendiprofiil*. Iga sihtsüsteemide nõuetele (näiteks meiliaadressi) vastavad segmendid võidakse eksportida.

**Segmendiekspordi piirangud**  
- Muude tootjate sihtsüsteemid võivad piirata ekspordita kliendiprofiilide arvu. 
- Üksikklientide puhul näete segmendiliikmete tegelikku arvu, kui valite eksportimiseks segmendi. Liiga suure segmendi korral kuvatakse hoiatus. 
- Äriettevõtete puhul näete segmenti kaasatud ettevõtete arvu; küll aga ei näidata nende kontaktide arvu, mida saab projekteerida. Mõnel juhul võib see kaasa tuua eksporditud segmendi, mis sisaldab tegelikult rohkem kliendiprofiile kui sihtsüsteem aktsepteerib. Sihtsüsteemide tulemuste piirangute ületamine jätab ekspordi vahele. 

## <a name="set-up-a-new-export"></a>Uue ekspordi seadistamine  
Ekspordi seadistamiseks või redigeerimiseks peavad teil olema saadaval ühendused. Ühendused sõltuvad teie [kasutajarollist](permissions.md):
- **Administraatoritel** on juurdepääs kõigile ühendustele. Nad saavad ekspordi seadistamisel luua ka uusi ühendusi.
- **Kaastöötajatel** on juurdepääs kindlatele ühendustele. Nad sõltuvad administraatoritest, et ühendusi konfigureerida ja jagada. Ekspordiloendis kuvatakse kaastöötajad, kes saavad veergu **Teie õigused** eksportimist muuta või ainult vaadata. Lisateavet leiate teemast [Luba toetajatel kasutada ekspordiühendust](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Vaaturid** saavad kuvada ainult olemasolevaid eksporte, mitte neid luu.

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

1. Redigeerimisõigusteta kasutajad valivad **Vaade** ekspordi üksikasjade kuvamiseks **Redigeeri** asemel.

1. Kõrvalpaanil kuvatakse ekspordi konfiguratsioon. Ilma redigeerimisõiguseta ei saa väärtusi muuta. Valige **Sulge** ekspordilehele naasmiseks.

## <a name="schedule-and-run-exports"></a>Ajasta ja käivita ekspordid

Igal konfigureeritud ekspordil on värskendusgraafik. Värskendamise ajal otsib süsteem uusi või värskendatud andmeid, mida eksporti kaasata. Vaikimisi käitatakse eksport iga [kavandatud süsteemivärskenduse](system.md#schedule-tab) osana. Saate värskendamise ajakava kohandada või selle käsitsi eksportimise käivitamiseks välja lülitada.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Ekspordigraafikud sõltuvad teie keskkonna olekust. Kui värskendused on pooleli [sõltuvused](system.md#refresh-processes), kui määratud eksport peaks algama, viib süsteem värskendused esmalt lõpule ja käivitab seejärel ekspordi. Näete, millal eksporti viimati veerus **Värskendati**.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]
