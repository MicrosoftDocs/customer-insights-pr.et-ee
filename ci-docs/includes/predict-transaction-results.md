---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611124"
---
- **Koolitusmudeli toimivus**: hinded A, B või C näitavad prognoos toimivust ja aitavad teil teha otsuse väljundolemisse salvestatud tulemuste kasutamise kohta.

  Astmed määratletakse vastavalt järgmistele reeglitele.
  - **A**, kui vähemalt 50% kõikidest prognoosidest olid täpsed ja kui täpsete loobunud klientide prognooside protsent on alusmäärast vähemalt 10% suurem.
  - **B**, kui vähemalt 50% kõikidest prognoosidest olid täpsed ja kui täpsete loobunud klientide prognooside protsent on alusmäärast kuni 10% suurem.
  - **C**, kui mudel ennustas täpselt vähem kui 50% koguprognoosidest või kui täpsete prognooside protsent klientide kohta, kes sõitsid, on väiksem kui võrdlusalus.
  - **Baseline** võtab mudeli jaoks prognoos ajaakna sisendi (näiteks üks aasta) ja loob erinevad ajaosad, jagades selle 2-ga, kuni see jõuab ühe kuuni või vähem. Mudel kasutab neid ajalõike, et luua ärireegel klientidele, kes pole selles ajavahemikus oste teinud. Need kliendid loetakse loobunuks. Baasmudeliks valitakse ajapõhine ärireegel, millel on kõige suurem võime ennustada, kes tõenäoliselt kükitab.

- **Voolavuse tõenäosus (klientide arv)**: Kliendirühmad nende prognoositud voolavuse riski põhjal. Valikuliselt [looge kõrge riskiga klientide](../prediction-based-segment.md) segmendid. Sellised segmendid aitavad mõista, kus segmendi liikmelisuse sulgemiskuupäev peaks olema.

- **Kõige mõjukamad tegurid**: Prognoosi loomisel võetakse arvesse paljusid tegureid. Mudeli loodavate koondprognooside jaoks arvutatakse iga teguri olulisus. Kasutage neid tegureid oma prognoos tulemuste valideerimiseks. Või kasutage seda teavet hiljem segmentide [loomiseks](../prediction-based-segment.md), mis võivad aidata mõjutada klientide riski.