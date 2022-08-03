---
title: Andmeallikate rikastamine (eelvaade)
description: Rikastage andmeallikaid enne andmete ühendamise protsessi läbimist.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 98e9e330e7ef9cf085caa94a506fa788cebdd67b
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207178"
---
# <a name="enrichment-for-data-sources-preview"></a>Andmeallikate rikastamine (eelvaade)

Kasutage kliendiandmete rikastamiseks enne andmete ühendamist sellistest allikatest nagu Microsoft ja muud partnerid pärinevaid andmeid. Andmeallikas rikastamine aitab luua suuremat andmete täielikkust ja kvaliteeti, mis võib aidata saavutada paremaid tulemusi, kui olete oma andmed ühendanud. Näiteks normaliseeritud ja standardiseeritud aadressivormingu kasutamine suurendab vaste tulemuste kvaliteeti. Toetatud rikastumiste loendi leiate teemast [Toetatud andmeallikas rikastamisvõimalused](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Rikastage andmeallikas

Rikastuste loomiseks või redigeerimiseks peavad teil olema kaasautori või administraatori [õigused](permissions.md).  

1. Avage **Jaotis Andmete** > **ühendamine**. Valige olem, mida soovite rikastada, ja valige olemi primaarvõtmeks [üks](map-entities.md#select-primary-key-and-semantic-type-for-attributes) atribuut.

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige rikastatava andmeallikas kõrval vertikaalne kolmikpunkt (&vellip;) ja valige **Rikasta**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="Andmeallikate leht, kus on esile tõstetud rikastamine":::

   Menüüs **Discover** kuvatakse [toetatud andmeallikas rikastamissuvandid](#supported-data-source-enrichments).

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Andmeallikate rikastamise leht.":::

1. Andmeallikas rikastamise konfigureerimiseks valige **Rikasta minu andmeid**. Väljundolemi nimi täidetakse automaatselt.

## <a name="supported-data-source-enrichments"></a>Toetatud andmeallikas rikastamine

Andmeallikate kohta on praegu saadaval järgmised rikastamised. Vaadake rikastamise üksikasjalikud sammud üle, et teada saada, kuidas seda konfigureerida.

- [Täiustatud aadressid](enrichment-enhanced-addresses.md)
- [Täiustatud ettevõtte andmed](enrichment-enhanced-company-data.md)
- [Identiteediandmed LiveRampist](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Olemasolevate andmeallikas rikastumiste haldamine

Avage **Andmed** > **Rikastamine**. **Vahekaardil Minu rikastamised** saate vaadata konfigureeritud rikastamisi, nende olekut, rikastatud klientide arvu ja viimast korda, kui andmeid värskendati. Rikastamiste loendit saate sortida mis tahes veeru järgi või kasutada otsingukasti, et leida rikastus, mida soovite hallata.

Valige rikastus, et näha saadaolevaid suvandeid. Valikute nägemiseks saate loendiüksusel valida ka vertikaalse kolmikpunkti (&vellip;).

Saate vaadata, redigeerida, käivitada või kustutada andmeallikas rikastamist. Lisateavet vaadake jaotisest [Olemasolevate rikastuste](enrichment-hub.md#manage-existing-enrichments) haldamine.
