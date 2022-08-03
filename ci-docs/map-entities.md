---
title: Lähteväljade valimine andmete ühendamiseks
description: Ühendamisprotsessi esimene samm on olemite, atribuutide, primaarvõtmete ja semantiliste tüüpide valimine andmete vastendamiseks ühtse kliendiprofiiliga.
recommendations: false
ms.date: 04/22/2022
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
ms.openlocfilehash: a75218c996b277e00924f2b7b38ea686a1f4dc38
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139777"
---
# <a name="select-source-fields-for-data-unification"></a>Lähteväljade valimine andmete ühendamiseks

Ühendamise esimene samm on nende andmekogumite olemite ja väljade valimine, mida soovite ühendada. Valige olemid, mis sisaldavad kliendiga seotud üksikasju, nagu nimi, aadress, telefoninumber ja meiliaadress. Saate valida ühe või mitu olemit.

## <a name="select-entities-and-fields"></a>Olemite ja väljade valimine

1. Avage **Jaotis Andmete** > **ühendamine**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Kuvatõmmis ühendamise sihtlehest esmakäivituskogemuse jaoks, kus on esile tõstetud alustamine.":::

1. Seejärel valige suvand **Alustamine**.

1. **Valige lehel Allikaväljad** suvand **Vali olemid ja väljad**. Kuvatakse **paan Olemite ja väljade** valimine.

1. Valige vähemalt üks olem.

1. Tuvastage iga valitud olemi puhul väljad, mida soovite kasutada kliendikirjete ja ühtsesse profiili kaasatavate väljade vastendamiseks. Neid välju nimetatakse *atribuutideks*. Saate valida nõutavad atribuudid olemilt eraldi või kaasata kõik olemi atribuudid, märkides olemi tasemel märkeruudu. Saate otsida atribuutide ja olemite üleselt märksõnu, et valida vajalikud atribuudid, mida soovite vastendada.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Valitud olemite ja atribuutide kuvatõmmis.":::

   Selles näites lisame **olemid Kontaktid** ja **CustomerLoyalty**. Nende olemite valimisel saate tuletada ülevaateid, kus veebikliendid on püsikliendiprogrammi liikmed.

1. Oma valikute kinnitamiseks valige suvand **Rakenda**. Valitud olemid ja atribuudid kuvatakse.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Atribuutide primaarvõtme ja semantilise tüübi valimine

   :::image type="content" source="media/m3_select_primary.png" alt-text="Valitud olemite kuvatõmmis, kus primaarvõtit pole valitud." lightbox="media/m3_select_primary.png":::

Tehke iga olemi puhul järgmised toimingud.

1. Valige **primaarvõti**. Primaarvõti on olemile ainuomane atribuut. Et atribuut saaks olla sobiv primaarvõti, ei tohi see sisaldada topeltväärtusi, puuduvaid väärtusi ega null-väärtusi. Stringi, täisarvu ja GUID andmetüübi atribuute toetatakse primaarvõtmetena.

1. Tehisintellekti mudelite kasutamiseks semantika nutikaks prognoos, aja säästmiseks ja täpsuse parandamiseks veenduge, et **intelligentne kaardistamine** oleks sisse lülitatud. Intelligentne vastendamine tõstab esile AI-põhise semantika soovituse väljal **Tüüp**. Soovitatud valiku saate alistada, valides saadaolevate suvandite loendist mis tahes semantilise tüübi.

1. Valige iga atribuudi jaoks semantiline **tüüp**, mis seda atribuuti kõige paremini kirjeldab (nt nimi, linn või meiliaadress).

   > [!NOTE]
   > Üks väli peaks vastendama semantilise tüübiga *Isik.FullName*, et asustada kliendikaardil olev kliendinimi. Vastasel juhul kuvatakse kliendikaardid ilma nimeta.

   1. Süsteemi poolt tuvastatud atribuuditüübi muutmiseks valige mõni muu tüüp. Kui tüüpi pole olemas, looge kohandatud semantiline tüüp, valides **atribuudi jaoks välja Tüüp** ja sisestades kohandatud semantilise tüübi nime.

   1. URL-i sisaldava atribuudi lisamiseks avalikult kättesaadavatele profiilipiltidele või logodele valige URL-i sisaldav olem ja väli. Sisestage väljale **Tüüp** järgmine teave.
      - Isiku korral: Person.ProfileImage
      - Organisatsiooni korral: Organization.LogoImage

   1. Kontonime atribuudi puhul sisestage väljale **Tüüp** "Organization.Name".

1. Vaadake üle atribuudid, kus semantiline tüüp tuvastatakse automaatselt. Need atribuudid on loetletud jaotises **Vaadake vastendatud väljad üle**. Ainult sama tüüpi atribuute saab kombineerida **etapis Ühtne klient**. Semantilisi tüüpe kasutatakse ülevaadete automaatseks soovitamiseks. Veenduge, et valitud tüübid oleksid kõigis valitud olemites ühesugused.

1. Atribuutide puhul, mida ei vasteta automaatselt semantilise tüübiga, valige semantiline tüübiväli, sisestage kohandatud atribuuditüübi nimi või jätke need kaardistamata. Need atribuudid on loetletud jaotises **Andmete määratlemine kaardistamata väljadel**.

1. Pärast iga olemi juhiste täitmist valige **Salvesta lähteväljad**.

1. Tehke valik **Edasi**.

> [!div class="nextstepaction"]
> [Järgmine samm: eemaldage duplikaadid](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
