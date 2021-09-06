---
title: Customer Insights andmete eksportimine Adobe Campaign Standardisse
description: Teave sihtrühma ülevaadete segmentide kasutamise kohta rakenduses Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d301b4f0cb875303fb3d373b77177acd1c1f5219cd6f23c2a1d29ce67a222eab
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032158"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Customer Insightsi segmentide kasutamine rakenduses Adobe Campaign Standard (eelvaade)

Dynamics 365 Customer Insights sihtrühma ülevaadete kasutajana, olete võinud luua segmente, et ,muuta oma turunduskampaaniad tõhusamaks, sihtides asjakohaseid vaatajaskondi. Adobe Experience Platform sihtrühma ülevaadetest saadud segmendi kasutamiseks ja rakendustes (nt Adobe Campaign Standard) peate järgima mõnda käesolevas artiklis kirjeldatud etappi.

:::image type="content" source="media/ACS-flow.png" alt-text="Selles artiklis kirjeldatud juhiste protsessiskeem.":::

## <a name="prerequisites"></a>Eeltingimused

-   Dynamics 365 Customer Insightsi litsents
-   Adobe Campaign Standard litsents
-   Azure’i bloobimälu konto

## <a name="campaign-overview"></a>Kampaania ülevaade

Et paremini mõista, kuidas kasutada sihtrühma ülevaadete segmente, vaadake Adobe Experience Platform väljamõeldud näidiskampaaniat.

Oletame, et teie ettevõte pakub teie USA klientidele igakuiseid, tellimusepõhiseid teenuseid. Soovite tuvastada kliendid, kelle kordustellimusi tuleb järgmise kaheksa päeva pärast uuendada, kuid kes pole veel oma kordustellimust pikendanud. Kui soovite need kliendid säilitada, soovite neile saata meiliga reklaampakkumise, kasutades selleks rakendust Adobe Campaign Standard.

Selles näites soovime käivitada ühekordse reklaamikampaania meili teel. See artikkel ei hõlma kampaania läbiviimist rohkem kui üks kord. Küll aga saab sihtrühma ülevaateid ja Adobe Campaign Standardit konfigureerida nii, et need töötaks ka korduva kampaaniastsenaariumiga.

## <a name="identify-your-target-audience"></a>Sihtrühma tuvastamine

Meie stsenaariumis eeldame, et klientide meiliaadressid on sihtrühmaülevaadetes saadaval ja nende reklaamieelistusi on analüüsitud segmendi liikmete tuvastamiseks.

[Sihtrühmaülevaadetes määratletud segmendi](segments.md) nimeks on **ChurnProneCustomers** ja plaanite neile klientidele saata meilikampaania.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Kuvatõmmis loodud ChurnProneCustomersi segmendiga segmentide lehest.":::

Väljasaatmiseks mõeldud pakkumismeilis on eesnimi, perekonnanimi ja kliendi kordustellimuse lõppkuupäev. See teavitab klienti allahindlusest, mille nad saavad, kui nad oma kordustellimuse enne aegumist pikendavad.

## <a name="export-your-target-audience"></a>Sihtrühma eksportimine

### <a name="configure-a-connection"></a>Ühenduse konfigureerimine

Kui sihtrühm on tuvastatud, saame konfigureerida ekspordi sihtrühmaülevaadetest Azure'i bloobimälu kontole.

