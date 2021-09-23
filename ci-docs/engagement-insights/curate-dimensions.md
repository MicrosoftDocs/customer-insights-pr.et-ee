---
title: Demograafiliste sihtide kasutamine käitumusliku teabe tükeldamiseks (kureeritud mõõtmed)
description: Kasutage ühtset profiili kureeritud mõõtmeid, et lubada vaatajaskonna statistika kliendiprofiili atribuute.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a3d7f9276330a6daacbe9428d84a371b81bbefe
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466343"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Demograafiliste sihtide kasutamine käitumusliku teabe tükeldamiseks

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Kasutades ühtseid profiili demograafilisi mõõtmeid, saavad kaasamisstatistika kasutajad juurdepääsu vaatajaskonna statistika profiili atribuutidele. Seejärel saate neid atribuute kasutada käitumisandmete, sealhulgas veebisaidi või mobiilirakenduse seotusteabe kogutud andmete interaktiivses analüüsis.

>[!NOTE]
> Kaasamisülevaateid sisaldab sündmuse atribuutide "karbist-väljad" dimensioone. Lisateave: [Mõõtmete kuvamine ja loomine](dimensions.md)

## <a name="prerequisite"></a>Eeltingimus

- Kaasamisülevaadete keskkond, kus teil on kliendiprofiili andmed lingitud vaatajaskonna statistika keskkonnaga, kus kliendiprofiilid luuakse. Lisateave: [Sihtrühma ülevaadete ja kaasamisülevaadete vahelise lingi loomine](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Pärast sihtrühma ülevaadete ja kaasamisstatistika keskkondade vahelise lingi loomist vajate ainult kliendiprofiili atribuutide kohta spetsiifilisi andmeid, mis võivad olla kasulikud kaasamisstatistika mõõtmetena. Lisateavet leiate teemast [Sihtrühma ülevaadete ühendatud profiilide atribuutide ja segmentide lubamine](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>Uue kohandatud aruande loomine

1. Valige vasakpoolsel paanil **Kohandatud** > **Uus aruanne** ja seejärel soovitud mõõdik. (Selle näite puhul valisime **Lehevaated tunni kaupa**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Valige mõõdik.":::

2. Valige visualiseerimisredaktoris **Mõõtmed** ja seejärel **Demograafiline** rippmenüüst **Mõõdiku tüüp**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Valige demograafiline.":::

3. Valige mõõdik **Signal.Customer.*xxx***. (Selles näites on kuvatud Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Valige mõõt.":::
  
## <a name="limitations"></a>Piirangud

Hetkel saate kasutada ainult demograafiliste sihtide käitumusliku teabe tükeldamist.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
