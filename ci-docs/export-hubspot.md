---
title: Customer Insightsi andmete eksportimine HubSpoti
description: Vaadake, kuidas konfigureerida ühendust ja eksportida HubSpoti.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588926"
---
# <a name="export-segments-to-hubspot-preview"></a>Segmentide eksportimine HubSpoti (eelvaade)

Eksportige ühtsete kliendiprofiilide segmendid HubSpoti ja kasutage neid meiliturunduseks.

## <a name="prerequisites-for-a-connection"></a>Ühenduse eeltingimus

- [HubSpoti konto](https://www.hubspot.com/) ja vastavad administraatori mandaadid.
- [API võti](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) HubSpotilt.
- [Konfigureeritud segmendid](segments.md) Customer Insightsis.

## <a name="known-limitations"></a>Teadaolevad piirangud

- Kuni 100 000 kliendiprofiili ühe ekspordi kohta HubSpoti, mille lõpuleviimiseks võib kuluda kuni 15 minutit. Kliendiprofiilide arv, mida saate HubSpoti eksportida, sõltub ja on piiratud teie lepingust HubSpotiga.
- Ainult segmendid.

## <a name="set-up-connection-to-hubspot"></a>HubSpotiga ühenduse seadistamine

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **ühenduse konfigureerimiseks HubSpot**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma HubSpoti mandaat, kui seda küsitakse.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Valige **Ühenda**, et lähtestada ühendus HubSpotiga.

1. Valige **Lisa mind ekspordikasutajana** ja sisestage oma Customer Insightsi identimisteave.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa eksport**.

1. Valige väljal **Ühendus ekspordiks** jaotisest HubSpot ühendus. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Valige jaotise **Andmete vastendamine** väljal **Meil**, mis esindab kliendi meiliaadressi. Korrake samu samme ka teiste valikuliste väljade puhul.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
