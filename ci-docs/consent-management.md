---
title: Kliendi nõusoleku kasutamine
description: Austage klientide nõusolekueelistusi Customer Insightsis, importides nõusolekuandmeid.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6c951219410b55adc34691f677158b574cea1e01
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245690"
---
# <a name="use-customer-consent"></a>Kliendi nõusoleku kasutamine

Andmekaitse- ja privaatsuseeskirjad annavad üksikisikutele õiguse reguleerida, kuidas organisatsioon nende isikuandmeid kasutab. Sellised eeskirjad on näiteks Euroopa Liidu isikuandmete kaitse üldmäärus või Ameerika Ühendriikides California tarbija privaatsusseadus. Need eeskirjad võimaldavad inimestel loobuda oma isikuandmete kogumisest, töötlemisest või jagamisest kolmandate osapooltega.  

Kliendid võivad valida, kas võtta tagasi või keelduda oma nõusolekust konkreetsete kontaktivormide jaoks. Samuti võivad nad taotleda, et loobuksite nende isikuandmete kogumisest, säilitamisest, kasutamisest või müügist. On oluline, et teie organisatsioon austaks kõigi klientide nõusolekut ja privaatsuseelistusi.  

Dynamics 365 Customer Insights aitab teil austada oma klientide soove, importides ja salvestades nende eelistused ühtse kliendiprofiili osana.

Kui nõusolekuandmeid säilitatakse teie kliendiprofiilidest eraldi, [lisage oma nõusolekuandmed uue andmeallikas](#import-and-unify-consent-data). Nõusolekuandmeid sisaldav andmeallikas lisatakse andmete ühendamise protsessi. Nõusolekuandmete ja kliendiprofiilide edukas ühendamine viib seejärel ühtsete kliendiprofiilideni, mis sisaldavad nõusolekuteavet. Kliendiprofiilide puhul, mis juba sisaldavad nõusolekuteavet, minge otse jaotisse [Kasutusloa andmed](#use-consent-data).

## <a name="prerequisites"></a>eeltingimused

Nõusolekuandmete ühendamiseks teiste kliendiprofiilidega peab teie lähteandmetes olema saadaval järgmine teave.

- Alternatiivvõti, et viia nõusolekuteave Customer Insightsis vastavusse kasutajaprofiilidega. Näiteks e-posti aadress või telefoninumber.
- Nõusoleku väärtus kliendi nõusoleku oleku määramiseks.

Kaaluge järgmise *valikulise* teabe lisamist.

- Esmane võti nõusoleku oleku värskendamiseks, kui klient taotleb muudatust.
- Nõusoleku tüüp, kui klienditeabe töötlemiseks on mitu võimalust.
- Nõusoleku kuupäev või muud tüüpi andmed, mis on seotud teie nõusoleku stsenaariumidega.

Näidistabel lihtsast nõusolekuandmebaasist, millel on mitu nõusolekusuvandit:

|Nõusoleku ID (primaarvõti)   |E-post (alternatiivvõti)  |Nõusoleku võimalus  |Nõusoleku väärtus  |
|---------|---------|---------|---------|
|1    |  holly@contoso.com       |  Infoleht       |  Väär       |
|2    |  holly@contoso.com       |  Tootevärskendused       |  Tõene       |
|3    |  frank@contoso.com       |  Infoleht       | Tõene        |
|4    |  frank@contoso.com       |  Tootevärskendused       |  Väär       |

## <a name="import-and-unify-consent-data"></a>Nõusolekuandmete importimine ja ühendamine

Importige nõusolekuandmed samamoodi nagu muud andmeallikad Customer Insightsi. Lisateavet toetatud andmeallikate ja nende importimise kohta leiate teemast [Andmeallikate ülevaade](data-sources.md).

Lisateavet andmeallikate ühendamise kohta leiate teemast [Andmete ühendamise ülevaade](data-unification.md).

## <a name="use-consent-data"></a>Nõusolekuandmete kasutamine

Kui teie nõusolekuandmed on osa teie ühtsest kliendiprofiilist, saate neid kasutada Customer Insightsis. Näiteks looge reegliga segment, mis tagab, et austate oma klientide privaatsus- ja andmekaitseeelistusi. Nõusolekueelistusi toetavaid reegleid kasutatakse kasutajate välistamiseks segmendist profiiliatribuutide alusel. Lisage segmendile reegel, mis välistab kliendiprofiilid, mis ei andnud kontaktiks nõusolekut.

Viidates ülaltoodud näidistabelile, võib segment sisaldada seda reeglit:`Consent option=Newsletter & Consent value=True`. Selle konfiguratsiooni tulemuseks on segment, mis austab kontakteelistusi uudiskirja saatmiseks.

Lisateavet ehitussegmentide kohta leiate teemast [Segmentide](segment-builder.md) loomine.

Kui segment on loodud, saate kasutada ühte paljudest [ekspordivõimalustest](export-destinations.md), et kasutada segmenti teistes rakendustes.

## <a name="ensure-updated-consent-status"></a>Värskendatud nõusoleku oleku tagamine

Oluline on hoida klientide nõusoleku olek ajakohasena. Customer Insightsi ajastatud värskendamine impordib alati teie andmeallikate uusima oleku. Seejärel töödeldakse seda teavet andmete ühendamise kaudu ja tulemuseks on värskendatud kliendiprofiilid. Neid värskendatud profiile kasutatakse seejärel segmentide värskendamiseks, et veenduda, et töötate kõige ajakohasema teabega.

Teisisõnu veenduge, et Customer Insightsi imporditavatel lähteandmetel oleks alati uusim teave.

Lisateavet leiate teemast [Segmentide](segments.md#refresh-segments) käsitsi värskendamine või [ajastatud värskendamise konfigureerimine](schedule-refresh.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
