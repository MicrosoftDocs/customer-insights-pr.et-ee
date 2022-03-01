---
title: Halda küpsiseid ja kasutaja nõustumisi kasutajaandmete talletamisel
description: Teave selle kohta, kuidas kasutatakse veebisaidikülastuste tuvastamiseks küpsiseid ja kasutaja nõusolekut.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7b3195a92c969ab36e5b43f4c2e4221ff477a0a8958838e1256528f58fe13dce
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036733"
---
# <a name="manage-cookies-and-user-consent"></a>Küpsiste ja kasutaja nõusoleku haldamine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights kaasamisülevaadete võimalused kasutavad küpsiseid ja kohalikku salvestusruumi (`localStorage`) veebisaidikülastuste tuvastamiseks.

Küpsised on väikesed failid, kus talletatakse bitt teavet kasutaja ja veebisaidi vahelise suhtluse kohta. Need on talletatud veebibrauserites. Kui kasutajad külastavad veebisaiti, mille jaoks teie kasutajad on küpsised salvestanud, saadab brauser selle teabe serverisse, mis tagab kasutajale kordumatu teabe. See on tehnoloogia, mis võimaldab näiteks veebipõhisel ostukorvil säilitada valitud üksused seal isegi juhul, kui kasutaja veebisaidilt lahkub.

## <a name="user-consent"></a>Kasutaja nõusolek

Üldine [Andmekaitse määrus (GDPR)](/dynamics365/get-started/gdpr/) on Euroopa Liiddu (EU) regulatsioon, mis täidab ülesandeid, kuidas organisatsioonid peaksid tegelema oma kasutajate privaatsuse ja turvalisusega. Küpsised talletavad või koguvad sageli "isikuandmeid" nagu näiteks veebipõhine identifikaator, mida kasutab GDPR. Kui teie ettevõte töötab ja / või müüb ELi andmesubjektidele, mõjutab GDPR teid. [Siit saate lisateavet selle kohta, kuidas Microsoft saab aidata teil järgida GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Kui soovite, et seotusteabe SDK salvestaks küpsiseid või muud tundlikku teavet, peate määrama, kas teie kasutajad on sellega nõustunud. See probleem ilmneb SDK lähtestamisel.

Kui näitate, et kasutaja ei nõustu, ei talleta SDK andmeid ega saada kasutaja käitumise jälitamiseks kasutatavaid sündmusi. Kõik varem salvestatud andmed kustutatakse brauserist.

Kui kasutaja nõusoleku väärtust ei määrata, siis eeldab SDK, et kasutaja on sellega nõustunud. See tähendab, et kui te (meie kliendina) ei määra SDK-s kasutaja nõusoleku väärtust, siis andmeid kogutakse. Kui aga täpsustate, et kasutaja nõusoleku väärtus peab olema "tõene", ei koguta andmeid, kui kasutaja keeldub või ei esita selget nõusolekut.

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Külastaja andmete talletus kaasamisülevaadete võimalustes

### <a name="cookies"></a>Küpsised

- _msei
    - Talletab anonüümse kasutaja ID. See küpsise valik määratakse kliendi domeenis ja aegub 365 päeva pärast.

### <a name="local-storage"></a>Kohalik salvestusruum

Kaasamisülevaadete võimalused kasutavad ka kohalikku salvestusruumi (`localStorage`) mittetundliku andmete jälitamiseks. Need andmed salvestatakse täielikult brauserisse endasse, ilma et teie serveritesse ega teie serveritesse liiklust saadaks.

- *EISeansi.Id* 
    - Talletab teavet jätkuva kasutajaseansi (nt seansi ID, selle käivitamisel ja aegumisjärgus) kohta.
- *EISeansi.Eelmine*
    - Talletab praeguse seansi varem külastatud lehe URL-i.
    
Kohaliku mäluruumi klahvid ei aegu automaatselt. SDK lähtestab need järgmisel seansil.

## <a name="deleting-cookies"></a>Küpsiste kustutamine

Kliendid saavad brauseri sätete kaudu küpsiseid ja kohalikke salvestusklahve igal ajal käsitsi kustutada.


[!INCLUDE[footer-include](../includes/footer-banner.md)]