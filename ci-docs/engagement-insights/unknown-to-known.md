---
title: Tunne ära varem autentitud külastajate tundmatust tuntuni veebisündmused
description: Tundmatust tuntuni funktsioon lubab seostada sündmuseid veebilehel koos külastajatega, kes on eelnevalt autentitud.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036778"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Tunne ära varem autentitud külastajate veebisündmused

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

**Tundmatust tuntuni** funktsioon kaasamisülevaates võimaldab sündmuseid veebilehel seostada koos kasutajatega, kes on varem autentitud. Kui funktsioon on keelatud, ei tuvastata varasema külastuse ajal autenditud ja seejärel lahkunud külastajad, kui nad tagasi tulemisel uuesti autenti ei tee. 

Näiteks isik, kes külastas eelmisel nädalal veebisaiti, logis oma veebisaidil oma kasutajakontosse ja sirvis tootekataloogi. Isik tuleb järgmisel nädalal tagasi, et rohkem tooteid sirvimida ilma oma kontole sisse logimata. Saidi omanik kasutades funktsiooni **teadmatust tuntuni** teaks, et sama isik on tagasi tulnud ning mida ta lehel juba teinud on. See võimaldab veebisaiditegevuste täpsemat aruandlust ja analüüsimist.

## <a name="enable-unknown-to-known"></a>Tundmatust tuntule lubatud

Selle funktsiooni lubamiseks pead sa olema [tööruumi administraator](user-roles.md). 

1. Minge kaasamisülevaadetes **administraatori** > **tööruumii**. 
2. Valige **Täpsemad sätted**.
3. **Tundmatust tuntuni** jaotises seadke lüliti väärtusele **Võimalda**.

![Tundmatust tuntule lubatud](media/U2Ktoggle.png "Tundmatust tuntule lubatud")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>JavaScript -i koodi lisamine saidi jälgimiskoodile lõigend

Veebisait võib hõivata **kasutaja authId** koos järgneva JavaScript -i näitega, kasutades [kaasamisülevaateid veebi SDK](advanced-SDK-implementation.md). Selleks, et **tundmatult tuntule** funktsioon töötaks peate hõivama AuthId *ja* lubama kasutaja Kaardistamist: Tõene JavaScript'i lõigendis nagu allolevas näites.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
