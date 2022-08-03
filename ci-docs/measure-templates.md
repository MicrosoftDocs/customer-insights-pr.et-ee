---
title: Mõõtude loomine mallidest
description: Määratlege mõõdud, kasutades levinud kasutusjuhtumite malle.
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
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170768"
---
# <a name="create-measures-from-templates"></a>Mõõtude loomine mallidest

Kasutage nende loomiseks tavaliselt kasutatavate [mõõtude](measures.md) eelmääratletud malle. Mallid põhinevad olemi *Ühendatud tegevus* kaardistatud andmetele. Seega veenduge, et olete konfigureerinud [klienditegevused](activities.md) enne malli põhjal mõõtühiku loomist.

Mõõtmalle toetatakse ainult üksikklientidele mõeldud **keskkondades**. Kohandatud mõõtude või B-B jaoks mõõtude loomise kohta leiate teavet teemast [Mõõtude koostaja kasutamine](measure-builder.md).

Saadaval mõõdumallid:
- Keskmine tehingu väärtus (ATV)
- Tehingu väärtus kokku
- Päeva keskmine tulu
- Kuu keskmine tulu
- Aasta keskmine tulu
- Kannete arv
- Teenitud püsikliendipunktid
- Lunastatud püsikliendipunktid
- Püsikliendipunktide saldo
- Aktiivse kliendi eluiga
- Püsikliendi liikmestaatuse kestus
- Aega viimasest ostust

## <a name="build-a-new-measure-using-a-template"></a>Uue mõõdu koostamine malli abil

1. Avage **Mõõdud**.

1. Valige **Uus** ja seejärel **Vali mall**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Rippmenüü ekraanipilt uue mõõtühiku loomisel malli esiletõstmisega.":::

1. Leidke teie vajadusele sobiv mall ja valige **Valige mall**.

1. Vaadake nõutavad andmed läbi ja valige **Alustamine**, kui kõik andmed on olemas.

1. Valige **Redigeeri üksikasju** valiku Mõõda nime kõrval. Sisestage mõõdu nimi. Soovi korral lisage [mõõdule sildid](work-with-tags-columns.md#manage-tags).

   :::image type="content" source="media/measures_edit_details.png" alt-text="Dialoogiboks Üksikasjade redigeerimine.":::

1. Valige nupp **Valmis**.

1. Määratlege **jaotises Ajaperioodi** määramine andmete ajavahemik. Valige, kas soovite uue näitaja abil hõlmata kogu andmekogumi, valides suvandi **Kogu aeg** või soovite, et näitaja keskenduks **Kindlale ajaperioodile**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Kuvatõmmis ajavahemiku jaotisest, kui konfigureerite malli põhjal mõõtmise.":::

1. Järgmises jaotises valige **Lisa andmed**, et valida tegevused ja kaardistada oma olemi *Ühendatud tegevus* vastavad andmed.

    1. 1. etapp: valige jaotises **Tegevuse tüüp** selle olemi tüüp, mida soovite kasutada. Valige väljal **Tegevused** olemid, mida soovite vastendada, ja seejärel valige **Edasi**.
    1. 2. etapp: valige atribuut olemist *Ühendatud Tegevus* valemiga nõutava komponendi jaoks. Näiteks keskmise tehingu väärtuse puhul on see atribuut, mis tähistab tehingu väärtust. Valige tegevuse ajatempli **jaoks** olemi Unified *Activity* atribuut, mis tähistab tegevuse kuupäeva ja kellaaega.
    1. Valige **Salvesta**.

    Kui andmete vastendamine õnnestub, kuvatakse **olek Lõpetatud** ning vastendatud tegevuste ja atribuutide nimi.

1. Mõõdu tulemite arvutamiseks valige **Käivita**. Valige **Käsk Salvesta mustand,** kui soovite praeguse konfiguratsiooni säilitada ja mõõdu hiljem käivitada. Kuvatakse **leht Mõõdud**.

## <a name="next-step"></a>Järgmine etapp

Kasutage kliendisegmendi loomiseks [olemasolevaid mõõtühikuid](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
