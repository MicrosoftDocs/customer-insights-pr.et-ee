---
title: Eksportimine (eelversioon) ülevaade
description: Andmete jagamiseks hallake eksporti.
ms.date: 07/25/2022
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
ms.openlocfilehash: fd234aff9021ded76d8226bf2f15e035cf75e7db
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245322"
---
# <a name="exports-preview-overview"></a>Eksportimine (eelversioon) ülevaade

 Eksport võimaldab teil jagada konkreetseid andmeid erinevate rakendustega. Need võivad sisaldada kliendiprofiile, olemeid, skeeme ja vastendamise üksikasju. Iga ekspordi jaoks on vaja [ühendust, mille on seadistanud administraator, et hallata autentimist ja juurdepääsu](connections.md). Lehel **Ekspordid** näete kõiki konfigureeritud eksporte.

## <a name="export-types"></a>Ekspordi tüübid

Eksporditüüpe on kaks peamist:  

- **Andmete eksportimine**: eksportige mis tahes tüüpi olemid, mis on Customer Insightsis saadaval. Ekspordiks valitud olemid eksporditakse kõigi andmeväljade, metaandmete, skeemide ja vastendamise üksikasjadega.
- **Segmendieksport**: ekspordisegmendi olemid Customer Insightsist. Segmendid esindavad kliendiprofiilide loendit. Ekspordi konfigureerimisel valite kaasatud andmeväljad sõltuvalt sihtsüsteemist, kuhu andmeid ekspordite.

### <a name="export-segments"></a>Ekspordi segmendid

**Segmentide eksportimine keskkondades äriettevõtete (B2B) või eratarbijate jaoks (B2C)**  
Enamik ekspordivalikuid toetab mõlemat tüüpi keskkondi. Segmentide eksportimisel erinevatesse sihtsüsteemidesse on erinõuded. 

**Segmentide eksport keskkondades eratarbijatele (B2C)**  
- Segmendid üksikutele klientidele mõeldud keskkondade kontekstis on üles ehitatud olemile *ühendatud kliendiprofiil*. Iga sihtsüsteemide nõuetele (näiteks meiliaadressi) vastavad segmendid võidakse eksportida.

