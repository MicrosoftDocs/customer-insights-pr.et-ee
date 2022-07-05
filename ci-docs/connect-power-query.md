---
title: Power Query andmeallikas ühenduse loomine (sisaldab videot)
description: Andmete allaneelamine konnektori kaudu Power Query (sisaldab videot).
ms.date: 06/13/2022
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
ms.openlocfilehash: 6736b253e3a7e652f92f61bc44bfb31ca69be31a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082173"
---
# <a name="connect-to-a-power-query-data-source"></a>Andmeallikas ühenduse loomine Power Query

Power Query pakub laias valikus konnektoreid andmete allaneelamiseks. Enamikku nendest konnektoritest toetab Dynamics 365 Customer Insights.

Andmeallikate lisamine konnektorite põhjal Power Query järgib tavaliselt selles jaotises kirjeldatud juhiseid. Olenevalt kasutatavast konnektorist on siiski vaja erinevat teavet. Lisateavet leiate konnektoriviite üksikute konnektorite dokumentatsioonist [Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Loo uus andmeallikas

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige suvand **Microsofti Power Query**.

1. **Esitage andmeallikas nimi** ja valikuline **kirjeldus** ning valige **Edasi**.

1. Valige üks [saadaolevatest konnektoritest](#available-power-query-data-sources). Selles näites valime **teksti/CSV** konnektori.

1. Sisestage valitud konnektorile jaotises **Konnektori sätted** nõutavad üksikasjad ja valige andmete üle vaatamiseks nupp **Edasi**.

1. Valige suvand **Andmete teisendamine**. Selles etapis lisate oma andmeallikale olemid. Olemid on andmekogud. Kui teil on andmebaas, mis sisaldab mitut andmekogumit, on iga andmekomplekt omaette olem.

1. Dialoogiboks **Power Query – päringute** redigeerimine võimaldab teil andmeid üle vaadata ja täpsustada. Olemid, mida süsteemid teie valitud andmeallikas tuvastasid, kuvatakse vasakpoolsel paanil.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Päringute redigeerimise dialoog":::

1. Samuti saate oma andmeid teisendada. Valige redigeeritav või teisendatav olem. Teisenduste Power Query rakendamiseks kasutage aknas olevaid suvandeid. Iga teisendus on loetletud jaotises **Rakendatud sammud**. Power Query pakub arvukalt eelnevalt ehitatud transformatsioonivõimalusi. Lisateavet vt teemast [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).

   Soovitame kasutada järgmisi teisendusi.

   - Kui valmendate andmeid CSV-failist, siis esimene rida sisaldab sageli päiseid. **Valige Teisendamine** ja valige **Kasuta esimest rida päistena**.
   - Veenduge, et andmetüüp oleks õigesti seadistatud. Näiteks kuupäevaväljade puhul valige kuupäevatüüp.

1. Dialoogiboksis **Päringute** redigeerimine andmeallikas täiendavate olemite lisamiseks avage **Avaleht** ja valige Too **andmed**. Korrake juhiseid 6–10, kuni olete lisanud kõik selle andmeallikas olemid.

1. Valige **Salvesta**. Avaneb **andmeallikate** leht, kus kuvatakse uus andmeallikas olekus **Värskendamine**.

### <a name="available-power-query-data-sources"></a>Saadaolevad Power Query andmeallikad

Vaadake konnektori [Power Query viidet](/power-query/connectors/) konnektorite loendi kohta, mida saate kasutada andmete importimiseks Customer Insightsi.

Veerus **Customer Insights (Dataflows)** märkega konnektorid on saadaval uute andmeallikate loomiseks rakenduse põhjal Power Query. Vaadake üle konkreetse konnektori dokumentatsioon, et saada lisateavet selle eeltingimuste, [päringupiirangute](/power-query/power-query-online-limits) ja muude üksikasjade kohta.

## <a name="add-data-from-on-premises-data-sources"></a>Andmete lisamine asutusesisene andmeallikatest

Andmete sisestamist asutusesisene andmeallikatest toetatakse andmevoogude (PPDF) põhjal Microsoft Power Platform. Andmevoogude lubamiseks Customer Insightsis [saate keskkonna häälestamisel esitada Microsoft Dataverse keskkonna URL-i](create-environment.md).

Andmeallikad, mis luuakse pärast keskkonna seostamist Dataverse Customer Insightsiga, kasutavad [Power Platform vaikimisi andmevooge](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Andmevood toetavad kohapealset ühenduvust andmelüüside abil. Andmeallikaid, mis eksisteerisid enne keskkonna seostamist Dataverse [, saate asutusesisene andmelüüside abil eemaldada ja uuesti luua andmeallikad](/data-integration/gateway/service-gateway-app).

Andmevõrgud olemasolevast Power BI või Power Apps keskkonnast on nähtavad ja saate neid uuesti kasutada jaotises Customer Insights. Andmeallikate lehel kuvatakse lingid, et minna Microsoft Power Platform keskkonda, kus saate vaadata ja konfigureerida asutusesiseseid andmevõrke.

> [!IMPORTANT]
> Veenduge, et teie lüüsid värskendatakse uusimale versioonile. Värskenduse saate installida ja lüüsi ümber konfigureerida lüüsi ekraanil kuvatavast viipast otse või [alla laadida uusima versiooni](https://powerapps.microsoft.com/downloads/). Kui te ei kasuta uusima lüüsi versiooni, nurjub andmevoo värskendamine tõrketeadetega, nagu **märksõna ei toetata: konfiguratsiooniatribuute. Parameetri nimi: märksõna**.

## <a name="edit-power-query-data-sources"></a>Andmeallikate redigeerimine Power Query

> [!NOTE]
> Ei pruugi olla võimalik muuta andmeallikaid, mis on samaaegselt kasutusel mõnes rakenduse protsessis (nt *segmentimine*, *vaste* või *ühinemine*).
>
> **Lehel Sätted** saate jälgida iga aktiivse protsessi edenemist. Protsessi lõpuleviimisel saate naasta **Andmeallikate** lehele ja teha soovitud muudatused.

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige värskendatava andmeallikas kõrval Käsk **Redigeeri**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

1. Rakendage oma muudatused ja teisendused dialoogiboksis **Power Query Päringute** redigeerimine, nagu on kirjeldatud [jaotises Uue andmeallikas](#create-a-new-data-source) loomine.

1. Muudatuste salvestamiseks valige **pärast muudatuste lõpuleviimist nupp Salvesta** sisse Power Query.
