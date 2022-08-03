---
title: Segmentide eksportimine rakendusse Dynamics 365 Sales (eelvaade)
description: Lugege, kuidas konfigureerida ühendust ja eksportida Dynamics 365 Sales'i.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195976"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Segmentide eksportimine rakendusse Dynamics 365 Sales (eelvaade)

Kasutage kliendiandmeid turundusloendite loomiseks, töövoogude järeltegevusteks ja kampaaniate saatmiseks Dynamics 365 Salesi abil.

## <a name="prerequisites"></a>eeltingimused

Enne segmendi eksportimist Customer Insightsist Salesi, peavad kontaktikirjed olema olemas rakenduses Dynamics 365 Sales. Lugege lisateavet selle kohta, kuidas dynamics 365 Salesist [kontakte alla neelata, kasutades Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > Segmentide eksportimine Customer Insightsist salesi ei loo müügieksemplarides uusi kontaktikirjeid. Salesi kontaktikirjed tuleb alla neelata Customer Insightsis ja neid tuleb kasutada andmeallikas. Need tuleb lisada ka ühendatud kliendi olemisse, et vastendada kliendi ID-d ja kontakti ID-deks, enne kui segmente saab eksportida.

## <a name="known-limitations"></a>Teadaolevad piirangud

Eksportimine rakendusse Dynamics 365 Sales on piiratud 100 000 segmendi kohta, mille lõpuleviimiseks võib kuluda kuni 3 tundi.

## <a name="set-up-connection-to-sales"></a>Ühenduse seadistamine müügiga

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Dynamics 365 Sales**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage väljale **Serveri aadress** oma organisatsiooni Salesi URL.

1. Jaotises **Serveri administraatorikonto** valige suvand **Logi sisse** ja valige rakenduse Dynamics 365 Sales konto.

1. Vastendage kliendi ID väli Dynamics 365 kontakti ID-ga.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus Dynamics 365 Sales jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige kliendi olemis väli Kontakti ID, mis vastab Dynamics 365-i kontakti ID-le.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
