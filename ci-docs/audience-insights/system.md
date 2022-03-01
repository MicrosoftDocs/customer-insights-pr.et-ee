---
title: Süsteemikonfiguratsioon sihtrühmaülevaadetes
description: Lisateave süsteemisätete kohta Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioonis.
ms.date: 10/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3ce767939b8fedf676dc569ede47104ecfe930dd
ms.sourcegitcommit: cd9f9a9d3da71c5420ef5c4c6ead91bc820d17a9
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 10/19/2021
ms.locfileid: "7651835"
---
# <a name="system-configuration"></a>Süsteemikonfiguratsioon

Leht **Süsteem** sisaldab järgmisi vahekaarte.
- [Olek](#status-tab)
- [Kavanda](#schedule-tab)
- [API kasutus](#api-usage-tab)
- [Teave](#about-tab)
- [Üldist](#general-tab)
- [Turve](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Sätete vahekaardid süsteemilehel.":::

## <a name="status-tab"></a>Oleku vaehekaart

Vahekaardil **Olek** lubab jälgida andmete kogumise, andmeekspordi ja mitme muu olulise tooteprotsessi edenemist. Vaadake sellel vahekaardil olev teave üle, et tagada aktiivsete protsesside terviklikkus.

Vahekaart sisaldab oleku ja erinevate protsessidega teabetöötlustabeleid. Iga tabel jälgib tööülesande **Nime** ja sellele vastavat olemit, viimase käitamise **Olekut** ja millal seda viimati **Värskendati**.

Tööülesande viimaste käitamiste üksikasjade kuvamiseks valige selle nimi.

### <a name="status-types"></a>Oleku tüübid

Ülesannete jaoks on kuus tüüpi olekuid. Järgmised olekutüübid on näha ka lehtedel *Vastendamine*, *Liitmine*, *Andmeallikaid*, *Segmendid*, *Meetmed*, *Rikastamine*, *Tegevused* ja *Prognoosid*.

- **Töötlemine:** toiming on pooleli. Olekuks võib muutuda kas Õnnestunud või Ebaõnnestunud.
- **Õnnestunud:** tööülesande lõpuleviimine õnnestus.
- **Vahele jäetud:** tööülesanne jäeti vahele. Üks või mitu järgnevat protsessi, millest see tööülessane sõltub, nurjuvad või jäid vahele.
- **Ebaõnnestunud:** tööülesande töötlemine ebaõnnestus.
- **Tühistatud:** kasutaja tühistas töötlemise enne selle lõpuleviimist.
- **Järjekorda lisatud**: töötlemine on lisatud järjekorda ja algab siis, kui kõik järjekorratoimingud on lõpule viidud. Lisateavet leiate jaotisest [Värskendamise poliitika](#refresh-policies).

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

Vahekaardil **Üldine** saate muuta keelt ja riigi/regiooni vormingut.

Customer Insights [toetab mitmeid keeli](/dynamics365/get-started/availability). Rakendus kasutab teie keele-eelistust, et kuvada teie eelistatud keeles elemente, nt menüü, silditekst ja süsteemiteated.

Käsitsi sisestatud imporditud andmeid ja teavet ei tõlgita.

### <a name="update-the-settings"></a>Värskenda sätteid

Eelistatud keele muutmiseks valige ripploendist **Keel**.

Eelistatud kuupäeva, kellaaja ja numbrite vormingute muutmiseks kasutage ripploendit **Riigi/piirkonna vorming**. Vormindamise eelvaade kuvatakse selle välja all. Kui valite uue keele, soovitab süsteem automaatselt valikut.

Valige käsk **Salvesta**, et kinnitada valikud.

## <a name="api-usage-tab"></a>API kasutuse vahekaart

Leidke API reaalajas kasutamise üksikasju ja vaadake, millised sündmused toimusid antud aja jooksul. Ajaraami saate valida rippmenüüst **Ajaraami valimine**. 

**API kasutus** sisaldab kolme järgmist jaotist. 
- **API-päringud** – diagramm, mis visualiseerib valitud aja jooksul API päringute koondarvu.

- **Andmeedastus** – diagramm, mis kuvab valitud ajaraamistikul API kaudu edastatud andmete hulga.

-  **Toimingud** – tabel, kus on reaga iga saadaolev API-toiming ja teave toimingute kasutamise kohta. Võite valida toimingu nime, et minna [API-viitele](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   [Reaalajalisi andmeatrikulaate](real-time-data-ingestion.md) kasutavad toimingud sisaldavad binokulaarse sümboliga nuppu reaalaja API kasutuse kuvamiseks. Valige nupp, et avada külgpaan, mis sisaldab reaalajas API kasutamise üksikasju praeguses keskkonnas.   
   Kasutage paanil **Reaalajaline API kasutus** välja **Rühmita kui**, et valida kuidas reaalajalist suhtlust kõige paremini esitada. Andmeid saate rühmitada API meetodi, olemi kvalifitseeritud nime (valmendatud olem), looja (sündmuse allikas), tulemuse (õnnestumine või nurjumine) või tõrkekoodide järgi. Andmed on saadaval ajaloodiagrammina ja tabelina.

## <a name="security-tab"></a>Turvevahekaart

Vahekaart **Turve** võimaldab teil linkida ja hallata keskkonna oma [Azure'i võtmehoidlat](/azure/key-vault/general/basic-concepts).
Sihtotstarbelise võtmehoidla abil saab etappe luua ja kasutada saladusi organisatsiooni vastavuse piirides. Sihtrühma ülevaated saavad kasutada Azure'i võtmehoidla saladusi [ühenduste loomiseks](connections.md) muude tootjate süsteemidega.

Lisateavet leiate jaotisest [Enda Azure'i võtmehoidla loomine](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]