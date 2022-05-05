---
title: Segmendid Customer Insightsis
description: Ülevaade segmentidest ning kuidas neid luua ja hallata.
ms.date: 03/30/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: 9791e971387eb7db91ed7c4e4fe76552656013ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642759"
---
# <a name="segments-overview"></a>Segmentide ülevaade

Segmentide abil saate oma kliente rühmitada demograafiliste, tehingupõhiste või käitumuslike atribuutide põhjal. Segmentide abil saate sihtida reklaamikampaaniaid, müügitegevusi ja klienditoe ttoiminguid oma ärieesmärkide saavutamiseks.

Kliendiprofiile, mis vastavad segmendi määratluse filtritele, nimetatakse segmendi *liikmeteks* . Kehtivad [teenusepiirangud](/dynamics365/customer-insights/service-limits).

## <a name="create-a-new-segment"></a>Looge uus segment

Uue segmendi loomiseks on mitu võimalust. 

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

- Keerukas segment segmendi ehitajaga: [Ehita enda oma](segment-builder.md#create-a-new-segment) 
- Lihtsad segmendid ühe tehtega: [Kiirsegment](segment-builder.md#quick-segments) 
- AI-powered viis sarnaste klientide leidmiseks: [Sarnased Kliendid](find-similar-customer-segments.md) 
- AI-powered soovitused, mis põhinevad mõõtmistel või atribuutidel: [Soovitatavad segmendid mõõtmiste parendamiseks](suggested-segments.md) 
- Tegevustel põhinevad soovitused: [Klienditegevusel põhinevad soovitatavad segmendid](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

- Keerukas segment segmendi ehitajaga: [Ehita enda oma](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Olemasolevate segmentide haldamine

**Avage leht Segmendid**, et vaadata kõiki salvestatud segmente ja neid hallata.

Igat segmenti esindab rida, mis sisaldab segmendi kohta täiendavat teavet.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valitud segment suvandite ripploendi ja saadaolevate suvanditega." lightbox="media/segments-selected-segment.png":::

Segmendi valimisel on saadaval järgmised toimingud.

- Segmendi üksikasjade **Vaatamine**, sealhulgas liikmete arvu suundumist, segmendi liikmete ülevaadet.
- Liikmete loendi **Allalaadimine** CSV-failina.
- Segmendi **Redigeerimine** atribuutide muutmiseks.
- Segmendi **Duplikaadi loomine**. Saate selle atribuute kohe redigeerida või lihtsalt duplikaadi salvestada.
- Segmendi **Värskendamine** viimaste andmete kaasamiseks.
- Segmendi **Aktiveerimine** või **Desaktiveerimine**. Passiivsete segmentide puhul segmendi määratlus on olemus, kuid see ei sisalda ühtegi klienti. Aktiivne segment otsib kliente, kes vastavad segmendi määratlusele. Kui [plaanitud värskendus](system.md#schedule-tab) on konfigureeritud, on passiivsete segmentide **olekuks** **Vahele jäetud**, mis näitab, et värskendamist isegi ei proovitud. Kui passiivne segment aktiveeritakse, värskendatakse seda ja lisatakse plaanitud värskendustesse.
  Teise võimalusena saate kasutada ripploendi **Aktiveeri/desaktiveeri** funktsiooni **Ajasta hiljem**, et määrata kindla segmendi aktiveerimise ja desaktiveerimise tulevane kuupäev ja kellaaeg.
- **[Leidke segmendist sarnaseid kliente](find-similar-customer-segments.md)**.
- Segmendi **Ümbernimetamine**.
- **Silt** [segmendi siltide](work-with-tags-columns.md#manage-tags) haldamiseks.
- Liikmete loendi **Allalaadimine** CSV-failina.
- **Eksportide haldamine** suvand ekspordiga seotud segmendi kuvamiseks ja haldamiseks. [Lisateave eksportide kohta.](export-destinations.md)
- Segmendi **Kustutamine**.
- **Veerud** kuvatavate veergude [kohandamiseks](work-with-tags-columns.md#customize-columns).
- **Filtreerige** siltidel [filtreerimiseks](work-with-tags-columns.md#filter-on-tags).
- **Otsige nime** segmendi nime järgi otsimiseks.

## <a name="refresh-segments"></a>Segmentide värskendamine

Saate kõiki segmente korraga värskendada, valides lehel **Segmendid** suvandi **Värskenda kõik** või saate ühte või mitut segmenti värskendada, kui valite need ja valite suvandite hulgast **Värskenda**. Teise võimalusena saate konfigureerida korduva värskendamise, valides **Administraator** > **Süsteem** > **Ajasta**. Korduva värskendamise konfigureerimisel kehtivad järgmised reeglid.
- Kõik segmendid, mille tüüp **on Dünaamiline** või **Laienemine**, värskendatakse automaatselt määratud kadentsil. Kui värskendamine on lõppenud, näitab olek **,** kas segmendi värskendamisel oli probleeme. Viimati **värskendatud** kuvatakse viimase eduka värskendamise ajatempel. Kui ilmneb tõrge, valige tõrge, et näha üksikasju selle kohta, mis juhtus.
- Segmente, mille tüüp **on Staatiline** *, ei* värskendata automaatselt. Viimati **värskendatud** kuvatakse ajatempel viimasest ajast, mil staatilisi segmente käsitsi käitati või värskendati.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Ekspordi segmendid

Segmenti saate eksportida segmentide lehelt või [ekspordilehelt](export-destinations.md). 

1. Minge lehele **Segmendid**.

1. Valige **Kuva rohkem [....]** segmendile, mille soovite eksportida.

1. Valige **Ekspordi haldamine** tegevuste ripploendist.

1. Avaneb **Segmendi ekspordid (eelvaade)** leht. Näete kõiki konfigureeritud eksporte rühmitatud selle järgi, kas need sisaldavad praegust segmenti või mitte.

   1. Valitud segmendi lisamiseks eksporti **Redigeerige** vastavat eksporti, et valida vastav segment, seejärel salvestage. Üksikklientide keskkondades saate valida loendist ekspordi ja valida sama tulemuse saavutamiseks suvandi **Lisa segment**.

   1. Valitud segmendiga uue ekspordi loomiseks valige **Lisa eksport**. Lisateavet ekspordi loomise kohta leiate teemast [Uue ekspordi häälestamine](export-destinations.md#set-up-a-new-export).

1. Segmentide põhilehele naasmiseks klõpsake nuppu **Tagasi**.

## <a name="view-processing-history-and-segment-members"></a>Vaadake töötlemise ajalugu ja segmendi liikmeid

Segmendi koondandmete nägemiseks vaadake üle selle üksikasjad.

Lehel **Segmendid** valige ülevaadatav segment.

Lehe ülaosa sisaldab suundumuse trendigraafikut, mis visualiseerib liikmete arvu muudatused. Hoidke kursorit andmepunktide kohal, et näha liikmete arvu kindlal kuupäeval.

Saate uuendada visualiseerimise ajavahemikku.

> [!div class="mx-imgBorder"]
> ![Segmendi ajavahemik.](media/segment-time-range.png "Segmendi ajavahemik")

Alaosa sisaldab segmendi liikmete loendit.

> [!NOTE]
> Selle loendi väljad põhinevad segmendi olemite atribuutidel.
>
>Loend on eelvaade kattuvatest segmendi liikmetest ja näitab segmendi 100 esimest kirjet, et saaksite vajadusel kiiresti seda hinnata ja kontrollida selle määratlusi. Kõikide kattuvate kirjete nägemiseks peate [eksportima segmendi](export-destinations.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
