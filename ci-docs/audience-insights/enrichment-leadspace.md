---
title: Ettevõtteprofiilide rikastamine kolmanda osapoole rikastamisteenusega Leadspace'ilt
description: Üldine teave Leadspace'i kolmanda osapoole rikastamise kohta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 34b73b37670ed45e2c31ea164c0788b793bee433829ce21317c83903f3fca1fe
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031698"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Ettevõtte profiilide rikastamine Leadspace'iga (eelvaade)

Leadspace on andmeteaduse ettevõte, mis pakub kliendi hulgiandmete platvormi. See võimaldab ettevõtetel kliendi koondprofiilidega klientide andmeid rikastada. Rikastused sisaldavad rohkem atribuute, nagu ettevõtte suurus, asukoht, tegevusala ja palju muud.

## <a name="prerequisites"></a>Eeltingimused

Leadspace'i seadistamiseks peavad olema täidetud järgmised eeltingimused.

- Teil on aktiivne Leadspace litsents.
- Teil on ettevõtete [kliendi koondprofiilid](customer-profiles.md).
- Administraator on juba konfigureerinud Leadspace'i ühenduse või teil on [administraatoriõigused](permissions.md#administrator) ja "alaline võti (nimetatakse **Leadspace tokeniks**). Võtke [Leadspaceiga](https://www.leadspace.com/products/leadspace-on-demand/) otse ühendust toodete üksikasjade teabe saamiseks.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Rikastamine**.

1. Valige **Mu andmete rikastamine** Leadspace paanil ja valige **Alustamine**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace'i paani kuvatõmmis.":::

1. Valige [ühendus](connections.md) ripploendist. Kui ühendusi pole saadaval, pöörduge administraatori poole. Kui olete administraator, saate ühenduse luua, kui valite suvandi **Lisa ühendus** ja valides **Leadspace**. 

1. Valige **Ühenda Leadspace**, et kinnitada ühendus.

1. Valige **Edasi** ja valige **Kliendi andmekomplekt**, mida soovite rikastada ettevõtte andmetega Leadspace'ilt.. Saate valida olemi **Klient**, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendiandmete kogumi valimisel.":::

1. Valige **Edasi** ja määratlege, millist tüüpi välju teie ühendatud profiilidest tuleks kasutada Leadspace ettevõtete andmete vastavuse otsimiseks. Nõutav on väli **Ettevõtte nimi**. Selleks et vasted oleksid täpsemad, saab lisada kuni kaks muud välja (**Ettevõtte veebisait** ja **Ettevõtte asukoht**).

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace'i väljade vastendamise paan.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Sisestage rikastamiseks nimi ja valige **Salvesta rikastamine** pärast valikute läbivaatamist.


## <a name="configure-the-connection-for-leadspace"></a>Konfigureerige ühendus Leadspace'iga 

Ühenduste konfigureerimiseks peate olema administraator. Valige **Lisa ühendus** rikastamise konfigureerimisel *või* minge **Administraator** > **Ühendused** ja valige **Seadista** Leadspace paanil.

1. Seejärel valige suvand **Alustamine**. 

1. Sisestage ühenduse nimi **Kuvatav nimi** väljale.

1. Sisestage kehtiv Leadspace token.

1. Vaadake üle ja esitage oma nõusolek **Andmete privaatsuse ja nõuetele vastavus** kohta, valides suvandi **Nõustun**.

1. Valige **Kontrolli** konfiguratsiooni valideerimiseks.

1. Pärast kontrollimise lõpuleviimist valige **Salvesta**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace ühenduse konfiguratsiooni leht.":::

## <a name="enrichment-results"></a>Rikastamise tulemused

Pärast rikastamise värskendamist saate värskelt rikastatud ettevõtte andmed üle vaadata jaotises [Minu rikastamised](enrichment-hub.md). Kuvatakse viimase värskendamise aeg ja rikastatud profiilide arvu.

Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.

Lisateavet leiate teemast [Leadspace'i API-d](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Järgmised etapid

Rikastatud kliendiandmetele toetumine. Looge [segmente](segments.md) ja [näitajaid](measures.md) ning isegi [eksportige andmed](export-destinations.md), et pakkuda oma klientidele isikupärastatud kogemust.

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Leadspace'i andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Leadspace täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insights administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
