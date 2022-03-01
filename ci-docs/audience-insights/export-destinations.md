---
title: Ekspordisihtkohad
description: Andmete eksportimine ja eksportimise sihtkohtade haldamine.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643858"
---
# <a name="export-destinations-preview"></a>Ekspordisihtkohad (eelvaade)

Lehel **Ekspordi sihtkohad** kuvatakse kõik sihtkohad, mis olete seadistanud andmete eksportimiseks. Samuti saate lisada uusi eksportimise sihtkohti. Lisaks kuvatakse siin praegu saadaolevad eksportimissuvandid. Saate kiire ülevaate, kirjelduse ning teabe selle kohta, mida saate iga laiendatavuse valiku abil teha. Eksportige ühendatud profiilid, meetmed ja segmendid teie äri jaoks olulistesse toetatud rakendustesse.

Avage jaotis **Administraator** > **Eksportimise sihtkohad**, et näha järgmisi laiendatavuse valikuid.

- [Dynamics 365 kliendikaardi lisandmoodul](customer-card-add-in.md)
- [Facebooki reklaamihalduri konnektor](export-facebook.md)
- [Power Automate'i konnektor](export-power-automate.md)
- [Power Apps'i konnektor](export-power-apps.md)
- [Power BI'i konnektor](export-power-bi.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure’i bloobimälu](export-azure-blob-storage.md)
- [LiveRamp&reg; konnektor](export-liveramp.md)
- [Microsoft Teamsi robot](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insightsi API](apis.md)

## <a name="add-a-new-export-destination"></a>Uue ekspordi sihtkoha lisamine

Eksportimise sihtkohtade lisamiseks on teil vaja [administraatoriõigusi](permissions.md). Kui ekspordite Microsofti teenustesse, eeldame, et mõlemad teenused on samas organisatsioonis.

1. Avage **Haldus** > **Ekspordi sihtkohad**.

1. Vahetage vahekaardile **Minu ekspordi sihtkohad**.

1. Uue ekspordi sihtkoha loomiseks valige suvand **Lisa sihtkoht**.

1. Valige paanil **Lisa sihtkoht** rippmenüüd ekspordi sihtkoha **tüüp**.

1. Sisestage nõutud üksikasjad ja valige **Edasi**, et luua ekspordi sihtkoht.

Samuti saate valida vahekaardi **Tuvastamine** paanil suvandi **Häälestamine**.

## <a name="view-export-destinations"></a>Ekspordi sihtkohtade kuvamine

Pärast ekspordi sihtkohtade loomist leiate need tabelist vahekaardil **Minu ekspordi sihtkohad**. Sellel tabelil on kolm veergu.

- **Kuvatav nimi**: nimi, mille sisestasite sihtkoha loomisel.
- **Tüüp**: eksportimise sihtkoha tüüp, mille määrate sihtkoha loomisel.
- **Loomiskuupäev**: sihtkoha loomise kuupäev.

## <a name="edit-an-export-destination"></a>Ekspordi sihtkoha redigeerimine

1. Klõpsake redigeeritava ekspordi sihtkoha juures kolmel vertikaalsel punktil.

   > [!div class="mx-imgBorder"]
   > ![Kolm vertikaalset punkti](media/export-destinations-page-ellipsis.png "Kolm vertikaalset punkti")

1. Valige rippmenüüst suvand **Redigeeri**.

1. Muutke väärtusi, mis vajavad värskendamist, ja valige **Salvesta**.

## <a name="export-data-on-demand"></a>Andmete eksport nõudmisel

Pärast ekspordi sihtkoha konnektori konfigureerimist käivitatakse eksport iga [ajastatud värskendusega](system.md#schedule-tab).

Andmete eksportimiseks ilma ajastatud värskendamist ootamata, avage vahekaart **Minu ekspordi sihtkohad** suvandis **Haldus** > **Ekspordi sihtkohad**.

> [!div class="mx-imgBorder"]
> ![Kolm vertikaalset punkti](media/export-destinations-page-ellipsis.png "Kolm vertikaalset punkti")

- Kõigi ekspordi sihtkohtade samaaegse ekspordi käitamiseks valige loendi kohal käsk **Ekspordi**,
- Valige loendiüksuse järel kolmikpunkt (...) ja seejärel valige suvand **Ekspordi**, et käivitada eksportimine ühe ekspordi sihtkoha jaoks.

## <a name="remove-an-export-destination"></a>Ekspordi sihtkoha eemaldamine

Ekspordi sihtkoha eemaldamiseks alustage lehelt **Ekspordi sihtkohad**.

1. Klõpsake eemaldatava ekspordi sihtkoha juures kolmel vertikaalsel punktil.

   > [!div class="mx-imgBorder"]
   > ![Kolm vertikaalset punkti](media/export-destinations-page-ellipsis.png "Kolm vertikaalset punkti")

2. Valige rippmenüüst **Eemalda**.

3. Eemaldamise kinnitamiseks valige kinnitusekraanil **Eemalda**.
