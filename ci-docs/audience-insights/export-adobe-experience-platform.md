---
title: Customer Insightsi andmete eksportimine Adobe Experience Platformi
description: Lugege, kuidas kasutada Adobe Experience Platformi sihtrühmaülevaadete segmente.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596264"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Customer Insightsi segmentide kasutamine Adobe Experience Platformis (eelversioon)

Dynamics 365 Customer Insightsi sihtrühmaülevaadete kasutajana olete võib-olla loonud segmente turunduskampaaniate tõhusamaks muutmiseks asjakohaseid sihtrühmi määrates. Adobe Experience Platformi ja rakendustest, nagu Adobe Campaign Standard pärit segmentide kasutamiseks peate järgima mõnda selles artiklis kirjeldatud juhist.

:::image type="content" source="media/AEP-flow.png" alt-text="Selles artiklis kirjeldatud juhiste protsessiskeem.":::

## <a name="prerequisites"></a>Eeltingimused

-   Dynamics 365 Customer Insightsi litsents
-   Adobe Experience Platformi litsents
-   Adobe Campaign Standardi litsents
-   Azure’i bloobimälu konto

## <a name="campaign-overview"></a>Kampaania ülevaade

Et paremini mõista, kuidas kasutada Adobe Experience Platformi sihtrühmaülevaadete segmente, vaatame väljamõeldud näidiskampaaniat.

Oletame, et teie ettevõte pakub teie USA klientidele igakuiseid, tellimusepõhiseid teenuseid. Soovite tuvastada kliendid, kelle kordustellimusi tuleb järgmise kaheksa päeva pärast uuendada, kuid kes pole veel oma kordustellimust pikendanud. Nende klientide alleshoidmiseks, soovite meili teel saata neile reklaampakkumise Adobe Experience Platformi kaudu.

Selles näites soovime käivitada ühekordse reklaamikampaania meili teel. See artikkel ei hõlma kampaania läbiviimist rohkem kui üks kord.

## <a name="identify-your-target-audience"></a>Sihtrühma tuvastamine

Meie stsenaariumis eeldame, et klientide meiliaadressid on sihtrühmaülevaadetes saadaval ja nende reklaamieelistusi on analüüsitud segmendi liikmete tuvastamiseks.

[Sihtrühmaülevaadetes määratletud segmendi](segments.md) nimeks on **ChurnProneCustomers** ja plaanite neile klientidele saata meilikampaania.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Kuvatõmmis loodud ChurnProneCustomersi segmendiga segmentide lehest.":::

Väljasaatmiseks mõeldud pakkumismeilis on eesnimi, perekonnanimi ja kliendi kordustellimuse lõppkuupäev. See teavitab klienti allahindlusest, mille nad saavad, kui nad oma kordustellimuse enne aegumist pikendavad.

## <a name="export-your-target-audience"></a>Sihtrühma eksportimine

Kui sihtrühm on tuvastatud, saame konfigureerida ekspordi sihtrühmaülevaadetest Azure'i bloobimälu kontole.

1. Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.

1. Tehke paanil **Azure'i bloobimälu** valik **Häälestamine**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure'i bloobimälu konfiguratsioonipaan.":::

1. Sisestage uue ekspordisihtkoha jaoks **Kuvatav nimi** ja seejärel sisestage **Konto nimi**, **Konto võti** ja selle Azure'i bloobimälu **Ümbris**, kuhu soovite segmendi eksportida.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Salvestusruumi konto konfiguratsiooni kuvatõmmis. "::: 

   - Lisateavet Azure'i bloobimälu konto nime ja kontovõtme kohta vaadake teemast [Salvestuskonto sätete haldamine Azure'i portaalis](/azure/storage/common/storage-account-manage).

   - Lisateavet konteineri loomise kohta leiate teemast [Konteineri loomine](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Tehke valik **Edasi**.

1. Valige segment, mille soovite eksportida. Selles näites on selleks **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Valitud segmendiga ChurnProneCustomers segmendivaliku kasutajaliidese kuvatõmmis.":::

1. Valige **Salvesta**.

Pärast ekspordisihtkoha valimist leiate selle asukohast **Haldus** > **Ekspordid** > **Minu ekspordisihtkohad**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Esiletõstetud eksportide loendi ja näidissegmendi kuvatõmmis.":::

Nüüd saate [nõudmisel segmendi](export-destinations.md#export-data-on-demand) Eksport käivitub ka iga [ajastatud värskendamisega](system.md).

> [!NOTE]
> Veenduge, et eksporditud segmendi kirjete arv jääb Adobe Campaign Standardi litsentsi lubatud piiridesse.

Eksporditud andmed talletatakse eespool konfigureeritud Azure'i bloobimälu ümbrisesse. Ümbrisesse luuakse automaatselt järgmine kaustatee:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Eksporditud olemite *model.json* asub tasemel *%ExportDestinationName%*.

Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Experience Data Modeli (XDM) määratlemine Adobe Experience Platformil

Enne sihtrühmaülevaadetest eksporditu andmete kasutamist Adobe Experience Platformil peame määratlema Experience Data Modeli skeemi ja [konfigureerima reaalajas kliendiprofiili andmed](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Lugege, [mis on XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ja tutvuge [skeemi loomise põhitõdedega](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Andmete importimine Adobe Experience Platformile

Nüüd, kui kõik on valmis, peame profiilide loomiseks importima ettevalmistatud sihtrühmaandmed sihtrühmaülevaadetest Adobe Experience Platformile.

Esmalt looge [Azure'i bloobimälu l'hteühendus](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Pärast lähteühenduse määratlemist [konfigureerige andmevoog](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) pilvsalvestusruumi pakettühenduse jaoks, et importida sihtrühmaülevaadete segmendiväljund Adobe Experience Platformi.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standardi sihtrühma loomine

Selle kampaania meili saatmiseks kasutame Adobe Campaign Standardit. Pärast andmete importimist Adobe Experience Platformi peame [looma sihtrühma](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) Adobe Campaign Standardis Adobe Experience Platformi andmete abil.

Lugege, kuidas [kasutada segmendikoosturit](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) Adobe Campaign Standardis, et määratleda sihtrühm Adobe Experience Platformi andmete põhjal.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Meili loomine ja saatmine Adobe Campaign Standardi kaudu

Looge meilisisu ja seejärel [testige ja saatke](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) oma meil.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standardi uuenduspakkumisega näidismeil.":::