---
title: Customer Insightsi andmete eksportimine rakendusse Adobe Campaign Standard
description: Lugege, kuidas kasutada Adobe Campaign Standardi sihtrühmaülevaadete segmente.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760276"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Customer Insightsi segmentide kasutamine Adobe Campaign Standardis (eelversioon)

Dynamics 365 Customer Insightsi sihtrühmaülevaadete kasutajana olete võib-olla loonud segmente turunduskampaaniate tõhusamaks muutmiseks asjakohaseid sihtrühmi määrates. Adobe Experience Platformi ja rakendustest, nagu Adobe Campaign Standard pärit segmentide kasutamiseks peate järgima mõnda selles artiklis kirjeldatud juhist.

:::image type="content" source="media/ACS-flow.png" alt-text="Selles artiklis kirjeldatud juhiste protsessiskeem.":::

## <a name="prerequisites"></a>Eeltingimused

-   Dynamics 365 Customer Insightsi litsents
-   Adobe Campaign Standardi litsents
-   Azure’i bloobimälu konto

## <a name="campaign-overview"></a>Kampaania ülevaade

Et paremini mõista, kuidas kasutada Adobe Experience Platformi sihtrühmaülevaadete segmente, vaatame väljamõeldud näidiskampaaniat.

Oletame, et teie ettevõte pakub teie USA klientidele igakuiseid, tellimusepõhiseid teenuseid. Soovite tuvastada kliendid, kelle kordustellimusi tuleb järgmise kaheksa päeva pärast uuendada, kuid kes pole veel oma kordustellimust pikendanud. Nende klientide alleshoidmiseks, soovite meili teel saata neile reklaampakkumise Adobe Campaign Standardi kaudu.

Selles näites soovime käivitada ühekordse reklaamikampaania meili teel. See artikkel ei hõlma kampaania läbiviimist rohkem kui üks kord. Sihtrühmaülevaateid ja rakendust Adobe Campaign Standard saab siiski konfigureerida töötama ka korduvate kampaaniastsenaariumide jaoks.

## <a name="identify-your-target-audience"></a>Sihtrühma tuvastamine

Meie stsenaariumis eeldame, et klientide meiliaadressid on sihtrühmaülevaadetes saadaval ja nende reklaamieelistusi on analüüsitud segmendi liikmete tuvastamiseks.

[Sihtrühmaülevaadetes määratletud segmendi](segments.md) nimeks on **ChurnProneCustomers** ja plaanite neile klientidele saata meilikampaania.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Kuvatõmmis loodud ChurnProneCustomersi segmendiga segmentide lehest.":::

Väljasaatmiseks mõeldud pakkumismeilis on eesnimi, perekonnanimi ja kliendi kordustellimuse lõppkuupäev. See teavitab klienti allahindlusest, mille nad saavad, kui nad oma kordustellimuse enne aegumist pikendavad.

## <a name="export-your-target-audience"></a>Sihtrühma eksportimine

### <a name="configure-a-connection"></a>Ühenduse konfigureerimine

Kui sihtrühm on tuvastatud, saame konfigureerida ekspordi sihtrühmaülevaadetest Azure'i bloobimälu kontole.

