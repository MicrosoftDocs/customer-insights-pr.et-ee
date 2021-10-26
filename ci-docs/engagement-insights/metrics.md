---
title: Mõõdikute kuvamine ja loomine
description: Mõõdikute loomine, redigeerimine ja kustutamine.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 79600a14bc7e98dfd066270f19c353fd007e1341
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623717"
---
# <a name="view-and-create-metrics"></a>Mõõdikute kuvamine ja loomine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Mõõdikud aitavad mõista külastaja käitumist. Nad koondavad sündmuse atribuute ning mõõtvad teie veebis asuvaid andmeid ja jõudlust.  

Oletame, et jooksutate oma veebisaidil turunduskampaaniat. Mõõdiku abil saate jälgida kordumatute külastuste või kasutajate arvu, kes kampaania ajal teie veebisaidile külastavad. Mõõdikute analüüsimine aitab teil oma veebisaidi sihtrühma paremini mõista. Kombineerides [mõõdikuid](dimensions.md) [kohandatud aruandes](custom-reports.md) saate mõõta käitumist, mis aitab teil aidata kasutajaid mõista. Näiteks saate külastajad eraldada uuteks ja tagasipöördumiskategooriatesse, et teha kindlaks rühmade vahelised erinevused huvis ja huvides ja eesmärkides.

## <a name="view-metrics"></a>Mõõdikute kuvamine

Kaasamisülevaated hõlmavad sündmuse atribuutide üldkasutatud koondamist süsteemimõõdikutena. 

- Külastajad
- Külastused
- Lehe vaatamised
- Klõpsamised

Need süsteemimõõdikud põhinevad baassündmuste olemasoleva sündmuse atribuutidel.

1. Valige vasakpoolsel navigeerimispaanil suvand **Andmed**. 
1. Tööruumi kõigi mõõdikute loendi miseks valige vahekaart **Mõõdikud**. 
   > [!NOTE]
   > Süsteemi genereeritud mõõdikud on kirjutuskaitstud. Te ei saa neid muuta ega kustutada. Kohandatud mõõdikuid saab ainult luua ja redigeerida.

## <a name="create-a-metric"></a>Mõõdiku loomine

Keskkond ja tööruumi administraatorid saavad luua mõõdikuid. Sündmuse atribuudid tuleb enne mõõdiku kasutamist tööruumi saata. Saate luua mõõdikuid, mis põhinevad sündmuse atribuutidel, mille on saatnud baassündmused või kasutada veebi SDK-d [kohandatud sündmuse atribuutide saatmiseks](advanced-SDK-implementation.md).

1. Minge **Andmed** > **Mõõdikud**.
1. Valige **Uus mõõdik**, et avada **Ressursside kogu** ja **Uus pealkirjata mõõdiku** dialoog.

   :::image type="content" source="media/new-metric.png" alt-text="Sündmusele mõõdiku lisamine.":::

1. Valige dialoogiboksis **Uus nimetu mõõdik** ripploendist **Vorming** väärtus **Täisarv** või **Kahekordne** andmetüüp. Täisarv on täisarv. Kahekordse väärtuse korral saate valida üks ja kolm kümnendkohta.

   :::image type="content" source="media/create-new-metric.png" alt-text="Uute mõõtmete loomine.":::
   
5. Leidke paanil **Ressursiteek** sündmuse atribuut, mille alusel mõõdik põhineb.
6. Kui soovite seda valemis kasutada, valige atribuudi kõrval **plussmärk (+)**. Saate luua ainult ühe atribuudi põhjal valemi. 
7. Valige üks järgmistest koondfunktsioonidest. 

   - Summa: kõigi väärtuste sümmeetriline summa 
   - Keskmine: kõigi väärtuste keskmine
   - Loendus: väärtuste koguarv
   - Erinev arv: erinevate väärtuste koguarv

   Pärast mõõdiku määratlemist näete mõõdiku viimase tunni tegevuse eelvaadet.

1. Valige **Salvesta**. 
1. Sisestage mõõdiku nimi ja seejärel valige **Salvesta**.

See võib võtta kuni minuti mõõdiku jaoks, enne kui saate seda kasutada [kohandatud aruannete loomiseks](custom-reports.md).

## <a name="edit-a-metric"></a>Mõõdiku redigeerimine

Redigeerida saate ainult kohandatud mõõdikuid.

1. Minge **Andmed** > **Mõõdikud**.
1. Valige mõõdiku loendist.
1. Mõõdiku määratluse muutmine
1. Valige **Salvesta**.

## <a name="change-the-name-of-a-metric"></a>Muudetakse mõõdiku nime

Muuta saate ainult kohandatud mõõdikute nime.

1. Minge **Andmed** > **Mõõdikud**.
1. Valige mõõdiku jaoks väärtus **Veel [...]** ja valige **Redigeeri nime**.
1. Muutke nime. 
1. Valige **Muuda nime**.

## <a name="delete-a-metric"></a>Mõõdiku kustutamine

Kustutada saate ainult kohandatud mõõdikuid.

1. Minge **Andmed** > **Mõõdikud**.
1. Valige mõõdiku jaoks väärtus **Veel [...]** ja valige **Kustuta**.

   :::image type="content" source="media/delete-metric.png" alt-text="Sündmuse mõõdiku kustutamine.":::

1. Valige käsk **Kustuta**, et kinnitada kustutamine.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
