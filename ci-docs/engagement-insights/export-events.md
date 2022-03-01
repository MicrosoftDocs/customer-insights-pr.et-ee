---
title: Täpsustatud sündmuste eksportimine
description: Täpsustatud sündmuste ja baassündmuste eksportimine.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032380"
---
# <a name="export-events"></a>Sündmuste eksportimine

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Sündmus tähistab kasutaja käitumist. See kirje salvestab, kui kasutaja vaatab lehte (kuvasündmus) või suhtleb sisuga (toimingusündmus). Kui saate otsustada, millised andmete atribuudid soovite aruandes kuvada, nimetatakse seda andmete virtuaalvaadet *Täpsustatud sündmuseks*. 

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

Sündmuse ekspordiks on kaks võimalust: 
- Minge jaotisesse **Andmed** > **Eksport** ja valige **Uus eksport**.
- Minge **Andmed** > **Sündmused**, valige **Veel [...]** sündmuse kõrvalt, mida te soovite eksportida ja valige ripploendist käsk **Ekspordi**. 

Teid juhendatakse ekspordi loomisel:

1. Sisestage **Ekspordinimi**.

1. Valige **Sündmuste valik** ripploendist baassündmused ja täpsustatud sündmused, mille soovite eksporti kaasata. 

1. Jaotises **Faili struktuur** valige kadents, et luua uusi faile sihtlaos. Sündmusi eksporditakse saabudes pidevalt.

1. Valige ekspordivorming. Saate valida nii **Common Data Model**, **CSV** kui ka **JSON** vormingu. Eksportimiseks koos muude Dynamics 365 rakendustega soovitame kasutada Common Data Model vormingut.

1. Määrake jaotises **Valige sihtkoha** samm, täpsustades Azure Data Lake Storage Gen 2 asukoht.
    1. **ADLS Gen 2 konto nimi** on selle mäluruumikonto nimi, kuhu soovite eksportimise salvestada. 
    1. **Kaustatee** määratleb, kuhu ekspordi tuleks salvestada salvestusruumikonto failisüsteemis ja kataloogistruktuuris.
    1. **Ühisvõti** on saadaval Azure'i portaalis salvestusruumi konto jaoks.

1. Vaadake üle ja kinnitage oma valikud.

## <a name="view-and-manage-exports"></a>Veebilehtede vaatamine ja haldamine

Kui olete ekspordi seadistanud, minge **Andmete** > **Eksport** vaatesse. Valige **Veel [...]** kui soovite olemasolevat eksporti redigeerida või kustutada.


[!INCLUDE[footer-include](../includes/footer-banner.md)]