---
title: Halda küpsiseid ja kasutaja nõusolekut kasutajaandmeid talletada Dynamics 365 Customer Insights -is
description: Teave selle kohta, kuidas kasutatakse veebisaidikülastuste tuvastamiseks küpsiseid ja kasutaja nõusolekut.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228980"
---
# <a name="manage-cookies-and-user-consent"></a>Küpsiste ja kasutaja nõusoleku haldamine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Dynamics 365 Customer Insights kaasamisülevaadete võimalused kasutavad küpsiseid ja (`localStorage`) võtmeid, et tuvastada veebilehe külastajaid.

Küpsised on väikesed failid, kus talletatakse bitt teavet kasutaja ja veebisaidi vahelise suhtluse kohta. Need on talletatud veebibrauserites. Kui kasutajad külastavad veebisaiti, mille jaoks teie kasutajad on küpsised salvestanud, saadab brauser selle teabe serverisse, mis tagab kasutajale kordumatu teabe. See on tehnoloogia, mis võimaldab näiteks veebipõhisel ostukorvil säilitada valitud üksused seal isegi juhul, kui kasutaja veebisaidilt lahkub.

## <a name="user-consent"></a>Kasutaja nõusolek

Üldine [Andmekaitse määrus (GDPR)](/dynamics365/get-started/gdpr/) on Euroopa Liiddu (EU) regulatsioon, mis täidab ülesandeid, kuidas organisatsioonid peaksid tegelema oma kasutajate privaatsuse ja turvalisusega. Küpsised talletavad või koguvad sageli "isikuandmeid" nagu näiteks veebipõhine identifikaator, mida kasutab GDPR. Kui teie ettevõte töötab ja / või müüb ELi andmesubjektidele, mõjutab GDPR teid. [Siit saate lisateavet selle kohta, kuidas Microsoft saab aidata teil järgida GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Kui soovite, et seotusteabe SDK salvestaks küpsiseid või muud tundlikku teavet, peate määrama, kas teie kasutajad on sellega nõustunud. See juhtub SDK lähtestamisel, seadistades `userConsent` konfiguratsioonis välja.

Kui näitate, et kasutaja ei nõustu, ei talleta SDK andmeid ega saada kasutaja käitumise jälitamiseks kasutatavaid sündmusi. Kõik varem salvestatud andmed kustutatakse brauserist.

Kui kasutaja nõusoleku väärtust ei määrata, siis eeldab SDK, et kasutaja on sellega nõustunud. See tähendab, et kui te (meie kliendina) ei määra SDK-s kasutaja nõusoleku väärtust, siis andmeid kogutakse. Kui aga täpsustate, et kasutaja nõusoleku väärtus peab olema "tõene", ei koguta andmeid, kui kasutaja keeldub või ei esita selget nõusolekut.

Allpool on koodilõigend SDK lähtestamine kasutaja loal:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Külastaja andmete talletus kaasamisülevaadete võimalustes

### <a name="cookies"></a>Küpsised

- _msei
    - Talletab anonüümse kasutaja ID. See küpsise valik määratakse kliendi domeenis ja aegub 365 päeva pärast.

### <a name="local-storage"></a>Kohalik salvestusruum

Kaasamisülevaadete võimalused kasutavad ka võtmeid (`localStorage`) mittetundliku andmete jälitamiseks. Need andmed salvestatakse täielikult brauserisse endasse, ilma et teie serveritesse ega teie serveritesse liiklust saadaks.

- *EISeansi.Id*
    - Talletab teavet jätkuva kasutajaseansi (nt seansi ID, selle käivitamisel ja aegumisjärgus) kohta.
- *EISeansi.Eelmine*
    - Talletab praeguse seansi varem külastatud lehe URL-i.

Kohaliku mäluruumi klahvid ei aegu automaatselt ja need lähtestatakse järgmise SDK seansi ajal.

## <a name="deleting-cookies"></a>Küpsiste kustutamine

Kliendid saavad brauseri sätete kaudu küpsiseid ja kohalikke salvestusklahve igal ajal käsitsi kustutada.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
