---
title: Rikastamine SFTP-põhist kohandatud importimist kasutades
description: Üldine teave SFTP-põhise kohandatud importimise kaudu rikastamise kohta.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b67aa7477033222b0bc9512a962a1580edd973b4882ce925620ff5ec14f83fe3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032707"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Kliendiprofiilide rikastamine kohandatud andmetega (eelversioon)

Turvalise failiedastuse protokolli (SFTP) põhine kohandatud importimine võimaldab importida andmeid, mida ei pea koondama. See on paindlik, turvaline ja lihtne viis andmete sissetoomiseks. SFTP-põhist kohandatud importimist saab kasutada koos [SFTP-põhise ekspordiga](export-sftp.md), mis võimaldab teil eksportida kliendiprofiili andmeid, mida on vaja rikastamiseks. Andmeid saab seejärel töödelda ja rikastada ning SFTP kohandatud importi saab kasutada, et tuua rikastatud andmed tagasi Dynamics 365 Customer Insights vaatajaskonna ülevaate võimekusse.

## <a name="prerequisites"></a>Eeltingimused

SFTP-põhise kohandatud importimise konfigureerimiseks peavad olema täidetud järgmised eeltingimused.

- Teil on SFTP-hostis imporditava faili nimi ja asukoht (tee).
- Imporditavate andmete jaoks on olemas fail *model.json*, mis määrab [Common Data Model skeemi](/common-data-model/) imporditavatele andmetele. See fail peab asuma imporditava failiga samas kataloogis.
- Administraator on SFTP-ühenduse juba konfigureerinud *või* teil on [administraatoriõigused](permissions.md#administrator). SFTP asukoha jaoks, kust soovite andmeid importida, vajate kasutaja volikirja, URL-i ja pordi numbrit.


## <a name="configure-the-import"></a>Impordi konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. **SFTP kohandatud impordipaanil** valige **Minu andmete rikastamine** ja seejärel valige **Alustamine**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP kohandatud impordipaan.":::

1. Valige [ühendus](connections.md) ripploendist. Kui ühendusi pole saadaval, pöörduge administraatori poole. Kui olete administraator, saate ühenduse luua, valides **Lisa ühendus** käsu ja valides **SFTP Custom Import** ripploendist.

1. Valige **Ühenda kohandatud importimisega**, et kinnitada ühenduse valik.

1.  Valige **Edasi** ning sisestage imporditava andmefaili **Tee** ja **Failinimi**.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Kuvatõmmis andmeasukoha sisestamisel.":::

1. Valige **Edasi** ja sisestage rikastamise nimi ja väljundolemi nimi. 

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP kohandatud impordi ühenduse konfigureerimine 

Ühenduste konfigureerimiseks peate olema administraator. Valige **Lisa ühendus** rikastamise konfigureerimisel *või* minge **Administraator** > **Ühendused** ja valige **Seadista** kohandatud importimise paanil.

1. Sisestage ühenduse nimi **Kuvatav nimi** väljale.

1. Sisestage SFTP-serveri jaoks kehtiv kasutajanimi, parool ja hosti URL, kus imporditavad andmed asuvad.

1. Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**.

1. Valige **Kontrolli** konfiguratsiooni valideerimiseks.

1. Kui kontroll on lõpule jõudnud, saab ühenduse salvestada, valides **Salvesta**.

   > [!div class="mx-imgBorder"]
   > ![Experian ühenduse konfiguratsiooni paan.](media/enrichment-SFTP-connection.png "Experian ühenduse konfiguratsiooni paan")


## <a name="defining-field-mappings"></a>Väljavastenduste määratlemine 

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

Rikastatud kliendiandmetele toetumine. Looge [segmente](segments.md) ja [näitajaid](measures.md) ning [eksportige andmed](export-destinations.md), et pakkuda oma klientidele isikupärastatud kogemust.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
