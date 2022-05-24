---
title: Ettevõtte profiilide rikastamine Dun & Bradstreet'iga
description: Üldine teave Dun & Bradstreet kolmanda osapoole rikastamise kohta.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755395"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Ettevõtte profiilide rikastamine Dun & Bradstreet'iga (Eelvaade)

Dun & Bradstreet pakub ettevõtetele äriandmeid, analüütikat ja teadmisi. See võimaldab ettevõtetel kliendi koondprofiilidega klientide andmeid rikastada. Rikastamine hõlmab selliseid atribuute nagu DUNS-i number, ettevõtte suurus, asukoht, tööstus ja palju muud.

## <a name="prerequisites"></a>eeltingimused

Dun & Bradstreet'i rikastamise konfigureerimiseks peavad olema täidetud järgmised eeltingimused.

- Teil on aktiivne [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) litsents.
- Teil on ettevõtete [kliendi koondprofiilid](customer-profiles.md).
- Dun & Bradstreet [ühenduse](connections.md) konfigureerib administraator. Saate selle luua, kui teil on [administraatoriõigused](permissions.md#admin) ja identimisteave saidilt Dun & Bradstreet Connect.

## <a name="setting-up-your-dun--bradstreet-project"></a>Dun & Bradstreet'i projekti seadistamine

Dun & Bradstreet'i litsentseeritud kasutajana saate projekti [seadistada Dun & Bradstreet Connectis](https://connect.dnb.com?lead_source=microsoft_audienceinsights).


1. Logige sisse [Dun & Bradstreet Connecti](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Identimisteabe toomiseks taastage [parool](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Laadige alla [meie CSV-malli fail](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv), mida kasutatakse väljade Customer Insights vastendamiseks vastavate Dun & Bradstreet väljadega.

1. Laadige fail **üles Dun & Bradstreeti projekti loomise kogemuse andmete** üleslaadimise etapis.

1. Valige äsja loodud Projekti Dun & Bradstreet vastava **allika** all horisontaalsed punktid, et näha saadaolevaid suvandeid.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Dun & Bradstreet projekti punktide kuvatõmmis.":::

1. Valige **Hangi S3 üksikasjad**. Hoidke seda teavet turvalises kohas. Teil on seda vaja, et häälestada [ühendus rikastamiseks](#configure-a-connection-for-dun--bradstreet) Customer Insightsis.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Kuvatõmmis s3-teabe valikust Dun & Bradstreet'i projektis.":::

## <a name="configure-the-enrichment"></a>Rikastamise konfigureerimine

1. Avage **Andmed** > **Rikastamine**.

1. Valige **Paanil Dun & Bradstreet suvand Rikasta minu andmeid** ja valige **Alustamine**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Kuvatõmmis paanist Dun & Bradstreet.":::

1. Valige [ühendus](connections.md) ripploendist. Kui ühendusi pole saadaval, pöörduge administraatori poole. Kui olete administraator, saate luua ühenduse. Valige **Lisa ühendus** ja valige **Dun & Bradstreet**.

1. Ühenduse kinnitamiseks valige **Ühenda Dun & Bradstreet'iga**.

1. Valige **Edasi** ja valige **kliendi andmekogum**, mida soovite ettevõtte andmetega rikastada Ettevõtte andmetega Ettevõttest Dun & Bradstreet. Saate valida **olemi Klient**, et rikastada kõiki oma kliendiprofiile, või valida segmendiolemi, et rikastada ainult selles segmendis sisalduvaid ühtseid kliendiprofiile.

1. Valige **Edasi** ja määratlege, milliseid teie ühtsete profiilide välju kasutatakse Dun & Bradstreet'ist sobivate ettevõtte andmete otsimiseks. Nõutav on kas **DUNS-i number** või **ettevõtte** ja **riigi** nimi. Riigiväli toetab [kahe- või kolmetähelisi riigikoode](https://www.iso.org/iso-3166-country-codes.html), riigi nime inglise keeles, riigi nime emakeeles ja telefoni eesliidet. Mõned levinud riigivariandid on järgmised:

- USA: Ameerika Ühendriigid, Ameerika Ühendriigid, Ameerika Ühendriigid, USA, Ameerika Ühendriigid.
- CA: Kanada.
- GB: Ühendkuningriik, Suurbritannia, Suurbritannia, GB, Suurbritannia ja Põhja-Iiri Ühendkuningriik, Suurbritannia Ühendkuningriik.
- AU: Austraalia, Austraalia Ühendus.
- FR: Prantsusmaa, Prantsuse Vabariik.
- DE: Saksamaa, Saksa, Deutschland, Allemagne, Saksamaa Liitvabariik, Saksamaa Vabariik.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Dun & Bradstreet välja vastendamise paan.":::

1. Valige **Edasi**, et lõpetada väljade kaardistamine.

1. Sisestage rikastamiseks nimi ja valige **Salvesta rikastamine** pärast valikute läbivaatamist.

## <a name="configure-a-connection-for-dun--bradstreet"></a>Dun & Bradstreet'i ühenduse konfigureerimine

Ühenduste konfigureerimiseks peate olema administraator. Valige **rikastamise** konfigureerimisel Ühendus Lisa ühendus *või* avage **administraatoriühendused** > **ja** valige **paanil Dun & Bradstreet käsk Häälesta**.

1. Seejärel valige suvand **Alustamine**.

1. Sisestage ühenduse nimi **Kuvatav nimi** väljale.

1. Esitage kehtiv Dun & Bradstreet'i mandaat ja Dun & Bradstreeti projekti üksikasjad *Piirkond, Kausta hülgamise tee ja Kausta Hülga nimi*. Sa [saad selle info](#setting-up-your-dun--bradstreet-project) Dun & Bradstreet projektist.

1. Vaadake üle ja esitage oma nõusolek **Andmete privaatsuse ja nõuetele vastavus** kohta, valides suvandi **Nõustun**.

1. Valige **Kontrolli** konfiguratsiooni valideerimiseks.

1. Pärast kontrollimise lõpuleviimist valige **Salvesta**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Dun & Bradstreet ühenduse konfiguratsiooni leht.":::

## <a name="enrichment-results"></a>Rikastamise tulemused

Pärast rikastamise värskendamist saate värskelt rikastatud ettevõtte andmed üle vaadata jaotises [Minu rikastamised](enrichment-hub.md). Kuvatakse viimase värskendamise aeg ja rikastatud profiilide arvu.

Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.

## <a name="next-steps"></a>Järgmised etapid

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights edastada andmeid Dun & Bradstreet'ile, lubate andmete edastamise väljaspool nõuetele vastavuse piiri Dynamics 365 Customer Insights, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste kohaselt, kuid teie vastutate selle eest, et Dun & Bradstreet täidaks kõik privaatsus- või turbekohustused, mis teil võivad olla. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insights administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

[!INCLUDE[footer-include](includes/footer-banner.md)]
