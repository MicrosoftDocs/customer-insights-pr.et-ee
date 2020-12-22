---
title: Customer Insightsi andmete eksportimine SFTP hostidesse
description: Teave selle kohta, kuidas konfigureerida ühendust SFTP hostiga.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643498"
---
# <a name="connector-for-sftp-preview"></a>SFTP konnektor (eelversioon)

Kasutage oma kliendiandmeid kolmanda osapoole rakendustes, eksportides need turvalise failiedastuse protokolli (SFTP) hosti.

## <a name="prerequisites"></a>Eeltingimused

- SFTP hosti ja vastavate mandaatide kättesaadavus.

## <a name="connect-to-sftp"></a>SFTP-ga ühenduse loomine

1. Avage **Haldus** > **Ekspordi sihtkohad**.

1. Valige jaotises **SFTP** suvand **Seadistamine**.

1. Sisestage väljale **Kuvatav nimi** oma sihtkoha äratuntav nimi.

1. Sisestage oma SFTP konto jaoks **Kasutajanimi**, **Parool** ja **Hostinimi**. Näide: kui teie SFTP serveri juurkaust on /root/folder ning te soovite, et andmed eksporditakse kohta /root/folder/ci_export_destination_folder, peab host olema sftp://<server_address>/ci_export_destination_folder".

1. Valige ühenduse testimiseks **Kinnita**.

1. Pärast edukat kinnitamist valige, kas soovite oma andmed eksportida **pakituna** või **lahtipakituna** ja valige eksporditud failide **väljaeraldaja**.

1. **Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.

1. Ekspordi konfigureerimise alustamiseks valige **Edasi**.

## <a name="configure-the-connection"></a>Ühenduse kontrollimine

1. Valige **kliendi atribuudid**, mille soovite eksportida. Saate eksportida ühe või mitu atribuuti.

1. Tehke valik **Edasi**.

1. Valige segmendid, mille soovite eksportida.

1. Valige **Salvesta**.

## <a name="export-the-data"></a>Andmete eksportimine

Saate [vajadusel andmeid eksportida](export-destinations.md). Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Andmete privaatsus ja nõuetele vastavus

Kui lubate Dynamics 365 Customer Insightsil SFTP kaudu andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed). Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et ekspordisihtkohad täidavad kõik teie privaatsus- või turbenõuded. Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).
Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.
