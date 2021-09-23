---
title: Luba out-of-box profiiliaruanded
description: Saate teada, kuidas luua out-of-box profiiliaruandeid, mis on rühmitatud soo, vanuse ja riigi või piirkonna järgi.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486115"
---
# <a name="out-of-box-profile-reports"></a>Luba out-of-box profiiliaruanded

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Aruanne on andmete visualiseerimise kogum, mis aitab teil mõista, kuidas kasutajad käituvad. Ühenduse loomisel Customer Insights audience ülevaadetega, saavad kaasamisülevaated kuvada aruande teabega, mis sisaldab teavet ühendatud kliendiprofiilide kohta. See aruanne sisaldab teie profiile, mis on rühmitatud soo, vanuse ja geograafilise asukoha järgi.

## <a name="prerequisites"></a>Eeltingimused

Sihtrühma ülevaadete keskkond peab talletama andmeid kliendi hallatavas Azure Data Lake Storage kontos.

Kui kasutate rakenduse Customer Insights hallatavates andmetes publiku ülevaadete data lake võimalusi, pöörduge abi saamiseks [meie](https://go.microsoft.com/fwlink/?linkid=2145734) poole.  


## <a name="enable-the-customer-profile-report"></a>Kliendiprofiili aruande lubamine

Keskkonnaadministraator peab [linkima kaasamisülevaated ja sihtrühma ülevaated](integrate-audience-insights-engagement-insights.md).

Pärast ühenduse üksikasjade määratlemist saab administraator anda aruande nägemiseks juurdepääsu teistele ettevõtte inimestele. Ühenduse seadistanud keskkonnaadministraatoril on aruandele automaatselt juurdepääs. 

Pärast ühenduse lõpetamist on **Profiilid** funktsioon saadaval vasakpoolsel navigeerimispaanil. 

- Minge **Avasta** > **Profiilid**, et näha aruannet.

Aruanne **Profiilid** sisaldab visualiseeringuid seotud kliendiprofiilide soo, vanuse ja geograafilise asukoha kohta.

:::image type="content" source="media/customer-profiles.png" alt-text="Kliendiprofiili aruanne.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]