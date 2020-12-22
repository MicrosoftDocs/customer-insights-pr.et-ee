---
title: Süsteemikonfiguratsioon sihtrühmaülevaadetes
description: Lisateave süsteemisätete kohta Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioonis.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405566"
---
# <a name="system-configuration"></a>Süsteemikonfiguratsioon

Lehel **Süsteem** on neli vahekaarti: **Olek**, **Ajastamine**, **Teave** ja **Üldine**.

> [!div class="mx-imgBorder"]
> ![Süsteemi leht](media/system-tabs.png "Süsteemi leht")

## <a name="status-tab"></a>Oleku vaehekaart

**Oleku vahekaart** võimaldab jälgida andmete sisestamist, andmete eksportimisi ja mitmeid olulisi toote protsesse. Vaadake sellel vahekaardil olev teave üle, et tagada aktiivsete protsesside terviklikkus.

See vahekaart sisaldab oleku tabeleid **Andmeallikad**, **Süsteemi protsessid** ja **Andmete ettevalmistamine**. Iga tabel jälgib tööülesande **Nime** ja sellele vastavat olemit, viimase käitamise **Olekut** ja millal seda viimati **Värskendati**.

Tööülesande viimaste käitamiste üksikasjade kuvamiseks valige selle nimi.

### <a name="status-types"></a>Oleku tüübid

Ülesannete jaoks on kuus tüüpi olekuid. Järgmised olekutüübid on näha ka lehtedel *Vastendamine*, *Liitmine*, *Andmeallikaid*, *Segmendid*, *Meetmed*, *Rikastamine*, *Tegevused* ja *Prognoosid*.

- **Töötlemine:** toiming on pooleli. Olekuks võib muutuda kas Õnnestunud või Ebaõnnestunud.
- **Õnnestunud:** tööülesande lõpuleviimine õnnestus.
- **Vahele jäetud:** tööülesanne jäeti vahele. Üks või mitu järgnevat protsessi, millest see tööülessane sõltub, nurjuvad või jäid vahele.
- **Ebaõnnestunud:** tööülesande töötlemine ebaõnnestus.
- **Tühistatud:** kasutaja tühistas töötlemise enne selle lõpuleviimist.
- **Järjekorda pandud:** töötlemine on järjekorras ja käivitub siis, kui kõik järgnevad tööülesanded on lõpule viidud. Lisateavet leiate jaotisest [Värskendamise poliitika](#refresh-policies).

### <a name="refresh-policies"></a>Värskendamise poliitika

Selles loendis kuvatakse iga põhiprotsessi värskendamise poliitika.

- **Andmeallikad:** käivitub vastavalt [konfigureeritud ajakavale](#schedule-tab). Ei sõltu muudest protsessidest. Vastendamine sõltub selle protsessi edukast lõpuleviimisest.
- **Vastendamine:** käivitub vastavalt [konfigureeritud ajakavale](#schedule-tab). Sõltub vastenduse määratluses kasutatud andmeallikate töötlemisest. Ühendamine sõltub selle protsessi edukast lõpuleviimisest.
- **Ühendamine:** käivitub vastavalt [konfigureeritud ajakavale](#schedule-tab). Sõltub vastenduse protsessi lõpuleviimisest. Segmendid, meetmed, rikastamine, otsing, tegevused, prognoosid ja andmete ettevalmistamine sõltuvad selle protsessi edukast lõpuleviimisest.
- **Segmendid**: käivitatakse käsitsi (ühekordne värskendamine) ja vastavalt [konfigureeritud ajakavale](#schedule-tab). Sõltub ühendamisest. Ülevaated sõltuvad selle töötlemisest.
- **Meetmed**: käivitatakse käsitsi (ühekordne värskendamine) ja vastavalt [konfigureeritud ajakavale](#schedule-tab). Sõltub ühendamisest.
- **Tegevused**: käivitatakse käsitsi (ühekordne värskendamine) ja vastavalt [konfigureeritud ajakavale](#schedule-tab). Sõltub ühendamisest.
- **Rikastamine**: käivitatakse käsitsi (ühekordne värskendamine) ja vastavalt [konfigureeritud ajakavale](#schedule-tab). Sõltub ühendamisest.
- **Otsing**: käivitatakse käsitsi (ühekordne värskendamine) ja vastavalt [konfigureeritud ajakavale](#schedule-tab). Sõltub ühendamisest.
- **Andmete ettevalmistamine:** käivitub vastavalt [konfigureeritud ajakavale](#schedule-tab). Sõltub ühendamisest.
- **Ülevaated**: käivitatakse käsitsi (ühekordne värskendamine) ja vastavalt [konfigureeritud ajakavale](#schedule-tab). Sõltub segmentidest.

Kogu seda sisaldava töö edenemise üksikasjade nägemiseks valige tööülesande olek. Eelnimetatud värskendamise poliitika aitab mõista, mida saate teha **Vahele jäetud** või **Järjekorda pandud** tööülesandega tegelemiseks.

## <a name="schedule-tab"></a>Ajastamise vahekaart

Kasutage vahekaarti **Ajastamine**, et ajastada kõigi [valmendatud andmeallikate](data-sources.md) jaoks automaatsed värskendused. Automaatne värskendamine aitab tagada, et teie andmeallikate värskendused kajastuksid teie kliendi koondprofiilidel.

1. Minge sihtrühmaülevaadetes lehele **Haldus** > **Süsteem** ja valige vahekaart **Ajastamine**.

2. Ajastatud värskendamise vaike-olek on **Väljas**. Ajastatud värskenduste luvamiseks lülitage ekraani ülaosas sisse valik **Sees**.

3. Värskendamisvalikuteks on **Iga nädal** (tavaline) ja **Iga päev**. Kui kavatsete värskendada iga nädal, valige vähemalt üks päev, mil tahate värskendada.

4. Määrake **Ajavöönd** ja seejärel kasutage ripploendit **Aeg** oma värskendamise aja määramiseks. Kui olete lõpetanud, valige käsk **Määra**. Kui tahate ajastada mitu värskendust ühel päeval, valige **Vali muu kellaaeg**.

5. Vajutage nuppu **Salvesta**, et muudatused rakendada.

## <a name="about-tab"></a>Teave vahekaardi kohta

Vahekaart **Teave** sisaldab teie organisatsiooni **Kuvatavat nime**, aktiivset **Keskkonna ID-d**, **Piirkonda** ja teie **Seansi ID-d**. Kui teil on rohkem kui üks töökeskkond, peate andma igale keskkonnale lihtsasti tuvastatava kuvatava nime.

## <a name="general-tab"></a>Vahekaart Üldine

Vahekaardil **Üldine** on kaks valikut, **Keel** ja **Riigi/regiooni vorming**.

Rakendus [toetab mitu keelt](supported-languages.md). Eelistatud keele muutmiseks valige ripploendist **Keel**.

Eelistatud kuupäeva, kellaaja ja numbrite vormingute muutmiseks kasutage ripploendit **Riigi/piirkonna vorming**. Vormindamise eelvaade kuvatakse selle välja all. Kui valite uue keele, soovitab süsteem automaatselt valikut.

Valige käsk **Salvesta**, et kinnitada valikud.

## <a name="api-usage-tab"></a>API kasutuse vahekaart

Siit leiate teavet reaalajas API kasutuse kohta ja näete, milliseid sündmusi teatud ajavahemikul esines. Lisateabe saamiseks vt [Reaalajas andmete valmendamine](real-time-data-ingestion.md).
