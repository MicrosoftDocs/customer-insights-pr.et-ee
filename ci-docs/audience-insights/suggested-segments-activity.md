---
title: Tegevusepõhised segmendisoovitused.
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
ms.openlocfilehash: 9c10a32b770ea110a1166f20f72116a3a12cb92e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354458"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Soovitatud segmendid, mis põhinevad tegevusandmetel (eelvaade)

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
Kui olete tervishoiuteenuseid pakkuv ettevõte pakkudes avalikku terviseteenust ja teie eesmärk on minimeerida individuaalsete patsientide kulutusi. Selleks võib vähendada korduvaid külastusi, pakkudes võimalikult palju hooldust võimalikult väheste külastuste korral. Sel juhul on teie eesmärk hoida külastussagedus madal ja minimeerida korduvaid kulusid patsiendile. Võite ka tuvastada patsientide segmente, kellel on sagedased külastused ja kõrged korduvad kulud ning analüüsida neid juhtumeid, et parandada üksikisiku ravimist. 

## <a name="required-data"></a>Nõutavad andmed

Soovitused luuakse valitud sisestusandmete põhjal. 

- Kliendiprofiilid: Kõik kindla segmendi kliendid või liikmed. 

- Ajaperiood: Eelmine kuu, eelmine aasta või mis tahes kohandatud ajaperiood.

- Tegevuse tüüp: ostud, jaetehingud, veebitehingud, klienditoe teenindusjuhtumid, kordustellimused jne.  

- Customer Insights /i olem, mis sisaldab tegevuse andmeid: Olem UnifiedActivity või konkreetse tegevuse olem. 

- Sisalduvad dimensioonid: Hiljutisus, sagedus või rahaline dimensioon vastavalt teie äri nõuetele.

## <a name="generate-suggested-segments"></a>Soovitatud segmentide genereerimine

1. Liikuge jaotisse **Segmendid**.

1. Valige vahekaart **Soovitused (eelvaade)**.

1. Valige **Otsi uusi soovitusi** ja valige või **Kliendi käitumise kuvamine või prognoosimine**. Valige **Alusta** juhitava kogemuse käivitamiseks.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Konfiguratsiooniviisardi esimene etapp tegevuse põhjal soovitatud segmendi jaoks.":::

1. Sisestage nõutavad sisestusandmed ja valige **Edasi**.

   - Klientide valik: Kaasa kõik kliendid või mõni kindel segment.
   - Valige tegevus: Valige tegevuse tüüp ja tegevust kirjeldavad olemid.
   - Eelistused: Määrake arvestav ajaperiood, soovituste tegurid ja vastendage atribuudid.

1. Vaadake sisestatud andmed läbi ja valige siis mudeli käivitamiseks ning soovituste genereerimiseks käsk **Käivita**.

1. Sõltuvalt kliendiprofiilide arvust ja valitud tegevustest võib lõpuleviimiseks aega võtta mõni minut. 

Pärast soovituste genereerimist saate neid filtreerida soovitud osa või väärtuse alusel, mis teile kõige rohkem huvi huvi tekitas. 

## <a name="view-details-of-a-suggested-segment"></a>Vaadake soovitatud segmendi üksikasju

Kui soovitused on loodud, leiate need **Segmendid** > **Soovitused (eelvaade)** jaotisest **Tegevuspõhised soovitused** .

:::image type="content" source="media/suggested-segments-details.png" alt-text="Laiendatud külgpaan, kus kuvatakse soovitatud segmendi üksikasjalikud andmed.":::

Valige **Kuva soovitused** segmendi üksikasjade vaatamiseks soovitatud segmendisoovitus. Kõrvalpaanil on esitatud üksikasjad, nagu iga dimensiooni ulatus sihtrühmaga võrreldes. Aruandes tuuakse esile ka segmenti potentsiaalsete liikmete arv ja vastav protsent klientide koguarvutest. Kui soovite soovituse säilitada segmendina, valige **Loo segment**.    

## <a name="save-a-suggestion-as-a-segment"></a>Salvestage soovitus segmendina

1. Minge jaotisesse **Segmendid** > **Soovitused (eelvaade)**.

1. Valige segment, mille soovite salvestada. 

1. Valige külgpaanil käsk **Loo segment**. 

1. Pärast segmendi salvestamist kuvatakse see segmentide loendis vahekaardil **Kõik segmendid**. Seda saab nüüd [värskendada või kustutada nagu mis tahes muud segmenti](segments.md). Segmendi üksikasju ei saa redigeerida. Siiski saate muuta soovituste sisestuskriteeriume ja luua erinevaid soovitusi.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Värskendage või muutke soovituste komplekti

1. Minge **Segmendid** > **Soovitused (eelvaade)** ja otsige segmenti jaotisest **Tegevusepõhised soovitused** .

1. Valige suvand **Värskenda soovitused**, et värskendada soovitusi konfigureeritud atribuutide säilitamise ajal. Või valige **Redigeerige soovitusi** konfigureeritud atribuutide muutmiseks. Süsteem käivitab protsessi uuesti, loob viimaste andmete põhjal segmendisoovitused ja asendab praegused soovitused.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
