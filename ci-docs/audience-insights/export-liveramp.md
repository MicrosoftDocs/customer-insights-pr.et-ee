---
title: LiveRamp konnektor
description: Vaadake, kuidas eksportida andmeid LiveRampi.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667179"
---
# <a name="liverampreg-connector-preview"></a>LiveRamp&reg;i konnektor (eelvaade)

Aktiveerige oma andmed LiveRampis, et luua ühendus üle 500 digi-, sotsiaal- ja teleökosüsteemi platvormiga. Töötage LiveRampis oma andmetega, et sihistada, tõkestada ja isikupärastada reklaamikampaaniaid.

## <a name="prerequisites"></a>Eeltingimused

- Selle konnektori kasutamiseks vajate LiveRampi tellimust.
- Tellimuse hankimiseks võtke otse [LiveRampiga ühendust](https://liveramp.com/contact/). [Lisateave LiveRampi kasutuselevõtu kohta](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>LiveRampiga ühendamine

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.

1. Valige paanil **LiveRamp** suvand **Seadista**.

1. Sisestage väljale **Kuvatav nimi** oma sihtkoha äratuntav nimi.

1. Sisestage oma LiveRampi Secure FTP (SFTP) konto **kasutajanimi** ja **parool**.
See identimisteave võib erineda teie LiveRampi kasutuselevõtu identimisteabest.

1. Valige suvand **Kinnita**, et testida LiveRampi ühendust.

1. Pärast edukat kinnitamist andke oma nõusolek **Andmete privaatsus ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**.

1. Valige suvand **Järgmine**, et häälestada LiveRampi konnektor.

## <a name="configure-the-connector"></a>Konnektori konfigureerimine

1. Valige väljal **Peamise identifikaatori valimine** kas **Meil**, **Nimi ja aadress** või **Telefon**, et saata LiveRampi identimise jaoks.

1. Vastendage vastavad atribuudid valitud põhiidentifikaatori ühtsest kliendiolemist.

1. Valige suvand **Lisa atribuut**, et vastendada LiveRampi saatmiseks täiendavaid atribuute.

   > [!TIP]
   > Rohkemate põhiidentifikaatorite LiveRampi saatmisel on vastete määr tõenäoliselt suurem.

1. Valige segmendid, mida soovite LiveRampi eksportida.

1. Valige **Salvesta**.

> [!div class="mx-imgBorder"]
> ![LiveRampi konnektor atribuutide vastendamisega](media/export-liveramp-segments.png "LiveRampi konnektor atribuutide vastendamisega")

## <a name="export-the-data"></a>Andmete eksportimine

Eksportimine algab varsti, kui kõik eksportimiseks vajalikud eeltingimused on täidetud. Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).
Pärast eksportimise lõpuleviimist saate oma andmete aktiveerimiseks ja levitamiseks LiveRampi kasutuselevõttu sisse logida.

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Liverampi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Liveramp täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.