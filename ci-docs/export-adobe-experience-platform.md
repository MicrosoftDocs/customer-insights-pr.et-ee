---
title: Segmentide eksportimine Adobe Experience Platform (eelvaade)
description: Vaadake, kuidas kasutada Customer Insightsi segmente rakenduses Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195285"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Segmentide eksportimine Adobe Experience Platform (eelvaade)

Eksportige segmente, mis on suunatud asjakohastele sihtrühmadele Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Selles artiklis kirjeldatud juhiste protsessiskeem.":::

## <a name="prerequisites"></a>eeltingimused

- Litsents Adobe Experience Platform.
- Kampaania Adobe standardlitsents.
- Azure'i [bloobi salvestusruumi konto](/azure/storage/blobs/create-data-lake-storage-account) nimi ja konto võti. Nime ja võtme leidmiseks vaadake teemat [Salvestuskonto sätete haldamine Azure'i portaalis](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Kampaania ülevaade

Customer Insightsi Adobe Experience Platform segmentide kasutamise paremaks mõistmiseks vaatame fiktiivset näidiskampaaniat.

Oletame, et teie ettevõte pakub teie USA klientidele igakuiseid, tellimusepõhiseid teenuseid. Soovite tuvastada kliendid, kelle kordustellimusi tuleb järgmise kaheksa päeva pärast uuendada, kuid kes pole veel oma kordustellimust pikendanud. Kui soovite need kliendid säilitada, soovite neile saata meiliga reklaampakkumise, kasutades selleks rakendust Adobe Experience Platform.

Selles näites soovime käivitada ühekordse reklaamikampaania meili teel. See artikkel ei hõlma kampaania läbiviimist rohkem kui üks kord.

## <a name="identify-your-target-audience"></a>Sihtrühma tuvastamine

Meie stsenaariumi puhul eeldame, et klientide e-posti aadressid on Customer Insightsis saadaval ja nende reklaamieelistusi analüüsiti segmendi liikmete tuvastamiseks.

[Customer Insightsis](segments.md) määratletud segment kannab nime **ChurnProneCustomers** ja kavatsete saata neile klientidele e-posti reklaami.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Kuvatõmmis loodud ChurnProneCustomersi segmendiga segmentide lehest.":::

Väljasaatmiseks mõeldud pakkumismeilis on eesnimi, perekonnanimi ja kliendi kordustellimuse lõppkuupäev. See teavitab klienti allahindlusest, mille nad saavad, kui nad oma kordustellimuse enne aegumist pikendavad.

## <a name="export-your-target-audience"></a>Sihtrühma eksportimine

Konfigureerime ekspordi Customer Insightsist Azure'i bloobimälu kontole.

### <a name="set-up-connection-to-azure-blob-storage"></a>Azure'i bloobimäluga ühenduse loomine

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Azure'i bloobimälu**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage **Konto nimi**, **Konto võti**, ja **Konteiner** Blob Storage konto jaoks, kuhu soovite segmendi eksportida.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Salvestusruumi konto konfiguratsiooni kuvatõmmis. ":::

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

### <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus Azure Blob Storage jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige segment, mille soovite eksportida. Selles näites on selleks **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Valitud segmendiga ChurnProneCustomers segmendivaliku kasutajaliidese kuvatõmmis.":::

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Veenduge, et eksporditud segmendis olevate kirjete arv oleks teie Adobe Campaign Standardi litsentsi lubatud piires.

Eksporditud andmed salvestatakse konfigureeritud Azure'i bloobimälu konteinerisse. Konteineris luuakse automaatselt järgmised kaustateed.

- Lähteolemite ja süsteemi loodud olemite jaoks:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- Eksporditud olemite *model.json* asub tasemel *%ExportDestinationName%*.

  Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Kogemuse andmemudeli (XDM) määratlemine rakenduses Adobe Experience Platform

Enne kui Customer Insightsist eksporditud andmeid saab kasutada Adobe Experience Platform, määratlege kogemuse andmemudeli skeem ja [konfigureerige andmed reaalajas kliendiprofiili](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials) jaoks.

Lugege, [mis on XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ja tutvuge [skeemi loomise põhitõdedega](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Andmete importimine Adobe Experience Platform'i

Importige ettevalmistatud vaatajaskonna andmed Customer Insightsist rakendusse Adobe Experience Platform.

1. [Looge Azure'i bloobimälu allikaühendus](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Konfigureerige andmevoog](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pilvsalvestusruumi partiiühenduse jaoks, et importida segmendiväljund Customer Insightsist rakendusse Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Sihtrühma loomine rakenduses Adobe Campaign Standard

Selle kampaania meili saatmiseks kasutame Adobe Campaign Standard'it.

1. [Looge kampaaniastandardis vaatajaskond](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission)Adobe, kasutades jaotises Adobe Experience Platform.

1. [Kasutage kampaania standardis segmendikoosturit](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) vaatajaskonna määratlemiseks jaotises Adobe.Adobe Experience Platform

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Meili loomine ja saatmine Adobe Campaign Standard abil

Looge meilisisu ja seejärel [testige ja saatke](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) oma meil.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Näidismeil uuenduspakkumisega rakendusest Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
