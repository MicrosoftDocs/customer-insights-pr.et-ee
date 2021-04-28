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
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896276"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="68816-103">Kliendiprofiilide rikastamine kohandatud andmetega (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="68816-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="68816-104">Turvalise failiedastuse protokolli (SFTP) kohandatud import võimaldab teil importida andmeid, mis ei pea läbima andmete ühendamise protsessi.</span><span class="sxs-lookup"><span data-stu-id="68816-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="68816-105">See on paindlik, turvaline ja lihtne viis andmete sissetoomiseks.</span><span class="sxs-lookup"><span data-stu-id="68816-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="68816-106">SFTP-põhist kohandatud importimist saab kasutada koos [SFTP-põhise ekspordiga](export-sftp.md), mis võimaldab teil eksportida kliendiprofiili andmeid, mida on vaja rikastamiseks.</span><span class="sxs-lookup"><span data-stu-id="68816-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="68816-107">Seejärel saab andmeid töödelda, rikastada ning SFTP-põhist kohandatud importimist saab kasutada, et tuua rikastatud andmed tagasi Dynamics 365 Customer Insightsi sihtrühmaülevaadete funktsiooni.</span><span class="sxs-lookup"><span data-stu-id="68816-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="68816-108">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="68816-108">Prerequisites</span></span>

