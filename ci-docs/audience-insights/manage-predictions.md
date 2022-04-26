---
title: Jagatud ülesanded prognoosistsenaariumide jaoks
description: Vaadake, kuidas ennustusi hallata, tõrkeotsingut teha ja prognoose määratleda.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8ff8d70ffb8489def072e5d8a6e43d062594141a
ms.sourcegitcommit: 696ad9ab6e10046c00f1ac86a7e8fc37386e6fe7
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/08/2022
ms.locfileid: "8555308"
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

- **Nimi:** vea, hoiatuse või soovituse kirjeldav nimi.
- **Samm:** mudeli faas, rong või skoor, teave viitab.
- **Olek:** Teabe raskusaste (viga, hoiatus, soovitus).
- **Veeru nimi:** olemi veerg, mida tuleb mudeli jõudluse parandamiseks muuta.
- **Olemi nimi:** olemi nimi, mida tuleb mudeli jõudluse parandamiseks muuta.
- **Üksikasjad:** tõrke, hoiatuse või soovituse üksikasjad.

## <a name="refresh-a-prediction"></a>Prognoosi värskendamine

Prognoose värskendatakse automaatselt [teie andmete värskendamiste ajakava](system.md#schedule-tab) järgi, mis on sätetes konfigureeritud. Neid saab värskendada ka käsitsi.

1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.

1. Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mida soovite värskendada.

1. Valige **Värskenda**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Prognoosi kustutamine

Prognoosi kustutamisel eemaldatakse ka selle väljundolem.

1. Minge jaotisse **Ärianalüüs** > **Prognoosid** ja valige vahekaart **Minu prognoosid**.

1. Valige vertikaalne kolmikpunkt selle prognoosi kõrval, mida soovite kustutada.

1. Valige **Kustuta**.
