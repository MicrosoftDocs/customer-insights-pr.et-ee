---
title: Dimensioonide kuvamine ja loomine
description: Dimensioonide loomine, redigeerimine ja kustutamine.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 136da1e1265c7087d861712d34d011b09cb60ad5
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623627"
---
# <a name="view-and-create-dimensions"></a>Dimensioonide kuvamine ja loomine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dimensioon on sündmuse atribuut, mis võib andmeid kirjeldada, filtreerida või rühmitada. Kui korraldate oma veebisaidil turunduspakkumist, saate dimensioonide abil külastajaid sortida uute ja tagasipöörduvate kasutajate järgi.  

Kaasamisülevaateid sisaldab sündmuse atribuutide karbist-välja (OOB) dimensioone. Allpool on mõned näited.

- Brauseri nimi
- Lehe nimi
- Seadme mudel
- Operatsioonisüsteem
- Riik/regioon

## <a name="view-dimensions"></a>Kuva dimensioonid

Dimensioonid põhinevad olemasolevatel sündmuse atribuutidel. Kaasamisülevaadete jälituskoodi kasutamisel luuakse süsteemiliide automaatselt.

1. Valige vasakpoolsel navigeerimispaanil suvand **Andmed**. 
1. Tööruumi kõigi dimensioonid loendi kuvamiseks valige **Dimensioonid**. 
   > [!NOTE]
   > Süsteemi genereeritud dimensioonid on kirjutuskaitstud. Saate neid redigeerida. Kohandatud dimensioone saab ainult luua ja redigeerida.

## <a name="create-a-dimension"></a>Dimensiooni loomine

Lisaks süsteemi genereeritud dimensioonidele saavad keskkonna- ja tööruumi administraatorid luua kohandatud dimensioone. Kohandatud dimensioonid põhinevad baassündmuste vaikeaatribuutidel või saavad kasutada [sündmuse kohandatud atribuute](advanced-SDK-implementation.md).

1. Minge **Andmed** > **Dimensioonid**.
1. Valige **Uus dimensioon**.

   :::image type="content" source="media/add-dimension.png" alt-text="Sündmusele dimensiooni lisamine.":::

1. Valige paanil **Loo dimensioon** soovitud atribuut, mille alusel saab dimensiooni luua. Atribuutide loendis kuvatakse kõik tööruumi atribuudid, mis pole dimensioonile määratud.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Uue dimensiooni loomine.":::
      
3. Sisestage **Kuva nimi** väljale. Soovi korral saate lisada **Kirjelduse**.
4. Dimensiooni salvestamiseks valige **Loo**. See võib võtta kuni ühe minuti, enne kui saate [kohandatud aruandes](custom-reports.md) või [segmendis](segments.md) kasutada dimensiooni. 

## <a name="edit-a-dimension"></a>Dimensiooni redigeerimine

Saate muuta dimensiooni nime ja kirjeldust. Redigeerida saate ainult kasutaja loodud mõõtmeid, kuid süsteemi mõõtmeid te redigeerida ei saa.


1. Minge **Andmed** > **Dimensioonid**.
1. Valige dimensioon, mille soovite kustutada.
1. Dimensiooni värskendage paanil **Redigeeri dimensiooni**.
1. Muudatuste salvestamiseks valige nupp **Rakenda**.

## <a name="delete-a-dimension"></a>Kustuta dimensioon

Saate kustutada ainult kasutaja loodud dimensioone, kuid te ei saa eemaldada süsteemi dimensioone.

Dimensiooni kustutamine on jääv. Kustutatud dimensiooni kasutavad aruanded ja segmendid ei tööta enam. 

1. Minge **Andmed** > **Dimensioonid**.
1. Valige dimensioon, mille soovite kustutada.
1. Valige paanil **Redigeeri dimensiooni** suvand **Kustuta dimensioon**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Sündmuse dimensiooni kustutamine.":::

1. Kustutamise kinnitamiseks sisestage **KINNITA KUSTUTAMINE** (suurtähtedega). 
1. Valige **Kustuta**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
