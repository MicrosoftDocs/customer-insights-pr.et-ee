---
title: Andmeallikate kasutamine andmete valmendamiseks
description: Vaadake, kuidas eri allikatest andmeid importida.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 27cbd0346b1219c7812f4b90327dd27b645c2b8e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732137"
---
# <a name="data-sources-overview"></a>Andmeallikate ülevaade

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Publiku taipamise võimalus Dynamics 365 Customer Insights ühendub laiast allikatest pärinevate andmetega. Andmeallikaga ühendamist nimetatakse sageli *andmete sisestamiseks*. Pärast andmete sisestamist saate need [ühendada](data-unification.md) ja nendega toiminguid teha.

## <a name="add-a-data-source"></a>Lisa andmeallikas

Vaadake üksikasjalikke artikleid selle kohta, kuidas andmeallikat lisada, olenevalt sellest, millise suvandi te valite.

Saate andmeallikat lisada kolmel peamisel viisil.

- [Kümnete Power Query konnektorite kaudu](connect-power-query.md)
- [Common Data Modeli kaustast](connect-common-data-model.md)
- [Oma Microsoft Dataverse järvest](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Andmete lisamine asutusesisene andmeallikatest

Microsoft Power Platform andmevoogude põhjal toetatakse asutusesisene andmeallikate andmete allaneelamist vaatajaskonna ülevaates. Andmevoogusid saab lubada kliendiülevaates, [pakkudes keskkonna seadistamisel Microsoft Dataverse keskkonna URL-i.](create-environment.md)

Andmeallikad, mis luuakse pärast Dataverse keskkonna seostamist kliendiülevaatega, kasutavad [vaikimisi Power Platform andmevooge.](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) Andmevood toetavad kohapealset ühenduvust andmelüüside abil. Eemaldage ja looge uuesti andmeallikad, mis olid olemas enne Dataverse keskkonna [seostamist asutusesisene andmelüüside kasutamiseks](/data-integration/gateway/service-gateway-app).

Olemasoleva Power BI või Power Apps keskkonna andmelüüsid on nähtavad ja saate neid klientide ülevaates uuesti kasutada. Andmeallikate lehel kuvatakse lingid, mis lähevad Microsoft Power Platform keskkonda, kus saate asutusesisene andmelüüse vaadata ja konfigureerida.

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
