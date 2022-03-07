---
title: Süsteemikonfiguratsioon sihtrühmaülevaadetes
description: Lisateave süsteemisätete kohta Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioonis.
ms.date: 11/01/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2c52f7b8a7d41ae4a985745c7b79bbc62f59bb5a
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354224"
---
# <a name="system-configuration"></a>Süsteemikonfiguratsioon

Süsteemikonfiguratsioonidele vaatajaskonna ülevaates juurdepääsuks valige **vasakpoolselt navigeerimisribalt Süsteemiülesannete ja protsesside loendi kuvamiseks AdministraatorSystem** > **·**.

Leht **Süsteem** sisaldab järgmisi vahekaarte.
- [Olek](#status-tab)
- [Kavanda](#schedule-tab)
- [API kasutus](#api-usage-tab)
- [Teave](#about-tab)
- [Üldist](#general-tab)
- [Turve](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Sätete vahekaardid süsteemilehel.":::

## <a name="status-tab"></a>Oleku vaehekaart

Vahekaart **Olek** võimaldab teil jälgida ülesannete edenemist, andmete allaneelamist, andmeeksporti ja mitmeid muid olulisi tooteprotsesse. Vaadake üle sellel vahekaardil olev teave, et tagada aktiivsete ülesannete ja protsesside täielikkus.

Vahekaart sisaldab oleku ja erinevate protsessidega teabetöötlustabeleid. Iga tabel jälgib tööülesande **Nime** ja sellele vastavat olemit, viimase käitamise **Olekut** ja millal seda viimati **Värskendati**. Viimase mitme jooksu üksikasju saate vaadata, valides ülesande või protsessi nime. 

Valige toimingu või protsessi kõrval olev olek veerus **Olek**, et avada paani Edenemise **üksikasjad**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Süsteemi edenemise üksikasjade paan":::

### <a name="status-definitions"></a>Olekumääratlused

Süsteem kasutab ülesannete ja protsesside jaoks järgmisi olekuid.

|Olek  |Määratlus  |
|---------|---------|
|Loobutud |Kasutaja tühistas töötlemise enne selle lõpetamist.   |
|Ebaõnnestus   |Andmete sisestamisel ilmnesid tõrked.         |
|Tõrge  |Töötlemine on nurjunud.  |
|Pole käivitatud   |Andmeallikas pole valmendatud andmeid või see on ikka mustandirežiimis.         |
|Töötlemine  |Ülesanne või protsess on pooleli.  |
|Värskendamine    |Andmete sisestamine on pooleli. Selle toimingu tühistamiseks valige **Peata värskendamine** **Toimingute** veerus. Andmeallika värskendamise peatamine ennistab selle viimase värskendamise olekusse.       |
|Vahele jäetud  |Ülesanne või protsess jäi vahele. Üks või mitu järgnevat protsessi, millest see tööülessane sõltub, nurjuvad või jäid vahele.|
|Tehtud  |Ülesanne või protsess on edukalt lõpule viidud. Andmeallikate puhul näitab, et andmed on edukalt sisse võetud, kui veerus **Värskendatud** mainitakse aega.|
|Järjekorras | Töötlemine on järjekorras ja algab siis, kui kõik eelnevad ülesanded ja protsessid on lõpule viidud. Lisateavet leiate teemast [Protsesside](#refresh-processes) värskendamine.|

### <a name="refresh-processes"></a>Protsesside värskendamine

Ülesannete ja protsesside värskendamine toimub vastavalt konfigureeritud [ajakavale](#schedule-tab). 

|Töötle  |Kirjeldus  |
|---------|---------|
|Tegevus  |Töötab käsitsi (ühekordne värskendamine). Sõltub ühendamisprotsessist. Ülevaated sõltuvad selle töötlemisest.|
|Analüüsi linkimine |Töötab käsitsi (ühekordne värskendamine). Sõltub segmentidest.  |
|Analüüsi ettevalmistamine |Töötab käsitsi (ühekordne värskendamine). Sõltub segmentidest.  |
|Andmete ettevalmistamine   |Sõltub ühinemisest.   |
|Andmeallikad   |Ei sõltu muudest protsessidest. Vastendamine sõltub selle protsessi edukast lõpuleviimisest.  |
|Rikastamised   |Töötab käsitsi (ühekordne värskendamine). Sõltub ühendamisprotsessist. |
|Ekspordi sihtkohad |Töötab käsitsi (ühekordne värskendamine). Sõltub segmentidest.  |
|Ülevaated |Töötab käsitsi (ühekordne värskendamine). Sõltub segmentidest.  |
|Ärianalüüs   |Sõltub ühinemisest.   |
|Vastenda |Sõltub vastenduse määratluses kasutatud andmeallikate töötlemisest.      |
|Näitajad  |Töötab käsitsi (ühekordne värskendamine). Sõltub ühendamisprotsessist.  |
|Liida   |Sõltub vastenduse protsessi lõpuleviimisest. Segmendid, meetmed, rikastamine, otsing, tegevused, prognoosid ja andmete ettevalmistamine sõltuvad selle protsessi edukast lõpuleviimisest.   |
|Profiilid   |Töötab käsitsi (ühekordne värskendamine). Sõltub ühendamisprotsessist. |
|Otsige   |Töötab käsitsi (ühekordne värskendamine). Sõltub ühendamisprotsessist. |
|Segmendid  |Töötab käsitsi (ühekordne värskendamine). Sõltub ühendamisprotsessist. Ülevaated sõltuvad selle töötlemisest.|
|Süsteem   |Sõltub vastenduse protsessi lõpuleviimisest. Segmendid, meetmed, rikastamine, otsing, tegevused, prognoosid ja andmete ettevalmistamine sõltuvad selle protsessi edukast lõpuleviimisest.   |
|User  |Töötab käsitsi (ühekordne värskendamine). Sõltub olemite kohta.  |

Valige protsessi olek, et näha kogu selle töö edenemisandmeid, milles see oli. Ülaltoodud värskendusprotsessid **aitavad mõista, mida saate teha vahele jäetud** või **järjekorras oleva ülesande või protsessi lahendamiseks**.

## <a name="schedule-tab"></a>Ajastamise vahekaart

Kasutage vahekaarti **Ajastamine**, et ajastada kõigi [valmendatud andmeallikate](data-sources.md) jaoks automaatsed värskendused. Automaatne värskendamine aitab tagada, et teie andmeallikate värskendused kajastuksid teie kliendi koondprofiilidel.

> [!NOTE]
> Andmeallikad, mida haldate, värskendate oma ajakavades. Teie hallatavate andmeallikate värskendamise kavandamiseks konfigureerige selle konkreetse andmeallikas **värskendamissätted lehel Andmeallikad**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform Andmevoo värskendamise sätted.":::

1. Minge sihtrühmaülevaadetes lehele **Haldus** > **Süsteem** ja valige vahekaart **Ajastamine**.

2. Ajastatud värskendamise vaike-olek on **Väljas**. Ajastatud värskenduste luvamiseks lülitage ekraani ülaosas sisse valik **Sees**.

3. Värskendamisvalikuteks on **Iga nädal** (tavaline) ja **Iga päev**. Kui kavatsete värskendada iga nädal, valige vähemalt üks päev, mil tahate värskendada.

4. Määrake **Ajavöönd** ja seejärel kasutage ripploendit **Aeg** oma värskendamise aja määramiseks. Kui olete lõpetanud, valige käsk **Määra**. Kui tahate ajastada mitu värskendust ühel päeval, valige **Vali muu kellaaeg**.

5. Vajutage nuppu **Salvesta**, et muudatused rakendada.

## <a name="about-tab"></a>Teave vahekaardi kohta

Vahekaart **Teave** sisaldab teie organisatsiooni **Kuvatavat nime**, aktiivset **Keskkonna ID-d**, **Piirkonda** ja teie **Seansi ID-d**. Kui teil on rohkem kui üks töökeskkond, peate andma igale keskkonnale lihtsasti tuvastatava kuvatava nime.

## <a name="general-tab"></a>Vahekaart Üldine

Vahekaardil **Üldine** saate muuta keelt ja riigi/regiooni vormingut.

Customer Insights [toetab paljusid keeli](/dynamics365/get-started/availability). Rakendus kasutab teie keele-eelistust, et kuvada teie eelistatud keeles elemente, nt menüü, silditekst ja süsteemiteated.

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

   Toimingud, mis kasutavad [reaalajas andmete allaneelamist](real-time-data-ingestion.md), sisaldavad binokli sümboliga nuppu, et vaadata reaalajas API kasutamist. Valige nupp, et avada külgpaan, mis sisaldab reaalajas API kasutamise üksikasju praeguses keskkonnas.   
   Kasutage paanil **Reaalajaline API kasutus** välja **Rühmita kui**, et valida kuidas reaalajalist suhtlust kõige paremini esitada. Andmeid saate rühmitada API meetodi, olemi kvalifitseeritud nime (valmendatud olem), looja (sündmuse allikas), tulemuse (õnnestumine või nurjumine) või tõrkekoodide järgi. Andmed on saadaval ajaloodiagrammina ja tabelina.

## <a name="security-tab"></a>Turvevahekaart

Vahekaart **Turve** võimaldab teil linkida ja hallata keskkonna oma [Azure'i võtmehoidlat](/azure/key-vault/general/basic-concepts).
Sihtotstarbelise võtmehoidla abil saab etappe luua ja kasutada saladusi organisatsiooni vastavuse piirides. Sihtrühma ülevaated saavad kasutada Azure'i võtmehoidla saladusi [ühenduste loomiseks](connections.md) muude tootjate süsteemidega.

Lisateavet leiate jaotisest [Enda Azure'i võtmehoidla loomine](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
