---
title: Rikastamine kolmanda osapoole rikastamisteenusega Experianilt
description: Üldine teave Experiani kolmanda osapoole rikastamise kohta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896368"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Kliendi profiilide rikastamine Experiani demograafiliste andmetega (eelvaade)

Experian on üleilmne liider tarbijate ja ärikrediidi aruandluse ning turundusega seotud teenuste valdkonnas. Experiani andmete rikastamise teenustega saate oma klientidest luua põhjalikuma ülevaate, rikastades klientide profiile selliste demograafiliste andmetega nagu leibkonna suurus, sissetulek ja palju muud.

## <a name="prerequisites"></a>Eeltingimused

Experiani konfigureerimiseks peavad olema täidetud järgmised eeltingimused.

- Teil on olemas aktiivne Experiani kordustellimus. Kordustellimuse saamiseks [võtke otse ühendust Experianiga](https://www.experian.com/marketing-services/contact). [vaadake lisateavet Experiani andmete rikastamise kohta](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Administraator on Experian ühenduse juba konfigureerinud *või* teil on [administraatori](permissions.md#administrator) õigused. Samuti on teil vaja SSH-toega turvalise transpordi (ST) konto kasutaja ID-d, osapoole ID-d ja mudelinumbrit, mille Experian on teie jaoks loonud.

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige Experiani paanilt suvand **Rikasta minu andmeid**.

   > [!div class="mx-imgBorder"]
   > ![Experiani paan](media/experian-tile.png "Experiani paan")
   > 

1. Valige ripploendist [ühendus](connections.md). Kui ühendusi pole saadaval, pöörduge administraatori poole. Kui olete administraator, saate ühenduse luua, valides ripploendist suvandi **Lisa ühendus** ja valides Experian. 

1. Valige **Ühenda Experianiga**, et kinnitada ühenduse valik.

1.  Valige **Edasi** ja valige **Kliendi andmekomplekt**, mida soovite Experian demograafiliste andmetega rikastada. Saate valida olemi **Klient**, et rikastada kõik oma kliendiprofiilid või valida segmendi olemi, et rikastada ainult selles segmendis sisalduvad kliendiprofiilid.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Kuvatõmmis kliendiandmete kogumi valimisel.":::

1. Valige **Edasi** ja määratlege, millist tüüpi välju teie ühendatud profiilidest tuleks kasutada Experian demograafiliste andmete sobitamiseks. Vähemalt üks väljadest **Nimi ja aadress**, **Telefon** või **E-post** on nõutav. Suurema sobivuse täpsuse saavutamiseks saab lisada kuni kaks muud välja. See valik mõjutab kaardistamisvälju, millele teil on järgmises etapis juurdepääs.

    > [!TIP]
    > Rohkemate võtmeidentifikaatori atribuutide saatmine Experianile annab tõenäoliselt suurema vastavuse määra.

1. Valige **Edasi**, et alustada väljade kaardistamist.

1. Määratlege, milliseid väljad teie ühendatud profiilidest tuleks kasutada Experianist sobivate demograafiliste andmete otsimiseks. Nõutud väljad on vastavalt tähistatud.

1. Sisestage rikastamise nimi ja väljundolemi nimi.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

## <a name="configure-the-connection-for-experian"></a>Konfigureerige ühendus Experianiga 

Ühenduste konfigureerimiseks peate olema administraator. Valige **Lisa ühendus** rikastamise konfigureerimisel *või* minge **Administraator** > **Ühendused** ja valige **Seadista** Experian paanil.

1. Seejärel valige suvand **Alustamine**.

1. Sisestage ühenduse nimi **Kuvatav nimi** väljale.

1. Sisestage oma Experian Secure Transport konto kehtiv kasutajanimi, osapoole ID ja mudeli number.

1. Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides **Nõustun** märkeruudu

1. Valige **Kontrolli** konfiguratsiooni valideerimiseks.

1. Pärast kontrollimise lõpuleviimist valige **Salvesta**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian ühenduse konfiguratsiooni paan.":::

## <a name="enrichment-results"></a>Rikastamise tulemused

Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**. Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab). Töötlemisaeg sõltub teie kliendiandmete mahust ja rikastamistoimingutest, mille Experian on teie konto jaoks seadistanud.

Kui rikastamistoiming on tehtud, saate värskelt rikastatud klientide profiile üle vaadata suvandi **Minu rikastamised** alt. Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.

Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.

## <a name="next-steps"></a>Järgmised etapid

Rikastatud kliendiandmetele toetumine. Klientidele isikustatud kogemuste pakkumiseks looge suvandid [Segmendid](segments.md), [Meetmed](measures.md) ja isegi [Ekspordi andmed](export-destinations.md).

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil Experiani andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et Experian täidab kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
