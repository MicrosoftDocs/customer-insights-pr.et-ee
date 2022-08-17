---
title: Vaadake süsteemi konfiguratsiooni
description: Lisateave Dynamics 365 Customer Insightsi süsteemi seadete kohta.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246242"
---
# <a name="view-system-configuration"></a>Vaadake süsteemi konfiguratsiooni

Vaadake süsteemiteavet, süsteemi olekut ja API kasutamist.

## <a name="view-api-usage"></a>Vaata API kasutust

Vaadake reaalajas API kasutamise üksikasju ja vaadake, millised sündmused antud aja jooksul toimusid.

1. Minge jaotisse **Haldussüsteem** > **ja** valige **vahekaart API kasutamine**.

1. **Valige vaadatav ajavahemik**.

   **API kasutamise** leht sisaldab kolme jaotist:

   - **API-päringud** – diagramm, mis visualiseerib valitud aja jooksul API päringute koondarvu.
   - **Andmeedastus** – diagramm, mis kuvab valitud ajaraamistikul API kaudu edastatud andmete hulga.
   - **Toimingud** – tabel, kus on reaga iga saadaolev API-toiming ja teave toimingute kasutamise kohta. Valige toimingu nimi, et minna API viite [juurde](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Toimingud, mis kasutavad [reaalajas andmete allaneelamist](real-time-data-ingestion.md), sisaldavad binokulaarset sümbolit API reaalajas kasutamise vaatamiseks.

   1. Valige binokkel, et avada **reaalajas API kasutamise** paan, mis sisaldab toimingu kasutusandmeid.
   1. **Valige vaadatav ajavahemik**.
   1. Kasutage kasti **Rühmitamine**, et valida, kuidas oma reaalajas suhtlust kõige paremini esitada. Rühmitage andmed API meetodi, olemi kvalifitseeritud nime **(allaneelatud olem),** loodud **(sündmuse allikas),** tulemuse **(edu või tõrge) või** tõrkekoodide **järgi.** **·** Andmed on saadaval ajaloodiagrammina ja tabelina.

## <a name="view-system-information"></a>Süsteemiteabe vaatamine

Vaadake keskkonna kuvatavat nime, ID-d, piirkonda, tüüpi ja seansi ID-d.

1. Avage **Haldussüsteem** > **ja** valige **vahekaart Teave**.

1. Keele ja riigi/regiooni vaatamiseks valige **vahekaart Üldine**.

### <a name="update-preferred-language-or-countryregion"></a>Eelistatud keele või riigi/regiooni värskendamine

Customer Insights [toetab paljusid keeli](/dynamics365/get-started/availability). Rakendus kasutab teie keele-eelistust, et kuvada teie eelistatud keeles elemente, nt menüü, silditekst ja süsteemiteated.

Käsitsi sisestatud imporditud andmeid ja teavet ei tõlgita.

1. Minge jaotisse **Haldussüsteem** > **ja** valige **vahekaart Üldine**.

1. Eelistatud keele muutmiseks valige ripploendist **Keel**.

1. Eelistatud kuupäeva, kellaaja ja numbrite vormingute muutmiseks kasutage ripploendit **Riigi/piirkonna vorming**. Kuvatakse vormindamise eelvaade. Süsteem soovitab uue keele valimisel automaatselt valikut.

1. Valige **Salvesta**.

## <a name="view-system-status"></a>Kuva süsteemi olek

Saate jälgida ülesannete edenemist, andmete allaneelamist, andmete eksportimist ja mitmeid muid olulisi tooteprotsesse. Vaadake teave üle, et tagada oma aktiivsete ülesannete ja protsesside täielikkus.

1. Avage **haldussüsteem** > **ja** valige **vahekaart Olek**.

   Kuvatakse erinevate protsesside oleku- ja töötlemisteave. **Vaadake tööülesande nime**, selle viimase käitamise olekut **ja** viimati **värskendatud aega**.

1. Mitme viimase jooksu üksikasjade vaatamiseks valige ülesande või protsessi nimi.

1. Ülesande edenemise üksikasjade vaatamiseks valige olek. Kuvatakse **paan Edenemise üksikasjad**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Süsteemi edenemise üksikasjade paan":::

1. Kõigi ülesannete edenemise üksikasjade vaatamiseks valige **Kogu töövoog**.

### <a name="status-definitions"></a>Staatuse määratlused

Süsteem kasutab ülesannete ja protsesside jaoks järgmisi olekuid.

|Olek  |Määratlus  |
|---------|---------|
|Loobutud |Kasutaja tühistas ülesande või protsessi enne selle lõpetamist.   |
|Ebaõnnestus   |Ülesanne või protsess sattus vigadesse.         |
|Tõrge  |Ülesanne või protsess on nurjunud.  |
|Pole käivitatud   |Andmeallikas pole veel andmeid alla neelanud või ülesanne on endiselt mustandirežiimis.         |
|Töötlemine  |Ülesanne või protsess on pooleli.  |
|Värskendamine    |Ülesanne või protsess on pooleli. Selle toimingu tühistamiseks valige **Värskendamine** ja **Tühista töö**. Ülesande või protsessi värskendamise peatamine taastab selle viimase värskendamise oleku.       |
|Vahele jäetud  |Ülesanne või protsess jäeti vahele. Üks või mitu järgnevat protsessi, millest see tööülessane sõltub, nurjuvad või jäid vahele.|
|Tehtud  |Ülesanne või protsess on edukalt lõpule viidud. Andmeallikate puhul näitab, et andmed on edukalt alla neelatud, kui veerus Värskendatud **on mainitud** aega.|
|Järjekorras | Töötlemine on järjekorda pandud ja algab siis, kui kõik eelnevad ülesanded ja protsessid on lõpule viidud. Lisateavet vaadake jaotisest [Protsesside](#refresh-processes) värskendamine.|

### <a name="refresh-processes"></a>Protsesside värskendamine

Ülesannete ja protsesside värskendamine käivitatakse vastavalt konfigureeritud [ajakavale](schedule-refresh.md).

|Töötle  |Kirjeldus  |
|---------|---------|
|Tegevus  |Töötab käsitsi (ühekordne värskendamine). Sõltub ühendamisprotsessist. Ülevaated sõltuvad selle töötlemisest.|
|Analüüsi linkimine |Töötab käsitsi (ühekordne värskendamine). Sõltub segmentidest.  |
|Analüüsi ettevalmistamine |Töötab käsitsi (ühekordne värskendamine). Sõltub segmentidest.  |
|Andmete ettevalmistamine   |Vajab töötamiseks olemit. Andmeallikas üksused sõltuvad allaneelamisest. Rikastunud üksused sõltuvad rikastumisest. Kliendi olem sõltub ühendamisest.  |
|Andmeallikad   |Ei sõltu muudest protsessidest. Vastendamine sõltub selle protsessi edukast lõpuleviimisest.  |
|Rikastamised   |Töötab käsitsi (ühekordne värskendamine). Sõltub ühendamisprotsessist. |
|Ekspordi sihtkohad |Töötab käsitsi (ühekordne värskendamine). Sõltub segmentidest.  |
|Ülevaated |Töötab käsitsi (ühekordne värskendamine). Sõltub segmentidest.  |
|Ärianalüüs   |Sõltub ühendamisest.   |
|Vastenda |Sõltub vastenduse määratluses kasutatud andmeallikate töötlemisest.      |
|Näitajad  |Töötab käsitsi (ühekordne värskendamine). Sõltub ühendamisprotsessist.  |
|Liida   |Sõltub vastenduse protsessi lõpuleviimisest. Segmendid, meetmed, rikastamine, otsing, tegevused, prognoosid ja andmete ettevalmistamine sõltuvad selle protsessi edukast lõpuleviimisest.   |
|Profiilid   |Töötab käsitsi (ühekordne värskendamine). Sõltub ühendamisprotsessist. |
|Otsige   |Töötab käsitsi (ühekordne värskendamine). Sõltub ühendamisprotsessist. |
|Segmendid  |Töötab käsitsi (ühekordne värskendamine). Sõltub ühendamisprotsessist. Ülevaated sõltuvad selle töötlemisest.|
|Süsteem   |Sõltub vastenduse protsessi lõpuleviimisest. Segmendid, meetmed, rikastamine, otsing, tegevused, prognoosid ja andmete ettevalmistamine sõltuvad selle protsessi edukast lõpuleviimisest.   |
|User  |Töötab käsitsi (ühekordne värskendamine). Sõltub olemitest.  |

Valige protsessi olek, et näha kogu poolelioleva töö edenemise üksikasju. Ülaltoodud värskendamisprotsessid aitavad mõista, mida saate teha vahelejäetud või järjestatud **ülesande või protsessi lahendamiseks**.**·**


[!INCLUDE [footer-include](includes/footer-banner.md)]
