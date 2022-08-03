---
title: ühenduse loomine Power Query andmeallikas (sisaldab videot)
description: Neelake andmeid konnektori Power Query kaudu (sisaldab videot).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 7af51ed04fbd28149ea501c58e6fe71b5fa6d4b6
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207040"
---
# <a name="connect-to-a-power-query-data-source"></a>Andmeallikas ühenduse loomine Power Query

Power Query pakub andmete allaneelamiseks laia valikut konnektoreid. Enamikku nendest konnektoritest toetab Dynamics 365 Customer Insights.

Konnektoritel Power Query põhinevate andmeallikate lisamisel järgitakse tavaliselt selles jaotises kirjeldatud juhiseid. Olenevalt kasutatavast konnektorist on siiski vaja erinevat teavet. Lisateabe saamiseks vaadake konnektori viites olevat [Power Query dokumentatsiooni üksikute konnektorite kohta](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Loo uus andmeallikas

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige suvand **Microsofti Power Query**.

1. Sisestage **andmeallikas nimi** ja valikuline **kirjeldus** ning valige **Edasi**.

1. Valige üks [saadaolevatest konnektoritest](#available-power-query-data-sources). Selles näites valime **teksti/ CSV-konnektori**.

1. Sisestage valitud konnektorile jaotises **Konnektori sätted** nõutavad üksikasjad ja valige andmete üle vaatamiseks nupp **Edasi**.

1. Valige suvand **Andmete teisendamine**.

1. **Power Query Dialoogis Päringute** redigeerimine saate andmeid üle vaadata ja täpsustada. Olemid, mida süsteemid teie valitud andmeallikas tuvastasid, kuvatakse vasakpoolsel paanil.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Päringute redigeerimise dialoog":::

1. Samuti saate oma andmeid teisendada. Valige redigeeritav või teisendatav olem. Teisenduste Power Query rakendamiseks kasutage aknas olevaid suvandeid. Iga teisendus on loetletud jaotises **Rakendatud etapid**. Power Query pakub arvukalt [eelnevalt ehitatud ümberkujundamisvõimalusi](/power-query/power-query-what-is-power-query#transformations).

   Soovitame kasutada järgmisi teisendusi.

   - Kui valmendate andmeid CSV-failist, siis esimene rida sisaldab sageli päiseid. Minge jaotisse **Teisendamine** ja valige **Kasuta esimest rida päistena**.
   - Veenduge, et andmetüüp oleks õigesti seadistatud. Näiteks kuupäevaväljade puhul valige kuupäeva tüüp.

1. Täiendavate olemite lisamiseks andmeallikas dialoogiboksis Päringute **redigeerimine avage** Avaleht **ja valige** Hangi andmed **.** Korrake juhiseid 5–10, kuni olete lisanud kõik selle andmeallikas olemid. Kui teil on andmebaas, mis sisaldab mitut andmekogumit, on iga andmekomplekt omaette olem.

1. Valige **Salvesta**. Avaneb **leht Andmeallikad**, kus kuvatakse uus andmeallikas olekus **Värskendamine**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Andmete laadimine võib võtta aega. Pärast edukat värskendamist saab allaneelatud andmeid vaadata lehelt [**Olemid**](entities.md).

> [!CAUTION]
> Andmeallikas, mis põhineb Power Query, loob [andmevoo rakenduses Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Ärge muutke Customer Insightsis Power Platform kasutatava halduskeskuse andmevoo nime. Andmevoo ümbernimetamine põhjustab probleeme viidetega Customer Insightsi andmeallikas ja Dataverse andmevoo vahel.

### <a name="available-power-query-data-sources"></a>Olemasolevad Power Query andmeallikad

Konnektori viitest [Power Query](/power-query/connectors/) leiate konnektorite loendi, mida saate kasutada andmete importimiseks Customer Insightsi.

Konnektorid, mille veerus **Customer Insights (Andmevood)** on linnuke, on saadaval uute andmeallikate loomiseks, mis põhinevad Power Query. Vaadake üle konkreetse konnektori dokumentatsioon, et saada lisateavet selle eeltingimuste, [päringupiirangute](/power-query/power-query-online-limits) ja muude üksikasjade kohta.

## <a name="add-data-from-on-premises-data-sources"></a>Andmete lisamine asutusesisene andmeallikatest

Asutusesisene andmeallikatest pärinevate andmete allaneelamist toetatakse andmevoogude (PPDF) põhjal Microsoft Power Platform. Saate lubada andmevood Customer Insightsis, sisestades [keskkonna seadistamisel Microsoft Dataverse keskkonna URL-i](create-environment.md).

Andmeallikad, mis luuakse pärast keskkonna seostamist Dataverse Customer Insightsiga, kasutavad [Power Platform vaikimisi andmevooge](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Andmevood toetavad kohapealset ühenduvust andmelüüside abil. Saate eemaldada ja taasluua andmeallikad, mis olid olemas enne keskkonna seostamist Dataverse [, kasutades asutusesisene andmelüüsi.](/data-integration/gateway/service-gateway-app)

Olemasoleva Power BI või Power Apps keskkonna andmelüüsid on nähtavad ja saate neid Customer Insightsis uuesti kasutada. Andmeallikate lehel kuvatakse lingid, et minna Microsoft Power Platform keskkonda, kus saate vaadata ja konfigureerida asutusesiseseid andmevõrke.

> [!IMPORTANT]
> Veenduge, et teie lüüsid oleksid värskendatud uusimale versioonile. Saate installida värskenduse ja konfigureerida lüüsi ümber otse lüüsi ekraanil kuvatavast viibast või [laadida alla uusima versiooni](https://powerapps.microsoft.com/downloads/). Kui te ei kasuta uusimat lüüsiversiooni, nurjub andmevoo värskendamine tõrketeadetega, nagu **märksõna ei toetata: konfiguratsiooniatribuudid. Parameetri nimi: märksõna**.
>
> Customer Insightsi asutusesisene andmelüüsidega seotud tõrked on sageli põhjustatud konfiguratsiooniprobleemidest. Lisateavet andmelüüside tõrkeotsingu kohta leiate teemast [andmelüüsi tõrkeotsing asutusesisene](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Andmeallikate redigeerimine Power Query

> [!NOTE]
> Võib-olla ei ole võimalik muuta andmeallikaid, mida praegu mõnes rakenduse protsessis kasutatakse (näiteks segmentimine või andmete ühendamine).
>
> **Lehel Sätted** saate jälgida iga aktiivse protsessi edenemist. Protsessi lõpuleviimisel saate naasta **Andmeallikate** lehele ja teha soovitud muudatused.

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige värskendatava andmeallikas kõrval käsk **Redigeeri**.

1. Rakendage oma muudatused ja teisendused **Power Query dialoogiboksis Päringute** redigeerimine, nagu on kirjeldatud [jaotises Uue andmeallikas](#create-a-new-data-source) loomine.

1. Muudatuste rakendamiseks ja lehele Andmeallikad **naasmiseks** valige **Salvesta**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
