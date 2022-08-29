---
title: Lähteväljade valimine andmete ühendamiseks
description: Ühendamisprotsessi esimene samm on olemite, atribuutide, primaarvõtmete ja semantiliste tüüpide valimine andmete vastendamiseks ühtse kliendiprofiiliga.
recommendations: false
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304560"
---
# <a name="select-source-fields-for-data-unification"></a>Lähteväljade valimine andmete ühendamiseks

Ühendamise esimene samm on nende andmekogumite olemite ja väljade valimine, mida soovite ühendada. Valige olemid, mis sisaldavad kliendiga seotud üksikasju, nagu nimi, aadress, telefoninumber ja meiliaadress. Saate valida ühe või mitu olemit.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Olemite ja väljade valimine

1. Avage **Jaotis Andmete** > **ühendamine**.

   Üksikklientide puhul (B-to-C) **kuvatakse sihtlehel Ühenda** üksused, **kus on kuvatud** väljad Alusta **esimese sammuga Allikas**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Üksikklientide esmakordse käitamise kogemuse jaoks mõeldud ühtse sihtlehe kuvatõmmis.":::

   Ärikontode (B-kuni B) puhul kuvatakse sihtlehel **Ühenda kontod**, kus on kuvatud **väljad** **Alusta esimesest juhisest** **Allikas.** Kontaktide **ühendamise (eelvaate)** etapid on valikulised ja ootavad konto ühendamise lõpuleviimist.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Kuvatõmmis ettevõttekontode esmakordse käitamise kogemuse sihtlehest Unify.":::

1. Seejärel valige suvand **Alustamine**.

1. **Valige lehel Allikaväljad** suvand **Vali olemid ja väljad**. Kuvatakse **paan Olemite ja väljade** valimine.

1. Valige vähemalt üks olem.

1. Tuvastage iga valitud olemi puhul väljad, mida soovite kasutada kliendikirjete ja ühtsesse profiili kaasatavate väljade vastendamiseks. Neid välju nimetatakse *atribuutideks*. Saate valida nõutavad atribuudid olemilt eraldi või kaasata kõik olemi atribuudid, märkides olemi tasemel märkeruudu. Saate otsida atribuutide ja olemite üleselt märksõnu, et valida vajalikud atribuudid, mida soovite vastendada.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Valitud olemite ja atribuutide kuvatõmmis.":::

   Selles näites lisame **eCommerceContacts** ja **LoyCustomer** olemid. Nende olemite valimisel saate tuletada ülevaateid, kus veebikliendid on püsikliendiprogrammi liikmed.

1. Oma valikute kinnitamiseks valige suvand **Rakenda**. Valitud olemid ja atribuudid kuvatakse.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Atribuutide primaarvõtme ja semantilise tüübi valimine

   :::image type="content" source="media/m3_select_primary.png" alt-text="Kuvatõmmis valitud olemitest, mille primaarvõti pole veel valitud." lightbox="media/m3_select_primary.png":::

Tehke iga olemi puhul järgmised toimingud.

1. Valige **primaarvõti**. Primaarvõti on olemile ainuomane atribuut. Et atribuut saaks olla sobiv primaarvõti, ei tohi see sisaldada topeltväärtusi, puuduvaid väärtusi ega null-väärtusi. Stringi, täisarvu ja GUID andmetüübi atribuute toetatakse primaarvõtmetena.

1. Tehisintellekti mudelite kasutamiseks nutikaks semantika prognoos, mis säästab aega ja parandab täpsust, veenduge, et **intelligentne kaardistamine** oleks sisse lülitatud. Arukas kaardistamine pakub tehisintellektil põhinevaid semantilisi soovitusi väljal **Tüüp**.

1. Valige iga atribuudi jaoks semantiline **tüüp**, mis seda atribuuti kõige paremini kirjeldab (nt nimi, linn või meiliaadress).

   > [!NOTE]
   > B-to-C-s peaks üks väli vastendama semantilise tüübiga *Isik.FullName*, et asustada kliendikaardil olev kliendinimi. B-to-B-s peaks konto nimi vastendama *Organization.Name*. Vastasel juhul kuvatakse kliendikaardid ilma nimeta.

   1. Süsteemi poolt tuvastatud atribuuditüübi alistamiseks valige mõni muu suvand. Kui tüüpi pole olemas, looge kohandatud semantiline tüüp, valides **atribuudi jaoks välja Tüüp** ja sisestades kohandatud semantilise tüübi nime.

   1. URL-i sisaldava atribuudi lisamiseks avalikult kättesaadavatele profiilipiltidele või logodele valige URL-i sisaldav olem ja väli. Sisestage väljale **Tüüp** järgmine teave.
      - Isiku korral: Person.ProfileImage
      - Organisatsiooni korral: Organization.LogoImage

1. Vaadake üle atribuudid, kus semantiline tüüp tuvastatakse automaatselt. Need atribuudid on loetletud jaotises **Vaadake vastendatud väljad üle**. Ainult sama tüüpi atribuute saab kombineerida **etapis Kliendiväljade** ühendamine. Semantilisi tüüpe kasutatakse ülevaadete automaatseks soovitamiseks. Veenduge, et valitud tüübid oleksid kõigis valitud olemites ühesugused.

1. Atribuutide puhul, mis ei vastendata automaatselt semantilise tüübiga, valige semantiline tüübiväli, sisestage kohandatud atribuuditüübi nimi või jätke need kaardistamata. Need atribuudid on loetletud jaotises **Andmete määratlemine kaardistamata väljadel**.

1. Pärast iga olemi juhiste täitmist valige **Salvesta lähteväljad**.

1. Tehke valik **Edasi**.

> [!div class="nextstepaction"]
> [Järgmine samm: eemaldage duplikaadid](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