1. Avage sihtrühma ülevaadetes **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Adobe Campaign** ühenduse konfigureerimiseks või klõpsake **Seadista** paanil **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Konfigureeri Adobe Campaign Standard paan.":::

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Sisestage **Konto nimi**, **Konto võti**, ja **Konteiner** Azure Blob Storage kontol, kuhu soovite segmendi eksportida.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Salvestusruumi konto konfiguratsiooni kuvatõmmis. "::: 

   - Lisateavet Azure Blob Storage konto nime ja kontovõtme kohta vaadake teemast [Salvestuskonto sätete haldamine Azure'i portaalis](/azure/storage/common/storage-account-manage).

   - Lisateavet konteineri loomise kohta leiate teemast [Konteineri loomine](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Ühenduse loomiseks valige **Salvesta**.

### <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa eksport**.

1. Valige **Ühendus ekspordiks** väljal soovitud ühendus Adobe Campaign jaotisest. Kui te seda jaotise nime ei näe, pole seda tüüpi ühendused teile saadaval.

1. Valige segment, mille soovite eksportida. Selles näites on selleks **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Valitud segmendiga ChurnProneCustomers segmendivaliku kasutajaliidese kuvatõmmis.":::

1. Tehke valik **Edasi**.

1. Nüüd vastendame sihtrühma ülevaadete segmendi **lähte** väljad Adobe Campaign Standard kampaania standardse profiiliskeemi **siht** välja nimedega.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Adobe Campaign Standard konnektori väljavastendus.":::

   Kui soovite lisada veel atribuute, valige **Lisa atribuut**. Sihtnimi võib erineda allikavälja nimest, nii et saate siiski segmendi väljundi sihtrühma statistikast kaardistada Adobe Campaign Standardiga, kui väljad ei ole kahes süsteemis sama nimega.

   > [!NOTE]
   > E-posti aadressi kasutatakse identiteediväljana, kuid saate kasutada mis tahes muud vaatajaskonna statistika kliendiprofiili identifikaatorit, et kaardistada andmed Adobe Campaign Standardiga.

1. Valige **Salvesta**.

Pärast ekspordi sihtkoha salvestamist leiate selle **Andmed** > **Eksport**.

Nüüd saate [nõudmisel segmendi](export-destinations.md#run-exports-on-demand) Eksport käivitub ka iga [ajastatud värskendamisega](system.md).

> [!NOTE]
> Veenduge, et eksporditud segmendis olevate kirjete arv oleks teie Adobe Campaign Standardi litsentsi lubatud piires.

Eksporditud andmed talletatakse eespool konfigureeritud Azure Blob Storage konteinerisse. Ümbrisesse luuakse automaatselt järgmine kaustatee:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Näide: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Konfigureeri Adobe Campaign Standard

Kui eksporditakse sihtrühmaülevaadetest pärit segment, sisaldab see veerge, mille olete ekspordi sihtkoha määratlemisel eelmises toimingus valinud. Seda teavet saab kasutada [Adobe Campaign Standard profiilide loomiseks](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Kui soovite segmenti kasutada rakenduses Adobe Campaign Standard, peame laiendama profiiliskeemi rakenduses Adobe Campaign Standard, et kaasata kaks lisavälja. Siit leiate teavet selle kohta, kuidas [laiendada profiiliressurssi](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) uute Adobe Campaign Standard väljadega.

Meie näites on need väljad *Segmendi nimi ja segmendi kuupäev (valikuline)*.

Nende väljade abil tuvastame profiilid rakenduses Adobe Campaign Standard, mida soovite selle kampaania jaoks sihtida.

Kui Adobe Campaign Standardis pole muid kirjeid peale selle, mida soovite importida, võite selle juhise vahele jätta.

## <a name="import-data-into-adobe-campaign-standard"></a>Andmete importimine rakendusse Adobe Campaign Standard

Nüüd, kui kõik on paigas, peame vaatajaskonna statistika põhjal koostatud vaatajaskonna andmed Adobe Campaign Standard'isse profiilide loomiseks importima. Siit leiate teavet selle kohta, [kuidas importida Adobe Campaign Standard profiile](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) töövoo abil.

Alloleval pildil oleva impordi töövoog on konfigureeritud käitama iga kaheksa tunni järel ja otsima eksporditud sihtrühma ülevaadete segmente (.csv fail Azure Blob Storage'is). Töövoog ekstraktib CSV-faili sisu määratud veerujärjestuses. See töövoog on rajatud selleks, et teostada põhilisi tõrkekäsitlusi ja tagada, et igal kirjel oleks meiliaadress enne andmete kirjutamist rakendusse Adobe Campaign Standard. Töövoog ekstraktib segmendi nime ka failinimest, enne kui salvestab selle Adobe Campaign Standard profiiliandmetesse.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Impordi töövoo kuvatõmmis Adobe Campaign Standard kasutajaliideses.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Sihtrühma pärimine rakenduses Adobe Campaign Standard

Kui andmed on imporditud rakendusse Adobe Campaign Standard, saate [luua töövoo](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ja teha klientidele [päringuid](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) *segmendi nime* ja *segmendi kuupäeva* põhjal, et valida meie näidiskampaania jaoks tuvastatud profiile.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Meili loomine ja saatmine Adobe Campaign Standard abil

Looge meilisisu ja seejärel [testige ja saatke](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) oma meil.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Näidismeil uuenduspakkumisega rakendusest Adobe Campaign Standard.":::
