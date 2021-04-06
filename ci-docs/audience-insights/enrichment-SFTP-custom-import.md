---
title: Rikastamine SFTP-põhist kohandatud importimist kasutades
description: Üldine teave SFTP-põhise kohandatud importimise kaudu rikastamise kohta.
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595850"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Kliendiprofiilide rikastamine kohandatud andmetega (eelversioon)

Turvalise failiedastuse protokolli (SFTP) põhine kohandatud importimine võimaldab importida andmeid, mida ei pea koondama. See on paindlik, turvaline ja lihtne viis andmete sissetoomiseks. SFTP-põhist kohandatud importimist saab kasutada koos [SFTP-põhise ekspordiga](export-sftp.md), mis võimaldab teil eksportida kliendiprofiili andmeid, mida on vaja rikastamiseks. Seejärel saab andmeid töödelda, rikastada ning SFTP-põhist kohandatud importimist saab kasutada, et tuua rikastatud andmed tagasi Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsiooni.

## <a name="prerequisites"></a>Eeltingimused

SFTP-põhise kohandatud importimise konfigureerimiseks peavad olema täidetud järgmised eeltingimused.

- Teil on selle SFTP asukoha identimisteave (kasutajanimi ja parool), kust andmeid hakatakse importima.
- Teil on STFP hosti URL ja pordinumber (tavaliselt 22).
- Teil on selle faili failinimi ja asukoht, mis imporditakse SFTP hosti kaudu.
- Seal on fail *model.json*, mis määratleb imporditavate andmete skeemi. See fail peab asuma imporditava failiga samas kataloogis.
- Teil on [administraatori](permissions.md#administrator) õigused.

## <a name="configuration"></a>Konfiguratsioon

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. Valige **SFTP-põhise kohandatud importimise paanil** suvand **Rikasta mu andmeid**.

   > [!div class="mx-imgBorder"]
   > ![SFTP-põhise kohandatud importimise paan](media/SFTP_Custom_Import_tile.png "SFTP-põhise kohandatud importimise paan")

1. Valige **Alusta** ning sisestage SFTP serveri identimisteave ja aadress. Näiteks sftp://mysftpserver.com:22.

1. Sisestage faili nimi, mis sisaldab andmeid ja failiteed SFTP serveris, kui see pole juurkaustas.

1. Kinnitage kõik sisendid, valides **Ühenda kohandatud importimisega**.

   > [!div class="mx-imgBorder"]
   > ![SFTP-põhise kohandatud importimise konfiguratsiooni hüpik](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP-põhise kohandatud importimise konfiguratsiooni hüpik")

## <a name="defining-field-mappings"></a>Väljavastenduste määratlemine 

Kataloog, mis sisaldab faili, mis imporditakse SFTP serveris, peab sisaldama ka faili *model.json*. See fail määratleb andmete importimiseks kasutatava skeemi. Skeem peab väljavastenduste määratlemiseks kasutama [Common Data Modelit](/common-data-model/). Lihtne näide model.json-failist on järgmine.

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
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
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

## <a name="enrichment-results"></a>Rikastamise tulemused

Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**. Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab). Töötlemise aeg sõltub imporditavate andmete mahust ja ühendusest SFTP serveriga.

Pärast rikastamisprotsessi lõpuleviimist saate oma värskelt imporditud kohandatud rikastatud andmed üle vaadata jaotises **Minu rikastamised**. Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.

Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.

## <a name="next-steps"></a>Järgmised etapid

Rikastatud kliendiandmetele toetumine. Looge [segmente](segments.md), [näitajaid](measures.md) ja [eksportige andmeid](export-destinations.md), et pakkuda klientidele isikupärastatud kogemust.




[!INCLUDE[footer-include](../includes/footer-banner.md)]