**Segmendi ekspordikeskkonnad ärikontode jaoks (B2B)**  
- Segmendid ärikontode keskkondades on rajatud *konto* olemile. Konto segmentide eksportimiseks nagu see on, peab sihtsüsteem toetama puhtaid konto segmente. See kehtib [LinkedIn'i](export-linkedin-ads.md) kohta, kui valite ekspordi määratlemisel suvandi **ettevõte**.
- Kõik muud sihtsüsteemid nõuavad kontaktiolemi välju. Tagamaks, et ettevõtte segmendid saavad tuua andmeid seotud kontaktidest, peab teie segmendi määratluses olema kontakti olemi projektiatribuudid. Lisateave [segmentide ja projektiatribuutide konfigureerimise kohta](segment-builder.md).

**Segmendiekspordi piirangud**  
- Muude tootjate sihtsüsteemid võivad piirata ekspordita kliendiprofiilide arvu. 
- Üksikklientide puhul näete segmendiliikmete tegelikku arvu, kui valite eksportimiseks segmendi. Liiga suure segmendi korral kuvatakse hoiatus. 
- Äriettevõtete puhul näete segmenti kaasatud ettevõtete arvu; küll aga ei näidata nende kontaktide arvu, mida saab projekteerida. Mõnel juhul võib see kaasa tuua eksporditud segmendi, mis sisaldab tegelikult rohkem kliendiprofiile kui sihtsüsteem aktsepteerib. Kui sihtsüsteemi piirid on ületatud, jäetakse eksport vahele.

## <a name="set-up-a-new-export"></a>Uue ekspordi seadistamine

Ekspordi seadistamiseks või redigeerimiseks on teil vaja õigeid ühendusi, mis on teile kättesaadavad. Ühendused sõltuvad teie [kasutajarollist](permissions.md):
- **Administraatoritel** on juurdepääs kõigile ühendustele. Nad saavad ekspordi seadistamisel luua ka uusi ühendusi.
- **Kaastöötajatel** on juurdepääs kindlatele ühendustele. Nad sõltuvad administraatoritest, et ühendusi konfigureerida ja jagada. Ekspordiloendis kuvatakse kaastöötajad, kes saavad veergu **Teie õigused** eksportimist muuta või ainult vaadata. Lisateavet leiate teemast [Luba toetajatel kasutada ekspordiühendust](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Vaaturid** saavad kuvada ainult olemasolevaid eksporte, mitte neid luu.

1. Minge **Andmed** > **Ekspordid**.

1. Uue ekspordi loomiseks valige **Lisa eksport**.

1. **Valige paanil Ekspordi** seadistamine, millist [ühendust](connections.md) kasutada.

1. Sisestage nõutavad üksikasjad ja valige **Salvesta** eksportimise loomiseks. Nõutavate üksikasjade saamiseks vaadake üle Customer Insightsi dokumentatsioonist konkreetse ekspordi kohta.

## <a name="manage-existing-exports"></a>Olemasolevate ekspordite haldamine

Avage **andmete** > **ekspordid**, nende ühenduse nimi, ühenduse tüüp ja olek. Kõik kasutajarollid saavad vaadata konfigureeritud eksporti. Ekspordiloendi saate sortida mis tahes veeru järgi või kasutada otsinguvälja, et leida eksport, mida soovite hallata.

Valige eksport saadaolevate toimingute vaatamiseks.

:::image type="content" source="media/exports_showmore.png" alt-text="Ekspordib lehekülg.":::

- **Ekspordi vaatamine** või **redigeerimine**. Redigeerimisõigusteta kasutajad valivad **Vaade** ekspordi üksikasjade kuvamiseks **Redigeeri** asemel.
- **Käivitage** eksport, et eksportida uusimaid andmeid.
- **Ekspordi duplikaadi** loomine.
- **[Ekspordi ajastamine](#schedule-and-run-exports)**.
- **Eemaldage ühendus** selle ekspordi ühenduse eemaldamiseks. Eraldumine ei eemalda ühendust, vaid deaktiveerib ekspordi. Veerus **Kasutatud** ühendus kuvatakse ühendus puudub.
- **Eemaldage** eksport.

## <a name="schedule-and-run-exports"></a>Ajasta ja käivita ekspordid

Igal konfigureeritud ekspordil on värskendusgraafik. Värskendamise ajal otsib süsteem uusi või värskendatud andmeid, mida eksporti kaasata. Vaikimisi käitatakse eksport iga [kavandatud süsteemivärskenduse](schedule-refresh.md) osana. Saate värskendamise ajakava kohandada või selle käsitsi eksportimise käivitamiseks välja lülitada.

Ekspordigraafikud sõltuvad teie keskkonna olekust. Kui värskendused on pooleli [sõltuvused](system.md#refresh-processes), kui määratud eksport peaks algama, viib süsteem värskendused esmalt lõpule ja käivitab seejärel ekspordi. Veerg **Värskendatud** näitab, millal eksporti viimati värskendati.

### <a name="schedule-exports"></a>Eksportide ajastamine

Määratlege kohandatud värskendamise ajakavad üksikute ekspordite või mitme ekspordi jaoks korraga. Praegu määratletud ajakava on ära toodud ekspordiloendi veerus **Ajakava**. Ajakava muutmise õigus on sama [, mis ekspordi redigeerimisel ja määratlemisel](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige eksport, mille soovite ajastada.

1. Valige **Kavanda**.

1. Määrake paanil **Ajasta eksportimine**, et muuta suvandi **Ajasta käivitus** väärtuseks **Sees** käitamisel automaatselt. Käsitsi värskendamiseks seadke selle väärtuseks **Väljas**.

1. Valige automaatselt värskendatud ekspordi korral väärtus **Korduvus** ja määrake selle üksikasjad. Määratletud aeg kehtib kõigile korduvuse eksemplaridele. On aeg, mil eksport peaks käivituma värskendamisel.

1. Valige **Salvesta**.

Mitme ekspordi ajakava redigeerimisel tehke valik jaotises **Säilita või alista graafikud**.

- **Säilitage individuaalsed graafikud**: säilitage valitud ekspordite jaoks eelnevalt määratletud ajakava ja keelake või lubage need ainult.
- **Kõigi valitud ekspordite jaoks uue ajakava määratlemine**: valitud ekspordi olemasolevate graafikute ülekirjutamine.

### <a name="run-exports-on-demand"></a>Käita ekspordid nõudmisel

Andmete eksportimiseks ilma ajastatud värskendamist ootamata minge **Andmed** > **Eksport**.

- Kõigi ekspordite käivitamiseks valige **Käivita kõik** käsuribalt. Käivitatakse ainult aktiivse ajakavaga ekspordid. Mitteaktiivse ekspordi käivitamiseks käivitage üks eksport.
- Ühe ekspordi käivitamiseks valige see loendist ja valige käsuribalt **Käivita**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
