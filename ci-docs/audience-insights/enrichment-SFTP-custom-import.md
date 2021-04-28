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
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896276"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Kliendiprofiilide rikastamine kohandatud andmetega (eelversioon)

Turvalise failiedastuse protokolli (SFTP) kohandatud import võimaldab teil importida andmeid, mis ei pea läbima andmete ühendamise protsessi. See on paindlik, turvaline ja lihtne viis andmete sissetoomiseks. SFTP-põhist kohandatud importimist saab kasutada koos [SFTP-põhise ekspordiga](export-sftp.md), mis võimaldab teil eksportida kliendiprofiili andmeid, mida on vaja rikastamiseks. Seejärel saab andmeid töödelda, rikastada ning SFTP-põhist kohandatud importimist saab kasutada, et tuua rikastatud andmed tagasi Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsiooni.

## <a name="prerequisites"></a>Eeltingimused

SFTP-põhise kohandatud importimise konfigureerimiseks peavad olema täidetud järgmised eeltingimused.

- Teil on SFTP-hostis imporditava faili nimi ja asukoht (tee).
- Imporditavate andmete jaoks on olemas fail *model.json*, mis määrab [Common Data Model skeemi](/common-data-model/) imporditavatele andmetele. See fail peab asuma imporditava failiga samas kataloogis.
- Administraator on SFTP-ühenduse juba konfigureerinud *või* teil on [administraatoriõigused](permissions.md#administrator). SFTP asukoha jaoks, kust soovite andmeid importida, vajate kasutaja volikirja, URL-i ja pordi numbrit.


## <a name="configure-the-import"></a>Impordi konfigureerimine

1. Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.

1. **SFTP kohandatud impordipaanil** valige **Minu andmete rikastamine** ja seejärel valige **Alustamine**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP kohandatud impordipaan.":::

1. Valige ripploendist [ühendus](connections.md). Kui ühendusi pole saadaval, pöörduge administraatori poole. Kui olete administraator, saate ühenduse luua, valides ripploendist suvandi **Lisa ühendus** ja valides **SFTP kohandatud importimine**.

1. Valige **Ühenda kohandatud importimisega**, et kinnitada ühenduse valik.

1.  Valige **Edasi** ning sisestage **Faili nimi** ja **Tee** andmefaili kohta, mida soovite importida.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Kuvatõmmis andmeasukoha sisestamisel.":::

1. Valige **Edasi** ja sisestage rikastamise nimi ja väljundolemi nimi. 

1. Valige **Salvesta rikastamine** pärast valikute läbivaatamist.

## <a name="configure-the-connection-for-sftp-custom-import"></a>SFTP kohandatud impordi ühenduse konfigureerimine 

Ühenduste konfigureerimiseks peate olema administraator. Valige **Lisa ühendus** rikastamise konfigureerimisel *või* minge **Administraator** > **Ühendused** ja valige **Seadista** kohandatud importimise paanil.

1. Sisestage ühenduse nimi **Kuvatav nimi** väljale.

1. Sisestage imporditavate andmete SFTP-serveri jaoks kehtiv kasutajanimi, parool ja hosti URL.

1. Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**.

1. Valige **Kontrolli** konfiguratsiooni valideerimiseks.

1. Kui kontroll on lõpule jõudnud, saab ühenduse salvestada, klõpsates nuppu **Salvesta**.

> [!div class="mx-imgBorder"]
   > ![Experian ühenduse konfiguratsiooni paan](media/enrichment-SFTP-connection.png "Experian ühenduse konfiguratsiooni paan")


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
