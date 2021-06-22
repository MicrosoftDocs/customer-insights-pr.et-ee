---
title: Seosed olemite ja olemiteede vahel
description: Looge ja hallake mitmest andmeallikast pärit olemite vahelisi seoseid.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171159"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="9c26e-103">Olemitevaheline seos</span><span class="sxs-lookup"><span data-stu-id="9c26e-103">Relationships between entities</span></span>

<span data-ttu-id="9c26e-104">Seosed ühendavad olemid ja määratlevad teie andmete graafiku, kui olemitel on ühine identifikaator (võõrvõti).</span><span class="sxs-lookup"><span data-stu-id="9c26e-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="9c26e-105">Seda võtit saab viidata ühest olemist teise.</span><span class="sxs-lookup"><span data-stu-id="9c26e-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="9c26e-106">Ühendatud olemid võimaldavad määratleda segmente ja mõõte mitmete andmeallikate alusel.</span><span class="sxs-lookup"><span data-stu-id="9c26e-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="9c26e-107">Seoseid on kolme tüüpi:</span><span class="sxs-lookup"><span data-stu-id="9c26e-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="9c26e-108">Mitteredigeeritavad süsteemiseosed, mille süsteem on loonud andmete ühendamise protsessi osana</span><span class="sxs-lookup"><span data-stu-id="9c26e-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="9c26e-109">Mitteredigeeritavad päritud seosed, mis luuakse andmeallikatest automaatselt</span><span class="sxs-lookup"><span data-stu-id="9c26e-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="9c26e-110">Redigeeritavad kohandatud seosed, mille on loonud ja konfigureerinud kasutajad</span><span class="sxs-lookup"><span data-stu-id="9c26e-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="9c26e-111">Mitteredigeeritavad süsteemiseosed</span><span class="sxs-lookup"><span data-stu-id="9c26e-111">Non-editable system relationships</span></span>

<span data-ttu-id="9c26e-112">Andmete ühendamisel luuakse süsteemiseosed intelligentse ühendamise põhjal automaatselt.</span><span class="sxs-lookup"><span data-stu-id="9c26e-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="9c26e-113">Need seosed aitavad seostada kliendiprofiili kirjeid vastavate kirjetega.</span><span class="sxs-lookup"><span data-stu-id="9c26e-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="9c26e-114">Järgmisel diagrammil on esitatud kolm süsteemipõhist seost.</span><span class="sxs-lookup"><span data-stu-id="9c26e-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="9c26e-115">Ühtse olemi *Klient* loomiseks sobitatakse kliendiüksus teiste üksustega.</span><span class="sxs-lookup"><span data-stu-id="9c26e-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagramm kolme 1-n-seosega kliendiolemi seoseteega;":::

- <span data-ttu-id="9c26e-117">***CustomerToContact* seos** loodi *kliendi* olemi ja *kontakti* olemi vahel.</span><span class="sxs-lookup"><span data-stu-id="9c26e-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="9c26e-118">*Kliendi* olem saab võtme välja **Contact_contactID**, et olla seotud *kontakti* olemi võtme väljaga **contactID**.</span><span class="sxs-lookup"><span data-stu-id="9c26e-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="9c26e-119">***CustomerToAccount* seos** loodi *kliendi* olemi ja *konto* olemi vahel.</span><span class="sxs-lookup"><span data-stu-id="9c26e-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="9c26e-120">*Kliendi* olem saab võtme välja **Account_accountID**, et olla seotud *konto* olemi võtme väljaga **accountID**.</span><span class="sxs-lookup"><span data-stu-id="9c26e-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="9c26e-121">***CustomerToWebAccount* seos** loodi *kliendi* olemi ja *veebikonto* olemi vahel.</span><span class="sxs-lookup"><span data-stu-id="9c26e-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="9c26e-122">*Kliendi* olem saab võtme välja **WebAccount_webaccountID**, et olla seotud *veebikonto* olemi võtme väljaga **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="9c26e-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="9c26e-123">Mitteredigeeritavad pärilikud suhted</span><span class="sxs-lookup"><span data-stu-id="9c26e-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="9c26e-124">Andmete kogumisprotsessi ajal kontrollib süsteem andmeallikaid olemasolevate seoste suhtes.</span><span class="sxs-lookup"><span data-stu-id="9c26e-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="9c26e-125">Kui seost pole olemas, loob süsteem need automaatselt.</span><span class="sxs-lookup"><span data-stu-id="9c26e-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="9c26e-126">Neid seoseid kasutatakse ka järgnevas protsessis.</span><span class="sxs-lookup"><span data-stu-id="9c26e-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="9c26e-127">Kohandatud seose loomine</span><span class="sxs-lookup"><span data-stu-id="9c26e-127">Create a custom relationship</span></span>

