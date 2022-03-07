---
title: Andmeallikate kasutamine andmete valmendamiseks
description: Vaadake, kuidas eri allikatest andmeid importida.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: e7bcf82c4fe3625ef791ec2b0a7651be0356a006
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354044"
---
# <a name="data-sources-overview"></a>Andmeallikate ülevaade



Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioon ühendub andmetega, mis on pärit paljudest allikatest. Andmeallikaga ühendamist nimetatakse sageli *andmete sisestamiseks*. Pärast andmete sisestamist saate need [ühendada](data-unification.md) ja nendega toiminguid teha.

## <a name="add-a-data-source"></a>Lisa andmeallikas

Vaadake üksikasjalikke artikleid andmeallikas lisamiseks sõltuvalt valitud valikust.

Saate lisada järgmisi andmeallikaid.

- [Läbi kümnete Power Query konnektorite](connect-power-query.md)
- [Common Data Modeli kaustast](connect-common-data-model.md)
- [Enda Microsoft Dataverse’i andmejärvest](connect-dataverse-managed-lake.md)
- [Andmebaasist Azure Synapse Analytics](connect-synapse.md)

> [!NOTE]
> Kui kasutate prooviversiooni, sisaldab **impordimeetodite jaotis Customer Insightsi andmeteegi** suvandit. Valige see suvand, et valida näidisandmestik, mis on saadaval erinevatele tööstusharudele. Lisateavet leiate teemast [Dynamics 365 Customer Insights Kohtuprotsess](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Andmete lisamine asutusesisene andmeallikatest

Kohalike andmeallikate andmete sisestamine vaatajaskonna statistikas toetub Microsoft Power Platform andmevoogudele. Saate lubada Andmevood Customer Insightsis, [pakkudes Microsoft Dataverse keskkonna seadistamisel keskkonna URL-i](create-environment.md).

Andmeallikad, mis luuakse pärast keskkonna seostamist Customer Insightsiga, Dataverse kasutavad [Power Platform vaikimisi andmevooge](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Andmevood toetavad kohapealset ühenduvust andmelüüside abil. Saate eemaldada ja taasluua andmeallikad, mis eksisteerisid enne Dataverse keskkonna seostamist [asutusesisene andmelüüside](/data-integration/gateway/service-gateway-app) abil.

Andmevõrgud olemasolevast Power BI või Power Apps keskkonnast on nähtavad ja saate neid uuesti kasutada jaotises Customer Insights. Andmeallikate lehel kuvatakse lingid, et minna Microsoft Power Platform keskkonda, kus saate vaadata ja konfigureerida asutusesiseseid andmevõrke.

## <a name="review-ingested-data"></a>Sisestatud andmete läbivaatus

Näete iga sisestatud andmeallika nime, selle olekut ja viimast korda, kui neid andmeid selle allika jaoks värskendati. Saate andmeallikate loendit iga veeru järgi sortida.

> [!div class="mx-imgBorder"]
> ![Andmeallikas lisatud.](media/configure-data-datasource-added.png "Andmeallikas lisatud")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

Andmete laadimine võib võtta aega. Pärast edukat värskendamist saab lisatud andmeid vaadata lehel **Olemid**. Lisateavet vt jaotisest [Olemid](entities.md).

## <a name="refresh-a-data-source"></a>Andmeallika värskendamine

Andmeallikaid saab värskendada automaatse ajakava järgi või soovi korral käsitsi. 

Minge jaotisse **Haldus** > **Süsteem** > [**Ajastamine**](system.md#schedule-tab), et konfigureerida kõigi valmendatud andmeallikate ajastatud värskendamine.

Andmeallika värskendamiseks mis tahes ajal toimige järgmiselt.

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2. Valige värskendatava andmeallika kõrval vertikaalne ellips ja valige **Värskenda** ripploendist.

3. Andmeallika jaoks käivitatakse nüüd käsitsivärskendamine. Andmeallika värskendamine uuendab nii olemiskeemi kui ka kõigi andmeallikas määratud olemite andmeid.

4. Kui soovite olemasoleva värskendamise tühistada, klõpsake **Lõpeta värskendamine** ja andmeallikas taastatakse viimase värskendamise olekusse.

## <a name="delete-a-data-source"></a>Andmeallika kustutamine

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2. Valige eemaldatava andmeallika kõrval vertikaalne ellips ja valige **Kustuta** ripploendist.

3. Kinnitage, et soovite kustutada.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
