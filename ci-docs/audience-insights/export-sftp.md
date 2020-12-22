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
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="26eee-103">SFTP konnektor (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="26eee-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="26eee-104">Kasutage oma kliendiandmeid kolmanda osapoole rakendustes, eksportides need turvalise failiedastuse protokolli (SFTP) hosti.</span><span class="sxs-lookup"><span data-stu-id="26eee-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26eee-105">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="26eee-105">Prerequisites</span></span>

- <span data-ttu-id="26eee-106">SFTP hosti ja vastavate mandaatide kättesaadavus.</span><span class="sxs-lookup"><span data-stu-id="26eee-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="26eee-107">SFTP-ga ühenduse loomine</span><span class="sxs-lookup"><span data-stu-id="26eee-107">Connect to SFTP</span></span>

1. <span data-ttu-id="26eee-108">Avage **Haldus** > **Ekspordi sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="26eee-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="26eee-109">Valige jaotises **SFTP** suvand **Seadistamine**.</span><span class="sxs-lookup"><span data-stu-id="26eee-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="26eee-110">Sisestage väljale **Kuvatav nimi** oma sihtkoha äratuntav nimi.</span><span class="sxs-lookup"><span data-stu-id="26eee-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="26eee-111">Sisestage oma SFTP konto jaoks **Kasutajanimi**, **Parool** ja **Hostinimi**.</span><span class="sxs-lookup"><span data-stu-id="26eee-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="26eee-112">Näide: kui teie SFTP serveri juurkaust on /root/folder ning te soovite, et andmed eksporditakse kohta /root/folder/ci_export_destination_folder, peab host olema sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="26eee-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="26eee-113">Valige ühenduse testimiseks **Kinnita**.</span><span class="sxs-lookup"><span data-stu-id="26eee-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="26eee-114">Pärast edukat kinnitamist valige, kas soovite oma andmed eksportida **pakituna** või **lahtipakituna** ja valige eksporditud failide **väljaeraldaja**.</span><span class="sxs-lookup"><span data-stu-id="26eee-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="26eee-115">**Andmete privaatsuse ja nõuetele vastavuse** kinnitamiseks valige **Nõustun**.</span><span class="sxs-lookup"><span data-stu-id="26eee-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="26eee-116">Ekspordi konfigureerimise alustamiseks valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="26eee-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="26eee-117">Ühenduse kontrollimine</span><span class="sxs-lookup"><span data-stu-id="26eee-117">Configure the connection</span></span>

1. <span data-ttu-id="26eee-118">Valige **kliendi atribuudid**, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="26eee-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="26eee-119">Saate eksportida ühe või mitu atribuuti.</span><span class="sxs-lookup"><span data-stu-id="26eee-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="26eee-120">Tehke valik **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="26eee-120">Select **Next**.</span></span>

1. <span data-ttu-id="26eee-121">Valige segmendid, mille soovite eksportida.</span><span class="sxs-lookup"><span data-stu-id="26eee-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="26eee-122">Valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="26eee-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="26eee-123">Andmete eksportimine</span><span class="sxs-lookup"><span data-stu-id="26eee-123">Export the data</span></span>

<span data-ttu-id="26eee-124">Saate [vajadusel andmeid eksportida](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="26eee-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="26eee-125">Eksport käivitub ka iga [ajastatud värskendamisega](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="26eee-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="26eee-126">Andmete privaatsus ja nõuetele vastavus</span><span class="sxs-lookup"><span data-stu-id="26eee-126">Data privacy and compliance</span></span>

<span data-ttu-id="26eee-127">Kui lubate Dynamics 365 Customer Insightsil SFTP kaudu andmeid edastada, ei kohaldata andmete edastamisel Dynamics 365 Customer Insightsi vastavustingimusi, sealhulgas potentsiaalselt tundlike andmete korral (nt isikuandmed).</span><span class="sxs-lookup"><span data-stu-id="26eee-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="26eee-128">Microsoft edastab sellised andmed, kui te seda soovite, kuid teie vastutate selle tagamise eest, et ekspordisihtkohad täidavad kõik teie privaatsus- või turbenõuded.</span><span class="sxs-lookup"><span data-stu-id="26eee-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="26eee-129">Lisateavet leiate artiklist [Microsofti privaatsusavaldus](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="26eee-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="26eee-130">Teie Dynamics 365 Customer Insightsi administraator saab selle ekspordisihtkoha igal ajal eemaldada, et lõpetada selle funktsiooni kasutamine.</span><span class="sxs-lookup"><span data-stu-id="26eee-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
