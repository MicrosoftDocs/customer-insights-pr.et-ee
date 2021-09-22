---
title: Segmentide kuvamine ja loomine
description: Segmentide loomine, redigeerimine, kustutamine ja kasutamine.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036143"
---
# <a name="view-and-create-segments"></a>Segmentide kuvamine ja loomine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Segmentide abil saate tuvastada külastaja alamhulki, võttes aluseks tunnused või veebisaidi suhtlused. Segmentide abil saate rakendada filtreid ja analüüsida neid alamhulki. See analüüs võib aidata teil ettevõtte trende uurida ja neile reageerida. 

:::image type="content" source="media/segments-page.png" alt-text="Kaasamisülevaadete rakenduse kuvatõmmis, mis näitab tööruumi olemasolevate segmentide loendit.":::

## <a name="view-segments"></a>Kuva segmendid

1. Valige vasakpoolsel navigeerimispaanil suvand **Andmed**. 

1. Tööruumi kõigi segmentide loendi saamiseks valige vahekaart **Segmendid**. 

## <a name="create-a-segment"></a>Loo segment

Segmendid koosnevad reeglitest ja tingimustest, mis on seotud loogikatehtetega. Tingimused rakendavad valitud dimensioonile filtrid. Iga segment saab kasutada kuni viit dimensiooni.

Järgmises näites on toodud ühe reegli kahe tingimustega segment. See filtreerib kõik veebisaidi sündmused, kus brauser on Chrome ja operatsioonisüsteemid on iOS või Android.

:::image type="content" source="media/segment-sample.png" alt-text="Näidissegmendid, mille puhul on veebisaidisündmuste filtreerimiseks reeglis kaks tingimust.":::

Selles jaotises kirjeldatakse, kuidas luua *tühja segmenti*.

1. Mine **Andmed** > **Segmendid**.

1. Valige **Uus segment**.

1. Valige **ressursiteegis** atribuut, mille alusel soovite filtreerida. Praegu saate luua segmente ainult dimensioonide alusel.

1. Valige valitud atribuudi tehtemärk ja väärtus. Toetatud on järgmised toimingud.
   - **on**: väärtuste kaasamiseks on vaja täpset vastet. Kasutab ühe väärtuse jaoks **võrdne** või mitme väärtuse lisamiseks **ükskõik millisest**.
   - **ei ole**: väärtuste välistamiseks on vaja täpset vastet. Kasutab ühe väärtuse jaoks **võrdne** või mitme väärtuse lisamiseks **ükskõik millisest**.
   - **algab sõnega**: sõne, millega vastavad väärtused algavad.
   - **lõppeb sõnega**: sõne, millega vastavad väärtused lõppevad.
   - **sisaldab**: sõne, mis sisaldub kattuvates väärtustes.

1. Rühmale täiendavate tingimuste lisamiseks saate kasutada kaht loogikatehet. Prognoositud atribuudid on teguriks seatud kasutades tehete kogumeid.
   - **AND** tehtemärk: mõlemad tingimused tuleb täita segmenteerimise võimaldamiseks. See valik on kõige kasulikum juhul, kui määratlete eri olemite tingimusi.
   - **VÕI** tehtemärk: üks tingimus tuleb täita segmenteerimise võimaldamiseks. See valik on kõige kasulikum juhul, kui määratlete sama olemi mitu tingimusi.

1. Sisestage segmendi nimi ja valige **Salvesta**. 

Segment kuvatakse lehel Segmendid ja saate seda rakendada kõigile tööruumi aruannetele ja lehtritele.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Aruande segmendi või lehtri kasutamine

Segmente saate rakendada aruandele või lehtrile, et neid segmentide tingimuste alusel filtreerida. Segmente ei saa aga reaalaja kasutusaruandele rakendada.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Lehevaadete aruanne laiendatud ripploendiga, mille abil saate valida, millised segmendid rakendada.":::

Segmendi rakendamiseks avage aruanne või lehter. Valige **Lisa tingimus** ja seejärel **Filtreeri segmentide alusel**. Valige loendist segment, mida soovite rakendada. Segment rakendatakse aruandele. Kui diagramm ei toeta segmenti, kuvatakse selles tõrge.
 
Aruandele või lehtrile saate rakendada *kuni kolm segmenti*.

## <a name="edit-a-segment"></a>Segmendi redigeerimine

1. Mine **Andmed** > **Segmendid**.
1. Valige selle avamiseks loendist segment. 
1. Muutke või lisage väärtused vastavalt vajadusele.
1. Vajutage nuppu **Salvesta**, et muudatused rakendada.

## <a name="change-the-name-of-a-segment"></a>Muutke segmendi nimi

1. Mine **Andmed** > **Segmendid**.
1. Valige segmendiloendist **Veel [...]**. 
1. Valige ripploendist **Redigeeri nimi**.
1. Sisestage uus nimi ja valige **Nimeta ümber**.

## <a name="delete-a-segment"></a>Kustuta segment

1. Mine **Andmed** > **Segmendid**.
1. Valige segmendiloendist **Veel [...]**. 
1. Valige ripploendist **Kustuta**.
1. Kinnitamiseks valige **Kustuta**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
