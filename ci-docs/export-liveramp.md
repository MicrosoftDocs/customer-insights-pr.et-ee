---
title: LiveRamp konnektor
description: Lugege, kuidas konfigureerida ühendust ja eksportida LiveRampi.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 973f69c94c625fe4ec543ca5fb57289c4102ea97
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642911"
---
# <a name="export-segments-to-liverampreg-preview"></a>Segmentide eksportimine LiveRamp&reg; (eelversioon)

Aktiveerige oma andmed LiveRampis, et luua ühendus üle 500 platvormiga nii digitaalmeedias, sotsiaalmeedias kui ka televisioonis. Töötage LiveRampis oma andmetega, et sihistada, tõkestada ja isikupärastada reklaamikampaaniaid.

## <a name="prerequisites-for-a-connection"></a>Ühenduse eeltingimus

- Selle konnektori kasutamiseks vajate LiveRampi tellimust.
- Tellimuse hankimiseks võtke otse [LiveRampiga ühendust](https://liveramp.com/contact/). [Lisateave LiveRampi kasutuselevõtu kohta](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Ühenduse loomine LiveRampiga

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **LiveRamp** ühenduse konfigureerimiseks.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage oma LiveRampi Secure FTP (SFTP) konto **kasutajanimi** ja **parool**.
See identimisteave võib erineda teie LiveRampi kasutuselevõtu identimisteabest.

1. Valige suvand **Kinnita**, et testida LiveRampi ühendust.

1. Pärast edukat kinnitamist andke oma nõusolek **Andmete privaatsus ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa sihtkoht**.

1. Valige **Ekspordiühendus** väljal ühendus LiveRamp jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Valige väljal **Peamise identifikaatori valimine** kas **Meil**, **Nimi ja aadress** või **Telefon**, et saata LiveRampi identimise jaoks.
   > [!div class="mx-imgBorder"]
   > ![LiveRampi konnektor atribuutide kaardistamiseks.](media/export-liveramp-segments.png "LiveRampi konnektor atribuutide vastendamisega")

1. Vastendage oma *Kliendi* olemi vastavad atribuudid valitud võtmeidentifikaatori jaoks.

1. Valige **Lisa atribuut**, et kaardistada rohkem atribuute LiveRampile saatmiseks.

   > [!TIP]
   > Rohkemate põhiidentifikaatorite LiveRampi saatmisel on vastete määr tõenäoliselt suurem.

1. Valige segmendid, mida soovite LiveRampi eksportida.

1. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Liverampi andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Liveramp täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

[!INCLUDE [footer-include](includes/footer-banner.md)]
