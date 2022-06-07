---
title: Kuidas – keskkondade haldamine
description: Vaadake, kuidas hallata olemasolevaid Customer Insightsi keskkondi administraatorina."
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833487"
---
# <a name="how-to-manage-environments"></a>Kuidas: Keskkondade haldamine

Administraatorid [loovad](create-environment.md) ja haldavad keskkondi. Nad võivad muuta mõningaid sätteid olemasolevates keskkondades. Äri, tüüp, regioon, salvestusruum ja Dataverse sätted fikseeritakse pärast keskkonna loomist. Kui soovite neid sätteid muuta, lähtestage keskkond või looge uus keskkond.

## <a name="edit-an-existing-environment"></a>Olemasoleva keskkonna redigeerimine

Saate muuta olemasolevate keskkondade teatud üksikasju.

1. Valige rakenduse päises valija **Environment** (Keskkond).

1. Valige ikoon **Edit** (Redigeeri).

   :::image type="content" source="media/edit-environment.png" alt-text="Ikoon keskkonnasätete redigeerimiseks.":::

1. Väljal **Redigeeri keskkonda** saate keskkonnasätteid värskendada.

Värske keskkonna alustamiseks lugege teemat [Uue keskkonna loomine](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Keskkonna omaniku muutmine

Mitmel kasutajal võivad olla administraatoriõigused, kuid keskkonna omanik on ainult üks kasutaja. Vaikimisi loob algselt keskkonna administraator. Keskkonna administraatorina saate määrata omandiõiguse teisele administraatoriõigustega kasutajale.

1. Valige rakenduse päises valija **Environment** (Keskkond).

1. Valige ikoon **Edit** (Redigeeri).

1. Avage väljal **Keskkonna** redigeerimine juhised **Põhiteave**.

1. Valige väljal **Keskkonna** omaniku muutmine keskkonna uus omanik.  

1. Muudatuste rakendamiseks valige **Läbivaatus ja lõpeta**, seejärel **Värskenda**.

## <a name="claim-ownership-of-an-environment"></a>Nõuda keskkonna omandiõigust

Kui omaniku kasutajakonto kustutatakse või peatatakse, ei ole keskkonnal omanikku. Iga administraatori kasutaja saab nõuda omandiõigust ja saada uueks omanikuks. Nad võivad jätkata keskkonna omamist või [omaniku muutmist teisele administraatorile](#change-the-owner-of-an-environment).

Omandiõiguse taotlemiseks valige **nupp Võta omandiõigus**, mis kuvatakse Customer Insightsi iga lehe ülaosas, kui algne omanik organisatsioonist lahkus.

## <a name="reset-an-existing-environment-preview"></a>Olemasoleva keskkonna lähtestamine (eelvaade)

Keskkonna omanikuna saate keskkonna lähtestada tühja olekusse, kui soovite kustutada kõik konfiguratsioonid ja eemaldada allaneelatud andmed.

1. Valige rakenduse päises valija **Environment** (Keskkond).

1. Valige keskkond, mida soovite lähtestada, ja valige vertikaalne kolmikpunkt (&vellip;).

1. Valige suvand **Reset** (Lähtesta).

   :::image type="content" source="media/reset-environment.png" alt-text="Keskkonna lähtestamise juhtimine.":::

1. Valige, kas soovite lähtestada kogu keskkonna, kõik peale andmeallikate või midagi, mis on konfigureeritud ühtse kliendiprofiili peal.

1. Kinnitamiseks sisestage keskkonna nimi ja valige **Lähtesta**.

## <a name="delete-an-existing-environment"></a>Olemasoleva keskkonna kustutamine

Keskkonna omanikuna saate kustutada hallatava keskkonna.

1. Valige rakenduse päises valija **Environment** (Keskkond).

1. Valige keskkond, mida soovite lähtestada, ja valige vertikaalne kolmikpunkt (&vellip;). 

1. Valige suvand **Delete** (Kustuta).

   :::image type="content" source="media/delete-environment.png" alt-text="Keskkonna kustutamise juhtimine.":::

1. Kustutamise kinnitamiseks sisestage soovitud keskkonna nimi ja valige **Kustuta**.

> [!IMPORTANT]
> Keskkonna kustutamine ei eemalda ühendust keskkonnaga Dataverse. Kui kavatsete tulevikus ühendada sama Dataverse keskkonna uue Customer Insightsi keskkonnaga, peate selle ühenduse eemaldama [Vaadake, kuidas olemasolevat ühendust keskkonnaga Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment) eemaldada.

[!INCLUDE [footer-include](includes/footer-banner.md)]
