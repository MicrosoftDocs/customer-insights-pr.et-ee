---
title: Andmeallikate kasutamine andmete valmendamiseks
description: Vaadake, kuidas eri allikatest andmeid importida.
ms.date: 03/18/2022
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
ms.openlocfilehash: 1fe8d6e8098831ecc8ff28e571340c56a654de6d
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/11/2022
ms.locfileid: "8739203"
---
# <a name="data-sources-overview"></a>Andmeallikate ülevaade



Dynamics 365 Customer Insights ühendub andmetega paljudest allikatest. Andmeallikaga ühendamist nimetatakse sageli *andmete sisestamiseks*. Pärast andmete sisestamist saate need [ühendada](data-unification.md) ja nendega toiminguid teha.

## <a name="add-a-data-source"></a>Lisa andmeallikas

Sõltuvalt valitud valikust vaadake üksikasjalikke artikleid andmeallikas lisamise kohta.

Saate lisada järgmised andmeallikad.

- [Läbi kümnete Power Query pistikute](connect-power-query.md)
- [Common Data Modeli kaustast](connect-common-data-model.md)
- [Enda Microsoft Dataverse’i andmejärvest](connect-dataverse-managed-lake.md)
- [Andmebaasist Azure Synapse Analytics](connect-synapse.md)

## <a name="add-data-from-on-premises-data-sources"></a>Andmete lisamine asutusesisene andmeallikatest

Andmevoogude põhjal Microsoft Power Platform toetatakse asutusesisene andmeallikatest andmete allaneelamist. Andmevooge saate lubada Customer Insightsis [, Microsoft Dataverse pakkudes keskkonna häälestamisel keskkonna URL-i](create-environment.md).

Andmeallikad, mis luuakse pärast keskkonna seostamist Dataverse Customer Insightsiga, kasutavad [Power Platform vaikimisi andmevooge](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Andmevood toetavad kohapealset ühenduvust andmelüüside abil. Andmeallikaid, mis eksisteerisid enne keskkonna seostamist Dataverse [, saate asutusesisene andmelüüside abil eemaldada ja uuesti luua andmeallikad](/data-integration/gateway/service-gateway-app).

Andmevõrgud olemasolevast Power BI või Power Apps keskkonnast on nähtavad ja saate neid uuesti kasutada jaotises Customer Insights. Andmeallikate lehel kuvatakse lingid, et minna Microsoft Power Platform keskkonda, kus saate vaadata ja konfigureerida asutusesiseseid andmevõrke.

> [!IMPORTANT]
> Veenduge, et teie lüüsid värskendatakse uusimale versioonile. Värskenduse saate installida ja lüüsi ümber konfigureerida lüüsi ekraanil kuvatavast viipast otse või [alla laadida uusima versiooni](https://powerapps.microsoft.com/downloads/). Kui te ei kasuta uusima lüüsi versiooni, nurjub andmevoo värskendamine tõrketeadetega, nagu **märksõna ei toetata: konfiguratsiooniatribuute. Parameetri nimi: märksõna**.

## <a name="review-ingested-data"></a>Sisestatud andmete läbivaatus
Kui teie keskkond sisaldab Power Platform andmevooge, loetletakse **lehel Andmeallikad** kolm jaotist. 
- **Ühiskasutuses**: andmeallikad, mida saavad hallata kõik Customer Insightsi administraatorid. Power BI andmevood, teie enda salvestuskonto ja hallatava andmejärve Dataverse külge kinnitamine on näited jagatud andmeallikatest.
- **Minu hallatav**: Power Platform andmevood on loodud ja neid saab hallata ainult teie. Teised Customer Insightsi administraatorid saavad vaadata ainult neid andmevooge, kuid mitte neid redigeerida, värskendada ega kustutada.
- **Teiste hallatavad**: Power Platform teiste administraatorite loodud andmevood. Neid saab ainult vaadata. See loetleb andmevoo omaniku, kellega abi saamiseks ühendust võtta.
> [!NOTE]
> Kõiki olemeid saavad vaadata ja kasutada teised kasutajad. Kasutaja kontekstuaalsus kehtib ainult andmeallikatele, mitte nendest andmevoogudest tulenevatele olemitele.

Kui andmevooge ei Power Platform kasutata, ei näe te ühtegi rühma ega jaotist. Leht **Andmeallikad** sisaldab ainult kõigi andmeallikate loendit.

Näete iga sisestatud andmeallika nime, selle olekut ja viimast korda, kui neid andmeid selle allika jaoks värskendati. Saate andmeallikate loendit iga veeru järgi sortida.

> [!div class="mx-imgBorder"]
> ![Andmeallikas lisatud.](media/configure-data-datasource-added.png "Andmeallikas lisatud")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Andmete laadimine võib võtta aega. Pärast edukat värskendamist saab lisatud andmeid vaadata lehel **Olemid**. Lisateavet vt jaotisest [Olemid](entities.md).

## <a name="refresh-a-data-source"></a>Andmeallika värskendamine

Andmeallikaid saab värskendada automaatse ajakava järgi või soovi korral käsitsi. 

Minge jaotisse **Haldus** > **Süsteem** > [**Ajastamine**](system.md#schedule-tab), et konfigureerida kõigi valmendatud andmeallikate ajastatud värskendamine.

Andmeallika värskendamiseks mis tahes ajal toimige järgmiselt.

1. Avage suvandid **Andmed** > **Andmeallikad**.

2. Valige värskendatava andmeallika kõrval vertikaalne ellips ja valige **Värskenda** ripploendist.

3. Andmeallika jaoks käivitatakse nüüd käsitsivärskendamine. Andmeallika värskendamine uuendab nii olemiskeemi kui ka kõigi andmeallikas määratud olemite andmeid.

4. Kui soovite olemasoleva värskendamise tühistada, klõpsake **Lõpeta värskendamine** ja andmeallikas taastatakse viimase värskendamise olekusse.

## <a name="delete-a-data-source"></a>Andmeallika kustutamine

1. Avage suvandid **Andmed** > **Andmeallikad**.

2. Valige eemaldatava andmeallika kõrval vertikaalne ellips ja valige **Kustuta** ripploendist.

3. Kinnitage, et soovite kustutada.


[!INCLUDE [footer-include](includes/footer-banner.md)]