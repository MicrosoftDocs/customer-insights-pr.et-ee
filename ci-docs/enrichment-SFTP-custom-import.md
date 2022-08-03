---
title: Rikastage kliendiprofiile SFTP kohandatud impordiga (eelvaade)
description: Üldine teave SFTP-põhise kohandatud importimise kaudu rikastamise kohta.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 81ef6c62240e26cb5c9475e6306e08edc7e5eb31
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195791"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>Rikastage kliendiprofiile SFTP kohandatud impordiga (eelvaade)

Turvalise failiedastuse protokolli (SFTP) põhine kohandatud importimine võimaldab importida andmeid, mida ei pea koondama. See on paindlik, turvaline ja lihtne viis andmete sissetoomiseks. SFTP-põhist kohandatud importimist saab kasutada koos [SFTP-põhise ekspordiga](export-sftp.md), mis võimaldab teil eksportida kliendiprofiili andmeid, mida on vaja rikastamiseks. Seejärel saab andmeid töödelda ja rikastada ning rikastatud andmete taastamiseks saab kasutada SFTP kohandatud importi Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>eeltingimused

- SFTP-hostisse imporditava faili nimi ja asukoht (tee) on teada.

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

Peate olema Customer Insightsi administraator [ja](permissions.md#admin) teil peab olema selle SFTP-asukoha kasutajamandaat, URL ja pordinumber, kust soovite andmeid importida.

1. Rikastamise konfigureerimisel valige **Lisa ühendus** või minge jaotisse **Administraatori** > **ühendused** ja valige paanil Kohandatud import käsk **Häälesta**.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Leht Kohandatud impordiühenduse konfiguratsioon.":::

1. Sisestage ühenduse nimi.

1. Sisestage SFTP-serveri jaoks kehtiv kasutajanimi, parool ja hosti URL, kus imporditavad andmed asuvad.

1. Vaadake üle ja esitage oma nõusolek [Andmete privaatsuse ja nõuetele vastavus](#data-privacy-and-compliance) kohta, valides suvandi **Nõustun**.

1. Valige **konfiguratsiooni valideerimiseks Kinnita** ja seejärel valige **Salvesta**.

### <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insights andmete edastamise kohandatud impordi abil, lubate edastada andmeid väljaspool nõuetele vastavuse piire, sh potentsiaalselt tundlike andmete puhul Dynamics 365 Customer Insights, nagu isikuandmed. Microsoft edastab selliseid andmeid teie korraldusel, kuid teie vastutate selle eest, et andmed vastaksid kõigile teie privaatsus- või turbekohustustele. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insights administraator saab selle rikastamise igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.

## <a name="configure-the-import"></a>Impordi konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **Rikasta minu andmeid** **SFTP kohandatud impordi** paanil.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP kohandatud impordipaan.":::

1. Vaadake ülevaade üle ja seejärel valige **Edasi**.

1. Valige ühendus. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. **Valige kliendiandmete kogum** ja valige profiil või segment, mida soovite rikastada. Kliendi *olem* rikastab kõiki teie kliendiprofiile, samas kui segment rikastab ainult selles segmendis sisalduvaid kliendiprofiile.

1. Tehke valik **Edasi**.

1. Sisestage **imporditava andmefaili tee** ja **failinimi**.

1. Tehke valik **Edasi**.

1. Sisestage **rikastamise nimi** ja **väljundolemi nimi**.

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

1. Valige **Käivita**, et alustada rikastamisprotsessi või sulgeda, et naasta **lehele Rikastamised**.

## <a name="view-enrichment-results"></a>Rikastumistulemuste vaatamine

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Järgmised toimingud

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
