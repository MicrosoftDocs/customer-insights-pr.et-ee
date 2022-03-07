---
title: Andmeallikas rikastamine
description: Rikastage andmeallikaid enne andmete ühendamise protsessi läbimist.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: eebaaf18795e80dd1ba16a15a23844d685c94c6e
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373058"
---
# <a name="enrichment-for-data-sources-preview"></a>Andmeallikate rikastamine (eelvaade)

Kasutage andmeid allikatest nagu Microsoft ja teised partnerid, et rikastada oma kliendiandmeid enne andmete ühendamist. Andmeallikas rikastamine aitab saavutada suuremat andmete täielikkust ja kvaliteeti, mis aitab saavutada paremaid tulemusi, kui olete oma andmed ühendanud. Näiteks normaliseeritud ja standardiseeritud vormingu kasutamine aadresside jaoks suurendab mängu tulemuste kvaliteeti. Toetatud rikastamise loendi leiate teemast [Toetatud andmeallikas rikastamissuvandid](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Rikastage andmeallikas

Rikastumise loomiseks või redigeerimiseks peavad teil olema kaasautori või administraatori õigused. Lisateavet vt teemast [Õigused](permissions.md).  

1. **Avage dataUnify** > **·**. Valige olem, mida soovite rikastada, ja valige olemi primaarvõtmeks üks atribuut. Lisateavet vt teemast [Select primary key](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Avage suvandid **Andmed** > **Andmeallikad**.
 
1. Valige rikastatava andmeallikas kõrval vertikaalne ellipsis ja valige **Rikasta**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Andmeallikate rikastamise leht.":::

   Vahekaardil **Avasta** kuvatakse [toetatud andmeallikas rikastamissuvandid](#supported-data-source-enrichments).

1. Andmeallikas rikastamise konfigureerimiseks valige **Rikasta minu andmeid**. Väljundolemi nimi asustutakse automaatselt.

## <a name="supported-data-source-enrichments"></a>Toetatud andmeallikas rikastamine

Andmeallikate jaoks on praegu saadaval järgmised rikastamised. Vaadake üle rikastamise üksikasjalikud juhised, et teada saada, kuidas seda konfigureerida.

- [Täiustatud aadressid](enrichment-enhanced-addresses.md)
- [LiveRampi identiteediandmed](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Olemasolevate andmeallikas rikastamise haldamine

Minge vahekaardile **Minu rikastused**, et näha kõiki konfigureeritud rikastusi.

Valige rikastus, et näha saadaolevaid suvandeid. Valikute nägemiseks võite loendikirjel valida ka ellipsi (...). Kui konfigureerite mitu rikastustegurit, saate selle kiiresti leidmiseks kasutada otsinguvälja.

Saate andmeallikas rikastamist vaadata, redigeerida, käitada või kustutada. Lisateavet vt teemast [Manage olemasolevate rikastuste.](enrichment-hub.md)
