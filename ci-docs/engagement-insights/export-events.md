---
title: Täpsustatud sündmuste eksportimine
description: Täpsustatud sündmuste ja baassündmuste eksportimine.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7881f8f63134170a7f76e3c75dcfc5fa8930754b
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606200"
---
# <a name="export-events"></a>Sündmuste eksportimine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Sündmus tähistab kasutaja käitumist. See kirje salvestab, kui kasutaja vaatab lehte (kuvasündmus) või suhtleb sisuga (toimingusündmus). Kui saate otsustada, millised andmete atribuudid soovite aruandes kuvada, nimetatakse seda andmete virtuaalvaadet *Täpsustatud sündmuseks*. Lisateavet leiate teemast [Sündmuste loomine ja muutmine](refined-events.md).

- Saate eksportida sündmusi ja täpsustatud sündmusi välismälusse. 
- Eksport on edasine andmevoog. Voogu ei saa uuesti täita. 
- Ekspordil on fikseeritud skeemid. Kui lisate sündmusele kohandatud atribuudid, siis neid ei kaasata. Peate looma uue ekspordi.

## <a name="prerequisites"></a>Eeltingimused

Enne ekspordi seadistamist peab teil olema juurdepääs Azure'i portaalile ja aktiivne kordustellimus. Teil on eksportimise ajal vaja mäluruumikonto teavet. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Loo Azure Data Lake Storage Gen 2 konto

1. Logige Azure'i portaali sisse [ja looge uus mäluruumi konto](/azure/storage/common/storage-account-create). 

1. Veenduge, et lubate **Hierarhilise nimeruumi** valiku **Täpsem** vahekaardil. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Veenduge, et lubate hierarhilise nimeruumi täpsemat valikut vahekaardil.":::

1. Pärast selle juurutamist minge äsja loodud salvestusruumikontole. Valige navigeerimispaanilt **Sätted** > **Juurdepääsemisklahvid**. 

1. Kopeerige **Ettevõtte nimi** ja **Võti** et neid uue ekspordi loomisel kasutada.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Juurdepääsuklahvid mäluruumikontol.":::

## <a name="export-events"></a>Ekspordi sündmused

Dialoogi **Sündmuste eksportimine** avamiseks on kaks võimalust: 
- Minge jaotisesse **Andmed** > **Eksport** ja valige **Uus eksport**.
- Minge **Andmed** > **Sündmused**, valige **Veel [...]** sündmuse kõrvalt, mida te soovite eksportida ja valige ripploendist käsk **Ekspordi**. 

:::image type="content" source="media/new-export.png" alt-text="Uue ekspordi loomine.":::

Teid juhendatakse ekspordi loomisel:

1. Sisestage **Ekspordi nimi** ja seejärel valige **Edasi**.

1. Valige **Sündmuste valik** ripploendist baassündmused ja täpsustatud sündmused, mille soovite eksporti kaasata. 

1. Valige jaotises **Faili struktuur** soovitud sagedus (tund või päev), et luua sihtmälus uued failid, ja seejärel valige **Edasi**. Sündmusi eksporditakse saabudes pidevalt.

1. Valige ekspordivorming dialoogis **Vormingu valimine**. Valige suvand **Tavalised andmemudelid**, **CSV** ja **JSON** vormingud. Eksportimiseks koos muude Dynamics 365 rakendustega soovitame kasutada **Common Data Model** vormingut.

1. Määrake dialoogiboksis **Sihtkoha valimine** Azure Data Lake Storage Gen 2 asukoht.
    1. **ADLS Gen 2 konto nimi** on selle mäluruumikonto nimi, kuhu soovite eksportimise salvestada. 
    1. **Kaustatee** määratleb, kuhu ekspordi tuleks salvestada salvestusruumikonto failisüsteemis ja kataloogistruktuuris.
    1. **Ühisvõti** on saadaval Azure'i portaalis salvestusruumi konto jaoks.

1. Vaadake oma valikud läbi ja kinnitage, et soovite lõpetada.

## <a name="view-and-manage-exports"></a>Veebilehtede vaatamine ja haldamine

Kui olete ekspordi seadistanud, minge **Andmete** > **Eksport** vaatesse. Valige **Veel [...]** kui soovite olemasolevat eksporti redigeerida või kustutada.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
