---
title: Customer Insights andmete eksportimine rakendusse Adobe Experience Platform
description: Lugege, kuidas kasutada sihtrühma ülevaadete segmente Adobe Experience Platform'il.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fac976a49b1b5c5485b75e1262135738c913bd2230be7df8aa0ec12c59734053
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032112"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Kasutage rakenduses Adobe Experience Platform (eelvaade) segmente Customer Insights

Dynamics 365 Customer Insights sihtrühma ülevaadete kasutajana, olete võinud luua segmente, et ,muuta oma turunduskampaaniad tõhusamaks, sihtides asjakohaseid vaatajaskondi. Adobe Experience Platform sihtrühma ülevaadetest saadud segmendi kasutamiseks ja rakendustes (nt Adobe Campaign Standard) peate järgima mõnda käesolevas artiklis kirjeldatud etappi.

:::image type="content" source="media/AEP-flow.png" alt-text="Selles artiklis kirjeldatud juhiste protsessiskeem.":::

## <a name="prerequisites"></a>Eeltingimused

-   Dynamics 365 Customer Insightsi litsents
-   Adobe Experience Platformi litsents
-   Adobe Campaign Standard litsents
-   Azure’i bloobimälu konto

## <a name="campaign-overview"></a>Kampaania ülevaade

Et paremini mõista, kuidas kasutada sihtrühma ülevaadete segmente, vaadake Adobe Experience Platform väljamõeldud näidiskampaaniat.

Oletame, et teie ettevõte pakub teie USA klientidele igakuiseid, tellimusepõhiseid teenuseid. Soovite tuvastada kliendid, kelle kordustellimusi tuleb järgmise kaheksa päeva pärast uuendada, kuid kes pole veel oma kordustellimust pikendanud. Kui soovite need kliendid säilitada, soovite neile saata meiliga reklaampakkumise, kasutades selleks rakendust Adobe Experience Platform.

Selles näites soovime käivitada ühekordse reklaamikampaania meili teel. See artikkel ei hõlma kampaania läbiviimist rohkem kui üks kord.

## <a name="identify-your-target-audience"></a>Sihtrühma tuvastamine

Meie stsenaariumis eeldame, et klientide meiliaadressid on sihtrühmaülevaadetes saadaval ja nende reklaamieelistusi on analüüsitud segmendi liikmete tuvastamiseks.

[Sihtrühmaülevaadetes määratletud segmendi](segments.md) nimeks on **ChurnProneCustomers** ja plaanite neile klientidele saata meilikampaania.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Kuvatõmmis loodud ChurnProneCustomersi segmendiga segmentide lehest.":::

Väljasaatmiseks mõeldud pakkumismeilis on eesnimi, perekonnanimi ja kliendi kordustellimuse lõppkuupäev. See teavitab klienti allahindlusest, mille nad saavad, kui nad oma kordustellimuse enne aegumist pikendavad.

## <a name="export-your-target-audience"></a>Sihtrühma eksportimine

Kui sihtrühm on tuvastatud, saame konfigureerida ekspordi sihtrühmaülevaadetest Azure'i bloobimälu kontole.

### <a name="configure-a-connection"></a>Ühenduse konfigureerimine

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Azure bloobimälu** või valige **Seadistage** paanil **Azure bloobimälu** ühenduse konfigureerimiseks.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Azure'i bloobimälu konfiguratsioonipaan."::: 

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Sisestage **Konto nimi**, **Konto võti**, ja **Konteiner** Blob Storage konto jaoks, kuhu soovite segmendi eksportida.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Salvestusruumi konto konfiguratsiooni kuvatõmmis. "::: 
   
    - Lisateavet Blob Storage konto nime ja konto võtme otsimise kohta leiate [Azure portaalis salvestusruumi konto sätete haldamine](/azure/storage/common/storage-account-manage).
    - Lisateavet konteineri loomise kohta leiate teemast [Konteineri loomine](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Ühenduse loomiseks valige **Salvesta**. 

### <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus Azure Blob Storage jaotisest. Kui te seda jaotise nime ei näe, pole seda tüüpi ühendused teile saadaval.

1. Valige segment, mille soovite eksportida. Selles näites on selleks **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Valitud segmendiga ChurnProneCustomers segmendivaliku kasutajaliidese kuvatõmmis.":::

1. Valige **Salvesta**.

Pärast ekspordi sihtkoha salvestamist leiate selle **Andmed** > **Eksport**.

Nüüd saate [nõudmisel segmendi](export-destinations.md#run-exports-on-demand) Eksport käivitub ka iga [ajastatud värskendamisega](system.md).

> [!NOTE]
> Veenduge, et eksporditud segmendis olevate kirjete arv oleks teie Adobe Campaign Standardi litsentsi lubatud piires.

Eksporditud andmed talletatakse eespool konfigureeritud Azure Blob Storage konteinerisse. Ümbrisesse luuakse automaatselt järgmine kaustatee:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

Eksporditud olemite *model.json* asub tasemel *%ExportDestinationName%*.

Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Kogemuse andmemudeli (XDM) määratlemine rakenduses Adobe Experience Platform

Enne, kui sihtrühma ülevaadetest eksporditud andmeid saab kasutada rakenduses Adobe Experience Platform, peab määratlema kogemuse andmemudeli skeemi ja [konfigureerima andmed reaalaja kliendiprofiili jaoks](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Lugege, [mis on XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) ja tutvuge [skeemi loomise põhitõdedega](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Andmete importimine Adobe Experience Platform'i

Nüüd, kui kõik on paigas, peame vaatajaskonna statistika põhjal koostatud vaatajaskonna andmed Adobe Experience Platformi importima.

Esmalt looge [Azure'i bloobimälu l'hteühendus](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Pärast lähteühenduse määratlemist [konfigureerige pilvemälu pakett-ühenduse andmevoog](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials), et importida segmendiväljund publiku ülevaadetest Adobe Experience Platform rakendusse.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Sihtrühma loomine rakenduses Adobe Campaign Standard

Selle kampaania meili saatmiseks kasutame Adobe Campaign Standard'it. Pärast andmete importimist rakendusse Adobe Experience Platform peame [looma sihtrühma](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission), rakenduses Adobe Campaign Standard kasutades Adobe Experience Platform andmeid.


Lugege, kuidas kasutada Adobe Campaign Standardis [segmentide ehitajat](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html), et määratleda sihtrühma, võttes aluseks Adobe Experience Platform andmed.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Meili loomine ja saatmine Adobe Campaign Standard abil

Looge meilisisu ja seejärel [testige ja saatke](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) oma meil.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Näidismeil uuenduspakkumisega rakendusest Adobe Campaign Standard.":::