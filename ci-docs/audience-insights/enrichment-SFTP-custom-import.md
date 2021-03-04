---
title: Rikastamine SFTP-põhist kohandatud importimist kasutades
description: Üldine teave SFTP-põhise kohandatud importimise kaudu rikastamise kohta.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269601"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="19e49-103">Kliendiprofiilide rikastamine kohandatud andmetega (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="19e49-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="19e49-104">Turvalise failiedastuse protokolli (SFTP) põhine kohandatud importimine võimaldab importida andmeid, mida ei pea koondama.</span><span class="sxs-lookup"><span data-stu-id="19e49-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="19e49-105">See on paindlik, turvaline ja lihtne viis andmete sissetoomiseks.</span><span class="sxs-lookup"><span data-stu-id="19e49-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="19e49-106">SFTP-põhist kohandatud importimist saab kasutada koos [SFTP-põhise ekspordiga](export-sftp.md), mis võimaldab teil eksportida kliendiprofiili andmeid, mida on vaja rikastamiseks.</span><span class="sxs-lookup"><span data-stu-id="19e49-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="19e49-107">Seejärel saab andmeid töödelda, rikastada ning SFTP-põhist kohandatud importimist saab kasutada, et tuua rikastatud andmed tagasi Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsiooni.</span><span class="sxs-lookup"><span data-stu-id="19e49-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="19e49-108">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="19e49-108">Prerequisites</span></span>

<span data-ttu-id="19e49-109">SFTP-põhise kohandatud importimise konfigureerimiseks peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="19e49-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="19e49-110">Teil on selle SFTP asukoha identimisteave (kasutajanimi ja parool), kust andmeid hakatakse importima.</span><span class="sxs-lookup"><span data-stu-id="19e49-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="19e49-111">Teil on STFP hosti URL ja pordinumber (tavaliselt 22).</span><span class="sxs-lookup"><span data-stu-id="19e49-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="19e49-112">Teil on selle faili failinimi ja asukoht, mis imporditakse SFTP hosti kaudu.</span><span class="sxs-lookup"><span data-stu-id="19e49-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="19e49-113">Seal on fail *model.json*, mis määratleb imporditavate andmete skeemi.</span><span class="sxs-lookup"><span data-stu-id="19e49-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="19e49-114">See fail peab asuma imporditava failiga samas kataloogis.</span><span class="sxs-lookup"><span data-stu-id="19e49-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="19e49-115">Teil on [administraatori](permissions.md#administrator) õigused.</span><span class="sxs-lookup"><span data-stu-id="19e49-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="19e49-116">Konfiguratsioon</span><span class="sxs-lookup"><span data-stu-id="19e49-116">Configuration</span></span>

1. <span data-ttu-id="19e49-117">Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.</span><span class="sxs-lookup"><span data-stu-id="19e49-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="19e49-118">Valige **SFTP-põhise kohandatud importimise paanil** suvand **Rikasta mu andmeid**.</span><span class="sxs-lookup"><span data-stu-id="19e49-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="19e49-119">![SFTP-põhise kohandatud importimise paan](media/SFTP_Custom_Import_tile.png "SFTP-põhise kohandatud importimise paan")</span><span class="sxs-lookup"><span data-stu-id="19e49-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="19e49-120">Valige **Alusta** ning sisestage SFTP serveri identimisteave ja aadress.</span><span class="sxs-lookup"><span data-stu-id="19e49-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="19e49-121">Näiteks sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="19e49-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="19e49-122">Sisestage faili nimi, mis sisaldab andmeid ja failiteed SFTP serveris, kui see pole juurkaustas.</span><span class="sxs-lookup"><span data-stu-id="19e49-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="19e49-123">Kinnitage kõik sisendid, valides **Ühenda kohandatud importimisega**.</span><span class="sxs-lookup"><span data-stu-id="19e49-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="19e49-124">![SFTP-põhise kohandatud importimise konfiguratsiooni hüpik](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP-põhise kohandatud importimise konfiguratsiooni hüpik")</span><span class="sxs-lookup"><span data-stu-id="19e49-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="19e49-125">Väljavastenduste määratlemine</span><span class="sxs-lookup"><span data-stu-id="19e49-125">Defining field mappings</span></span> 

<span data-ttu-id="19e49-126">Kataloog, mis sisaldab faili, mis imporditakse SFTP serveris, peab sisaldama ka faili *model.json*.</span><span class="sxs-lookup"><span data-stu-id="19e49-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="19e49-127">See fail määratleb andmete importimiseks kasutatava skeemi.</span><span class="sxs-lookup"><span data-stu-id="19e49-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="19e49-128">Skeem peab väljavastenduste määratlemiseks kasutama [Common Data Modelit](https://docs.microsoft.com/common-data-model/).</span><span class="sxs-lookup"><span data-stu-id="19e49-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="19e49-129">Lihtne näide model.json-failist on järgmine.</span><span class="sxs-lookup"><span data-stu-id="19e49-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="19e49-130">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="19e49-130">Enrichment results</span></span>

<span data-ttu-id="19e49-131">Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="19e49-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="19e49-132">Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="19e49-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="19e49-133">Töötlemise aeg sõltub imporditavate andmete mahust ja ühendusest SFTP serveriga.</span><span class="sxs-lookup"><span data-stu-id="19e49-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="19e49-134">Pärast rikastamisprotsessi lõpuleviimist saate oma värskelt imporditud kohandatud rikastatud andmed üle vaadata jaotises **Minu rikastamised**.</span><span class="sxs-lookup"><span data-stu-id="19e49-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="19e49-135">Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="19e49-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="19e49-136">Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.</span><span class="sxs-lookup"><span data-stu-id="19e49-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="19e49-137">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="19e49-137">Next steps</span></span>

<span data-ttu-id="19e49-138">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="19e49-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="19e49-139">Looge [segmente](segments.md), [näitajaid](measures.md) ja [eksportige andmeid](export-destinations.md), et pakkuda klientidele isikupärastatud kogemust.</span><span class="sxs-lookup"><span data-stu-id="19e49-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]