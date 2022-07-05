---
title: Ettevõtte profiilide rikastamine müügivihjeruumiga (eelvaade)
description: Üldine teave Leadspace'i kolmanda osapoole rikastamise kohta.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b58532a541ee22a5e34d0af1a3334ccbd53627b2
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082362"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Ettevõtte profiilide rikastamine müügivihjeruumiga (eelvaade)

Leadspace on andmeteadusega tegelev ettevõtte, mis pakub B2B kliendiandmete platvormi. See võimaldab keskkondades, kus on ettevõtetel põhinevad unified kliendiprofiilid, nende andmeid rikastada. Rikastage *Kliendiprofiile* selliste atribuutidega nagu ettevõtte suurus, asukoht või tööstus. Rikastage *Kontaktiprofiile* atribuutidega nagu pealkiri, isik või meili kontrollimine.

## <a name="prerequisites"></a>eeltingimused

- Aktiivne Leadspace'i litsents.
- [Kontodel põhinevad ühtsed kliendiprofiilid](customer-profiles.md).
- Müügivihjeruumi [ühenduse](connections.md) konfigureerib [administraator](#configure-the-connection-for-leadspace). Võtke [Leadspaceiga](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) otse ühendust toodete üksikasjade teabe saamiseks.

## <a name="configure-the-connection-for-leadspace"></a>Konfigureerige ühendus Leadspace'iga

Peate olema Customer Insightsi administraator [ja teil peab olema](permissions.md#admin)"igavene võti" (nimetatakse **müügivihjeruumi loaks**).

1. Valige **rikastamise konfigureerimisel Lisa ühendus** või minge valikule **Administraatoriühendused** > **ja** valige **paanil** Müügivihjeruumi häälestamine.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Leadspace ühenduse konfiguratsiooni leht.":::

1. Sisestage ühenduse nimi ja kehtiv müügivihjeruumi luba.

1. Vaadake üle ja esitage oma nõusolek [Andmete privaatsuse ja nõuetele vastavus](#data-privacy-and-compliance) kohta, valides suvandi **Nõustun**.

1. Konfiguratsiooni kinnitamiseks valige **Kinnita** ja seejärel valige **Salvesta**.

### <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Leadspace'i andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Leadspace täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insights administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **Kopeeri müügivihjeruumi** paanilt ettevõtte andmed ettevõtte andmete **kohta**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Leadspace'i paani kuvatõmmis.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Valige ühendus. Võtke ühendust administraatoriga, kui see pole saadaval.

1. Tehke valik **Edasi**.

1. **Valige kliendi andmestik** ja valige profiil või segment, mida soovite müügivihjeruumi ettevõtte andmetega rikastada. Olem *Klient* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendiandmete kogumi valimisel.":::

1. Määratlege, millist tüüpi välju ühtsetest profiilidest sobitamiseks kasutada: esmane ja/või sekundaarne aadress. Mõlemale aadressile saate määrata välja kaardistamise ja mõlema aadressi profiilid eraldi rikastada. Näiteks kodune aadress ja ettevõtte aadress. Tehke valik **Edasi**.

1. Vastendage oma väljad ettevõtte andmetega Leadspace'ist. Nõutav on väli **Ettevõtte nimi**. Selleks et vasted oleksid täpsemad, saab lisada kuni kaks muud välja (**Ettevõtte veebisait** ja **Ettevõtte asukoht**).

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Leadspace'i väljade vastendamise paan.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Märkige ruut, kui teil on *Kontaktiprofiilid*, mida soovite rikastada. Customer Insights vastendab nõutavad väljad automaatselt.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Müügivihjeruumi kontaktikirjete rikastamine.":::

1. Tehke valik **Edasi**.

1. Sisestage **rikastamise nimi** ja väljundolemi **nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Rikastamisprotsessi alustamiseks või lehele Rikastamine naasmise **lähedal** valige **Käivita**.

## <a name="view-enrichment-results"></a>Rikastamise tulemuste kuvamine

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Lisateavet leiate teemast [Leadspace'i API-d](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
