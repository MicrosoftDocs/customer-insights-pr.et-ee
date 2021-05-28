---
title: Tegevusepõhised segmendisoovitused.
description: Lubage masinaõppel aidata teil leida uusi ja huvitavaid klienditegevusel põhinevaid segmente.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034065"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="a4581-103">Soovitatud segmendid, mis põhinevad tegevusandmetel (eelvaade)</span><span class="sxs-lookup"><span data-stu-id="a4581-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="a4581-104">Avastage oma klientidele põnevaid segmente, mis põhinevad klienditegevuse andmetel, mis on sisse toodud Customer Insights -i.</span><span class="sxs-lookup"><span data-stu-id="a4581-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="a4581-105">Tegevuseandmed on näiteks tehingud, kõne kestuse tugi, ostud või tagastamised.</span><span class="sxs-lookup"><span data-stu-id="a4581-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="a4581-106">Segmentide soovitamiseks analüüsitakse tegevuse andmid toimumise aja, sageduse ja rahalise väärtuse järgi (või kestuse).</span><span class="sxs-lookup"><span data-stu-id="a4581-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="a4581-107">Samuti saate luua soovitatud [segmente, et parandada mõõtühikut või paremini mõista, mis atribuuti mõjutab](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="a4581-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Vahekaart Soovitatavad segmendid, kus on kuvatud segmendisoovitused tegevuse- ja atribuudipõhiste segmentide kohta.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="a4581-109">Klientide kategoriseerimiseks tegevuste järgi</span><span class="sxs-lookup"><span data-stu-id="a4581-109">Categorize customers by activity</span></span>

<span data-ttu-id="a4581-110">Koos [tegevusandmete](activities.md) kättesaadavusega Customer Insights -is saame luua soovitusi, mis esindavad kliendirühmi:</span><span class="sxs-lookup"><span data-stu-id="a4581-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="a4581-111">kõige aktiivsemad kliendid</span><span class="sxs-lookup"><span data-stu-id="a4581-111">most active customers</span></span> 
- <span data-ttu-id="a4581-112">Kliendid, kes on teinud kõige rohkem oste</span><span class="sxs-lookup"><span data-stu-id="a4581-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="a4581-113">Kliendid, kes teenisid tõid rohkem tulu</span><span class="sxs-lookup"><span data-stu-id="a4581-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="a4581-114">Kliendid, kes pole olnud aktiivsed</span><span class="sxs-lookup"><span data-stu-id="a4581-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="a4581-115">Kliendid, kes suhtlevad sageli teie ettevõttega</span><span class="sxs-lookup"><span data-stu-id="a4581-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="a4581-116">Kui teil on jaeäri, võite välja uurida, millised kliendid toovad kõige rohkem kasumit ja autasustage neid preemiatega.</span><span class="sxs-lookup"><span data-stu-id="a4581-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="a4581-117">Samuti võite tuvastada juhuslikke kliente ja pakkuda neile võimalust liituda autasuprogrammiga, et nad külastaksid teie ettevõtet sagedamini.</span><span class="sxs-lookup"><span data-stu-id="a4581-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="a4581-118">Kui olete tervishoiuteenuseid pakkuv ettevõte pakkudes avalikku terviseteenust ja teie eesmärk on minimeerida individuaalsete patsientide kulutusi.</span><span class="sxs-lookup"><span data-stu-id="a4581-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="a4581-119">Selleks võib vähendada korduvaid külastusi, pakkudes võimalikult palju hooldust võimalikult väheste külastuste korral.</span><span class="sxs-lookup"><span data-stu-id="a4581-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="a4581-120">Sel juhul on teie eesmärk hoida külastussagedus madal ja minimeerida korduvaid kulusid patsiendile.</span><span class="sxs-lookup"><span data-stu-id="a4581-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="a4581-121">Võite ka tuvastada patsientide segmente, kellel on sagedased külastused ja kõrged korduvad kulud ning analüüsida neid juhtumeid, et parandada üksikisiku ravimist.</span><span class="sxs-lookup"><span data-stu-id="a4581-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="a4581-122">Nõutavad andmed</span><span class="sxs-lookup"><span data-stu-id="a4581-122">Required data</span></span>

<span data-ttu-id="a4581-123">Soovitused luuakse valitud sisestusandmete põhjal.</span><span class="sxs-lookup"><span data-stu-id="a4581-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="a4581-124">Kliendiprofiilid: Kõik kindla segmendi kliendid või liikmed.</span><span class="sxs-lookup"><span data-stu-id="a4581-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="a4581-125">Ajaperiood: Eelmine kuu, eelmine aasta või mis tahes kohandatud ajaperiood.</span><span class="sxs-lookup"><span data-stu-id="a4581-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="a4581-126">Tegevuse tüüp: ostud, jaetehingud, veebitehingud, klienditoe teenindusjuhtumid, kordustellimused jne.</span><span class="sxs-lookup"><span data-stu-id="a4581-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="a4581-127">Customer Insights /i olem, mis sisaldab tegevuse andmeid: Olem UnifiedActivity või konkreetse tegevuse olem.</span><span class="sxs-lookup"><span data-stu-id="a4581-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="a4581-128">Sisalduvad dimensioonid: Hiljutisus, sagedus või rahaline dimensioon vastavalt teie äri nõuetele.</span><span class="sxs-lookup"><span data-stu-id="a4581-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="a4581-129">Soovitatud segmentide genereerimine</span><span class="sxs-lookup"><span data-stu-id="a4581-129">Generate suggested segments</span></span>

