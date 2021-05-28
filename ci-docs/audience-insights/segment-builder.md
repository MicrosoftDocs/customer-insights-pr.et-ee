---
title: Segmentide loomine ja haldamine
description: Looge klientide segmente, et rühmitada neid vastavalt eri atribuutidele.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064932"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="2edc1-103">Segmentide loomine ja haldamine</span><span class="sxs-lookup"><span data-stu-id="2edc1-103">Create and manage segments</span></span>

<span data-ttu-id="2edc1-104">Määratlege keerukad filtrid ühendatud kliendiolemi ümber ja sellega seotud olemid.</span><span class="sxs-lookup"><span data-stu-id="2edc1-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="2edc1-105">Pärast töötlemist loob iga segment hulga kliendi kirjeid, mille saate eksportida ja nendega toiminguid teha.</span><span class="sxs-lookup"><span data-stu-id="2edc1-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="2edc1-106">Segmente saab hallata lehel **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="2edc1-107">Järgmine näide illustreerib segmenteerimise võimalust.</span><span class="sxs-lookup"><span data-stu-id="2edc1-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="2edc1-108">Oleme määratlenud segmendi klientidele, kes on tellinud vähemalt 500 USD eest kaupu viimase 90 päeva jooksul *ja* kes olid seotud klienditeeninduse kõnega, mida eskaleeriti.</span><span class="sxs-lookup"><span data-stu-id="2edc1-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Segmendi meisterdamis kasutajaliidese kuvatõmmis kahe kliendisegmendiga rühmaga.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="2edc1-110">Looge uus segment</span><span class="sxs-lookup"><span data-stu-id="2edc1-110">Create a new segment</span></span>

