---
title: Andmeallikate ülevaade
description: Vaadake, kuidas importida või alla neelata andmeid erinevatest allikatest.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6ab97c535454e84c1bb18aca00bca2568eb65a2a
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207086"
---
# <a name="data-sources-overview"></a>Andmeallikate ülevaade

Dynamics 365 Customer Insights pakub ühendusi, et tuua andmeid paljudest allikatest. Andmeallikaga ühendamist nimetatakse sageli *andmete sisestamiseks*. Pärast andmete allaneelamist saate [ühendada](data-unification.md), luua ülevaateid ja aktiveerida andmeid isikupärastatud kasutuskogemuste loomiseks.

## <a name="add-or-edit-data-sources"></a>Andmeallikate lisamine või redigeerimine

Andmeallikaid saate Manustada või importida Customer Insightsi. Allolevad lingid annavad juhiseid andmeallikate lisamiseks ja redigeerimiseks.

**Kinnitage andmeallikas**

Kui teil on andmeid ette valmistatud mõnes Microsofti Azure'i andmeteenuses, saab Customer Insights hõlpsasti andmeallikas ühenduse luua, ilma et peaksite andmeid uuesti alla neelama. Valige üks järgmistest suvanditest.
- [Azure Data Lake Storage(csv- või parketifailid kaustas Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics(Järve andmebaasid)](connect-synapse.md)
- [Microsoft Dataverse andmejärv](connect-dataverse-managed-lake.md)

**Importimine ja teisendamine**

Kui kasutate asutusesiseseid andmeallikaid, Microsofti või kolmanda osapoole andmeid, importige ja teisendage andmed konnektorite abil Power Query.
- [Power Query Pistikud](connect-power-query.md)

## <a name="review-data-sources"></a>Andmeallikate ülevaatamine

Kui teie keskkond oli konfigureeritud kasutama Customer Insightsi salvestusruumi ja kasutate asutusesiseseid andmeallikaid, kasutate Power Platform andmevooge. Andmevoogude abil Power Platform saate vaadata ühisandmeallikaid ja teiste hallatavaid andmeallikaid. Lehel **Andmeallikad** on andmeallikad loetletud kolmes jaotises.
- **Ühiskasutuses**: andmeallikad, mida saavad hallata kõik Customer Insightsi administraatorid. Power Platform andmevood, teie enda salvestusruumikonto ja manustamine hallatavale andmejärvele Dataverse on näited jagatud andmeallikatest.
- **Minu** hallatav: Power Platform andmevood, mille olete loonud ja mida haldate ainult teie. Teised Customer Insightsi administraatorid saavad neid andmevooge ainult vaadata, kuid mitte neid redigeerida, värskendada ega kustutada.
- **Haldavad teised**: Power Platform teiste administraatorite loodud andmevood. Saate neid ainult vaadata. Selles on loetletud andmevoo omanik, kellega abi saamiseks ühendust võtta.
> [!NOTE]
> Kõik olemid saavad vaadata ja kasutada teised kasutajad. Kuigi andmeallikad kuuluvad kasutajale, kes need lõi, saavad andmete allaneelamisest tulenevaid üksusi kasutada kõik Customer Insightsi kasutajad.

Kui teie keskkond ei kasuta Power Platform andmevooge, **sisaldab leht Andmeallikad** ainult kõigi andmeallikate loendit. Sektsioone ei kuvata.

## <a name="manage-existing-data-sources"></a>Olemasolevate andmeallikate haldamine

Avage **Andmeallikad** > **·**, et vaadata iga allaneelatud andmeallikas nime, olekut ja viimast korda, millal selle allika andmeid värskendati. Andmeallikate loendit saate sortida mis tahes veeru järgi või kasutada otsinguvälja, et leida andmeallikas, mida soovite hallata.

Valige saadaolevate toimingute vaatamiseks andmeallikas.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Andmeallikas lisatud.":::

- [**Redigeerige**](#add-or-edit-data-sources) andmeallikas, et muuta selle atribuute.
- [**Värskendage**](#refresh-data-sources) andmeallikas, et lisada uusimad andmed.
- [**Rikastage**](data-sources-enrichment.md) andmeallikas enne ühendamist.
- **Kustutage** andmeallikas. Andmeallikas saab kustutada ainult siis, kui andmeid ei kasutata üheski töötlemises, nagu ühendamine, ülevaated, aktiveerimised või eksportimine.

## <a name="refresh-data-sources"></a>Andmealilkate värskendamine

Andmeallikaid saab värskendada automaatse ajakava järgi või soovi korral käsitsi. [Kohapealsed andmeallikad](connect-power-query.md#add-data-from-on-premises-data-sources) värskendavad oma ajakavasid, mis on seadistatud andmete allaneelamise ajal. Manustatud andmeallikate puhul tarbib allaneelamine uusimaid andmeid, mis on sellest andmeallikas kättesaadavad.

Avage **Jaotis Haldussüsteemi** > **·** > [**ajakava**](system.md#schedule-tab), et konfigureerida allaneelatud andmeallikate süsteemi ajastatud värskendusi.

Andmeallikas värskendamiseks nõudmisel tehke järgmist.

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige andmeallikas, mida soovite värskendada, ja valige **Värskenda**. Andmeallika jaoks käivitatakse nüüd käsitsivärskendamine. Andmeallika värskendamine uuendab nii olemiskeemi kui ka kõigi andmeallikas määratud olemite andmeid.

1. Valige olek, et avada edenemise **üksikasjade** paan ja vaadata edenemist. Töö tühistamiseks valige **paani allosas käsk Tühista töö**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
