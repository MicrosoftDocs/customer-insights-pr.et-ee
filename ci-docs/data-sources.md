---
title: Andmeallikate kasutamine andmete valmendamiseks
description: Vaadake, kuidas eri allikatest andmeid importida.
ms.date: 05/31/2022
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
ms.openlocfilehash: e22977107565a0b28b74f41576a1c7ccc74f6dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011744"
---
# <a name="data-sources-overview"></a>Andmeallikate ülevaade

Dynamics 365 Customer Insights pakub ühendusi, et tuua andmeid paljudest allikatest. Andmeallikaga ühendamist nimetatakse sageli *andmete sisestamiseks*. Pärast andmete allaneelamist saate [isikupärastatud kasutuskogemuste loomiseks andmeid ühendada](data-unification.md), luua ülevaateid ja aktiveerida.

## <a name="add-data-sources"></a>Andmeallikate lisamine

Andmeallikaid saate manustada või importida Customer Insightsi. Alltoodud lingid annavad juhiseid andmeallikate lisamiseks.

**andmeallikas manustamine**

Kui teil on mõnes Microsofti Azure'i andmeteenuses koostatud andmed, saab Customer Insights hõlpsalt andmeallikas ühenduse luua, ilma et peaksite andmeid uuesti alla neelama. Valige üks järgmistest suvanditest.
- [Azure Data Lake Storage(csv- või parkettfailid kaustas Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics(Järve andmebaasid)](connect-synapse.md)
- [Microsoft Dataverse data lake](connect-dataverse-managed-lake.md)

**Importimine ja teisendamine**

Kui kasutate kohapealseid andmeallikaid, Microsofti või kolmanda osapoole andmeid, importige ja teisendage andmed konnektorite abil Power Query.
- [Power Query Pistikud](connect-power-query.md)

## <a name="review-data-sources"></a>Andmeallikate ülevaatamine

Kui teie keskkond konfigureeriti kasutama Customer Insightsi salvestusruumi ja kasutate kohapealseid andmeallikaid, kasutate Power Platform andmevooge. Andmevoogude abil Power Platform saate vaadata teiste hallatavaid ühisandmeallikaid ja andmeallikaid. Lehel **Andmeallikad** on andmeallikad loetletud kolmes jaotises.
- **Ühiskasutuses**: andmeallikad, mida saavad hallata kõik Customer Insightsi administraatorid. Power Platform andmevood, teie enda salvestuskonto ja hallatava andmejärve Dataverse külge kinnitamine on näited jagatud andmeallikatest.
- **Minu hallatav**: Power Platform andmevood, mille on loonud ja hallanud ainult teie. Teised Customer Insightsi administraatorid saavad vaadata ainult neid andmevooge, kuid mitte neid redigeerida, värskendada ega kustutada.
- **Teiste hallatavad**: Power Platform teiste administraatorite loodud andmevood. Neid saab ainult vaadata. See loetleb andmevoo omaniku, kellega abi saamiseks ühendust võtta.
> [!NOTE]
> Kõiki olemeid saavad vaadata ja kasutada teised kasutajad. Kuigi andmeallikad kuuluvad kasutajale, kes need lõi, saavad andmete allaneelamisest saadud olemeid kasutada kõik Customer Insightsi kasutajad.

Kui teie keskkond ei kasuta Power Platform andmevooge, **sisaldab leht Andmeallikad** ainult kõigi andmeallikate loendit. Jaotisi ei kuvata.

Minge **andmeallikatesse** > **·**, et vaadata iga allaneelatud andmeallikas nime, olekut ja viimast korda, kui andmeid selle allika jaoks värskendati. Saate andmeallikate loendit iga veeru järgi sortida.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Andmeallikas lisatud.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Andmete laadimine võib võtta aega. Pärast edukat värskendamist saab lisatud andmeid vaadata lehel **Olemid**. Lisateavet vt jaotisest [Olemid](entities.md).

## <a name="refresh-data-sources"></a>Andmealilkate värskendamine

Andmeallikaid saab värskendada automaatse ajakava järgi või soovi korral käsitsi. [Kohapealsed andmeallikad](connect-power-query.md#add-data-from-on-premises-data-sources) värskendatakse oma ajakavades, mis seadistatakse andmete allaneelamise ajal. Manustatud andmeallikate puhul tarbib andmete allaneelamine selle andmeallikas uusimaid andmeid.

**·** > **Allaneelatud andmeallikate süsteemi ajastatud värskenduste konfigureerimiseks avage administraatori ajakava** > [**·**](system.md#schedule-tab).

Andmeallika värskendamiseks mis tahes ajal toimige järgmiselt.

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige värskendatava andmeallikas kõrval vertikaalne kolmikpunkt (&vellip;) ja valige ripploendist **Värskenda**. Andmeallika jaoks käivitatakse nüüd käsitsivärskendamine. Andmeallika värskendamine uuendab nii olemiskeemi kui ka kõigi andmeallikas määratud olemite andmeid.

1. Kui soovite olemasoleva värskendamise tühistada, klõpsake **Lõpeta värskendamine** ja andmeallikas taastatakse viimase värskendamise olekusse.

## <a name="delete-a-data-source"></a>Andmeallika kustutamine

Andmeallikas saab kustutada ainult siis, kui andmeid ei kasutata üheski töötlemises (nt ühendamises, ülevaates, aktiveerimises või ekspordis).

1. Avage suvandid **Andmed** > **Andmeallikad**.

2. Valige eemaldatava andmeallikas kõrval vertikaalne kolmikpunkt (&vellip;) ja valige rippmenüüst Käsk **Kustuta**.

3. Kinnitage, et soovite kustutada.


[!INCLUDE [footer-include](includes/footer-banner.md)]