<span data-ttu-id="2edc1-111">Uue segmendi loomiseks on mitu võimalust.</span><span class="sxs-lookup"><span data-stu-id="2edc1-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="2edc1-112">Selles jaotises kirjeldatakse, kuidas luua *tühja segmenti*.</span><span class="sxs-lookup"><span data-stu-id="2edc1-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="2edc1-113">Samuti saate luua olemasolevatel olemitel põhineva *kiirsegmendi* või kasutada Masinõpe mudeleid et saada *soovitatud segmente*.</span><span class="sxs-lookup"><span data-stu-id="2edc1-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="2edc1-114">Lisateave: [Segmentide ülevaade](segments.md).</span><span class="sxs-lookup"><span data-stu-id="2edc1-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="2edc1-115">Segmenti luues saate mustandi salvestada.</span><span class="sxs-lookup"><span data-stu-id="2edc1-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="2edc1-116">See salvestatakse passiivse segmendina ja seda ei saa kehtiva konfiguratsiooniga aktiveeritud olla.</span><span class="sxs-lookup"><span data-stu-id="2edc1-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="2edc1-117">Minge lehele **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="2edc1-118">Valige **Uus** > **Tühi segment**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="2edc1-119">Paanil **Uus segment** valige segmendi tüüp.</span><span class="sxs-lookup"><span data-stu-id="2edc1-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="2edc1-120">**Dünaamilised segmendid** [värskenda](segments.md#refresh-segments) korduva ajakava puhul.</span><span class="sxs-lookup"><span data-stu-id="2edc1-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="2edc1-121">**Staatilisi segmente** käitatakse üks kord selle loomisel.</span><span class="sxs-lookup"><span data-stu-id="2edc1-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="2edc1-122">Sisestage **Väljundi olemi nimi** segmendi jaoks.</span><span class="sxs-lookup"><span data-stu-id="2edc1-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="2edc1-123">Soovi korral sisestage segmendi tuvastamist hõlbustav näidatav nimi ja kirjeldus.</span><span class="sxs-lookup"><span data-stu-id="2edc1-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="2edc1-124">Rühma määramise lehele **Segmendikoostur** minemiseks valige **Järgmine**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="2edc1-125">Rühm on hulk kliente.</span><span class="sxs-lookup"><span data-stu-id="2edc1-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="2edc1-126">Valige olem, mis sisaldab segmenteeritavat atribuuti.</span><span class="sxs-lookup"><span data-stu-id="2edc1-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="2edc1-127">Valige atribuut, mille järgi segmenteerida.</span><span class="sxs-lookup"><span data-stu-id="2edc1-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="2edc1-128">Atribuudil võib olla üks neljast väärtuse tüübist: arvuline, string, kuupäev või Boolean.</span><span class="sxs-lookup"><span data-stu-id="2edc1-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="2edc1-129">Valige valitud atribuudi tehtemärk ja väärtus.</span><span class="sxs-lookup"><span data-stu-id="2edc1-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2edc1-130">![Kohandatud rühma filter](media/customer-group-numbers.png "Kliendi rühma filter")</span><span class="sxs-lookup"><span data-stu-id="2edc1-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="2edc1-131">Number</span><span class="sxs-lookup"><span data-stu-id="2edc1-131">Number</span></span> |<span data-ttu-id="2edc1-132">Määratlus</span><span class="sxs-lookup"><span data-stu-id="2edc1-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="2edc1-133">1</span><span class="sxs-lookup"><span data-stu-id="2edc1-133">1</span></span>     |<span data-ttu-id="2edc1-134">Entity</span><span class="sxs-lookup"><span data-stu-id="2edc1-134">Entity</span></span>          |
   |<span data-ttu-id="2edc1-135">2</span><span class="sxs-lookup"><span data-stu-id="2edc1-135">2</span></span>     |<span data-ttu-id="2edc1-136">Atribuut</span><span class="sxs-lookup"><span data-stu-id="2edc1-136">Attribute</span></span>          |
   |<span data-ttu-id="2edc1-137">3</span><span class="sxs-lookup"><span data-stu-id="2edc1-137">3</span></span>    |<span data-ttu-id="2edc1-138">Operaator</span><span class="sxs-lookup"><span data-stu-id="2edc1-138">Operator</span></span>         |
   |<span data-ttu-id="2edc1-139">4</span><span class="sxs-lookup"><span data-stu-id="2edc1-139">4</span></span>    |<span data-ttu-id="2edc1-140">Väärtus</span><span class="sxs-lookup"><span data-stu-id="2edc1-140">Value</span></span>         |

   1. <span data-ttu-id="2edc1-141">Rühmale täiendavate tingimuste lisamiseks saate kasutada kaht loogikatehet:</span><span class="sxs-lookup"><span data-stu-id="2edc1-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="2edc1-142">**AND** tehtemärk: mõlemad tingimused tuleb täita segmenteerimise võimaldamiseks.</span><span class="sxs-lookup"><span data-stu-id="2edc1-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="2edc1-143">See valik on kõige kasulikum juhul, kui määratlete eri olemite tingimusi.</span><span class="sxs-lookup"><span data-stu-id="2edc1-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="2edc1-144">**VÕI** tehtemärk: üks tingimus tuleb täita segmenteerimise võimaldamiseks.</span><span class="sxs-lookup"><span data-stu-id="2edc1-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="2edc1-145">See valik on kõige kasulikum juhul, kui määratlete sama olemi mitu tingimusi.</span><span class="sxs-lookup"><span data-stu-id="2edc1-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="2edc1-146">![OR tehtemärk, kus tuleb täita üks tingimustest](media/segmentation-either-condition.png "OR tehtemärk, kus tuleb täita üks tingimustest")</span><span class="sxs-lookup"><span data-stu-id="2edc1-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="2edc1-147">Praegu saab pesastada tehtemärki **OR** tehtemärgi **AND** põhjal, ent mitte vastupidi.</span><span class="sxs-lookup"><span data-stu-id="2edc1-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="2edc1-148">Iga rühm vastab klientide komplektile.</span><span class="sxs-lookup"><span data-stu-id="2edc1-148">Each group matches set of customers.</span></span> <span data-ttu-id="2edc1-149">Saate ühendada rühmad, et kaasata teie ärijuhtumi jaoks nõutavad kliendid.</span><span class="sxs-lookup"><span data-stu-id="2edc1-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="2edc1-150">Valige **Lisa rühm**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="2edc1-151">![Kliendirühma lisamine](media/customer-group-add-group.png "Kliendirühma lisamine")</span><span class="sxs-lookup"><span data-stu-id="2edc1-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="2edc1-152">Valige üks tehingukomplekt: **Liit**, **Lõikuv** või **Välja arvatud**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2edc1-153">![Kliendirühma ühendi lisamine](media/customer-group-union.png "Kliendirühma ühendi lisamine")</span><span class="sxs-lookup"><span data-stu-id="2edc1-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="2edc1-154">**ühend** ühendab kaks rühma.</span><span class="sxs-lookup"><span data-stu-id="2edc1-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="2edc1-155">**Ühisosa** kattub kahe rühmaga.</span><span class="sxs-lookup"><span data-stu-id="2edc1-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="2edc1-156">Koondatud rühma jäetakse alles ainult andmed, mis on mõlemas rühmas *ühised*.</span><span class="sxs-lookup"><span data-stu-id="2edc1-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="2edc1-157">**Välja arvatud** kombineerib kaks rühma.</span><span class="sxs-lookup"><span data-stu-id="2edc1-157">**Except** combines the two groups.</span></span> <span data-ttu-id="2edc1-158">Alles jäetakse ainult sellised rühma A andmed, mida *ei leidu* rühmas B.</span><span class="sxs-lookup"><span data-stu-id="2edc1-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="2edc1-159">Kui olem on ühtlustatud kliendi olemiga seotud läbi [seoste](relationships.md), peate määratlema seose tee kehtiva segmendi loomiseks.</span><span class="sxs-lookup"><span data-stu-id="2edc1-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="2edc1-160">Lisage olemid seose teest, kuni saate valida ripploendist olemi vormi **Klient: CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="2edc1-161">Seejärel valige **Kõik kirjed** iga etapi jaoks.</span><span class="sxs-lookup"><span data-stu-id="2edc1-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2edc1-162">![Seose tee segmendi loomise ajal](media/segments-multiple-relationships.png "Seose tee segmendi loomise ajal")</span><span class="sxs-lookup"><span data-stu-id="2edc1-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="2edc1-163">Vaikimisi genereerivad segmendid väljundolemi, mis sisaldab määratletud filtritele vastavaid kliendiprofiilide kõiki atribuute.</span><span class="sxs-lookup"><span data-stu-id="2edc1-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="2edc1-164">Kui segment põhineb muudel olemitel kui olem *Klient*, saate väljundolendisse lisada rohkem atribuute nendest olemitest.</span><span class="sxs-lookup"><span data-stu-id="2edc1-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="2edc1-165">Valige **Projekti tribuudid**, et valida väljundolemile lisatavad atribuudid.</span><span class="sxs-lookup"><span data-stu-id="2edc1-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="2edc1-166">Näide: segment põhineb olemil, mis sisaldab klienditegevuse andmeid, mis on seotud olemiga *Klient*.</span><span class="sxs-lookup"><span data-stu-id="2edc1-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="2edc1-167">Segment otsib kõiki kliente, kes on viimase 60 päeva jooksul klienditoele helistanud.</span><span class="sxs-lookup"><span data-stu-id="2edc1-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="2edc1-168">Saate valida kõne kestuse ja kõnede arvu lisamise kõigile väljundolemi vastavatele kliendikirjeile.</span><span class="sxs-lookup"><span data-stu-id="2edc1-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="2edc1-169">See teave võib kasulik olla meili saatmiseks koos kasulike linkidega võrgus asuvatele spikriartiklitele ja KKK-dele klientidele, kes sageli helistasid.</span><span class="sxs-lookup"><span data-stu-id="2edc1-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="2edc1-170">Prognoositud atribuudid töötavad ainult olemitega, kellel on üks-mitmele-seos kliendiolemiga.</span><span class="sxs-lookup"><span data-stu-id="2edc1-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="2edc1-171">Näiteks võib ühel kliendil olla mitu tellimust.</span><span class="sxs-lookup"><span data-stu-id="2edc1-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="2edc1-172">Saate luua ainult selle olemi projektiatribuute, mida kasutatakse igas teie kasutatava segmendipäringu rühmas.</span><span class="sxs-lookup"><span data-stu-id="2edc1-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="2edc1-173">Prognoositud atribuudid on teguriks seatud kasutades tehete kogumeid.</span><span class="sxs-lookup"><span data-stu-id="2edc1-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="2edc1-174">Segmendi salvestamiseks valige nupp **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="2edc1-175">Segment salvestatakse ja töödeldakse, kui kõik nõuded on kinnitatud.</span><span class="sxs-lookup"><span data-stu-id="2edc1-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="2edc1-176">Vastasel juhul salvestatakse see mustandina.</span><span class="sxs-lookup"><span data-stu-id="2edc1-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="2edc1-177">Valige **Tagasi segmentidesse**, et naasta lehele **Segmendid**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="2edc1-178">Kiirsegmendid</span><span class="sxs-lookup"><span data-stu-id="2edc1-178">Quick segments</span></span>

