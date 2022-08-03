---
title: Segmendi ülevaated (eelversioon)
description: Vaadake ülevaadet olemasolevate segmentide kohta, et näha erinevusi ja sarnasusi.
ms.date: 06/10/2020
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-insights
- customerInsights
ms.openlocfilehash: ccb33594a3a92e87d307f3300c77772ef8b4a82f
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170998"
---
# <a name="segment-insights-preview"></a>Segmendi ülevaated (eelversioon)

Tutvuge lisateabega ja ülevaadetega olemasolevate segmentide kohta. Saage teada, mis on kahe segmendi puhul erinev või mis on neil ühist.

## <a name="segment-overlap"></a>Segmendi kattumine

Segmendi kattumise analüüs näitab, kui paljudel ja millistel klientidel on kaks või rohkem ühist segmenti. Näiteks kuidas sagedaste klientide segment kattub segmendiga, mis sisaldab kliente, kes on teie teenuse või tootega rahul.
Lisaks saate analüüsida, kuidas kattumine teatud atribuute muudab.

### <a name="run-an-overlap-analysis"></a>Kattumise analüüsi käitamine

1. Avage **Segmendid** ja valige vahekaart **Ülevaated (eelversioon)**.

1. Valige **Uus** ja valige suvand **Kattumine** paanil **Ülevaate tüübi valimine**.

1. Valige huvipakkuvad segmendid ja valige **Edasi**.

1. Soovi korral võite valida ühe või mitu huvipakkuvat välja, et analüüsida iga võimaliku välja väärtuse kattumist, ja valige **Edasi**.

1. Sisestage kattumise analüüsi nimi, valikuline kuvatav nimi ja kirjeldus.

1. Analüüsi käivitamiseks valige **Salvesta**. Kattumise analüüs on valmis, kui olek muutub valikust Värskendab valikule Õnnestus.

### <a name="view-and-optimize-an-overlap-analysis"></a>Kattumise analüüsi vaatamine ja optimeerimine

1. Pärast analüüsi lõpetamist näete selle ülevaate kohta üksikasju suvandis **Segmendid** > **Ülevaated (eelversioon)**.

   :::image type="content" source="media/segment-overlap.png" alt-text="Segmendi kattumise ülevaate üksikasjad.":::

1. Analüüsi tulemuste nägemiseks valige ülevaade.

   - Liikmete arv, kelle segmendid valitud analüüsis kattuvad.
   - Liikmete arv, mis sisaldub ühes segmendis, kuid mitte teistes segmentides.
   - Kui valisite kattuva analüüsi konfigureerimisel väljad, leiate need vastavatelt vahekaartidelt. Filtri ripploendi abil saate valida mis tahes atribuudi huvitaseme ja allservas olevas tabelis kuvatakse vastavad andmed.

## <a name="segment-differentiators"></a>Segmendidiferentseerijad

Segmentide eristajad aitavad teil selgitada välja, mis eristab segmenti teistest klientidest või teisest segmendist. Valige segment ja süsteem tuvastab profiili atribuudid ja mõõdud, mis eristavad valitud segmenti.

### <a name="run-a-differentiator-analysis"></a>Eristajate analüüsi käitamine

1. Avage **Segmendid** ja valige vahekaart **Ülevaated (eelversioon)**.

1. Valige **Uus** ja valige **paanil Valige ülevaate tüüp** suvand **Diferentsaatorid**.

1. Valige segment, mida soovite analüüsida, kui **Primaarne segment** ja valige nupp **Edasi**.

1. Valige **Kõik kliendid** või **Teisene segment**, et oma primaarset segmenti sellega võrrelda, ja valige **Edasi**.

1. Soovi korral võite valida ühe või mitu huvivälja, et keskenduda konkreetsete atribuutide analüüsile, ja valige **Edasi**.

1. Sisestage diferentseerimisanalüüsi nimi, valikuline kuvatav nimi ja kirjeldus.

1. Analüüsi käivitamiseks valige **Salvesta**. Diferentseerimisanalüüs on valmis, kui olek muutub värskendamisest edukaks.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Eristajate analüüsi vaatamine ja otimeerimine

1. Pärast analüüsi lõpuleviimist minge jaotisse **Segmentide** > **ülevaated (eelvaade)**.

   :::image type="content" source="media/segment-differentiators.png" alt-text="Segmendi eristaja ülevaate üksikasjad.":::

1. Analüüsi tulemuste nägemiseks valige ülevaade. Eristaja analüüs hõlmab kahte vahekaarti. Vahekaart **Atribuudid** loetleb profiili atribuudid, mida loetakse eristajateks. Vahekaart **Meetmed** loetleb eristajad. Iga vahekaart sisaldab järgmisi üksikasju.

   - Eristajate järjestatud loendit, mis on erinevuse skoori alusel sorditud.
   - Iga eristaja **Erinevuse skoor**. Erinevuse skoor tähistab atribuudi erinevust kahe segmendi vahel. Mida suurem on erinevuse skoor, seda suurem on kahe segmendi vaheline atribuutide erinevus. Valige skoor, et avada paan **Erinevuse skoor** selle atribuudi eristaja väärtustega.

## <a name="manage-segment-insights"></a>Segmendi ülevaadete haldus

Minge jaotisse **Segmentide** > **statistika (eelvaade),** et vaadata oma segmentide statistikat ja seda hallata. Valige saadaolevate toimingute vaatamiseks segmendiülevaade.

- **Vaadake** ülevaateanalüüsi
- **Ülevaate redigeerimine** selle atribuutide muutmiseks
- **Ülevaate värskendamine** analüüsi uuesti käivitamiseks
- **Ülevaate ümbernimetamine**
- **Ülevaate kustutamine**

[!INCLUDE [footer-include](includes/footer-banner.md)]
