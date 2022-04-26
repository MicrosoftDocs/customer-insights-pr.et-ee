---
title: Mõõtude loomine mallidest
description: Määratlege meetmed mallide abil levinud kasutusjuhtumite puhul.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: eeabd889f7b694f8d809894169a3cdc068acc340
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529396"
---
# <a name="use-a-template-to-build-a-measure"></a>Malli abil mõõdu loomine

Nende loomiseks saate kasutada sagedamini kasutatavate [meetmete](measures.md) eelmääratletud malle. Mallide üksikasjalik kirjeldus ja juhendatud kogemused aitavad teil luua tõhusa mõõtmissüsteemi. Mallid põhinevad olemi *Ühendatud tegevus* kaardistatud andmetele. Seega veenduge, et olete konfigureerinud [klienditegevused](activities.md) enne malli põhjal mõõtühiku loomist.

Kohandatud mõõtude loomiseks lugege teemat [Mõõte koostaja kasutamine nullist loomiseks](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Üksikud tarbijad (B-st C-ni)](#tab/b2c)

Saadaval mõõdumallid: 
- Keskmine tehingu väärtus (ATV)
- Tehingu väärtus kokku
- Päeva keskmine tulu
- Aasta keskmine tulu
- Kannete arv
- Teenitud püsikliendipunktid
- Lunastatud püsikliendipunktid
- Püsikliendipunktide saldo
- Aktiivse kliendi eluiga
- Püsikliendi liikmestaatuse kestus
- Aega viimasest ostust

## <a name="build-a-new-measure-using-a-template"></a>Uue mõõdu loomine malli abil

1. Minge meetmete **juurde**.

1. Valige **Uus** ja seejärel **Vali mall**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Rippmenüü ekraanipilt uue mõõtühiku loomisel malli esiletõstmisega.":::

1. Leidke teie vajadusele sobiv mall ja valige **Valige mall**.

1. Vaadake nõutavad andmed läbi ja valige **Alustamine**, kui kõik andmed on olemas.

1. Valige **Käsu Mõõda nime kõrval käsk Redigeeri üksikasju**. Esitage meetmele nimi. Soovi korral lisage [mõõdule sildid](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoogiboksi Üksikasjade redigeerimine.":::

1. Valige nupp **Valmis**.

1. Määrake **Sea ajaperiood** jaotises ajavahemikud andmete kasutamiseks. Valige, kas soovite uue näitaja abil hõlmata kogu andmekogumi, valides suvandi **Kogu aeg** või soovite, et näitaja keskenduks **Kindlale ajaperioodile**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Kuvatõmmis ajavahemiku jaotisest, kui konfigureerite malli põhjal mõõtmise.":::

1. Järgmises jaotises valige **Lisa andmed**, et valida tegevused ja kaardistada oma olemi *Ühendatud tegevus* vastavad andmed.

    1. 1. etapp: valige jaotises **Tegevuse tüüp** selle olemi tüüp, mida soovite kasutada. Valige **Tegevused** jaoks olemid, mida soovite kaardistada.
    1. 2. etapp: valige atribuut olemist *Ühendatud Tegevus* valemiga nõutava komponendi jaoks. Näiteks keskmise tehingu väärtuse puhul on see atribuut, mis tähistab tehingu väärtust. Valige **Tegevuse ajatempli** jaoks atribuut olemist Ühendatud tegevus, mis tähistab tegevuse kuupäeva ja kellaaega.
   
1. Kui andmete kaardistamine õnnestub, näete olekut **Lõpule viidud** ning kaardistatud tegevuste ja atribuutide nime.

1. Nüüd saate valida suvandi **Käita**, et arvutada mõõtmise tulemused. Hiljem viimistlemiseks valige **Salvesta mustand**.

# <a name="business-accounts-b-to-b"></a>[Ettevõtte kontod (B-st B-ni)](#tab/b2b)

See funktsioon on saadaval ainult keskkondades loodud juhtudeks, kus üksikud kliendid on esmaseks sihtrühmaks.

---
