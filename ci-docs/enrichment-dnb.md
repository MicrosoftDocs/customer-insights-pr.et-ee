---
title: Rikastage ettevõtte profiile Dun ja Bradstreet’iga (eelvaade)
description: Üldine teave Dun / Bradstreet kolmanda osapoole rikastumise kohta.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237899"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>Rikastage ettevõtte profiile Dun ja Bradstreet’iga (eelvaade)

Dun ja Bradstreet pakub ettevõtetele äriandmeid, analüütikat ja teadmisi. See võimaldab ettevõtetel kliendi koondprofiilidega klientide andmeid rikastada. Rikastamised hõlmavad selliseid atribuute nagu DUNS-i number, ettevõtte suurus, asukoht, tööstus ja palju muud.

## <a name="prerequisites"></a>eeltingimused

- Aktiivne [Dun ja Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) litsents.
- [Ühtsed kliendiprofiilid](customer-profiles.md) ettevõtetele.
- Käivitatakse Dun ja Bradstreet [projekt](#set-up-your-dun--bradstreet-project).
- Dun ja Bradstreet [ühenduse](connections.md) konfigureerib [administraator](#configure-a-connection-for-dun--bradstreet).

## <a name="set-up-your-dun--bradstreet-project"></a>Seadistage oma Dun ja Bradstreet projekt

Dun & Bradstreet litsentsitud kasutajana saate seadistada projekti [Dun & Bradstreet Connectis](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Logige sisse [Dun ja Bradstreet Connecti](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Identimisteabe toomiseks taastage [oma parool](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Laadige alla [meie csv-malli fail](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), mida kasutatakse Customer Insightsi väljade vastendamiseks vastavate Dun ja Bradstreet väljadega.

1. Laadige fail **üles Dun & Bradstreet projekti loomise etapi andmete** üleslaadimise etapis.

1. Valige vastloodud Dun ja Bradstreet projektis vastava **allika** all olevad horisontaalsed punktid, et näha saadaolevaid suvandeid.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Dun ja Bradstreet projekti punktide kuvatõmmis.":::

1. Valige **Hangi S3 üksikasjad**. Hoidke seda teavet kindlas kohas. Teil on seda vaja, et seadistada [ühendus Customer Insightsi rikastamiseks](#configure-a-connection-for-dun--bradstreet).

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Kuvatõmmis s3 teabe valikust Dun ja Bradstreet projektis.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Dun ja Bradstreet ühenduse konfigureerimine

Peate olema Customer Insightsi administraator [ja](permissions.md#admin) teil peavad olema Dun ja Bradstreet Connecti mandaadid.

1. Rikastamise konfigureerimisel valige **Lisa ühendus** või minge jaotisse **Administraatori** > **ühendused** ja valige paanil Dun & Bradstreet käsk **Seadista**.

1. Sisestage ühenduse nimi.

1. Esitage kehtivad Dun & Bradstreet mandaadid ja Dun & Bradstreet projekti üksikasjad *Piirkond, Drop kausta tee ja Drop kausta nimi*. Selle teabe [saate](#set-up-your-dun--bradstreet-project) Dun ja Bradstreet projektist.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Valige **konfiguratsiooni valideerimiseks Kinnita** ja seejärel valige **Salvesta**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun ja Bradstreet ühenduse konfiguratsiooni leht.":::

## <a name="supported-countries-or-regions"></a>Toetatud riikides või regioonides

Praegu toetame järgmisi riigi/regiooni valikuid: Kanada (inglise keeles) või Ameerika Ühendriikides (inglise keeles).

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **Rikasta minu andmeid** ettevõtte andmetes **Dun** ja Bradstreet paani jaoks.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Dun ja Bradstreet plaadi kuvatõmmis.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Valige ühendus ja kinnitage. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Tehke valik **Edasi**.

1. **Valige kliendiandmete kogum** ja valige profiil või segment, mida soovite ettevõtte andmetega rikastada, alates Dun ja Bradstreet. Kliendi *olem* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

1. Määratlege, millist tüüpi välju oma ühtsetest profiilidest kasutada Ettevõtte andmete sobitamiseks Dun ja Bradstreet. Vähemalt üks väljadest **Nimi ja aadress**, **Telefon** või **E-post** on nõutav.

1. Vali **Järgmine**

1. Kaardistage oma väljad Dun ja Bradstreet ettevõtte andmetega. Kohustuslikud on kas **DUNS-i number** või **ettevõtte** nimi ja **riik**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun ja Bradstreet välikaardistuspaan.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Sisestage **rikastamise nimi** ja **väljundolemi nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Valige **Käivita**, et alustada rikastamisprotsessi või sulgeda, et naasta **lehele Rikastamised**.

## <a name="view-enrichment-results"></a>Rikastumistulemuste vaatamine

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
