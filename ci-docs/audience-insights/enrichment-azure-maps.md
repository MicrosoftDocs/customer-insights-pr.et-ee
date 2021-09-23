---
title: Kliendiprofiilide rikastamine Azure Mapsi asukohaandmetega
description: Üldine teave Azure Maps esimese osapoole rikastamise kohta.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 63f241c27ec86f357c83a301d6797f9ff87c2241
ms.sourcegitcommit: 2acda3c5adf40bc3f5bbb4b2b4b6c22f84371da7
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466757"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Kliendiprofiilide rikastamine Azure Mapsi abil (eelvaade)

Azure Maps pakub asukohakeskseid andmeid ja teenuseid, et pakkuda georuumilistel andmetel põhinevaid kogemusi sisseehitatud asukohaanalüüsiga. Azure Mapsi andmete rikastamise teenused täiustavad teie klientide asukohateabe täpsust. See toob võimalusi, nagu näiteks normaliseerimine ning laius- ja pikkuskraadide eraldamise rakendusele Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Eeltingimused

Azure Mapsi andmete rikastamise konfigureerimiseks peavad olema täidetud järgmised eeltingimused.

- Teil peab olema aktiivne Azure Maps kordustellimus. Kordustellimuse saamiseks võite [registreeruda või saada tasuta prooviversiooni](https://azure.microsoft.com/services/azure-maps/).

- Azure Mapsi kaartide [ühendus](connections.md) on saadaval *või* teil on [administraatori](permissions.md#administrator) õigused ja aktiivne Azure Mapsi API-võti.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage **Andmed** > **Rikastamine**. 

1. Valige paanil **Asukoht** suvand **Rikasta minu andmed**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Azure Mapsi paan.":::

1. Valige [ühendus](connections.md) ripploendist. Kui Azure Mapsi ühendus pole saadaval, pöörduge administraatori poole. Kui olete administraator, saate [konfigureerida Azure Mapsi ühenduse](#configure-the-connection-for-azure-maps). 

1. Valiku kinnitamiseks klõpsake nuppu **Edasi**.

1. Valige **Kliendi andmekomplekt**, mida soovite Azure Mapsi asukohaandmetega rikastada. Saate valida olemi **Klient**, et rikastada kõiki oma ühendatud kliendiprofiile, või valida segmendiolemi, et rikastada ainult selles segmendis sisalduvaid kliendiprofiile.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendi andmekomplekti valimisel.":::

1. Valige, kas soovite vastendada väljad esmase ja/või teise aadressiga. Saate määrata väljavastenduse nii aadresside jaoks kui ka rikastada mõlema aadressi profiile eraldi (nt koduaadressi ja äriaadressi puhul). Tehke valik **Edasi**.

1. Määratlege, milliseid väljad teie ühendatud profiilidest kasutada sobivate asukohtade otsimiseks rakenduses Azure Maps. Valitud esmase või teisese aadressi jaoks on nõutavad väljad **Street1** ja **Sihtnumber**. Suurema vaste täpsuse saamiseks saate lisada rohkem välju.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Azure Mapsi rikastamise konfigureerimise leht.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Hinnata, kas soovite muuta suvandit **Täpsemad sätted**. Need on ette nähtud maksimaalse paindlikkuse tagamiseks täiustatud kasutusjuhtumite käsitlemiseks, kuid enamikul juhtudel on vaikeväärtused piisavad.
   - **Aadresside tüüp**: vaikekäitumine on see, et rikastamine tagastab parima aadressi vaste, isegi kui see on lõpetamata. Ainult täielike aadresside (nt aadresside, mis sisaldavad majanumbrit) toomine tühjendage kõik märkeruudud peale **punktiaadresside**. 
   - **Keel**: vaikimisi tagastatakse aadressid selle piirkonna keeles, kuhu aadress on määratletud. Standardiseeritud aadressikeele rakendamiseks valige ripploendist soovitud keel. Kui näiteks valite **inglise keele**, tagastatakse **Kopenhaagen, Taani**, selle asemel, et **København, Taani**.

1. Peate rikastamise jaoks sisestama nime.

1. Vaadake valikud üle ja valige nupp **Salvesta rikastus**.

## <a name="configure-the-connection-for-azure-maps"></a>Konfigureerige ühendus Azure Mapsi jaoks

Ühenduste konfigureerimiseks peate olema sihtrühma ülevaadetes administraator. Valige rikastamise konfigureerimisel **Lisa ühendus** või minge **Administraator** > **Ühendused** ja valige **Seadista** Azure Mapsi paanil.

1. Sisestage väljale **Kuvatav nimi** ühenduse nimi.

1. Sisestage sobiv Azure Mapsi API võti.

1. Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides **Nõustun** märkeruudu

1. Valige **Kontrolli** konfiguratsiooni valideerimiseks.

1. Pärast kontrollimise lõpuleviimist valige **Salvesta**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Azure Mapsi ühenduse konfigureerimise leht.":::

## <a name="enrichment-results"></a>Rikastamise tulemused

Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**. Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab). Töötlemisaeg sõltub teie kliendiandmete suurusest ja API reageerimisajast.

Kui rikastusprotsess on lõpetatud, saate vaadata äsja rikastatud kliendiprofiilide andmeid jaotises **Minu rikastused**. Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.

Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.

## <a name="next-steps"></a>Järgmised etapid

Rikastatud kliendiandmetele toetumine. Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [Ekspordi andmed](export-destinations.md).

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights edastada andmeid Azure Mapsi, lubate andmete edastamist väljapoole vastavuse piiri Dynamics 365 Customer Insights jaoks, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste alusel, kuid teie vastutate selle eest, et Azure Maps täidaks kõiki privaatsus- või turvakohustusi, mis teil võivad olla. Lisateavet leiate jaotisest [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

[!INCLUDE[footer-include](../includes/footer-banner.md)]