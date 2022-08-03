---
title: Customer Insightsi segmentide eksportimine kampaania standardisse Adobe (eelvaade)
description: Vaadake, kuidas kasutada Customer Insightsi segmente kampaania standardis Adobe.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195515"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>Customer Insightsi segmentide eksportimine kampaania standardisse Adobe (eelvaade)

Eksportige asjakohaseid vaatajaskondi sihtivad segmendid kampaania standardisse Adobe.

:::image type="content" source="media/ACS-flow.png" alt-text="Selles artiklis kirjeldatud juhiste protsessiskeem.":::

## <a name="prerequisites"></a>eeltingimused

- Kampaania Adobe standardlitsents.
- Azure'i [bloobi salvestusruumi konto](/azure/storage/blobs/create-data-lake-storage-account) nimi ja konto võti. Nime ja võtme leidmiseks vaadake teemat [Salvestuskonto sätete haldamine Azure'i portaalis](/azure/storage/common/storage-account-manage).
- An [Azure Blob Storage container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Kampaania ülevaade

Customer Insightsi Adobe Experience Platform segmentide kasutamise paremaks mõistmiseks vaatame fiktiivset näidiskampaaniat.

Oletame, et teie ettevõte pakub teie USA klientidele igakuiseid, tellimusepõhiseid teenuseid. Soovite tuvastada kliendid, kelle kordustellimusi tuleb järgmise kaheksa päeva pärast uuendada, kuid kes pole veel oma kordustellimust pikendanud. Kui soovite need kliendid säilitada, soovite neile saata meiliga reklaampakkumise, kasutades selleks rakendust Adobe Campaign Standard.

Selles näites soovime käivitada ühekordse reklaamikampaania meili teel. See artikkel ei hõlma kampaania läbiviimist rohkem kui üks kord. Kuid Customer Insightsi ja Adobe Campaign Standardit saab konfigureerida töötama ka korduva kampaania stsenaariumi korral.

## <a name="identify-your-target-audience"></a>Sihtrühma tuvastamine

Meie stsenaariumi puhul eeldame, et klientide e-posti aadressid on Customer Insightsis saadaval ja nende reklaamieelistusi analüüsiti segmendi liikmete tuvastamiseks.

[Customer Insightsis](segments.md) määratletud segment kannab nime **ChurnProneCustomers** ja kavatsete saata neile klientidele e-posti reklaami.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Kuvatõmmis loodud ChurnProneCustomersi segmendiga segmentide lehest.":::

Väljasaatmiseks mõeldud pakkumismeilis on eesnimi, perekonnanimi ja kliendi kordustellimuse lõppkuupäev. See teavitab klienti allahindlusest, mille nad saavad, kui nad oma kordustellimuse enne aegumist pikendavad.

## <a name="export-your-target-audience"></a>Sihtrühma eksportimine

### <a name="set-up-connection-to-adobe-campaign"></a>Kampaaniaga ühenduse Adobe seadistamine

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Adobe Kampaania**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. **Sisestage Bloobi salvestusruumi konto nimi**, **kontovõti** ja **konteiner**.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Salvestusruumi konto konfiguratsiooni kuvatõmmis. ":::

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

### <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige **Ühendus ekspordiks** väljal soovitud ühendus Adobe Campaign jaotisest. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordi nimi.

1. Valige segment, mille soovite eksportida. Selles näites on selleks **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Valitud segmendiga ChurnProneCustomers segmendivaliku kasutajaliidese kuvatõmmis.":::

1. Tehke valik **Edasi**.

1. Vastendage **segmendi** Customer Insights lähteväljad **kampaania standardi profiiliskeemi sihtväljade** nimedega Adobe.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard konnektori väljavastendus.":::

   Kui soovite lisada veel atribuute, valige **Lisa atribuut**. Sihtnimi võib lähtevälja nimest erineda, nii et saate siiski vastendada segmendi väljundi Customer Insightsist kampaaniastandardisse Adobe, kui väljadel pole kahes süsteemis sama nime.

   > [!NOTE]
   > E-posti aadressi kasutatakse identiteediväljana, kuid saate kasutada mis tahes muud kliendiprofiili identifikaatorit, et vastendada andmed kampaania standardiga Adobe.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Veenduge, et eksporditud segmendis olevate kirjete arv oleks teie Adobe Campaign Standardi litsentsi lubatud piires.

Eksporditud andmed talletatakse eespool konfigureeritud Azure Blob Storage konteinerisse. Teie konteineris luuakse automaatselt järgmine kaustatee: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigureeri Adobe Campaign Standard

Eksporditud segmendid sisaldavad veerge, mille valisite ekspordi konfigureerimisel. Seda teavet saab kasutada [Adobe Campaign Standard profiilide loomiseks](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Segmendi kasutamiseks kampaaniastandardis Adobe laiendage profiili skeemi [kampaaniastandardis](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing), Adobe et kaasata kaks lisavälja.

Meie näites on need väljad Segmendi nimi ja Segmendi kuupäev. Nende väljade abil tuvastame profiilid rakenduses Adobe Campaign Standard, mida soovite selle kampaania jaoks sihtida.

Kui kampaaniastandardis Adobe pole muid kirjeid peale selle, mida kavatsete importida, jätke see toiming vahele.

## <a name="import-data-into-adobe-campaign-standard"></a>Andmete importimine rakendusse Adobe Campaign Standard

Importige ettevalmistatud vaatajaskonna andmed Customer Insightsist kampaaniastandardisse Adobe, et [luua töövoo](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) abil profiile.

Alloleval pildil olev importimise töövoog on konfigureeritud töötama iga kaheksa tunni järel ja otsima eksporditud Customer Insightsi segmente (.csv faili Azure'i bloobimälus). Töövoog ekstraktib CSV-faili sisu määratud veerujärjestuses. See töövoog on rajatud selleks, et teostada põhilisi tõrkekäsitlusi ja tagada, et igal kirjel oleks meiliaadress enne andmete kirjutamist rakendusse Adobe Campaign Standard. Töövoog ekstraktib segmendi nime ka failinimest, enne kui salvestab selle Adobe Campaign Standard profiiliandmetesse.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Impordi töövoo kuvatõmmis Adobe Campaign Standard kasutajaliideses.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Sihtrühma pärimine rakenduses Adobe Campaign Standard

Kui andmed on kampaaniastandardisse Adobe imporditud, [looge töövoog](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ja [küsige klientidelt](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) segmendi nime ja segmendikuupäeva alusel, et valida profiilid, mis tuvastati meie näidiskampaania jaoks.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Meili loomine ja saatmine Adobe Campaign Standard abil

Looge meilisisu ja seejärel [testige ja saatke](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) oma meil.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Näidismeil uuenduspakkumisega rakendusest Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
