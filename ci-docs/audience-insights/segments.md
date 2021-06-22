---
title: Segmendid publiku ülevaates
description: Ülevaade segmentidest ning kuidas neid luua ja hallata.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111382"
---
# <a name="segments-overview"></a>Segmentide ülevaade

Segmentide abil saate oma kliente rühmitada demograafiliste, tehingupõhiste või käitumuslike atribuutide põhjal. Segmentide abil saate sihtida reklaamikampaaniaid, müügitegevusi ja klienditoe ttoiminguid oma ärieesmärkide saavutamiseks.

Kliendiprofiile, mis vastavad segmendi määratluse filtritele, nimetatakse segmendi *liikmeteks* . Kehtivad [teenusepiirangud](service-limits.md).

## <a name="create-a-new-segment"></a>Looge uus segment

Uue segmendi loomiseks on mitu võimalust. 

- Keerukas segment segmendi ehitajaga: [Tühi segment](segment-builder.md#create-a-new-segment)
- Lihtsad segmendid ühe tehtega: [Kiirsegment](segment-builder.md#quick-segments)
- AI-powered viis sarnaste klientide leidmiseks: [Sarnased Kliendid](find-similar-customer-segments.md)
- AI-powered soovitused, mis põhinevad mõõtmistel või atribuutidel: [Soovitatavad segmendid mõõtmiste parendamiseks](suggested-segments.md)
- Tegevustel põhinevad soovitused: [Klienditegevusel põhinevad soovitatavad segmendid](suggested-segments-activity.md)

## <a name="manage-existing-segments"></a>Olemasolevate segmentide haldamine

Minge lehele **Segmendid** et vaadata ja hallata kõiki oma salvestatud segmente.

Igat segmenti esindab rida, mis sisaldab segmendi kohta täiendavat teavet.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valitud segment suvandite ripploendi ja saadaolevate suvanditega.":::

Segmendi valimisel on saadaval järgmised tegevused.

- Segmendi üksikasjade **Vaatamine**, sealhulgas liikmete arvu suundumist, segmendi liikmete ülevaadet.
- Segmendi **Redigeerimine** atribuutide muutmiseks.
- Segmendi **Duplikaadi loomine**. Saate selle atribuute kohe redigeerida või lihtsalt duplikaadi salvestada.
- Segmendi **Värskendamine** viimaste andmete kaasamiseks.
- Segmendi **Aktiveerimine** või **Desaktiveerimine**. Segmentidel on kaks võimalikku olekut – aktiivne või passiivne. Nendest olekutest on kasu segmendi redigeerimise ajal. Passiivsete segmentide puhul segmendi määratlus on olemus, kuid see ei sisalda ühtegi klienti. Kui aktiveerite segmendi, siis selle olekuks muutub valikult passiivne valikule aktiivne ja see hakkab otsima kliente, mis vastavad segmendi määratlusele. Kui [plaanitud värskendus](system.md#schedule-tab) on konfigureeritud, on passiivsete segmentide **olekuks** **Vahele jäetud**, mis näitab, et värskendamist isegi ei proovitud. Kui passiivne segment aktiveeritakse, värskendatakse seda ja lisatakse plaanitud värskendustesse.
  Teise võimalusena saate kasutada ripploendi **Aktiveeri/desaktiveeri** funktsiooni **Ajasta hiljem**, et määrata kindla segmendi aktiveerimise ja desaktiveerimise tulevane kuupäev ja kellaaeg.
- Segmendi **Ümbernimetamine**.
- Liikmete loendi **Allalaadimine** CSV-failina.
- **Eksportide haldamine** suvand ekspordiga seotud segmendi kuvamiseks ja haldamiseks. [Lisateave eksportide kohta.](export-destinations.md)
- Segmendi **Kustutamine**.

## <a name="refresh-segments"></a>Segmentide värskendamine

Saate kõiki segmente korraga värskendada, valides lehel **Segmendid** suvandi **Värskenda kõik** või saate ühte või mitut segmenti värskendada, kui valite need ja valite suvandite hulgast **Värskenda**. Teise võimalusena saate konfigureerida korduva värskendamise, valides **Administraator** > **Süsteem** > **Ajasta**.

> [!TIP]
> Ülesannete/protsesside jaoks on [kuus tüüpi olekuid](system.md#status-types). Lisaks sõltuvad enamikud protsessid [muudest järgnevatest protsessidest](system.md#refresh-policies). Kogu töö edenemise üksikasjade nägemiseks saate valida protsessi oleku. Kui olete valinud ühe tööülesande jaoks suvandi **Kuva üksikasjad**, näete järgmist lisateavet: töötlemise aeg, viimane töötlemise kuupäev ja kõik ülesandega seotud tõrked ja hoiatused.

## <a name="export-segments"></a>Ekspordi segmendid

Segmenti saate eksportida segmentide lehelt või [ekspordilehelt](export-destinations.md). 

1. Minge lehele **Segmendid**.

1. Valige **Kuva rohkem [....]** segmendile, mille soovite eksportida.

1. Valige toimingute rippmenüüst **Eksportide haldamine**.

1. Avaneb **Segmendi ekspordid (eelvaade)** leht. Näete kõiki konfigureeritud eksporte, mis on rühmitatud praegust segmenti sisaldavate või seda mitte sisaldavate ekspordite järgi.

   1. Valitud segmendi lisamiseks ekspordile valige loendist eksport ja valige **Lisa segment**.

   1. Valitud segmendiga uue ekspordi loomiseks valige **Lisa eksport**. Lisateavet ekspordi loomise kohta leiate teemast [Uue ekspordi häälestamine](export-destinations.md#set-up-a-new-export).

1. Segmentide põhilehele naasmiseks klõpsake nuppu **Tagasi**.

## <a name="view-processing-history-and-segment-members"></a>Vaadake töötlemise ajalugu ja segmendi liikmeid

Segmendi koondandmete nägemiseks vaadake üle selle üksikasjad.

Lehel **Segmendid** valige ülevaadatav segment.

Lehe ülaosa sisaldab suundumuse trendigraafikut, mis visualiseerib liikmete arvu muudatused. Hoidke kursorit andmepunktide kohal, et näha liikmete arvu kindlal kuupäeval.

Saate uuendada visualiseerimise ajavahemikku.

> [!div class="mx-imgBorder"]
> ![Segmendi ajavahemik](media/segment-time-range.png "Segmendi ajavahemik")

Alaosa sisaldab segmendi liikmete loendit.

> [!NOTE]
> Selle loendi väljad põhinevad segmendi olemite atribuutidel.
>
>Loend on eelvaade kattuvatest segmendi liikmetest ja näitab segmendi 100 esimest kirjet, et saaksite vajadusel kiiresti seda hinnata ja kontrollida selle määratlusi. Kõikide kattuvate kirjete nägemiseks peate [eksportima segmendi](export-destinations.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
