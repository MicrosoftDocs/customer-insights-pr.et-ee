---
title: Ettevõtteprofiilide rikastamine kolmanda osapoole rikastamisteenusega Leadspace'ilt
description: Üldine teave Leadspace'i kolmanda osapoole rikastamise kohta.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269417"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Ettevõtte profiilide rikastamine Leadspace'iga (eelvaade)

Leadspace on andmeteaduse ettevõte, mis pakub kliendi hulgiandmete platvormi. See võimaldab ettevõtetel kliendi koondprofiilidega klientide andmeid rikastada. Rikastamised hõlmavad lisaatribuute, nt ettevõtte suurus, asukoht, valdkond jne.

## <a name="prerequisites"></a>Eeltingimused

Leadspace'i seadistamiseks peavad olema täidetud järgmised eeltingimused.

- Teil on aktiivne Leadspace'i litsents ja „igavene võti“ (edaspidi **Leadspace'i tõend**). Nende toote kohta üksikasjade saamiseks võtke otse [Leadspace’iga](https://www.leadspace.com/products/leadspace-on-demand/) ühendust.
- Teil on [administraatori](permissions.md#administrator) õigused.
- Teil on ettevõtete [kliendi koondprofiilid](customer-profiles.md).

## <a name="configuration"></a>Konfiguratsioon

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Rikastamine**.

1. Valige Leadspace’i paanil suvand **Rikasta minu andmeid**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace'i paani kuvatõmmis.":::

1. Valige **Alusta** ja seejärel sisestage aktiivne **Leadspace'i tõend** (igavene võti). Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**. Kinnitage mõlemad sisendid, valides **Loo ühendus Leadspace'iga**.

1. Valige **Vastenda andmed** ja valige andmete kogum, mida soovite Leadspace'i ettevõtte andmetega rikastada. Saate valida olemi *Klient*, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Valige kliendiprofiili ja segmendi rikastamise vahel.":::

1. Klõpsake suvandit **Edasi** ja määratlege, milliseid teie koondatud profiilide välju tuleks kasutada, et otsida ühtivad andmeid Leadspace'ist. Nõutav on väli **Ettevõtte nimi**. Selleks et vasted oleksid täpsemad, saab lisada kuni kaks muud välja (**Ettevõtte veebisait** ja **Ettevõtte asukoht**).

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace'i väljade vastendamise paan.":::
   
1. Valige **Rakenda**, et lõpetada väljade vastendamine.

1. Valige ettevõtte profiilide rikastamiseks **Käivita**. Rikastamise kestus sõltub koondatud kliendiprofiilide arvust.

## <a name="enrichment-results"></a>Rikastamise tulemused

Pärast rikastamise värskendamist saate värskelt rikastatud ettevõtte andmed üle vaadata jaotises [Minu rikastamised](enrichment-hub.md). Kuvatakse viimase värskendamise aeg ja rikastatud profiilide arvu.

Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.

Lisateavet leiate teemast [Leadspace'i API-d](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Järgmised etapid

Rikastatud kliendiandmetele toetumine. Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [Ekspordi andmed](export-destinations.md).

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Leadspace'i andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Leadspace täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]