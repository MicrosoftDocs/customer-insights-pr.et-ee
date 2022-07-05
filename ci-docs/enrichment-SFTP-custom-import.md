---
title: Kliendiprofiilide rikastamine SFTP kohandatud impordiga (eelvaade)
description: Üldine teave SFTP-põhise kohandatud importimise kaudu rikastamise kohta.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 88fc366ab9478c3b67034af794e237ff4573da7c
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082320"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Kliendiprofiilide rikastamine SFTP kohandatud impordiga (eelvaade)

Turvalise failiedastuse protokolli (SFTP) põhine kohandatud importimine võimaldab importida andmeid, mida ei pea koondama. See on paindlik, turvaline ja lihtne viis andmete sissetoomiseks. SFTP-põhist kohandatud importimist saab kasutada koos [SFTP-põhise ekspordiga](export-sftp.md), mis võimaldab teil eksportida kliendiprofiili andmeid, mida on vaja rikastamiseks. Seejärel saab andmeid töödelda ja rikastada ning SFTP kohandatud importi saab kasutada rikastatud andmete taastamiseks Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>eeltingimused

- SFTP hostis imporditava faili faili nimi ja asukoht (tee) on teada.

- Saadaval *on fail model.json*, mis määrab imporditavate andmete jaoks ühise andmemudeli skeemi. See fail peab asuma imporditava failiga samas kataloogis.

- SFTP-ühendus [on](connections.md) [konfigureeritud](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Failiskeemi näide

Kataloog, mis sisaldab faili, mis imporditakse SFTP serveris, peab sisaldama ka faili *model.json*. See fail määratleb andmete importimiseks kasutatava skeemi. Skeemis tuleb kasutada [Common Data Model](/common-data-model/) välja kaardistamise määramiseks. Lihtne näide model.json-failist on järgmine.

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP kohandatud impordi ühenduse konfigureerimine

Peate olema Customer Insightsi administraator [ja teil peab olema](permissions.md#admin) kasutajamandaat, URL ja pordi number SFTP asukohas, kust soovite andmeid importida.

1. Valige **Rikastamise konfigureerimisel Nupp Lisa ühendus** või minge valikule **Administraatoriühendused** > **ja** valige paanil Kohandatud import käsk **Häälesta**.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Kohandatud impordi ühenduse konfiguratsiooni leht.":::

1. Sisestage ühenduse nimi.

1. Sisestage SFTP-serveri jaoks kehtiv kasutajanimi, parool ja hosti URL, kus imporditavad andmed asuvad.

1. Vaadake üle ja esitage oma nõusolek [Andmete privaatsuse ja nõuetele vastavus](#data-privacy-and-compliance) kohta, valides suvandi **Nõustun**.

1. Konfiguratsiooni kinnitamiseks valige **Kinnita** ja seejärel valige **Salvesta**.

### <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights andmeid edastada kohandatud impordi abil, lubate andmete edastamise väljaspool nõuetele vastavuse piiri Dynamics 365 Customer Insights, sealhulgas potentsiaalselt tundlikke andmeid, näiteks isikuandmeid. Microsoft edastab sellised andmed teie juhiste kohaselt, kuid teie vastutate selle eest, et andmed vastaksid mis tahes privaatsus- või turbekohustustele, mis teil võivad olla. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insights administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

## <a name="configure-the-import"></a>Impordi konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige SFTP kohandatud impordipaanil **käsk** **Rikasta minu andmeid**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP kohandatud impordipaan.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Valige ühendus. Võtke ühendust administraatoriga, kui see pole saadaval.

1. **Valige kliendi andmestik** ja valige profiil või segment, mida soovite rikastada. Olem *Klient* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

1. Tehke valik **Edasi**.

1. **Sisestage imporditava andmefaili tee**- ja **failinimi**.

1. Tehke valik **Edasi**.

1. Sisestage **rikastamise nimi** ja väljundolemi **nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Rikastamisprotsessi alustamiseks või lehele Rikastamine naasmise **lähedal** valige **Käivita**.

## <a name="view-enrichment-results"></a>Rikastamise tulemuste kuvamine

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
