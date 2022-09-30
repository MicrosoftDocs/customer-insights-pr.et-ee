---
title: Keskkondade haldamine
description: Siit saate teada, kuidas hallata olemasolevaid Customer Insightsi keskkondi administraatorina.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 6d48f7088d722b27ca69cd591178651bdb6e2c23
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588807"
---
# <a name="manage-environments"></a>Keskkondade haldamine

Administraatorid [loovad](create-environment.md) ja haldavad keskkondi. Nad saavad muuta mõningaid seadeid olemasolevates keskkondades. Äri, tüüp, piirkond, salvestussuvand ja Dataverse sätted parandatakse pärast keskkonna loomist. Kui soovite neid sätteid muuta, [lähtestage keskkond](#reset-an-existing-environment-preview) või [looge uus keskkond](create-environment.md).

## <a name="edit-an-existing-environment"></a>Olemasoleva keskkonna redigeerimine

Redigeerige olemasoleva keskkonna üksikasju, näiteks nime või vaikekeskkonna määramist.

1. Valige rakenduse päises valija **Environment** (Keskkond).

1. Valige ikoon **Edit** (Redigeeri).

   :::image type="content" source="media/edit-environment.png" alt-text="Ikoon keskkonnasätete muutmiseks.":::

1. Värskendage **paanil Keskkonna** redigeerimine keskkonnasätteid.

1. Muudatuste rakendamiseks valige **Läbivaatus ja lõpeta**, seejärel **Värskenda**.

## <a name="change-the-owner-of-an-environment"></a>Keskkonna omaniku vahetamine

Administraatoriõigusi võib olla mitu kasutajat, kuid keskkonna omanik on ainult üks kasutaja. Vaikimisi on administraator see, kes algselt keskkonna loob. Keskkonna administraatorina saate määrata omandiõiguse teisele kasutajale administraatoriõigustega.

1. Valige rakenduse päises valija **Environment** (Keskkond).

1. Valige ikoon **Edit** (Redigeeri).

1. **Minge paanil** Keskkonna **redigeerimine etappi Põhiteave**.

1. Valige väljal **Keskkonna** omaniku muutmine keskkonna uus omanik.  

1. Muudatuste rakendamiseks valige **Läbivaatus ja lõpeta**, seejärel **Värskenda**.

## <a name="claim-ownership-of-an-environment"></a>Keskkonna omandiõiguse taotlemine

Kui omaniku kasutajakonto kustutatakse või peatatakse, pole keskkonnal omanikku. Iga administraatori kasutaja saab taotleda omandiõigust ja saada uueks omanikuks. Omanikust administraator saab jätkata keskkonna omamist või [muuta omanikuõiguse mõneks muuks administraatoriks](#change-the-owner-of-an-environment).

Omandiõiguse taotlemiseks valige **nupp Võta omandiõigus** üle, mis kuvatakse Customer Insightsi iga lehe ülaosas, kui algne omanik organisatsioonist lahkus.

## <a name="reset-an-existing-environment-preview"></a>Olemasoleva keskkonna lähtestamine (eelvaade)

Keskkonna omanikuna lähtestage keskkond tühja olekusse, kui soovite kustutada kõik konfiguratsioonid ja eemaldada allaneelatud andmed.

1. Valige rakenduse päises valija **Environment** (Keskkond).

1. Valige keskkond, mida soovite lähtestada, ja valige vertikaalne kolmikpunkt (&vellip;).

1. Valige **Lähtesta (eelvaade)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Keskkonna lähtestamise juhtimine.":::

1. Valige, kas soovite lähtestada kogu keskkonna, kõik peale andmeallikate või midagi, mis on konfigureeritud ühtse kliendiprofiili peal.

1. Kinnitamiseks sisestage keskkonna nimi ja valige **Lähtesta**.

## <a name="delete-an-existing-environment"></a>Olemasoleva keskkonna kustutamine

Keskkonna omanikuna saate selle kustutada.

> [!IMPORTANT]
> Keskkonna kustutamine ei eemalda ühendust keskkonnaga Dataverse. Kui kavatsete tulevikus ühendada sama Dataverse keskkonna uue Customer Insightsi keskkonnaga, peate selle ühenduse keskkonnaga [Dataverse eemaldama](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Valige rakenduse päises valija **Environment** (Keskkond).

1. Valige keskkond, mille soovite kustutada, ja valige vertikaalne kolmikpunkt (&vellip;). 

1. Valige **Kustuta**.

   :::image type="content" source="media/delete-environment.png" alt-text="Keskkonna kustutamise juhtimine.":::

1. Kustutamise kinnitamiseks sisestage soovitud keskkonna nimi ja valige **Kustuta**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
