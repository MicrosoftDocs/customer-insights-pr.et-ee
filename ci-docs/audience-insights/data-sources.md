---
title: Andmeallikate kasutamine andmete valmendamiseks
description: Vaadake, kuidas eri allikatest andmeid importida.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ca979527c9cb8418e12af4a74513033047e4901c
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046583"
---
# <a name="data-sources-overview"></a>Andmeallikate ülevaade



Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsioon ühendub andmetega, mis on pärit paljudest allikatest. Andmeallikaga ühendamist nimetatakse sageli *andmete sisestamiseks*. Pärast andmete sisestamist saate need [ühendada](data-unification.md) ja nendega toiminguid teha.

## <a name="add-a-data-source"></a>Lisa andmeallikas

Sõltuvalt valitud valikust vaadake üksikasjalikke artikleid andmeallikas lisamiseks.

Saate lisada järgmisi andmeallikaid.

- [Power Query Pistikud](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse järv](connect-dataverse-managed-lake.md)

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
