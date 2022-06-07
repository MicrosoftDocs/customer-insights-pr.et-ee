---
title: Andmeallikas rikastamine
description: Rikastage andmeallikaid enne andmete ühendamise protsessi läbimist.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 1225482c4bf432ed747537b2c9bec9ab0e692a51
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800276"
---
# <a name="enrichment-for-data-sources-preview"></a>Andmeallikate rikastamine (eelvaade)

Kasutage andmeid sellistest allikatest nagu Microsoft ja teised partnerid, et rikastada oma kliendiandmeid enne andmete ühendamist. Andmeallikas rikastamine aitab saavutada suuremat andmete täielikkust ja kvaliteeti, mis aitab saavutada paremaid tulemusi pärast andmete ühendamist. Näiteks normaliseeritud ja standardiseeritud vormingu kasutamine aadresside jaoks suurendab mängu tulemuste kvaliteeti. Toetatud rikastamiste loendi leiate teemast [Toetatud andmeallikas rikastamissuvandid](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Rikastage andmeallikas

Rikastamiste loomiseks või redigeerimiseks peavad teil olema kaasautori või administraatori õigused. Lisateavet vt teemast [Õigused](permissions.md).  

1. **Avage jaotisSe Andmete** > **ühendamine**. Valige olem, mida soovite rikastada, ja valige olemi esmaseks võtmeks üks atribuut. Lisateavet leiate teemast [Primaarvõtme valimine](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige selle andmeallikas kõrval vertikaalne kolmikpunkt (&vellip;), mida soovite rikastada, ja valige **Rikasta**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Andmeallikate rikastamise leht.":::

   Vahekaardil **Avasta** kuvatakse [toetatud andmeallikas rikastamise suvandid](#supported-data-source-enrichments).

1. Andmeallikas rikastamise konfigureerimiseks valige **Rikasta minu andmeid**. Väljundolemi nimi täidetakse automaatselt.

## <a name="supported-data-source-enrichments"></a>Toetatud andmeallikas rikastamised

Andmeallikate jaoks on praegu saadaval järgmised rikastamised. Vaadake üle rikastamise üksikasjalikud juhised, et teada saada, kuidas seda konfigureerida.

- [Täiustatud aadressid](enrichment-enhanced-addresses.md)
- [Täiustatud ettevõtte andmed](enrichment-enhanced-company-data.md)
- [LiveRampi identiteediandmed](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Olemasolevate andmeallikas rikastamiste haldamine

Minge vahekaardile **Minu rikastused**, et näha kõiki konfigureeritud rikastusi.

Valige rikastus, et näha saadaolevaid suvandeid. Suvandite nägemiseks saate loendiüksusel valida ka vertikaalse kolmikpunkti (&vellip;). Kui konfigureerite mitu rikastustegurit, saate selle kiiresti leidmiseks kasutada otsinguvälja.

Saate vaadata, redigeerida, käivitada või kustutada andmeallikas rikastamist. Lisateavet leiate teemast [Olemasolevate rikastamiste](enrichment-hub.md) haldamine.
