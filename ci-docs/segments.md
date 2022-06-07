---
title: Segmendid Customer Insightsis
description: Ülevaade segmentidest ning kuidas neid luua ja hallata.
ms.date: 05/20/2022
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
ms.openlocfilehash: d616ec8273115203dddb59334a348c66e72fa678
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800737"
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
- Segmendi **Duplikaadi loomine**. Saate valida selle atribuutide kohese redigeerimise või duplikaadi salvestamise.
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

- Kõik segmendid, mille tüüp **on Dünaamiline** või **Laienemine**, värskendatakse automaatselt määratud kadentsil. Kui värskendamine on lõppenud, näitab olek **,** kas segmendi värskendamisel ilmnes probleeme. Viimati **värskendatud** kuvatakse viimase eduka värskendamise ajatempel. Tõrke ilmnemisel valige tõrge, et näha üksikasju selle kohta, mis juhtus.
- Segmente, mille tüüp **on Staatiline** *, ei* värskendata automaatselt. Viimati **värskendatud** kuvatakse ajatempel viimasest ajast, mil staatilisi segmente käsitsi käitati või värskendati.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Ekspordi segmendid

Segmenti saate eksportida segmentide lehelt või [ekspordilehelt](export-destinations.md). 

1. Minge lehele **Segmendid**.

1. Valige eksporditava segmendi vertikaalne kolmikpunkt (&vellip;).

1. Valige **Ekspordi haldamine** tegevuste ripploendist.

1. Avaneb **Segmendi ekspordid (eelvaade)** leht. Näete kõiki konfigureeritud eksporte rühmitatud selle järgi, kas need sisaldavad praegust segmenti või mitte.

   1. Valitud segmendi lisamiseks eksporti **Redigeerige** vastavat eksporti, et valida vastav segment, seejärel salvestage. Üksikute klientide keskkondades saate selle asemel valida loendist ekspordi ja valida sama tulemuse saavutamiseks suvandi **Lisa segment**.

   1. Valitud segmendiga uue ekspordi loomiseks valige **Lisa eksport**. Lisateavet ekspordi loomise kohta leiate teemast [Uue ekspordi häälestamine](export-destinations.md#set-up-a-new-export).

1. Segmentide põhilehele naasmiseks klõpsake nuppu **Tagasi**.

## <a name="track-usage-of-a-segment"></a>Segmendi kasutamise jälgimine

Kui kasutate rakendustes segmente, mis põhinevad samal Microsoft Dataverse organisatsioonil, mis on seotud Customer Insightsiga, saate jälgida segmendi kasutamist. Dynamics 365 Marketingi [kliendireisidel kasutatavate Customer Insightsi segmentide puhul](/dynamics365/marketing/real-time-marketing-ci-profile) teavitab süsteem teid selle segmendi kasutamisest.

Customer Insightsi keskkonnas kasutatava segmendi või turunduse klienditeekond redigeerimisel teavitab segmendikoosturi [bänner](segment-builder.md) teid sõltuvustest. Sõltuvuse üksikasju saate kontrollida otse bännerilt või valides **segmendikoosturis suvandi Kasutus**.

Segmendi **kasutuspaanil** kuvatakse üksikasjad selle segmendi kasutamise kohta põhinevates rakendustes Dataverse. Kliendireisidel kasutatavate segmentide puhul leiate lingi teekonna kontrollimiseks turunduses, kus seda segmenti kasutatakse. Kui teil on õigused rakendusele Marketing juurdepääs, pääsete seal juurde rohkematele üksikasjadele.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Külgpaan koos segmendi kasutuse üksikasjadega segmendikoosturis.":::

Süsteem teavitab teid jälgitava segmendi kasutamisest, kui proovite seda kustutada. Kui kustutatavat segmenti kasutatakse turunduse klienditeekond, peatub see teekond kõigi segmendi kasutajate jaoks. Kui teekond on osa turunduskampaaniast, mõjutab kustutamine seda kampaaniat ennast. Siiski saate segmendi hoiatustest hoolimata kustutada.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialoogiboks segmendi kustutamise kinnitamiseks, kui rakenduses kasutatakse segmenti Dataverse .":::

### <a name="supported-apps"></a>Toetatud rakendused

Kasutust jälgitakse praegu järgmistes Dataverse rakendustes.

- [Klienditeekonnad rakenduses Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

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
