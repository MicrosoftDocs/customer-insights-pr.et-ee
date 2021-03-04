---
title: Microsoft Teamsi robot
description: Otsige roboti abil Microsoft Teamsis koondatud kliendiprofiile.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267947"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="e8d03-103">Teamsi robot Dynamics 365 Customer Insightsi jaoks (eelversioon)</span><span class="sxs-lookup"><span data-stu-id="e8d03-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="e8d03-104">Ühenduge Microsoft Teamsiga, et lasta robotil otsida koondatud kliendiprofiile Teamsi kanalites.</span><span class="sxs-lookup"><span data-stu-id="e8d03-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e8d03-105">![Kliendi kirjet kuvav Teamsi robot](media/teams-bot.png "Kliendi kirjet kuvav Teamsi robot")</span><span class="sxs-lookup"><span data-stu-id="e8d03-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e8d03-106">Eeltingimused</span><span class="sxs-lookup"><span data-stu-id="e8d03-106">Prerequisites</span></span>

<span data-ttu-id="e8d03-107">Boti seadistamiseks ja konfigureerimiseks peavad olema täidetud järgmised eeltingimused.</span><span class="sxs-lookup"><span data-stu-id="e8d03-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e8d03-108">Vähemalt üks [andmeallikas on lisatud](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="e8d03-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="e8d03-109">[Ühendamisprotsess](data-unification.md) on lõpule viidud.</span><span class="sxs-lookup"><span data-stu-id="e8d03-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="e8d03-110">[Otsingu ja filtri indeksisse](search-filter-index.md) on lisatud väljad.</span><span class="sxs-lookup"><span data-stu-id="e8d03-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="e8d03-111">Customer Insights ja Teams on samas organisatsioonis.</span><span class="sxs-lookup"><span data-stu-id="e8d03-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="e8d03-112">Boti konfigureerimine</span><span class="sxs-lookup"><span data-stu-id="e8d03-112">Configure the bot</span></span>

1. <span data-ttu-id="e8d03-113">Avage sihtrühmaülevaadetes jaotis **Haldus** > **Eksportimise sihtkohad**.</span><span class="sxs-lookup"><span data-stu-id="e8d03-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="e8d03-114">Valige Microsoft Teamsi paanil suvand **Seadista**.</span><span class="sxs-lookup"><span data-stu-id="e8d03-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="e8d03-115">Teid suunatakse ümber Teamsi alale **Rakendused**.</span><span class="sxs-lookup"><span data-stu-id="e8d03-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="e8d03-116">Võite avada Teamsi ja valida alumises vasakus nurgas suvandi **Rakendused** või [hankida selle AppSource’ist](https://go.microsoft.com/fwlink/?linkid=2124104) otse.</span><span class="sxs-lookup"><span data-stu-id="e8d03-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="e8d03-117">Otsige mõistet **Customer Insights** ja valige rakendus.</span><span class="sxs-lookup"><span data-stu-id="e8d03-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="e8d03-118">Valige suvand **Lisa**.</span><span class="sxs-lookup"><span data-stu-id="e8d03-118">Select **Add**.</span></span>
1. <span data-ttu-id="e8d03-119">Pärast Teamsis Customer Insightsi sisselogimist näete tervitussõnumit ja võite alustada.</span><span class="sxs-lookup"><span data-stu-id="e8d03-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="e8d03-120">Asjad, mida saate botiga teha</span><span class="sxs-lookup"><span data-stu-id="e8d03-120">Things you can do with the bot</span></span>

<span data-ttu-id="e8d03-121">Bot pakub ühendatud kliendiprofiilide otsinguvõimalusi.</span><span class="sxs-lookup"><span data-stu-id="e8d03-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="e8d03-122">Sisestage **otsing**, millele järgneb nimi, meiliaadress või mis tahes muu väli ühendatud kliendiprofiilis, mis lisatakse otsingu ja filtri indeksisse.</span><span class="sxs-lookup"><span data-stu-id="e8d03-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="e8d03-123">Saate tulemuseks olevalt kliendiprofiililt kaardi kuni 15 väljaga.</span><span class="sxs-lookup"><span data-stu-id="e8d03-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="e8d03-124">Mitu vastet tagastavad tulemite loendi, kust saate valida soovitud profiili.</span><span class="sxs-lookup"><span data-stu-id="e8d03-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="e8d03-125">Täpse vaste otsimiseks saate lisada otsingusõna kahekordsetes jutumärkides.</span><span class="sxs-lookup"><span data-stu-id="e8d03-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="e8d03-126">Kui teie organisatsioon haldab ühes organisatsioonis mitut Customer Insightsi keskkonda, saate sisestada **switchinstance**, et valida, millise keskkonnaga soovite robotit ühendada.</span><span class="sxs-lookup"><span data-stu-id="e8d03-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="e8d03-127">Sisestage märksõna **spikker** boti jaoks saadaolevate käskude loendi kuvamiseks.</span><span class="sxs-lookup"><span data-stu-id="e8d03-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]