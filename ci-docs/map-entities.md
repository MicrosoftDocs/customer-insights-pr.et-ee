---
title: Valige andmete ühendamiseks lähteväljad.
description: Ühendamise protsessi esimene samm on olemite, atribuutide, primaarvõtmete ja semantiliste tüüpide valimine andmete vastendamiseks ühtse kliendiprofiiliga.
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
ms.openlocfilehash: a962f1353b6e25b40c60b39a81ac936873f34d92
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740990"
---
# <a name="select-source-fields-for-data-unification"></a>Valige andmete ühendamiseks lähteväljad.

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Esimene samm ühendamisel on nende andmekogumite olemite ja väljade valimine, mida soovite ühendada. Valige olemid, mis sisaldavad kliendiga seotud üksikasju (nt nime, aadressi, telefoninumbrit ja meili). Saate valida ühe või mitu olemi.

## <a name="select-entities-and-fields"></a>Olemite ja väljade valimine

1. **Avage jaotisSe Andmete** > **ühendamine**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Kuvatõmmis ühendatava sihtlehest, et näha esimest käivitamiskogemust, kus esiletõstetud on käivitatud algus.":::

1. Seejärel valige suvand **Alustamine**.

1. **Valige lehel Allikas väärtus** **Vali olemid ja väljad**. Kuvatakse **paan Vali olemid ja väljad**.

1. Valige vähemalt üks olem.

1. Tuvastage iga valitud olemi puhul väljad, mida soovite kasutada kliendikirjete ja väljade sobitamiseks ühtsesse profiili kaasamiseks. Neid välju nimetatakse *atribuutideks*. Saate valida nõutavad atribuudid olemist eraldi või kaasata kõik olemi atribuudid, valides olemitasemel märkeruudu. Saate otsida atribuutide ja olemite üleselt märksõnu, et valida vajalikud atribuudid, mida soovite vastendada.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Valitud olemite ja atribuutide kuvatõmmis.":::

   Selles näites lisame **olemid Kontaktid** ja **Kliendilojaalsus**. Nende olemite valimisel saate tuletada ülevaateid, kus veebikliendid on püsikliendiprogrammi liikmed.

1. Oma valikute kinnitamiseks valige suvand **Rakenda**. Kuvatakse valitud olemid ja atribuudid.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Atribuutide primaarvõtme ja semantilise tüübi valimine

   :::image type="content" source="media/m3_select_primary.png" alt-text="Kuvatõmmis valitud olemitest, mille primaarvõti pole valitud." lightbox="media/m3_select_primary.png":::

Tehke iga olemi puhul järgmised juhised.

1. **Valige primaarvõti**. Primaarvõti on olemile ainuomane atribuut. Et atribuut saaks olla sobiv primaarvõti, ei tohi see sisaldada topeltväärtusi, puuduvaid väärtusi ega null-väärtusi. Põhivõtmetena toetatakse stringi-, täisarvu- ja GUID-andmetüübi atribuute.

1. Tehisintellekti mudelite kasutamiseks nutikaks semantika prognoos, aja säästmiseks ja täpsuse parandamiseks veenduge, et **intelligentne kaardistamine** on sisse lülitatud. Intelligentne vastendamine tõstab esile AI-põhise semantika soovituse väljal **Tüüp**. Soovitatud valiku alistamiseks valige saadaolevast suvandite loendist mis tahes semantiline tüüp.

1. Valige iga atribuudi puhul semantiline **tüüp**, mis kirjeldab seda atribuuti kõige paremini (nt nime, linna või meiliaadressi).

   > [!NOTE]
   > Üks väli peaks vastendama semantilise tüübiga *Isik.FullName*, et kliendinimi kliendikaardil asustada. Vastasel juhul kuvatakse kliendikaardid ilma nimeta.

   1. Süsteemi poolt tuvastatud atribuuditüübi muutmiseks valige mõni muu tüüp. Kui tüüpi pole olemas, looge kohandatud semantiline tüüp, valides **atribuudi välja Tüüp** ja sisestades oma kohandatud semantilise tüübi nime.

   1. URL-i sisaldava atribuudi lisamiseks avalikult saadaolevatele profiilipiltidele või logodele valige URL-i sisaldav olem ja väli. Sisestage väljale **Liik** järgmine tekst.
      - Isiku korral: Person.ProfileImage
      - Organisatsiooni korral: Organization.LogoImage

   1. Konto nime atribuudi puhul sisestage väljale **Liik** "Organization.Name".

1. Vaadake üle atribuudid, kus semantiline tüüp automaatselt tuvastatakse. Need atribuudid on loetletud jaotises **Vastendatud väljad** Läbivaatus. Ühendatud kliendiväljade **etapis saab kombineerida** ainult sama tüüpi atribuute. Statistika automaatseks soovitamiseks kasutatakse semantilisi tüüpe. Veenduge, et valitud tüübid oleksid kõigis valitud olemites ühtsed.

1. Atribuutide puhul, mis pole automaatselt vastendatud semantilise tüübiga, valige semantiline tüübiväli, sisestage kohandatud atribuudi tüüpi nimi või jätke need vastendamata. Need atribuudid on loetletud jaotises **Vastendamata väljade** andmete määratlemine.

1. Pärast iga olemi juhiste täitmist valige **Salvesta lähteväljad**.

1. Tehke valik **Edasi**.

> [!div class="nextstepaction"]
> [Järgmine samm: Duplikaatide eemaldamine](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
