---
title: Tegevusel põhinevad soovitatud segmendid (eelvaade)
description: Lubage masinaõppel aidata teil leida uusi ja huvitavaid klienditegevusel põhinevaid segmente.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170584"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Tegevusel põhinevad soovitatud segmendid (eelvaade)

Avastage oma klientidele põnevaid segmente, mis põhinevad klienditegevuse andmetel, mis on sisse toodud Customer Insights -i. Tegevuseandmed on näiteks tehingud, kõne kestuse tugi, ostud või tagastamised. Segmentide soovitamiseks analüüsitakse tegevuse andmid toimumise aja, sageduse ja rahalise väärtuse järgi (või kestuse). Samuti saate luua soovitatud [segmente, et parandada mõõtühikut või paremini mõista, mis atribuuti mõjutab](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Vahekaart Soovitatavad segmendid, kus on kuvatud segmendisoovitused tegevuse- ja atribuudipõhiste segmentide kohta.":::

## <a name="categorize-customers-by-activity"></a>Klientide kategoriseerimiseks tegevuste järgi

Koos [tegevusandmete](activities.md) kättesaadavusega Customer Insights -is saame luua soovitusi, mis esindavad kliendirühmi:

- kõige aktiivsemad kliendid 
- Kliendid, kes on teinud kõige rohkem oste 
- Kliendid, kes teenisid tõid rohkem tulu 
- Kliendid, kes pole olnud aktiivsed 
- Kliendid, kes suhtlevad sageli teie ettevõttega  

Kui teil on jaeäri, võite välja uurida, millised kliendid toovad kõige rohkem kasumit ja autasustage neid preemiatega. Samuti võite tuvastada juhuslikke kliente ja pakkuda neile võimalust liituda autasuprogrammiga, et nad külastaksid teie ettevõtet sagedamini.
Kui osutate riiklikke tervishoiuteenuseid ja teie eesmärk on minimeerida üksikute patsientide kulusid, võite proovida vähendada korduvaid visiite, pakkudes parimat võimalikku ravi võimalikult väheste külastustega. Sel juhul on teie eesmärk hoida külastussagedus madal ja minimeerida korduvaid kulusid patsiendile. Võite ka tuvastada patsientide segmente, kellel on sagedased külastused ja kõrged korduvad kulud ning analüüsida neid juhtumeid, et parandada üksikisiku ravimist.

## <a name="required-data"></a>Nõutavad andmed

Soovitused luuakse valitud sisestusandmete põhjal.

- Kliendiprofiilid: Kõik kindla segmendi kliendid või liikmed.

- Ajaperiood: Eelmine kuu, eelmine aasta või mis tahes kohandatud ajaperiood.

- Tegevuse tüüp: ostud, jaetehingud, veebitehingud, klienditoe teenindusjuhtumid, kordustellimused jne.  

- Customer Insights /i olem, mis sisaldab tegevuse andmeid: Olem UnifiedActivity või konkreetse tegevuse olem.

- Sisalduvad dimensioonid: Hiljutisus, sagedus või rahaline dimensioon vastavalt teie äri nõuetele.

## <a name="generate-suggested-segments"></a>Soovitatud segmentide genereerimine

1. Minge jaotisse **Segmendid** ja valige **vahekaart Soovitused (eelvaade).**

1. Valige **Otsi uusi soovitusi** ja valige või **Kliendi käitumise kuvamine või prognoosimine**. Valige **Start**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Konfiguratsiooniviisardi esimene etapp tegevuse põhjal soovitatud segmendi jaoks.":::

1. Sisestage nõutavad sisendandmed ja valige **Edasi**.

   - Klientide valik: Kaasa kõik kliendid või mõni kindel segment.
   - Valige tegevus: Valige tegevuse tüüp ja tegevust kirjeldavad olemid.
   - Eelistused: Määrake arvestav ajaperiood, soovituste tegurid ja vastendage atribuudid.

1. Vaadake sisestatud andmed läbi ja valige siis mudeli käivitamiseks ning soovituste genereerimiseks käsk **Käivita**.

Sõltuvalt kliendiprofiilide arvust ja valitud tegevustest võib lõpuleviimiseks aega võtta mõni minut.

Pärast soovituste genereerimist saate neid filtreerida soovitud osa või väärtuse alusel, mis teile kõige rohkem huvi huvi tekitas.

## <a name="manage-suggested-segments"></a>Soovitatud segmentide haldamine

Minge jaotisse **Segmendid** ja valige **vahekaart Soovitused (eelvaade).** **Valige jaotises Tegevuspõhised soovitused** soovitatud segment saadaolevate toimingute vaatamiseks.

- **Vaadake soovitust**, et vaadata selle segmendi üksikasju, näiteks iga dimensiooni ulatust võrreldes sihtrühmaga. Aruandes tuuakse esile ka segmenti potentsiaalsete liikmete arv ja vastav protsent klientide koguarvutest.
- **Looge segment**, et salvestada soovitatud segmendina. See kuvatakse vahekaardil **Kõik segmendid** ja seda [saab värskendada või kustutada](segments.md). Segmendi üksikasju ei saa redigeerida. Siiski saate muuta soovituste sisestuskriteeriume ja luua erinevaid soovitusi.
- **Redigeerige soovitusi** konfigureeritud atribuutide muutmiseks, mis asendavad praegused soovitused.
- **Värskendage soovitusi** soovituste värskendamiseks, säilitades konfigureeritud atribuudid.

[!INCLUDE [footer-include](includes/footer-banner.md)]
