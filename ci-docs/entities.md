---
title: Rakenduse Customer Insights olemid
description: Saate vaadata andmeid olemite lehel.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610093"
---
# <a name="entities-in-customer-insights"></a>Rakenduse Customer Insights olemid

Pärast [andmeallikate konfigureerimist](data-sources.md)minge lehele **Olemid**, et hinnata sisestatud andmete kvaliteeti. Olemeid käsitletakse andmekogumitena. Nende olemite põhjal on loodud mitu Dynamics 365 Customer Insightsi funktsiooni. Nende lähedasem läbivaatamine aitab teil nende võimaluste väljundit valideerida.

Kui töötate Customer Insightsis, rikastades oma andmeid või luues segmente, mõõtühikuid ja tegevusi, kuvatakse **nendest toimingutest loodud olemid lehel Olemid**.

## <a name="view-a-list-of-entities"></a>Olemite loendi kuvamine

Olemite **loendi kuvamiseks avage** > **Andmeüksused**. Iga olemi kohta kuvatakse järgmine teave.

- **Nimi**: andmeüksuse nimi. Kui olemi nime kõrval kuvatakse hoiatuse sümbol, tähendab see, et selle olemi andmeid ei laaditud edukalt.
- **Allikas**: olemi allaneelanud andmeallikas tüüp.
- **Värskendatud** aeg: olemi viimase värskendamise aeg.
- **Olek**: üksikasjad olemi viimase värskenduse kohta.

## <a name="explore-a-specific-entitys-data"></a>Avasta kindlat andmeüksust

1. Avage **Jaotis Andmeüksused** > **·**.
1. Üksikasjade lehe avamiseks valige olem.  
1. Uurige selle olemi erinevaid välju ja kirjeid.

- Vahekaart **Atribuudid** on vaikimisi valitud ja kuvab valitud olemi üksikasjad, nagu väljanimed, andmetüübid ja tüübid. Veerus **Tüüp** kuvatakse ühise andmemudeli seostatavad tüübid, mis on süsteemi poolt automaatselt tuvastatud või mille on kasutajad [käsitsi vastendanud](map-entities.md). Need tüübid on semantilised tüübid, mis võivad atribuutide andmetüüpidest erineda. Näiteks alloleval väljal *Meil* on andmetüüp *String*, kuid selle (semantiline) tüüp Common Data Model võib olla *Email*, *EmailAddress* või *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Väljade tabel.":::

   > [!NOTE]
   > Sellel lehel kuvatakse ainult teie olemi andmete näidis. Täieliku andmekogumi vaatamiseks minge **lehele Andmeallikad**, valige olem, valige **Redigeeri** ja seejärel vaadake selle olemi andmeid Power Query redaktoriga, nagu on selgitatud jaotises [Andmeallikad](data-sources.md).

   Olemis **allaneelatud andmete kohta lisateabe saamiseks leiate veerust Kokkuvõte** mõned olulised andmeomadused, nagu nullid, puuduvad väärtused, kordumatud väärtused, loendused ja jaotused, olenemata sellest, mis teie andmetele rakendub. Andmete kokkuvõtte kuvamiseks valige diagrammi ikoon.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Andmete kokkuvõtlik tabel.":::

- Vahekaardil **Andmed** kuvatakse üksikasjad olemi üksikute kirjete kohta. Loetletud üksikasjad sõltuvad olemi andmetüübist.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Valige olem.":::

- Vahekaart **Aruanded** (saadaval mõne olemi jaoks) võimaldab teil oma andmeid visualiseerida, luues aruande, mis sisaldab järgmisi veerge.

  - **Aruande nimi**: aruande nimi.
  - **Loodud**: olemi loonud isiku nimi.
  - **Loodud**: olemi loomise kuupäev ja kellaaeg.
  - **Toimetanud**: Olemit muutnud isiku nimi.
  - **Redigeeritud**: olemi muutmise kuupäev ja kellaaeg.

[!INCLUDE [footer-include](includes/footer-banner.md)]