1. Avage sihtrühma ülevaadetes **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Adobe Campaig** ühenduse konfigureerimiseks või klõpsake **Seadista** **Adobe Campaign** paanil

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Adobe Campaign Standardi konfiguratsioonipaan.":::

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Sisestage **Konto nimi**, **Konto võti**, ja **Konteiner** Azure Blob Storage kontol, kuhu soovite segmendi eksportida.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Salvestusruumi konto konfiguratsiooni kuvatõmmis. "::: 

   - Lisateavet Azure'i bloobimälu konto nime ja kontovõtme kohta vaadake teemast [Salvestuskonto sätete haldamine Azure'i portaalis](/azure/storage/common/storage-account-manage).

   - Lisateavet konteineri loomise kohta leiate teemast [Konteineri loomine](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Ühenduse loomiseks valige **Salvesta**.

### <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa eksport**.

1. Valige **Ekspordiühendus** väljal ühendus Adobe Campaign jaotisest. Kui te seda jaotisenime ei näe, pole seda tüüpi ühendusi teie jaoks saadaval.

1. Valige segment, mille soovite eksportida. Selles näites on selleks **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Valitud segmendiga ChurnProneCustomers segmendivaliku kasutajaliidese kuvatõmmis.":::

1. Tehke valik **Edasi**.

1. Nüüd vastendame sihtrühmaülevaadete segmendi väljad **Lähtekoht** Adobe Campaign Standardi profiiliskeemi väljanimedele **Sihtkoht**.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standardi konnektori väljade vastendamine.":::

   Kui soovite lisada veel atribuute, valige **Lisa atribuut**. Sihtvälja nimi võib lähtevälja nimest erineda, et saaksite endiselt vastendada sihtrühmaülevaadete segmendiväljundi Adobe Campaign Standardiga, kui väljade nimed kahes süsteemis ei kattu.

   > [!NOTE]
   > Meiliaadressi kasutatakse nende väljade tuvastamiseks, mida saate kasutada muu ID-na oma sihtrühmaülevaadete profiilist, et vastendada andmed Adobe Campaign Standard andmetega.

1. Valige **Salvesta**.

Pärast ekspordi sihtkoha salvestamist leiate selle **Andmed** > **Eksport**.

Nüüd saate [nõudmisel segmendi](export-destinations.md#run-exports-on-demand) Eksport käivitub ka iga [ajastatud värskendamisega](system.md).

> [!NOTE]
> Veenduge, et eksporditud segmendi kirjete arv jääb Adobe Campaign Standardi litsentsi lubatud piiridesse.

Eksporditud andmed talletatakse eespool konfigureeritud Azure'i bloobimälu ümbrisesse. Ümbrisesse luuakse automaatselt järgmine kaustatee:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Adobe Campaign Standardi konfigureerimine

Kui eksporditakse sihtrühmaülevaadetest pärit segment, sisaldab see veerge, mille olete ekspordi sihtkoha määratlemisel eelmises toimingus valinud. Nende andmete abil saab [luua profiile rakenduses Adobe Campaign Standard ](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Segmendi kasutamiseks Adobe Campaign Standardis peame laiendama Adobe Campaign Standardi profiiliskeemi ja kaasama kaks lisavälja. Siit leiate teavet [profiiliressursside laiendamise](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) kohta uute väljadega Adobe Campaign Standardis.

Meie näites on need väljad *Segmendi nimi ja segmendi kuupäev (valikuline).*

Nende väljade abil tuvastame profiile, mida soovime selle kampaania jaoks Adobe Campaign Standardis määrata.

Kui Adobe Campaign Standardis pole muid kirjeid, kui need, mille plaanite importida, võite selle juhise vahele jätta.

## <a name="import-data-into-adobe-campaign-standard"></a>Andmete importimine Adobe Campaign Standardisse

Nüüd, kui kõik on valmis, peame profiilide loomiseks importima ettevalmistatud sihtrühmaandmed sihtrühmaülevaadetest Adobe Campaign Standardisse. Lugege, [kuidas importida Adobe Campaign Standardi profiile](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) töövoo abil.

Alloleval pildil oleva impordi töövoog on konfigureeritud käitama iga 8 tunni järel ja see otsib eksporditud sihtrühmaülevaadete segmente (Azure'i bloobimälu CSV-fail). Töövoog ekstraktib CSV-faili sisu määratud veerujärjestuses. See töövoog on rajatud tegema peamisi tõrketöötlusi ja tagama, et igal kirjel oleks meiliaadress enne enne domeeniandmete laadimist Adobe Campaign Standardis. Töövoog ekstraktib ka segmendi nime failinimest enne ACS-i profiiliandmetesse sisestamist või selle värskendamist.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Adobe Campaign Standardi kasutajaliidese töövoo importimise kuvatõmmis.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Adobe Campaign Standardi sihtrühma toomine

Kui andmed on Adobe Campaign Standardisse imporditud, [saate luua töövoo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ja saata [päringu](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) klientide kohta väljade *Segmendi nimi* ja *Segmendi kuupäev* alusel, et valida profiilid, mis tuvastati meie näidiskampaania jaoks.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Meili loomine ja saatmine Adobe Campaign Standardi kaudu

Looge meilisisu ja seejärel [testige ja saatke](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) oma meil.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Adobe Campaign Standardi uuenduspakkumisega näidismeil.":::