<span data-ttu-id="9c26e-128">Seos koosneb *lähteolemist*, mis sisaldab võõrvõtit ja *sihtolemit*, millele lähteolemi võti viitab.</span><span class="sxs-lookup"><span data-stu-id="9c26e-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="9c26e-129">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Seosed**.</span><span class="sxs-lookup"><span data-stu-id="9c26e-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="9c26e-130">Valige **Uus seos**.</span><span class="sxs-lookup"><span data-stu-id="9c26e-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="9c26e-131">Sisestage paanil **Uus seos** järgmised andmed.</span><span class="sxs-lookup"><span data-stu-id="9c26e-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Uus tühjade sisestusväljadega seosepoolne paan.":::

   - <span data-ttu-id="9c26e-133">**Seose nimi**: nimi, mis kajastab seose eesmärki.</span><span class="sxs-lookup"><span data-stu-id="9c26e-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="9c26e-134">Näide: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="9c26e-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="9c26e-135">**Kirjeldus**: seose kirjeldus.</span><span class="sxs-lookup"><span data-stu-id="9c26e-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="9c26e-136">**Lähteolem**: olem, mida kasutatakse seoses lähteolemina.</span><span class="sxs-lookup"><span data-stu-id="9c26e-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="9c26e-137">Näide: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="9c26e-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="9c26e-138">**Sihtolem**: olem, mida kasutatakse seoses sihtolemina.</span><span class="sxs-lookup"><span data-stu-id="9c26e-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="9c26e-139">Näide: klient.</span><span class="sxs-lookup"><span data-stu-id="9c26e-139">Example: Customer.</span></span>
   - <span data-ttu-id="9c26e-140">**Allika kardinaalsus**: lähteallika kardinaalsuse määratlemiseks.</span><span class="sxs-lookup"><span data-stu-id="9c26e-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="9c26e-141">Kardiaalsus kirjeldab määratud elemendi võimalike elementide arvu.</span><span class="sxs-lookup"><span data-stu-id="9c26e-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="9c26e-142">See on alati seotud sihtkardiaalsusega.</span><span class="sxs-lookup"><span data-stu-id="9c26e-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="9c26e-143">Saate valida **ühe** ja **mitme**.</span><span class="sxs-lookup"><span data-stu-id="9c26e-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="9c26e-144">Toetatakse vaid mitu-ühele ja üks-ühele seoseid.</span><span class="sxs-lookup"><span data-stu-id="9c26e-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="9c26e-145">Mitu-ühele: mitu lähtekirjet võivad olla seotud ühe sihtkirjega.</span><span class="sxs-lookup"><span data-stu-id="9c26e-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="9c26e-146">Näide: üksiku kliendi mitu tugiteenusejuhtumeid.</span><span class="sxs-lookup"><span data-stu-id="9c26e-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="9c26e-147">Üks-ühele: üks lähtekirje on seotud ühe sihtkirjega.</span><span class="sxs-lookup"><span data-stu-id="9c26e-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="9c26e-148">Näide: üks püsikliendi ID ühele kliendile.</span><span class="sxs-lookup"><span data-stu-id="9c26e-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="9c26e-149">Mitu-mitmele seoseid saab luua kahe mitu-ühele seose ning linkiva olemi abil, mis seob lähte- ja sihtolemi.</span><span class="sxs-lookup"><span data-stu-id="9c26e-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="9c26e-150">**Sihtkardinaalsus**: valige sihtolemi kirjete kardinaalsus.</span><span class="sxs-lookup"><span data-stu-id="9c26e-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="9c26e-151">**Lähtevõtme väli**: lähteolemi võõrvõtme väli.</span><span class="sxs-lookup"><span data-stu-id="9c26e-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="9c26e-152">Näide: SupportCase võib kasutada CaseID-d võõrvõtme väljana.</span><span class="sxs-lookup"><span data-stu-id="9c26e-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="9c26e-153">**Sihtvõtme väli**: sihtolemi võtme väli.</span><span class="sxs-lookup"><span data-stu-id="9c26e-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="9c26e-154">Näiteks võib klient kasutada võtmevälja **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="9c26e-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="9c26e-155">Kohandatud seose loomiseks valige **Salvesta**.</span><span class="sxs-lookup"><span data-stu-id="9c26e-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="9c26e-156">Kuva seosed</span><span class="sxs-lookup"><span data-stu-id="9c26e-156">View relationships</span></span>

