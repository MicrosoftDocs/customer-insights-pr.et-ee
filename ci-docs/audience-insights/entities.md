---
title: Olemid ja andmekomplektid
description: Saate vaadata andmeid olemite lehel.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049389"
---
# <a name="entities-in-audience-insights"></a>Olemid sihtrühmaülevaadetes

Pärast [andmeallikate konfigureerimist](data-sources.md)minge lehele **Olemid**, et hinnata sisestatud andmete kvaliteeti. Olemeid käsitletakse andmekogumitena. Nende olemite põhjal on loodud mitu Dynamics 365 Customer Insightsi funktsiooni. Nende lähedasem läbivaatamine aitab teil nende võimaluste väljundit valideerida.

**Olemite** lehel loetletakse olemid ja see sisaldab mitut veergu.

- **Nimi**: teie andmete olemi nimi. Kui olemi nime kõrval kuvatakse hoiatuse sümbol, tähendab see, et selle olemi andmeid ei laaditud edukalt.
- **Allikas**: andmeallika tüüp, mis olemisse sisestati
- **Looja**: olemi loonud inimese nimi
- **Loodud**: olemi loomise kuupäev ja kellaaeg
- **Värskendaja**: olemit värskendanud inimese nimi
- **Viimati värskendatud**: olemi viimase värskendamise kuupäev ja kellaaeg
- **Viimane värskendatud**: viimase andmete värskendamise kuupäev ja kellaaeg

## <a name="exploring-a-specific-entitys-data"></a>Kindla olemi andmete avastamine

Valige olem, et avastada selles olemis sisalduvaid erinevaid välju ja kirjeid.

> [!div class="mx-imgBorder"]
> ![Olemi valimine](media/data-manager-entities-data.png "Vali olem")

- Vahekaardil **Andmed** kuvatakse olemin üksikkirjete tabeli analüüsimise üksikasjad.

> [!div class="mx-imgBorder"]
> ![Väljade tabel](media/data-manager-entities-fields.PNG "Väljade tabel")

- Vahekaart **Atribuudid** on vaikimisi valitud ja kuvab tabeli et vaadata üle valitud olemi üksikasjad nagu välja nimed, andmetüübid ja tüübid. Veerus **Tüüp** kuvatakse ühise andmemudeli seostatavad tüübid, mis on süsteemi poolt automaatselt tuvastatud või mille on kasutajad [käsitsi vastendanud](map-entities.md). Need on semantilised tüübid, mis võivad atribuutide andmetüüpide hulgast erineda, nt allpool on *Meili* välja andmetüüp *Tekst*, kuid selle (semantiline) ühine andmemudel võib olla *Meil* või *Meiliaadress*.

> [!NOTE]
> Mõlemad tabelid näitavad ainult teie olemi andmete näidiseid. Täieliku andmekogumise vaatamiseks minge lehele **Andmeallikad**, valige olem, valige **Redigeeri** ja seejärel vaadake selle olemi andmeid Power Query redaktoriga, nagu on selgitatud [andmeallikates](data-sources.md).

Kui soovite lisateavet olemisse sisestatud andmete kohta, on **Kokkuvõtte** veerus toodud teie jaoks olulised kohaldatavad andmed, nt nullid, puuduvad väärtused, kordumatud väärtused, arvud ja jaotused.

Andmete kokkuvõtte kuvamiseks valige diagrammi ikoon.

> [!div class="mx-imgBorder"]
> ![Kokkuvõtte sümbol](media/data-manager-entities-summary.png "Andmete kokkuvõtte tabel")

### <a name="next-step"></a>Järgmine etapp

Vaadake jaotise [Ühendamine](data-unification.md) teemat, et õppida sisestatud andmete *kaardistamist*, *vastendamist* ja *ühendamist*.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
