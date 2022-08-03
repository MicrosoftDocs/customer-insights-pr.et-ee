---
title: Sarnaste klientide leidmine tehisintellekti abil (eelvaade) (sisaldab videot)
description: Leidke tehisintellekti abil sarnaseid kliendi segmente.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170722"
---
# <a name="find-similar-customers-with-ai-preview"></a>Sarnaste klientide leidmine tehisintellekti abil (eelvaade)

Leidke tehisintellekti kasutades oma kliendibaasist sarnaseid kliente. Selle funktsiooni kasutamiseks on vaja luua vähemalt üks segment. Olemasoleva segmendi kriteeriumide laiendamine aitab leida kliente, kes on selle segmendiga sarnased.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Sarnaste klientide* leidmine kasutab andmete hindamiseks ja nende põhjal prognooside tegemiseks automatiseeritud vahendeid. Seetõttu on seda võimalik kasutada profiilianalüüsi meetodina, kuna see mõiste on määratletud isikuandmete kaitse üldmääruses ("GDPR"). Kui klient seda funktsiooni andmete töötlemiseks kasutab, võivad kohalduda GDPR või muud seadused ja määrused. Teie vastutate selle eest, et Dynamics 365 Customer Insightsi kasutades (sh prognoose kasutades) järgite te kõiki kohaldatavaid seadusi ja määrusi, sh eraelu puutumatuse, isikuandmete, biomeetriliste andmete, andmekaitse ja suhtluse konfidentsiaalsusega seotud seadusi.

## <a name="find-similar-customers"></a>Leia sarnased kliendid

1. Minge jaotisse **Segmendid** ja valige segment, millele soovite oma uue segmendi rajada. See on teie *lähtesegment*.

1. Valige **Otsi sarnaseid kliente**.

1. Vaadake uue segmendi jaoks soovitatud nimi üle ja muutke vajaduse korral seda.

1. Soovi korral lisage [uuele segmendile silte](work-with-tags-columns.md#manage-tags).

1. Vaadake üle väljad, mis teie uue segmendi määratlevad. Need väljad määratlevad aluse, mille põhjal süsteem proovib leida teie lähtesegmendile sarnaseid kliente. Süsteem valib vaikimisi soovitatavad väljad. Vajadusel lisage veel välju.
  Väljad, mis võivad mudeli jõudlust oluliselt vähendada, jäetakse automaatselt kõrvale.
  
   - Järgmiste andmetüüpidega väljad: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Väljad, mille kardinaalsus (välja elementide arv) on alla 2 või üle 30

1. Valige, kas soovite kaasata **kõik kliendid**, välja arvatud lähtesegment või ainult teises segmendis **olevad** kliendid uues segmendis.

1. Vaikimisi soovitab süsteem väljundisse kaasata vaid 20% sihtrühma suurusest. Redigeerige seda lävendit vastavalt vajadusele. Lävendi suurendamine vähendab täpsust.

1. Kaasake kliendid oma lähtesegmenti, **märkides ruudu Kaasa liikmeid lähtesegmendist lisaks sarnaste atribuutidega** klientidele.

1. Valige **lehe allosas käsk Käivita**, et alustada [binaarset klassifitseerimisülesannet](#about-similarity-scores) (Masinõpe meetod), mis analüüsib andmekogumit.

## <a name="view-the-similar-segment"></a>Sarnase segmendi vaatamine

Pärast sarnase segmendi töötlemist leiate uue segmendi lehelt **Segmendid** tüübiga **Laiendus**.

Valige **Vaade**, et näha tulemuste jaotust [sarnasuse skooride ja sarnasuse](#about-similarity-scores) skoori väärtuste vahel jaotises **Segmenti liikmete eelvaade**.

:::image type="content" source="media/expanded-segment.png" alt-text="Sarnaste klientide segmendid.":::

## <a name="manage-a-similar-segment"></a>Sarnase segmendi haldamine

[Töötage sarnase segmendiga](segments.md#manage-existing-segments) ja hallake seda teiste segmentidega. Näiteks eksportida segmendi või luua meetme.

Redigeerige, värskendage, nimetage ümber, laadige alla ja kustutage sarnane segment. Sarnase segmendi redigeerimine töötleb teie andmed ümber. Varem loodud segmenti värskendatakse uuendatud andmetega.

## <a name="about-similarity-scores"></a>Sarnasuse skoori teave

Kahendliigituse masinõppemudel määrav sarnases segmendis olevatele klientidele skoori. Skoor põhineb sarnasusel lähtesegmendis olevate klientidega.

- Sarnasuse skoor alla 0,55 on kliendid, kelle süsteem liigitab kui lähtesegmendis olevate klientidega *mitte sarnased*
- Sarnasuse skoorid vahemikus 0,55–0,7 liigitatakse *mõnevõrra sarnaseks*
- Sarnasuse skoorid vahemikus 0,7–0,85 liigitatakse *sarnaseks*
- Sarnasuse skoorid vahemikus 0,85–1 on kliendid, kelle süsteem liigitas kui *väga sarnased*

Kliente sarnasuse skooriga alla 0,4 ei kaasata mudeli väljundisse. Süsteem ei pea neid lähtesegmendiga piisavalt sarnaseks.

[!INCLUDE [footer-include](includes/footer-banner.md)]
