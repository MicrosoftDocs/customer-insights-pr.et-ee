---
title: Kaasamisülevaadete veebiandmete integreerimine sihtrühmaülevaadetega
description: Saate tuua veebiteavet klientide kohta kaasamisülevaadetest sihtrühmaülevaadetesse.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2789a7d1379e0cf56511b272a763c904d8a3d347058ea9e029aaff0f723a028
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033764"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Kaasamisülevaadete veebiandmete integreerimine sihtrühmaülevaadetega

Kliendid teevad sageli oma igapäevaseid veebitehinguid veebisaitide abil. Kaasamisülevaadete (eelversioon) võimalus tarkvaras Dynamics 365 Customer Insights on käepärane lahendus veebiandmete integreerimiseks lähteandmetega. Ühendatud kliendiprofiilides näete lisaks tehingute, demograafilistele või käitumuslikele andmetele ka veebitegevusi. Me võime kasutada neid profiile, et saada täiendavaid ülevaateid, nagu vaatajaskonna aktiveerimise segmendid, mõõdikud või prognoosid.

Selles artiklis kirjeldatakse, kuidas tuua klientide veebitegevuse andmed kaasamisülevaadetest oma olemasolevasse sihtrühmaülevaadete keskkonda.

Selles näites kasutame keskkonda, mis sisaldab ühendatud kliendiprofiile. Profiilid ühendati uuringutest, jaemüügist ja piletisüsteemist pärinevate allikate abil. Samuti kuvatakse siin klientidega seotud tegevusi. 

Me soovime nüüd teada, kas klient külastab meie veebiatribuute ja saada aru nende tegevustest. Tegevuste hulka kuuluvad näiteks külastatud veebisaidid või meili teel saadetud lingi kaudu vaadatud tootelehed.

## <a name="prerequisites"></a>Eeltingimused

Kaasamisülevaadetest andmete integreerimiseks peavad olema täidetud mõned eeltingimused. 

