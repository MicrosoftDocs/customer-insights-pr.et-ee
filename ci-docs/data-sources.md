---
title: Andmeallikate ülevaade
description: Vaadake, kuidas importida või alla neelata andmeid erinevatest allikatest.
ms.date: 09/29/2022
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
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610047"
---
# <a name="data-sources-overview"></a>Andmeallikate ülevaade

Dynamics 365 Customer Insights pakub ühendusi, et tuua andmeid paljudest allikatest. Andmeallikaga ühendamist nimetatakse sageli *andmete sisestamiseks*. Pärast andmete allaneelamist saate [ühendada](data-unification.md), luua ülevaateid ja aktiveerida andmeid isikupärastatud kasutuskogemuste loomiseks.

## <a name="add-or-edit-data-sources"></a>Andmeallikate lisamine või redigeerimine

Andmeallikaid saate Manustada või importida Customer Insightsi. Allolevad lingid annavad juhiseid andmeallikate lisamiseks ja redigeerimiseks.

**Kinnitage andmeallikas**

Kui teil on andmeid ette valmistatud mõnes Microsofti Azure’i andmeteenuses, saab Customer Insights hõlpsasti andmeallikas ühenduse luua, ilma et peaksite andmeid uuesti alla neelama. Valige üks järgmistest suvanditest.
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

Andmeallikaid saab värskendada automaatse ajakava järgi või soovi korral käsitsi. [Kohapealsed andmeallikad](connect-power-query.md#add-data-from-on-premises-data-sources) värskendavad oma ajakavasid, mis on seadistatud andmete allaneelamise ajal. Tõrkeotsingu näpunäiteid leiate teemast [PPDF-põhise Power Query tõrkeotsing andmeallikas värskendusprobleeme](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

Manustatud andmeallikate puhul tarbib allaneelamine uusimaid andmeid, mis on sellest andmeallikas kättesaadavad.

Avage **Jaotis Haldussüsteemi** > **·** > [**ajakava**](schedule-refresh.md), et konfigureerida allaneelatud andmeallikate süsteemi ajastatud värskendusi.

Andmeallikas värskendamiseks nõudmisel tehke järgmist.

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige andmeallikas, mida soovite värskendada, ja valige **Värskenda**. Andmeallika jaoks käivitatakse nüüd käsitsivärskendamine. Andmeallika värskendamine uuendab nii olemiskeemi kui ka kõigi andmeallikas määratud olemite andmeid.

1. Valige olek, et avada edenemise **üksikasjade** paan ja vaadata edenemist. Töö tühistamiseks valige **paani allosas käsk Tühista töö**.

## <a name="corrupt-data-sources"></a>Rikutud andmeallikad

Allaneelatavatel andmetel võivad olla rikutud kirjed, mis võivad põhjustada andmete allaneelamise protsessi tõrgete või hoiatustega.

> [!NOTE]
> Kui andmete allaneelamine lõpeb vigadega, jäetakse järgnev töötlemine (nt ühendamine või tegevuse loomine), mis kasutab seda andmeallikas, vahele. Kui allaneelamine lõpeb hoiatustega, jätkub edasine töötlemine, kuid mõnda kirjet ei pruugita lisada.

Neid vigu võib näha ülesande üksikasjades.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Ülesande üksikasjad, mis näitavad rikutud andmete viga.":::

Rikutud kirjed kuvatakse süsteemi loodud olemites.

### <a name="fix-corrupt-data"></a>Vigaste andmete parandamine

1. Rikutud andmete vaatamiseks minge jaotisse **Andmeüksused** > **ja** otsige jaotisest **Süsteem** rikutud olemeid. Korrumpeerunud üksuste nimetamise skeem: "DataSourceName_EntityName_corrupt".

1. Valige rikutud olem ja seejärel **vahekaart Andmed**.

1. Tuvastage kirje rikutud väljad ja põhjus.

   :::image type="content" source="media/corruption-reason.png" alt-text="Korruptsiooni põhjus." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Andmeüksused** > **kuvavad** ainult osa rikutud kirjetest. Kõigi rikutud kirjete vaatamiseks eksportige failid salvestuskonto konteinerisse, kasutades [Customer Insightsi ekspordiprotsessi](export-destinations.md). Kui kasutasite oma salvestusruumikontot, saate vaadata ka oma salvestusruumikonto kausta Customer Insights.

1. Parandage rikutud andmed. Näiteks Azure Data Lake’i andmeallikate [puhul parandage andmed Andmejärve salvestusruumis või värskendage faili](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data) manifest/model.json andmetüüpe. Andmeallikate puhul Power Query parandage lähtefailis olevad andmed ja [parandage andmetüüpi teisendusetapp](connect-power-query.md#data-type-does-not-match-data) lehel **Power Query - Päringute** redigeerimine.

Pärast järgmise andmeallikas värskendamist antakse parandatud kirjed customer Insights'ile üle ja edastatakse järgmistele protsessidele.

Näiteks veeru "sünnipäev" andmetüübiks on seatud "kuupäev". Kliendikirjel on sisestatud sünnipäev "01/01/19777". Süsteem märgib selle kirje korrumpeerunuks. Muutke lähtesüsteemis sünnipäev väärtuseks "1977". Pärast andmeallikate automaatset värskendamist on väljal nüüd kehtiv vorming ja kirje eemaldatakse rikutud olemist.

[!INCLUDE [footer-include](includes/footer-banner.md)]
