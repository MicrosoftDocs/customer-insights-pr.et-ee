---
title: Sarnaste klientide leidmine tehisintellektiga (sisaldab videot)
description: Leidke tehisintellekti abil sarnaseid kliendi segmente.
ms.date: 06/25/2020
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 5626b980ad8802aae9657052e3ca51a70c49baf9
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355240"
---
# <a name="similar-customers-preview"></a>Sarnased kliendid (eelversioon)

See funktsioon võimaldab tehisintellekti kasutades leida teie kliendibaasist sarnaseid kliente. Selle funktsiooni kasutamiseks peab teil olema loodud vähemalt üks segment. Olemasoleva segmendi kriteeriumide laiendamine aitab leida sellele segmendile sarnaseid kliente.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Sarnaste klientide leidmine* kasutab automatiseeritud vahendeid andmete hindamiseks ja andmete põhjal prognooside tegemiseks ning seega saab seda kasutada ka profiilimismeetodina, nagu see mõiste on isikuandmete kaitse üldmääruses (GDPR) määratletud. Kui klient seda funktsiooni andmete töötlemiseks kasutab, võivad kohalduda GDPR või muud seadused ja määrused. Teie vastutate selle eest, et Dynamics 365 Customer Insightsi kasutades (sh prognoose kasutades) järgite te kõiki kohaldatavaid seadusi ja määrusi, sh eraelu puutumatuse, isikuandmete, biomeetriliste andmete, andmekaitse ja suhtluse konfidentsiaalsusega seotud seadusi.

## <a name="finding-similar-customers"></a>Sarnaste klientide leidmine

1. Minge sihtrühmaülevaadetes jaotisse **Segmendid** ja valige segment, mille põhjal soovite uue segmendi luua. See on teie *lähtesegment*.

1. Valige tegevusribal **Leia sarnased kliendid**.

1. Vaadake uue segmendi jaoks soovitatud nimi üle ja muutke vajaduse korral seda.

1. Vaadake üle väljad, mis teie uue segmendi määratlevad. Need väljad määratlevad aluse, mille põhjal süsteem proovib leida teie lähtesegmendile sarnaseid kliente. Süsteem valib vaikimisi soovitatavad väljad.
  Väljad, mis võivad mudeli jõudlust oluliselt vähendada, jäetakse automaatselt kõrvale.
  
   - Järgmiste andmetüüpidega väljad: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Väljad, mille kardinaalsus (välja elementide arv) on alla 2 või üle 30

1. Valige, kas soovite kaasata uude segmenti **kõik kliendid** või ainult **kindlas olemasolevas segmendis** olevad kliendid.

1. Välistage lähtesegmendis olevad kliendid, valides märkeruudu **Välista kõik lähtesegmendis olijad**.

1. Vaikimisi soovitab süsteem väljundisse kaasata vaid 20% sihtrühma suurusest. Redigeerige seda lävendit vastavalt vajadusele. Lävendi suurendamine vähendab täpsust.

1. Valige lehe allosas käsk **Käivita**, et käivitada kahendliigituse ülesanne (masinõppe meetod), mis analüüsib andmekomplekti.

## <a name="view-the-similar-segment"></a>Sarnase segmendi vaatamine

Pärast sarnase segmendi töötlemist näete uut segmenti loetletuna lehel **Segmendid**.

> [!div class="mx-imgBorder"]
> ![Sarnaste klientide segmendid.](media/expanded-segment.png "Sarnaste klientide segmendid")

Segmendi üksikasjade avamiseks valige tegevusribal käsk **Vaade**. See vaade sisaldab teavet tulemi jaotuse kohta [sarnasuse skooride lõikes](#about-similarity-scores). Sarnasuse skoori väärtused leiate ka suvandis **Segmendi liikmete eelvaade**.

## <a name="use-the-output-of-a-similar-segment"></a>Sarnase segmendi väljundi kasutamine

Saate [sarnase segmendi väljundiga töötada](segments.md) samamoodi kui teiste segmentidega. Näiteks eksportida segmendi või luua meetme.

## <a name="refresh-and-edit-a-similar-segment"></a>Sarnaste segmentide lähtestamine ja redigeerimine

Sarnase segmendi värskendamiseks valige see lehel **Segmendid** ja valige tegevusribal nupp **Värskenda**.

Sarnase segmendi redigeerimine töötleb teie andmeid uuesti. Varem loodud segmenti värskendatakse uuendatud andmetega.    
Sarnase segmendi redigeerimiseks valige see lehel **Segmendid** ja valige tegevusribal nupp **Redigeeri**. Rakendage muudatused ja valige töötlemise käivitamiseks käsk **Käivita**.

## <a name="delete-a-similar-segment"></a>Sarnase segmendi kustutamine

Valige segment lehel **Segmendid** ja valige tegevusribal nupp **Kustuta**. Seejärel kinnitage oma kustutamine.

## <a name="about-similarity-scores"></a>Sarnasuse skoori teave

Kahendliigituse masinõppemudel määrav sarnases segmendis olevatele klientidele skoori. Skoor põhineb sarnasusel lähtesegmendis olevate klientidega.

- Sarnasuse skoor alla 0,55 on kliendid, kelle süsteem liigitab kui lähtesegmendis olevate klientidega *mitte sarnased*
- Sarnasuse skoorid vahemikus 0,55–0,7 liigitatakse *mõnevõrra sarnaseks*
- Sarnasuse skoorid vahemikus 0,7–0,85 liigitatakse *sarnaseks*
- Sarnasuse skoorid vahemikus 0,85–1 on kliendid, kelle süsteem liigitas kui *väga sarnased*

Kliente sarnasuse skooriga alla 0,4 ei kaasata mudeli väljundisse. Süsteem ei pea neid lähtesegmendiga piisavalt sarnaseks.


[!INCLUDE[footer-include](../includes/footer-banner.md)]