<span data-ttu-id="68816-109">SFTP-põhise kohandatud importimise konfigureerimiseks peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="68816-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="68816-110">Teil on SFTP-hostis imporditava faili nimi ja asukoht (tee).</span><span class="sxs-lookup"><span data-stu-id="68816-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="68816-111">Imporditavate andmete jaoks on olemas fail *model.json*, mis määrab [Common Data Model skeemi](/common-data-model/) imporditavatele andmetele.</span><span class="sxs-lookup"><span data-stu-id="68816-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="68816-112">See fail peab asuma imporditava failiga samas kataloogis.</span><span class="sxs-lookup"><span data-stu-id="68816-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="68816-113">Administraator on SFTP-ühenduse juba konfigureerinud *või* teil on [administraatoriõigused](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="68816-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="68816-114">SFTP asukoha jaoks, kust soovite andmeid importida, vajate kasutaja volikirja, URL-i ja pordi numbrit.</span><span class="sxs-lookup"><span data-stu-id="68816-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="68816-115">Impordi konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="68816-115">Configure the import</span></span>

1. <span data-ttu-id="68816-116">Avage suvandid **Andmed** > **Rikastamine** ja valige vahekaart **Avasta**.</span><span class="sxs-lookup"><span data-stu-id="68816-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="68816-117">**SFTP kohandatud impordipaanil** valige **Minu andmete rikastamine** ja seejärel valige **Alustamine**.</span><span class="sxs-lookup"><span data-stu-id="68816-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="SFTP kohandatud impordipaan.":::

1. <span data-ttu-id="68816-119">Valige ripploendist [ühendus](connections.md).</span><span class="sxs-lookup"><span data-stu-id="68816-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="68816-120">Kui ühendusi pole saadaval, pöörduge administraatori poole.</span><span class="sxs-lookup"><span data-stu-id="68816-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="68816-121">Kui olete administraator, saate ühenduse luua, valides ripploendist suvandi **Lisa ühendus** ja valides **SFTP kohandatud importimine**.</span><span class="sxs-lookup"><span data-stu-id="68816-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="68816-122">Valige **Ühenda kohandatud importimisega**, et kinnitada ühenduse valik.</span><span class="sxs-lookup"><span data-stu-id="68816-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="68816-123">Valige **Edasi** ning sisestage **Faili nimi** ja **Tee** andmefaili kohta, mida soovite importida.</span><span class="sxs-lookup"><span data-stu-id="68816-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Kuvatõmmis andmeasukoha sisestamisel.":::

1. <span data-ttu-id="68816-125">Valige **Edasi** ja sisestage rikastamise nimi ja väljundolemi nimi.</span><span class="sxs-lookup"><span data-stu-id="68816-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="68816-126">Valige **Salvesta rikastamine** pärast valikute läbivaatamist.</span><span class="sxs-lookup"><span data-stu-id="68816-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="68816-127">SFTP kohandatud impordi ühenduse konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="68816-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="68816-128">Ühenduste konfigureerimiseks peate olema administraator.</span><span class="sxs-lookup"><span data-stu-id="68816-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="68816-129">Valige **Lisa ühendus** rikastamise konfigureerimisel *või* minge **Administraator** > **Ühendused** ja valige **Seadista** kohandatud importimise paanil.</span><span class="sxs-lookup"><span data-stu-id="68816-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="68816-130">Sisestage ühenduse nimi **Kuvatav nimi** väljale.</span><span class="sxs-lookup"><span data-stu-id="68816-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="68816-131">Sisestage imporditavate andmete SFTP-serveri jaoks kehtiv kasutajanimi, parool ja hosti URL.</span><span class="sxs-lookup"><span data-stu-id="68816-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="68816-132">Vaadake üle ja andke oma nõusolek **Andmete privaatsuse ja nõuetele vastavuse** jaoks, valides märkeruudu **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="68816-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="68816-133">Valige **Kontrolli** konfiguratsiooni valideerimiseks.</span><span class="sxs-lookup"><span data-stu-id="68816-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="68816-134">Kui kontroll on lõpule jõudnud, saab ühenduse salvestada, klõpsates nuppu **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="68816-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="68816-135">![Experian ühenduse konfiguratsiooni paan](media/enrichment-SFTP-connection.png "Experian ühenduse konfiguratsiooni paan")</span><span class="sxs-lookup"><span data-stu-id="68816-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="68816-136">Väljavastenduste määratlemine</span><span class="sxs-lookup"><span data-stu-id="68816-136">Defining field mappings</span></span> 

<span data-ttu-id="68816-137">Kataloog, mis sisaldab faili, mis imporditakse SFTP serveris, peab sisaldama ka faili *model.json*.</span><span class="sxs-lookup"><span data-stu-id="68816-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="68816-138">See fail määratleb andmete importimiseks kasutatava skeemi.</span><span class="sxs-lookup"><span data-stu-id="68816-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="68816-139">Skeem peab väljavastenduste määratlemiseks kasutama [Common Data Modelit](/common-data-model/).</span><span class="sxs-lookup"><span data-stu-id="68816-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="68816-140">Lihtne näide model.json-failist on järgmine.</span><span class="sxs-lookup"><span data-stu-id="68816-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="68816-141">Rikastamise tulemused</span><span class="sxs-lookup"><span data-stu-id="68816-141">Enrichment results</span></span>

<span data-ttu-id="68816-142">Rikastamistoimingu käivitamiseks valige käsuribalt suvand **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="68816-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="68816-143">Samuti saate lasta süsteemil rikastamise automaatselt käivitada [ajastatud värskenduse osana](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="68816-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="68816-144">Töötlemise aeg sõltub imporditavate andmete mahust ja ühendusest SFTP serveriga.</span><span class="sxs-lookup"><span data-stu-id="68816-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="68816-145">Pärast rikastamisprotsessi lõpuleviimist saate oma värskelt imporditud kohandatud rikastatud andmed üle vaadata jaotises **Minu rikastamised**.</span><span class="sxs-lookup"><span data-stu-id="68816-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="68816-146">Peale selle näete ka viimase värskenduse aega ja rikastatud profiilide arvu.</span><span class="sxs-lookup"><span data-stu-id="68816-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="68816-147">Saate tutvuda iga rikastatud profiili üksikasjaliku vaatega, valides suvandi **Kuva rikastatud andmed**.</span><span class="sxs-lookup"><span data-stu-id="68816-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="68816-148">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="68816-148">Next steps</span></span>

<span data-ttu-id="68816-149">Rikastatud kliendiandmetele toetumine.</span><span class="sxs-lookup"><span data-stu-id="68816-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="68816-150">Looge [segmente](segments.md), [näitajaid](measures.md) ja [eksportige andmeid](export-destinations.md), et pakkuda klientidele isikupärastatud kogemust.</span><span class="sxs-lookup"><span data-stu-id="68816-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
