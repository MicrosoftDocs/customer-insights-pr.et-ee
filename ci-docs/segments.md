---
title: Segmentide ülevaade
description: Ülevaade segmentidest ning kuidas neid luua ja hallata.
ms.date: 08/12/2022
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
ms.openlocfilehash: d4de3a6af6bc7d54305a23e3fbd3cc95d464d352
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304790"
---
# <a name="segments-overview"></a>Segmentide ülevaade

Segmentide abil saate oma kliente rühmitada demograafiliste, tehingupõhiste või käitumuslike atribuutide põhjal. Segmentide abil saate sihtida reklaamikampaaniaid, müügitegevusi ja klienditoe ttoiminguid oma ärieesmärkide saavutamiseks.

Kliendi- või kontaktiprofiile, mis vastavad segmendimääratluse filtritele, *nimetatakse segmendi liikmeteks*. Kehtivad [teenusepiirangud](/dynamics365/customer-insights/service-limits).

## <a name="create-a-segment"></a>Loo segment

Valige, kuidas luua segment oma sihtrühma põhjal.

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

- Keerukad segmendid segmendiehitajaga: [koostage oma](segment-builder.md)
- Lihtsad segmendid ühe tehtega: [Kiirsegment](segment-quick.md)
- Tehisintellektil põhinev viis sarnaste klientide leidmiseks: [sarnased kliendid](find-similar-customer-segments.md)
- Mõõtudel või atribuutidel põhinevad tehisintellektipõhised soovitused: [mõõtudel põhinevad soovitatud segmendid](suggested-segments.md)
- Tegevustel põhinevad soovitused: [Klienditegevusel põhinevad soovitatavad segmendid](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

Kontode segmentimine või kontaktide segmentimine (eelvaade) segmendikoosturiga: [looge oma](segment-builder.md)

> [!NOTE]
> Enamik ekspordisihtkohti nõuab turunduseesmärkidel kontaktteavet. Seetõttu looge kontaktide segmendid, mida nende ekspordi jaoks kasutada.

---

## <a name="manage-existing-segments"></a>Olemasolevate segmentide haldamine

Minge **lehele Segmendid**, et vaadata loodud segmente, nende olekut ja olekut ning viimast korda, kui andmeid värskendati. Segmentide loendit saate sortida mis tahes veeru järgi või kasutada hallatava segmendi leidmiseks otsinguvälja.

> [!TIP]
> B-to-B keskkondades tuvastab veerg Vaatajaskonna tüüp **,** kas segment põhineb kontodel või kontaktidel.

Valige segment saadaolevate toimingute vaatamiseks.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Valitud segment suvandite ripploendi ja saadaolevate suvanditega." lightbox="media/segments-selected-segment.png":::

- [**Saate vaadata**](#view-segment-details) segmendi üksikasju, sh liikmete arvu trendi ja segmendiliikmete eelvaadet.
- Liikmete loendi **Allalaadimine** CSV-failina.
- Segmendi **Redigeerimine** atribuutide muutmiseks.
- Segmendi **Duplikaadi loomine**. Saate selle atribuute kohe redigeerida või duplikaadi salvestada.
- [**Värskendage**](#refresh-segments) segmenti, et kaasata uusimad andmed.
- Segmendi **Aktiveerimine** või **Desaktiveerimine**. Passiivseid segmente ei värskendata ajastatud värskendamise [ajal](schedule-refresh.md) ja nende olekuks **on** märgitud **vahelejäetud**, mis näitab, et värskendamist isegi ei proovitud. Aktiivseid segmente värskendatakse vastavalt nende tüübile: staatiline või dünaamiline.
- **Muutke segmendi tüüp staatiliseks** või **Muutke dünaamiliseks**. Staatilisi segmente tuleb värskendada käsitsi. Dünaamilisi segmente värskendatakse süsteemi värskendamise ajal automaatselt.
- [**Leidke segmendist sarnaseid kliente**](find-similar-customer-segments.md).
- Segmendi **Ümbernimetamine**.
- **Silt** segmendi siltide [haldamiseks](work-with-tags-columns.md#manage-tags).
- [**·**](#export-segments) Ekspordiga seotud segmentide vaatamiseks ja haldamiseks eksportide haldamine. [Lisateave eksportide kohta.](export-destinations.md)
- Segmendi **Kustutamine**.
- **Veerud** [kuvatavate veergude](work-with-tags-columns.md#customize-columns) kohandamiseks.
- **Filtreerige** siltide [filtreerimiseks](work-with-tags-columns.md#filter-on-tags).
- **Otsige nime**, et otsida segmendi nime järgi.

## <a name="view-segment-details"></a>Segmendi üksikasjade kuvamine

**Valige lehel Segmendid** segment, et vaadata töötlemisajalugu ja segmentida liikmeid.

Lehe ülaosa sisaldab suundumuse trendigraafikut, mis visualiseerib liikmete arvu muudatused. Hoidke kursorit andmepunktide kohal, et näha liikmete arvu kindlal kuupäeval. Muutke visualiseerimise ajakava.

:::image type="content" source="media/segment-time-range.png" alt-text="Segmendi ajavahemik.":::

Alaosa sisaldab segmendi liikmete loendit.

> [!NOTE]
> Selle loendi väljad põhinevad segmendi olemite atribuutidel.
>
> Loend on eelvaade kattuvatest segmendi liikmetest ja näitab segmendi 100 esimest kirjet, et saaksite vajadusel kiiresti seda hinnata ja kontrollida selle määratlusi. Kõigi kattuvate kirjete vaatamiseks valige **Kuva rohkem**, mis avab [**lehe Olemid**](entities.md), või [eksportige segment](export-destinations.md).

## <a name="refresh-segments"></a>Segmentide värskendamine

Segmente saab värskendada automaatse ajakava alusel või soovi korral käsitsi värskendada. Ühe või mitme segmendi käsitsi värskendamiseks valige need ja valige **Värskenda**.

Automaatse värskendamise ajastamiseks [minge jaotisse](schedule-refresh.md) Haldussüsteemi **·** > **ajakava** > **.** Kehtivad järgmised reeglid:

- Kõiki segmente, mille tüüp **on Dünaamiline** või **Laiendus**, värskendatakse automaatselt määratud sagedusega. Kui värskendamine on lõpule jõudnud, näitab olek **,** kas segmendi värskendamisel esines probleeme. Viimati **värskendatud** näitab viimase eduka värskendamise ajatemplit. Tõrke ilmnemisel valige tõrge, et näha juhtunu üksikasju.
- Segmendid tüübiga **Staatiline** *ei* värskendata automaatselt. Viimati **värskendatud** kuvab ajatempli viimasest korrast, millal staatiline segment käsitsi käitati või värskendati.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Ekspordi segmendid

Eksportige segmente teistesse rakendustesse andmete edasiseks kasutamiseks. Eksportige segment segmendilehelt või [ekspordilehelt](export-destinations.md).

1. Minge **lehele Segmendid** ja valige segment, mida soovite eksportida.

1. Valige **Ekspordi haldamine**. Avaneb **Segmendi ekspordid (eelvaade)** leht. Saate vaadata kõiki konfigureeritud ekspordiid rühmitatuna selle järgi, kas need sisaldavad praegust segmenti või mitte.

   1. Valitud segmendi lisamiseks eksporti **Redigeerige** vastavat eksporti, et valida vastav segment, seejärel salvestage. Üksikklientidele mõeldud keskkondades valige loendist eksport ja valige **sama tulemuse saavutamiseks Lisa segment**.

   1. Valitud segmendiga uue ekspordi loomiseks valige **Lisa eksport**. Lisateavet ekspordi loomise kohta leiate teemast [Uue ekspordi häälestamine](export-destinations.md#set-up-a-new-export).

1. Segmentide põhilehele naasmiseks klõpsake nuppu **Tagasi**.

## <a name="track-usage-of-a-segment"></a>Segmendi kasutamine rööbasteel

Kui kasutate segmente rakendustes, mis põhinevad samal Microsoft Dataverse organisatsioonil, mis on seotud Customer Insightsiga, saate segmendi kasutamist jälgida. Rakenduse Dynamics 365 Marketing [klienditeekondades kasutatavate Customer Insightsi segmentide puhul](/dynamics365/marketing/real-time-marketing-ci-profile) teavitab süsteem teid selle segmendi kasutamisest.

Customer Insightsi keskkonnas kasutatava segmendi redigeerimisel või rakenduse Marketing klienditeekond teavitab segmendikoostaja [bänner](segment-builder.md) teid sõltuvustest. Kontrollige sõltuvuse üksikasju otse bännerilt või valides **segmendiehitajas käsu Kasutus**.

**Segmendi kasutamise** paanil kuvatakse üksikasjad selle segmendi kasutamise kohta põhistes rakendustes Dataverse. Klienditeekondades kasutatavate segmentide puhul leiate lingi teekonna kontrollimiseks rakendusest Marketing, kus seda segmenti kasutatakse. Kui teil on rakendusele Marketing juurdepääsu luba, vaadake seal lisateavet.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Külgpaneel segmendi kasutamise üksikasjadega segmendikoostajas.":::

Süsteem teavitab teid jälgitava segmendi kasutamisest, kui proovite seda kustutada. Kui segmenti, mille kavatsete kustutada, kasutatakse rakenduse Marketing klienditeekond, peatub see teekond kõigi segmendi kasutajate jaoks. Kui teekond on osa turunduskampaaniast, mõjutab kustutamine seda kampaaniat ennast. Vaatamata hoiatustele saate segmendi siiski kustutada.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Dialoogiboks segmendi kustutamise kinnitamiseks, kui rakenduses kasutatakse segmenti Dataverse .":::

### <a name="supported-apps"></a>Toetatud rakendused

Kasutust jälgitakse praegu järgmistes Dataverse põhistes rakendustes.

- [Klienditeekonnad rakenduses Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
