---
title: Kliendi nõusoleku kasutamine
description: Austage oma klientide nõusolekueelistusi Customer Insightsis nõusolekuandmete importimise teel.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 77b09b6eb0a916e724542d503d96d19c5581aca1
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/14/2022
ms.locfileid: "8947519"
---
# <a name="use-customer-consent"></a>Kliendi nõusoleku kasutamine

Andmekaitse- ja privaatsuseeskirjad annavad üksikisikutele õiguse reguleerida, kuidas organisatsioon oma isikuandmeid kasutab. Selliste määruste näideteks on isikuandmete kaitse üldmäärus Euroopa Liidus või California tarbijate privaatsuse seadus Ameerika Ühendriikides. Need eeskirjad võimaldavad inimestel loobuda oma isikuandmete kogumisest, töötlemisest või jagamisest kolmandate osapoolte poolt.  

Kliendid võivad valida, kas võtta tagasi või keelduda oma nõusolekust konkreetsete kontaktivormide jaoks. Samuti võivad nad nõuda, et te loobuksite nende isikuandmete kogumisest, säilitamisest, kasutamisest või müügist. On oluline, et teie organisatsioon austaks kõigi klientide nõusolekut ja privaatsuseelistusi.  

Dynamics 365 Customer Insights aitab teil austada oma klientide taotlusi, importides ja säilitades nende eelistused ühtsete kliendiprofiilide osana.

Kui nõusolekuandmeid säilitatakse kliendiprofiilidest eraldi, [lisage nõusolekuandmed uue andmeallikas](#import-and-unify-consent-data). Nõusolekuandmeid sisaldavad andmeallikas lisatakse andmete ühendamise protsessi. Nõusolekuandmete ja kliendiprofiilide edukas ühendamine viib seejärel ühtsete kliendiprofiilideni, mis sisaldavad nõusolekuteavet. Kliendiprofiilide puhul, mis juba sisaldavad nõusolekuteavet, minge otse nõusolekuandmete [jaotisse](#use-consent-data) Kasuta.

## <a name="prerequisites"></a>eeltingimused

Nõusolekuandmete ühendamiseks teiste kliendiprofiilidega peab lähteandmetes olema saadaval järgmine teave.

- Alternatiivvõti nõusolekuteabe vastendamiseks Customer Insightsi kasutajaprofiilidega. Näiteks e-posti aadress või telefoninumber.
- Nõusoleku väärtus kliendi nõusoleku oleku määramiseks.

Kaaluge järgmise *valikulise* teabe lisamist.

- Peamine võti nõusoleku oleku värskendamiseks, kui klient taotleb muudatust.
- Nõusoleku tüüp, kui klienditeabe töötlemiseks on mitu võimalust.
- Nõusoleku kuupäev või muud teie nõusolekustsenaariumidega seotud andmed.

Näidistabel lihtsast nõusolekuandmebaasist, millel on mitu nõusolekuvõimalust:

|Nõusoleku ID (primaarvõti)   |E-post (alternatiivvõti)  |Nõusoleku suvand  |Nõusoleku väärtus  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Infoleht       |  Väär       |
|2    |  holly@contoso.com       |  Tootevärskendused       |  Tõene       |
|3    |  frank@contoso.com       |  Infoleht       | Tõene        |
|4    |  frank@contoso.com       |  Tootevärskendused       |  Väär       |

## <a name="import-and-unify-consent-data"></a>Nõusolekuandmete importimine ja ühendamine

Nõusolekuandmeid saate importida samamoodi nagu muid andmeallikaid Customer Insightsi. Lisateavet toetatud andmeallikate ja nende importimise kohta leiate andmeallikate [ülevaatest](data-sources.md).

Andmeallikate ühendamise kohta leiate lisateavet teemast [Andmete ühendamise ülevaade](data-unification.md).

## <a name="use-consent-data"></a>Nõusolekuandmete kasutamine

Kui teie nõusolekuandmed on osa teie ühtsetest kliendiprofiilidest, saate neid kasutada Customer Insightsis. Näiteks looge segment reegliga, mis tagab, et austate oma klientide privaatsuse ja andmekaitse eelistusi. Nõusolekueelistusi toetavaid reegleid kasutatakse kasutajate väljajätmiseks profiiliatribuutidel põhinevast segmendist. Reegli lisamine segmendile, mis välistab kliendiprofiilid, mis ei andnud nõusolekut kontakteerumiseks.

Viidates ülaltoodud näidistabelile, võib segment sisaldada järgmist reeglit:`Consent option=Newsletter & Consent value=True`. Selle konfiguratsiooni tulemuseks on segment, mis austab kontaktide eelistusi uudiskirja saatmiseks.

Lisateavet ehitussegmentide kohta leiate teemast [Segmentide](segment-builder.md) loomine.

Kui segment on loodud, saate segmendi kasutamiseks teistes rakendustes kasutada ühte paljudest [ekspordisuvanditest](export-destinations.md).

## <a name="ensure-updated-consent-status"></a>Värskendatud nõusoleku oleku tagamine

Oluline on hoida oma klientide nõusoleku olek ajakohasena. Customer Insightsi ajastatud värskendamine impordib alati teie andmeallikate uusima oleku. Seejärel töödeldakse seda teavet andmete ühendamise kaudu ja tulemuseks on värskendatud kliendiprofiilid. Neid värskendatud profiile kasutatakse seejärel segmentide värskendamiseks, veendumaks, et töötate kõige ajakohasema teabega.

Teisisõnu veenduge, et Customer Insightsi imporditavatel lähteandmetel oleks alati uusim teave.

Lisateavet leiate teemast [Segmentide käsitsi](segments.md#refresh-segments) värskendamine või [ajastatud värskenduse](system.md#schedule-tab) konfigureerimine.
