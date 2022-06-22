---
title: Ettevõtte profiilide rikastamine Dun & Bradstreet'iga
description: Üldine teave Dun & Bradstreet kolmanda osapoole rikastamise kohta.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953886"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Ettevõtte profiilide rikastamine Dun & Bradstreet'iga (Eelvaade)

Dun & Bradstreet pakub ettevõtetele äriandmeid, analüütikat ja teadmisi. See võimaldab ettevõtetel kliendi koondprofiilidega klientide andmeid rikastada. Rikastamine hõlmab selliseid atribuute nagu DUNS-i number, ettevõtte suurus, asukoht, tööstus ja palju muud.

## <a name="prerequisites"></a>eeltingimused

- Aktiivne [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) litsents.
- [Ettevõtete ühtsed kliendiprofiilid](customer-profiles.md).
- Luuakse Dun & Bradstreet [projekt](#set-up-your-dun--bradstreet-project).
- Dun & Bradstreet [ühenduse](connections.md) konfigureerib [administraator](#configure-a-connection-for-dun--bradstreet).

## <a name="set-up-your-dun--bradstreet-project"></a>Dun & Bradstreet' projekti häälestamine

Dun & Bradstreet'i litsentseeritud kasutajana saate projekti [seadistada Dun & Bradstreet Connectis](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Logige sisse [Dun & Bradstreet Connecti](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Identimisteabe toomiseks taastage [parool](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Laadige alla [meie CSV-malli fail](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), mida kasutatakse väljade Customer Insights vastendamiseks vastavate Dun & Bradstreet väljadega.

1. Laadige fail **üles Dun & Bradstreeti projekti loomise kogemuse andmete** üleslaadimise etapis.

1. Valige äsja loodud Projekti Dun & Bradstreet vastava **allika** all horisontaalsed punktid, et näha saadaolevaid suvandeid.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Dun & Bradstreet projekti punktide kuvatõmmis.":::

1. Valige **Hangi S3 üksikasjad**. Hoidke seda teavet turvalises kohas. Teil on seda vaja, et häälestada [ühendus rikastamiseks](#configure-a-connection-for-dun--bradstreet) Customer Insightsis.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Kuvatõmmis s3-teabe valikust Dun & Bradstreet'i projektis.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Dun & Bradstreet'i ühenduse konfigureerimine

Peate olema Customer Insightsi administraator [ja teil peab olema](permissions.md#admin) Dun & Bradstreet Connecti mandaat.

1. Valige **rikastamise konfigureerimisel Ühendus Lisa ühendus** või avage **administraatoriühendused** > **ja** valige **paanil Dun & Bradstreet käsk Häälesta**.

1. Sisestage ühenduse nimi.

1. Esitage kehtiv Dun & Bradstreet'i mandaat ja Dun & Bradstreeti projekti üksikasjad *Piirkond, Kausta hülgamise tee ja Kausta Hülga nimi*. Sa [saad selle info](#set-up-your-dun--bradstreet-project) Dun & Bradstreet projektist.

1. Vaadake üle ja esitage oma nõusolek [Andmete privaatsuse ja nõuetele vastavus](#data-privacy-and-compliance) kohta, valides suvandi **Nõustun**.

1. Konfiguratsiooni kinnitamiseks valige **Kinnita** ja seejärel valige **Salvesta**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet ühenduse konfiguratsiooni leht.":::

### <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights edastada andmeid Dun & Bradstreet'ile, lubate andmete edastamise väljaspool nõuetele vastavuse piiri Dynamics 365 Customer Insights, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste kohaselt, kuid teie vastutate selle eest, et Dun & Bradstreet täidaks kõik privaatsus- või turbekohustused, mis teil võivad olla. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insights administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

## <a name="supported-countries-or-regions"></a>Toetatud riikides või regioonides

Praegu toetame järgmisi riigi/regiooni võimalusi: Kanada (inglise) või Ameerika Ühendriigid (inglise keeles).

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **Rikasta minu andmeid** paani Dun & Bradstreet ettevõtte andmete **kohta**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Kuvatõmmis paanist Dun & Bradstreet.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Valige ühendus ja kinnitage. Võtke ühendust administraatoriga, kui see pole saadaval.

1. Tehke valik **Edasi**.

1. **Valige kliendi andmestik** ja valige profiil või segment, mida soovite dun & Bradstreet'i ettevõtte andmetega rikastada. Olem *Klient* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

1. Määratlege, millist tüüpi välju teie ühtsetest profiilidest kasutada Dun & Bradstreet'i ettevõtte andmete sobitamiseks. Vähemalt üks väljadest **Nimi ja aadress**, **Telefon** või **E-post** on nõutav.

1. Vali **Järgmine**

1. Vastendage oma väljad Dun & Bradstreet'i ettevõtte andmetega. Nõutav on kas **DUNS-i number** või **ettevõtte** ja **riigi** nimi.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet välja vastendamise paan.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Sisestage **rikastamise nimi** ja väljundolemi **nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Rikastamisprotsessi alustamiseks või lehele Rikastamine naasmise **lähedal** valige **Käivita**.

## <a name="enrichment-results"></a>Rikastamise tulemused

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
