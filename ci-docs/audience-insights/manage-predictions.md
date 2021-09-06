---
title: Jagatud ülesanded prognoosistsenaariumide jaoks
description: Vaadake, kuidas ennustusi hallata, tõrkeotsingut teha ja prognoose määratleda.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: eaccf23a81ca4de19763b761cc5a27c14515fe522ee36dc78f294208b681966e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036460"
---
# <a name="manage-predictions"></a>Prognooside haldamine

Selles artiklis käsitletakse mõningaid toiminguid, mida enamik prognoosistsenaariume jagavad.

## <a name="troubleshoot-a-failed-prediction"></a>Nurjunud prognoosi tõrkeotsing

1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.

1. Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mille tõrkelogisid soovite vaadata.

1. Valige **Logid**.

1. Kõikide tõrgete läbivaatamine. Esineda võib mitmesuguseid tüüpe tõrkeid ja need kirjeldavad, mis olukord selle tõrke tekitad. Näiteks tõrge, et täpse prognoosi tegemiseks pole piisavalt andmeid, lahendatakse tavaliselt täiendavate andmete laadimisel Customer Insightsis.

## <a name="input-data-usability-report"></a>Sisendandmete kasutatavusaruanne

Sisendandmete kasutatavuse aruanne annab konsolideeritud ülevaate tõrgetest ja hoiatustest, mida teie "karbist-väljas" prognoosid võivad tekitada. See annab ka soovitusi, kuidas mudeli tulemuslikkust parandada.

Aruanne on saadaval pärast seda, kui mudel on oma treeninguprotsessi lõpetanud. See luuakse iga mudeli jaoks eraldi, olenemata sellest, kas see on edukalt lõpule viidud või mitte.

### <a name="view-the-input-data-usability-report"></a>Vaata sisendandmete kasutatavusaruannet

Pärast seda, kui "karbist väljas" mudel on läbinud oma koolitusetapi, vaadake aruannet.
- Valige mudeli nime kõrval kolmikpunkt ja valige **Sisendandmete kasutatavuse aruanne**.
- Valige mudeli olek ja valige külgpaanil käsk **Kuva sisendandmete kasutatavuse** aruanne.
- Valige loendist üks mudelitest ja valige käsuribal **Sisendandmete kasutatavuse aruanne**.
- Avage mudeli tulemuste leht ja valige käsuribal **Sisendandmete kasutatavuse aruanne**.

### <a name="information-in-the-input-data-usability-report"></a>Sisendandmete kasutatavusaruande teave

Aruande järgmised veerud sisaldavad kasulikku teavet mudeli andmete täiustamiseks.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Sisendandmete kasutatavuse aruande näide, milles on kuvatud tõrgete, hoiatuste ja soovitustega tabel.":::

- Nimi: tõrke, hoiatuse või soovituse kirjeldav nimi.
- Etapp: mudeli faas, treening või skoor, millele teave viitab.
- Olek: teabe raskusaste (viga, hoiatus, soovitus).
- Veeru nimi: olemi veerg, mida tuleb mudeli jõudluse parandamiseks muuta.
- Oleku nimi: olemi nimi, mida tuleb mudeli jõudluse parandamiseks muuta.
- Üksikasjad: tõrke, hoiatuse või soovituse üksikasjad.

## <a name="refresh-a-prediction"></a>Prognoosi värskendamine

Prognoose värskendatakse automaatselt [teie andmete värskendamiste ajakava](system.md#schedule-tab) järgi, mis on sätetes konfigureeritud. Neid saab värskendada ka käsitsi.

1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.

1. Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mida soovite värskendada.

1. Valige **Värskenda**.

## <a name="delete-a-prediction"></a>Prognoosi kustutamine

Prognoosi kustutamisel eemaldatakse ka selle väljundolem.

1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.

1. Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mida soovite kustutada.

1. Valige **Kustuta**.
