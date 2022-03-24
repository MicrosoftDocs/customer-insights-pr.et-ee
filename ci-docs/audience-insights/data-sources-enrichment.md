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
ms.openlocfilehash: 56f6a8ad20224922f9968f0ad3b6a0e0a400214b
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376574"
---
# <a name="enrichment-for-data-sources-preview"></a>Andmeallikate rikastamine (eelvaade)

Kasutage andmeid sellistest allikatest nagu Microsoft ja teised partnerid, et rikastada oma kliendiandmeid enne andmete ühendamist. Andmeallikas rikastamine aitab luua suuremat andmete täielikkust ja kvaliteeti, mis aitab pärast andmete ühendamist saavutada paremaid tulemusi. Näiteks normaliseeritud ja standardiseeritud vormingu kasutamine aadresside jaoks suurendab mängu tulemuste kvaliteeti. Toetatud rikastamiste loendi leiate teemast [Toetatud andmeallikas rikastamissuvandid](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Rikastage andmeallikas

Rikastamiste loomiseks või redigeerimiseks peavad teil olema kaasautori või administraatori õigused. Lisateavet vt teemast [Õigused](permissions.md).  

1. Avage veebisait **DataUniify** > **·**. Valige olem, mida soovite rikastada, ja valige olemi esmaseks võtmeks üks atribuut. Lisateavet leiate teemast [Primaarvõtme valimine](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Avage suvandid **Andmed** > **Andmeallikad**.
 
1. Valige andmeallikas kõrval vertikaalne kolmikpunkt, mida soovite rikastada, ja valige **Rikasta**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Andmeallikate rikastamise leht.":::

   Vahekaardil **Avasta** kuvatakse [toetatud andmeallikas rikastamise suvandid](#supported-data-source-enrichments).

1. Andmeallikas rikastamise konfigureerimiseks valige **Rikasta minu andmeid**. Väljundolemi nimi täidetakse automaatselt.

## <a name="supported-data-source-enrichments"></a>Toetatud andmeallikas rikastamised

Andmeallikate jaoks on praegu saadaval järgmised rikastamised. Vaadake üle rikastamise üksikasjalikud juhised, et teada saada, kuidas seda konfigureerida.

- [Täiustatud aadressid](enrichment-enhanced-addresses.md)
- [Täiustatud ettevõtte andmed](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>Olemasolevate andmeallikas rikastamiste haldamine

Minge vahekaardile **Minu rikastused**, et näha kõiki konfigureeritud rikastusi.

Valige rikastus, et näha saadaolevaid suvandeid. Valikute nägemiseks võite loendikirjel valida ka ellipsi (...). Kui konfigureerite mitu rikastustegurit, saate selle kiiresti leidmiseks kasutada otsinguvälja.

Saate vaadata, redigeerida, käivitada või kustutada andmeallikas rikastamist. Lisateavet leiate teemast [Olemasolevate rikastamiste](enrichment-hub.md) haldamine.
