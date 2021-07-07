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
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304645"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="01eb9-103">Kliendiprofiilide rikastamine kohandatud andmetega (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="01eb9-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="01eb9-104">Turvalise failiedastuse protokolli (SFTP) põhine kohandatud importimine võimaldab importida andmeid, mida ei pea koondama.</span><span class="sxs-lookup"><span data-stu-id="01eb9-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="01eb9-105">See on paindlik, turvaline ja lihtne viis andmete sissetoomiseks.</span><span class="sxs-lookup"><span data-stu-id="01eb9-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="01eb9-106">SFTP-põhist kohandatud importimist saab kasutada koos [SFTP-põhise ekspordiga](export-sftp.md), mis võimaldab teil eksportida kliendiprofiili andmeid, mida on vaja rikastamiseks.</span><span class="sxs-lookup"><span data-stu-id="01eb9-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="01eb9-107">Andmeid saab seejärel töödelda ja rikastada ning SFTP kohandatud importi saab kasutada, et tuua rikastatud andmed tagasi Dynamics 365 Customer Insights vaatajaskonna ülevaate võimekusse.</span><span class="sxs-lookup"><span data-stu-id="01eb9-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="01eb9-108">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="01eb9-108">Prerequisites</span></span>

<span data-ttu-id="01eb9-109">SFTP-põhise kohandatud importimise konfigureerimiseks peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="01eb9-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="01eb9-110">Teil on SFTP-hostis imporditava faili nimi ja asukoht (tee).</span><span class="sxs-lookup"><span data-stu-id="01eb9-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="01eb9-111">Imporditavate andmete jaoks on olemas fail *model.json*, mis määrab [Common Data Model skeemi](/common-data-model/) imporditavatele andmetele.</span><span class="sxs-lookup"><span data-stu-id="01eb9-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="01eb9-112">See fail peab asuma imporditava failiga samas kataloogis.</span><span class="sxs-lookup"><span data-stu-id="01eb9-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="01eb9-113">Administraator on SFTP-ühenduse juba konfigureerinud *või* teil on [administraatoriõigused](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="01eb9-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="01eb9-114">SFTP asukoha jaoks, kust soovite andmeid importida, vajate kasutaja volikirja, URL-i ja pordi numbrit.</span><span class="sxs-lookup"><span data-stu-id="01eb9-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="01eb9-115">Impordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="01eb9-115">Configure the import</span></span>

1. <span data-ttu-id="01eb9-116">Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.</span><span class="sxs-lookup"><span data-stu-id="01eb9-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="01eb9-117">**SFTP kohandatud impordipaanil** valige **Minu andmete rikastamine** ja seejärel valige **Alustamine**.</span><span class="sxs-lookup"><span data-stu-id="01eb9-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP kohandatud impordipaan.":::

1. <span data-ttu-id="01eb9-119">Valige [ühendus](connections.md) ripploendist.</span><span class="sxs-lookup"><span data-stu-id="01eb9-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="01eb9-120">Kui ühendusi pole saadaval, pöörduge administraatori poole.</span><span class="sxs-lookup"><span data-stu-id="01eb9-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="01eb9-121">Kui olete administraator, saate ühenduse luua, valides **Lisa ühendus** käsu ja valides **SFTP Custom Import** ripploendist.</span><span class="sxs-lookup"><span data-stu-id="01eb9-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="01eb9-122">Valige **Ühenda kohandatud importimisega**, et kinnitada ühenduse valik.</span><span class="sxs-lookup"><span data-stu-id="01eb9-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="01eb9-123">Valige **Edasi** ning sisestage imporditava andmefaili **Tee** ja **Failinimi**.</span><span class="sxs-lookup"><span data-stu-id="01eb9-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Kuvatõmmis andmeasukoha sisestamisel.":::

1. <span data-ttu-id="01eb9-125">Valige **Edasi** ja sisestage rikastamise nimi ja väljundolemi nimi.</span><span class="sxs-lookup"><span data-stu-id="01eb9-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="01eb9-126">Valige **Salvesta rikastamine** pärast valikute läbivaatamist.</span><span class="sxs-lookup"><span data-stu-id="01eb9-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="01eb9-127">SFTP kohandatud impordi ühenduse konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="01eb9-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="01eb9-128">Ühenduste konfigureerimiseks peate olema administraator.</span><span class="sxs-lookup"><span data-stu-id="01eb9-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="01eb9-129">Valige **Lisa ühendus** rikastamise konfigureerimisel *või* minge **Administraator** > **Ühendused** ja valige **Seadista** kohandatud importimise paanil.</span><span class="sxs-lookup"><span data-stu-id="01eb9-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="01eb9-130">Sisestage ühenduse nimi **Kuvatav nimi** väljale.</span><span class="sxs-lookup"><span data-stu-id="01eb9-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="01eb9-131">Sisestage SFTP-serveri jaoks kehtiv kasutajanimi, parool ja hosti URL, kus imporditavad andmed asuvad.</span><span class="sxs-lookup"><span data-stu-id="01eb9-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="01eb9-132">Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="01eb9-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="01eb9-133">Valige **Kontrolli** konfiguratsiooni valideerimiseks.</span><span class="sxs-lookup"><span data-stu-id="01eb9-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="01eb9-134">Kui kontroll on lõpule jõudnud, saab ühenduse salvestada, valides **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="01eb9-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01eb9-135">![Experian ühenduse konfiguratsiooni paan](media/enrichment-SFTP-connection.png "Experian ühenduse konfiguratsiooni paan")</span><span class="sxs-lookup"><span data-stu-id="01eb9-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="01eb9-136">Väljavastenduste määratlemine</span><span class="sxs-lookup"><span data-stu-id="01eb9-136">Defining field mappings</span></span> 

<span data-ttu-id="01eb9-137">Kataloog, mis sisaldab faili, mis imporditakse SFTP serveris, peab sisaldama ka faili *model.json*.</span><span class="sxs-lookup"><span data-stu-id="01eb9-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="01eb9-138">See fail määratleb andmete importimiseks kasutatava skeemi.</span><span class="sxs-lookup"><span data-stu-id="01eb9-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="01eb9-139">Skeemis tuleb kasutada [Common Data Model](/common-data-model/) välja kaardistamise määramiseks.</span><span class="sxs-lookup"><span data-stu-id="01eb9-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="01eb9-140">Lihtne näide model.json-failist on järgmine.</span><span class="sxs-lookup"><span data-stu-id="01eb9-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="01eb9-141">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="01eb9-141">Enrichment results</span></span>

<span data-ttu-id="01eb9-142">Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="01eb9-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="01eb9-143">Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="01eb9-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="01eb9-144">Töötlemise aeg sõltub imporditavate andmete mahust ja ühendusest SFTP serveriga.</span><span class="sxs-lookup"><span data-stu-id="01eb9-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="01eb9-145">Pärast rikastamisprotsessi lõpuleviimist saate oma värskelt imporditud kohandatud rikastatud andmed üle vaadata jaotises **Minu rikastamised**.</span><span class="sxs-lookup"><span data-stu-id="01eb9-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="01eb9-146">Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="01eb9-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="01eb9-147">Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.</span><span class="sxs-lookup"><span data-stu-id="01eb9-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="01eb9-148">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="01eb9-148">Next steps</span></span>

<span data-ttu-id="01eb9-149">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="01eb9-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="01eb9-150">Looge [segmente](segments.md) ja [näitajaid](measures.md) ning [eksportige andmed](export-destinations.md), et pakkuda oma klientidele isikupärastatud kogemust.</span><span class="sxs-lookup"><span data-stu-id="01eb9-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