<span data-ttu-id="2edc1-179">Kiirsegmendid lasevad teil luua lihtsaid segmente ühe tehtega kiiresti, et saada kiiremaid ülevaateid.</span><span class="sxs-lookup"><span data-stu-id="2edc1-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="2edc1-180">Lehel **Segmendid** klõpsake **Uus** > **Loo vorm**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="2edc1-181">Valige suvand **Profiilid** etehitada segment, mis põhineb *ühendatud kliendi* olemil.</span><span class="sxs-lookup"><span data-stu-id="2edc1-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="2edc1-182">Valige suvand **Mõõtmised**, et luua segment juba loodud segmentide ümber.</span><span class="sxs-lookup"><span data-stu-id="2edc1-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="2edc1-183">Valige suvand **Ärianalüüs**, et luua segment ümber ühe väljundi olemi, mille olete loonud, kasutades kas **Prognooside** või **Kohandatud mudelite** võimalusi.</span><span class="sxs-lookup"><span data-stu-id="2edc1-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="2edc1-184">Valige dialoogiboksis **Uus kiirsegment** atribuut ripploendist **Väli**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="2edc1-185">Süsteem esitab paar täiendavat ülevaadet, mis aitavad luua klientidest paremad segmendid.</span><span class="sxs-lookup"><span data-stu-id="2edc1-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="2edc1-186">Kategooria väljade puhul näitame 10 peamist kliendi arvu.</span><span class="sxs-lookup"><span data-stu-id="2edc1-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="2edc1-187">Valige **Väärtus** ja **Ülevaatamine**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="2edc1-188">Süsteem näitab numbrilise atribuudi puhul, mis atribuudi väärtus langeb iga kliendi protsendiili alla.</span><span class="sxs-lookup"><span data-stu-id="2edc1-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="2edc1-189">Valige **Tehtemärk**, **Väärtus** ja **Ülevaatamine**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="2edc1-190">Süsteem esitab **hinnangulise segmendi mahu**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="2edc1-191">Saate valida, kas luua määratletud segment või esmalt vaadata seda uuesti, et hankida muus mahus segment.</span><span class="sxs-lookup"><span data-stu-id="2edc1-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="2edc1-192">![Kiirsegmendi nimi ja hinnang](media/quick-segment-name.png "Kiirsegmendi nimi ja hinnang")</span><span class="sxs-lookup"><span data-stu-id="2edc1-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="2edc1-193">Sisestage segmendi **nimi**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="2edc1-194">Soovi korral sisestage **Kuvatav nimi**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="2edc1-195">Segmendi loomiseks valige käsk **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="2edc1-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="2edc1-196">Pärast segmendi töötlust saate seda vaadata nagu kõiki teisi loodud segmente.</span><span class="sxs-lookup"><span data-stu-id="2edc1-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2edc1-197">Järgmised etapid</span><span class="sxs-lookup"><span data-stu-id="2edc1-197">Next steps</span></span>

<span data-ttu-id="2edc1-198">Kliendi taseme ülevaadete hankimiseks [eksportige segment](export-destinations.md) ja tutvuge [kliendikaardiga](customer-card-add-in.md) ning [ühendajatega](export-power-bi.md).</span><span class="sxs-lookup"><span data-stu-id="2edc1-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