- Integreerige kaasamisülevaadete SDK oma veebisaidiga. Lisateavet leiate [Arendaja ressursside ülevaade](../engagement-insights/developer-resources.md).
- Veebisündmuste eksportimiseks kaasamisülevaadetest on vaja juurdepääsu Azure Data Lake Storage kontole, mida kasutatakse veebisündmuste andmete vaatajaskonna ülevaate saamiseks. Lisateavet leiate teemast [Sündmuste eksportimine](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Kaasamisülevaadete täpsustatud sündmuste konfigureerimine

Kui administraator kasutab kaasamisülevaadetega SDK-ga veebisaiti, kogutakse *baassündmused* kokku, kui kasutaja vaatab veebilehte või klõpsab soovitud teavet. Baassündmused võivad sisaldada paljusid üksikasju. Sõltuvalt kasutusjuhtumist vajate baassündmuses andmete alamhulka. Kaasamisülevaadete abil saate luua *täpsustatud sündmusi*, mis sisaldavad ainult teie valitud baassündmuse atribuute.     

Lisateavet leiate teemast [Täpsustatud sündmuste loomine ja muutmine](../engagement-insights/refined-events.md).

Mida võtta arvesse täpsustatud sündmuste loomisel. 

- Pange täpsustatud sündmusele tähenduslik nimi. Seda kasutatakse sihtrühma ülevaadetes tegevuse nimena.
- Valige sihtrühmaülevaadetes tegevuse loomiseks vähemalt järgmised atribuudid. 
    - Signal.Action.Name – tähistab tegevuse üksikasju.
    - Signal.User.Id – kasutatakse kliendi ID-ga kaardistamiseks.
    - Signal.View.Uri – kasutatakse veebiaadressina segmentide või mõõtude alusena.
    - Signal.Export.Id – kasutatakse sündmuste primaarvõtmena.
    - Signal.Timestamp – kuvab tegevuse edastuse kuupäeva ja kellaaja.

Valige filtrid, et keskenduda sündmustele ja lehtedele, mis teie kasutusjuhtumi jaoks olulised on. Selles näites kasutame tegevuse nime „Meilikampaania”.

## <a name="export-the-refined-web-events"></a>Täpsustatud veebisündmuste eksportimine 

Pärast täpsustatud sündmuse määratlemist peate konfigureerima sündmuse andmete eksportimise Azure Data Lake Storage, mille saab seada vaatajaskonna statistikasse sisestamise andmeallikaks. Ekspordid toimuvad pidevalt sündmuste voolamisel veebiatribuudist.

Lisateavet leiate teemast [Sündmuste eksportimine](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Sündmuse andmete valmendamine sihtrühmaülevaadetesse

Kui olete määratlenud täpsustatud sündmused ja konfigureerinud selle eksportimise, liigume edasi andmete valmendamisega sihtrühmaülevaadetesse. Peate looma uue andmeallika Common Data Modeli kausta põhjal. Sisestage selle salvestusruumikonto üksikasjad, kuhu sündmused ekspordite. Valige failis *default.cdm.json* täpsustatud sündmus, mida valmendada ja looge olem sihtrühmaülevaadetes.

Lisateavet leiate teemast [Common Data Modeli kaustaga ühendamine Azure Data Lake'i konto abil](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Täpsustatud sündmuse andmete seostamine kliendiprofiili tegevusega

Pärast olemi valmendamise lõpule viimist saate konfigureerida tegevuse kliendiprofiili jaoks.

Lisateavet vt teemast [Klienditegevused](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Tegevuste leht laiendatud Redigeeri toimingupaaniga ja täidetud väljadega.":::

Konfigureerige uus tegevus järgmise vastendusega. 

- **Primaarvõti**: Signal.Export.Id, kordumatu ID, mis on saadaval iga kaasamisülevaadete sündmusekirje jaoks. See atribuut luuakse automaatselt.

- **Ajatempel**: Signal.Timestamp sündmuse atribuudis.

- **Sündmus**: Signal.Name, sündmuse nimi, mida soovite jälgida.

- **Veebiaadress**: Signal.View.Uri, mis viitab sündmuse loonud lehe URI-le.

- **Üksikasjad**: Signal.Action.Name, mis tähistab sündmusega seostatavat teavet. Valitud atribuut näitab antud juhul seda, et sündmus on meilikampaania jaoks.

- **Tegevuse tüüp**: selles näites valime olemasoleva tegevusetüübi WebLog. See valik on kasulik filtrisuvand prognoosimudelite käitamiseks või segmentide loomiseks selle tegevusetüübi põhjal.

- **Seose seadistamine**: See oluline säte seob tegevuse olemasolevate kliendiprofiilidega. **Signal.User.Id** on SDK-s konfigureeritud kogutav identifikaator, mis on seotud sihtrühmaülevaadetes konfigureeritud muude andmeallikate kasutaja ID-ga. Selles näites konfigureerime seose Signal.User.Id ja RetailCustomers:CustomerRetailId vahel, mis on primaarvõti, mis määratleti andmete ühendamise protsessi kaardietapis.

Pärast tegevuste töötlemist saate vaadata üle kliendikirjed ja avada kliendikaardi, et kuvada ajajoonel kaasamisülevaadete tegevused. 

> [!TIP]
> Kaasamisülevaadete tegevusega kliendi ID leidmiseks avage **Olemid** ja vaadake üle olemi UnifiedActivity andmed. ActivityTypeDisplay = WebLog sisaldab ülaltoodud näites konfigureeritud kaasamisülevaadete tegevust. Kopeerige üks kirjetest ja selle ID kliendi ID lehel **Kliendid**.

## <a name="next-steps"></a>Järgmised etapid

Nüüd saate luua [segmente](segments.md), [mõõte](measures.md) ja [prognoose](predictions.md), et luua klientidega mõtestatud ühendus.


[!INCLUDE[footer-include](../includes/footer-banner.md)]