1. <span data-ttu-id="a4581-130">Liikuge jaotisse **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="a4581-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="a4581-131">Valige vahekaart **Soovitused (eelvaade)**.</span><span class="sxs-lookup"><span data-stu-id="a4581-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="a4581-132">Valige **Otsi uusi soovitusi** ja valige või **Kliendi käitumise kuvamine või prognoosimine**.</span><span class="sxs-lookup"><span data-stu-id="a4581-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="a4581-133">Valige **Alusta** juhitava kogemuse käivitamiseks.</span><span class="sxs-lookup"><span data-stu-id="a4581-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Konfiguratsiooniviisardi esimene etapp tegevuse põhjal soovitatud segmendi jaoks.":::

1. <span data-ttu-id="a4581-135">Sisestage nõutavad sisestusandmed ja valige **Edasi**.</span><span class="sxs-lookup"><span data-stu-id="a4581-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="a4581-136">Klientide valik: Kaasa kõik kliendid või mõni kindel segment.</span><span class="sxs-lookup"><span data-stu-id="a4581-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="a4581-137">Valige tegevus: Valige tegevuse tüüp ja tegevust kirjeldavad olemid.</span><span class="sxs-lookup"><span data-stu-id="a4581-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="a4581-138">Eelistused: Määrake arvestav ajaperiood, soovituste tegurid ja vastendage atribuudid.</span><span class="sxs-lookup"><span data-stu-id="a4581-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="a4581-139">Vaadake sisestatud andmed läbi ja valige siis mudeli käivitamiseks ning soovituste genereerimiseks käsk **Käivita**.</span><span class="sxs-lookup"><span data-stu-id="a4581-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="a4581-140">Sõltuvalt kliendiprofiilide arvust ja valitud tegevustest võib lõpuleviimiseks aega võtta mõni minut.</span><span class="sxs-lookup"><span data-stu-id="a4581-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="a4581-141">Pärast soovituste genereerimist saate neid filtreerida soovitud osa või väärtuse alusel, mis teile kõige rohkem huvi huvi tekitas.</span><span class="sxs-lookup"><span data-stu-id="a4581-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="a4581-142">Vaadake soovitatud segmendi üksikasju</span><span class="sxs-lookup"><span data-stu-id="a4581-142">View details of a suggested segment</span></span>

<span data-ttu-id="a4581-143">Kui soovitused on loodud, leiate need **Segmendid** > **Soovitused (eelvaade)** jaotisest **Tegevuspõhised soovitused** .</span><span class="sxs-lookup"><span data-stu-id="a4581-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Laiendatud külgpaan, kus kuvatakse soovitatud segmendi üksikasjalikud andmed.":::

<span data-ttu-id="a4581-145">Valige **Kuva soovitused** segmendi üksikasjade vaatamiseks soovitatud segmendisoovitus.</span><span class="sxs-lookup"><span data-stu-id="a4581-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="a4581-146">Kõrvalpaanil on esitatud üksikasjad, nagu iga dimensiooni ulatus sihtrühmaga võrreldes.</span><span class="sxs-lookup"><span data-stu-id="a4581-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="a4581-147">Aruandes tuuakse esile ka segmenti potentsiaalsete liikmete arv ja vastav protsent klientide koguarvutest.</span><span class="sxs-lookup"><span data-stu-id="a4581-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="a4581-148">Kui soovite soovituse säilitada segmendina, valige **Loo segment**.</span><span class="sxs-lookup"><span data-stu-id="a4581-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="a4581-149">Salvestage soovitus segmendina</span><span class="sxs-lookup"><span data-stu-id="a4581-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="a4581-150">Minge jaotisesse **Segmendid** > **Soovitused (eelvaade)**.</span><span class="sxs-lookup"><span data-stu-id="a4581-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="a4581-151">Valige segment, mille soovite salvestada.</span><span class="sxs-lookup"><span data-stu-id="a4581-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="a4581-152">Valige külgpaanil käsk **Loo segment**.</span><span class="sxs-lookup"><span data-stu-id="a4581-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="a4581-153">Pärast segmendi salvestamist kuvatakse see segmentide loendis vahekaardil **Kõik segmendid**. Seda saab nüüd [värskendada või kustutada nagu mis tahes muud segmenti](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a4581-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="a4581-154">Segmendi üksikasju ei saa redigeerida.</span><span class="sxs-lookup"><span data-stu-id="a4581-154">You can't edit the segment details.</span></span> <span data-ttu-id="a4581-155">Siiski saate muuta soovituste sisestuskriteeriume ja luua erinevaid soovitusi.</span><span class="sxs-lookup"><span data-stu-id="a4581-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="a4581-156">Värskendage või muutke soovituste komplekti</span><span class="sxs-lookup"><span data-stu-id="a4581-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="a4581-157">Minge **Segmendid** > **Soovitused (eelvaade)** ja otsige segmenti jaotisest **Tegevusepõhised soovitused** .</span><span class="sxs-lookup"><span data-stu-id="a4581-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="a4581-158">Valige suvand **Värskenda soovitused**, et värskendada soovitusi konfigureeritud atribuutide säilitamise ajal.</span><span class="sxs-lookup"><span data-stu-id="a4581-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="a4581-159">Või valige **Redigeerige soovitusi** konfigureeritud atribuutide muutmiseks.</span><span class="sxs-lookup"><span data-stu-id="a4581-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="a4581-160">Süsteem käivitab protsessi uuesti, loob viimaste andmete põhjal segmendisoovitused ja asendab praegused soovitused.</span><span class="sxs-lookup"><span data-stu-id="a4581-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