<span data-ttu-id="9c26e-157">Lehel Seosed kuvatakse kõik loodud seosed.</span><span class="sxs-lookup"><span data-stu-id="9c26e-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="9c26e-158">Iga rida tähistab suhet, mis sisaldab ka üksikasju lähte-, sihtüksuse ja kardinaalsuse kohta.</span><span class="sxs-lookup"><span data-stu-id="9c26e-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Seoste ja suvandite loend lehe Seosed toiminguribal.":::

<span data-ttu-id="9c26e-160">Sellel lehel on olemasolevate ja uute seoste suvandid.</span><span class="sxs-lookup"><span data-stu-id="9c26e-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="9c26e-161">**Uus seos**: [kohandatud seose loomine](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="9c26e-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="9c26e-162">**Visualiseerija**: [tutvuge seose visualiseerijaga](#explore-the-relationship-visualizer), et näha olemasolevate seoste võrgudiagrammi ja nende kardiaalsust.</span><span class="sxs-lookup"><span data-stu-id="9c26e-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="9c26e-163">**Filtreerimisalus**: valige loendis kuvamisseoste tüüp.</span><span class="sxs-lookup"><span data-stu-id="9c26e-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="9c26e-164">**Otsinguseosed**: kasutage tekstipõhist otsingut seoste atribuutide põhjal.</span><span class="sxs-lookup"><span data-stu-id="9c26e-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="9c26e-165">Tutvuge seose visualiseerijaga</span><span class="sxs-lookup"><span data-stu-id="9c26e-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="9c26e-166">Seose visualiseerija näitab ühendatud üksuste vaheliste olemasolevate suhete ja nende kardinaalsuse skeemi.</span><span class="sxs-lookup"><span data-stu-id="9c26e-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="9c26e-167">Vaate kohandamiseks saate muuta kastide asukohta, lohistades neid lõuendil.</span><span class="sxs-lookup"><span data-stu-id="9c26e-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Kuvatõmmis seose visualiseerija võrgudiagrammist, mis on seotud olemite vaheliste ühendustega.":::

<span data-ttu-id="9c26e-169">Saadaolevad suvandid:</span><span class="sxs-lookup"><span data-stu-id="9c26e-169">Available options:</span></span> 
- <span data-ttu-id="9c26e-170">**Ekspordi pildina**: praeguse vaate salvestamine pildifailina.</span><span class="sxs-lookup"><span data-stu-id="9c26e-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="9c26e-171">**Muuda horisontaal-/vertikaalseks paigutuseks**: muutke olemite ja seoste joondust.</span><span class="sxs-lookup"><span data-stu-id="9c26e-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="9c26e-172">**Redigeeri**: redigeerige kohandatud seoste atribuute redigeerimispaanil ja salvestage muudatused.</span><span class="sxs-lookup"><span data-stu-id="9c26e-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="9c26e-173">Olemasolevate seoste haldamine</span><span class="sxs-lookup"><span data-stu-id="9c26e-173">Manage existing relationships</span></span> 

<span data-ttu-id="9c26e-174">Lehel Seosed tähistab iga seost rida.</span><span class="sxs-lookup"><span data-stu-id="9c26e-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="9c26e-175">Valige seos ja üks järgmistest suvanditest:</span><span class="sxs-lookup"><span data-stu-id="9c26e-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="9c26e-176">**Redigeeri**: redigeerige kohandatud seoste atribuute redigeerimispaanil ja salvestage muudatused.</span><span class="sxs-lookup"><span data-stu-id="9c26e-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="9c26e-177">**Kustutamine**: kohandatud seoste kustutamine.</span><span class="sxs-lookup"><span data-stu-id="9c26e-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="9c26e-178">**Kuvamine**: saate vaadata süsteemi loodud ja päritud seoseid.</span><span class="sxs-lookup"><span data-stu-id="9c26e-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="9c26e-179">Järgmine etapp</span><span class="sxs-lookup"><span data-stu-id="9c26e-179">Next step</span></span>

<span data-ttu-id="9c26e-180">Süsteemi ja kohandatud seoseid kasutatakse [segmentide loomiseks](segments.md) vastavalt mitte enam eraldatud mitmele andmeallikale.</span><span class="sxs-lookup"><span data-stu-id="9c26e-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
