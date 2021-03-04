---
title: Seosed olemite ja olemiteede vahel
description: Looge ja hallake mitmest andmeallikast pärit olemite vahelisi seoseid.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269868"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="1c082-103">Olemitevaheline seos</span><span class="sxs-lookup"><span data-stu-id="1c082-103">Relationships between entities</span></span>

<span data-ttu-id="1c082-104">Seosed aitavad ühendada olemeid ja luua andmetest graafik, mil olemid jagavad ühist tunnust (võõrvõti), mida saab viita ühest olemist teise.</span><span class="sxs-lookup"><span data-stu-id="1c082-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="1c082-105">Ühendatud olemid võimaldavad määratleda segmente ja mõõte mitmete andmeallikate alusel.</span><span class="sxs-lookup"><span data-stu-id="1c082-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="1c082-106">Seoseid on kahte tüüpi:</span><span class="sxs-lookup"><span data-stu-id="1c082-106">There are two types of relationships.</span></span> <span data-ttu-id="1c082-107">Kasutajate loodud ja seadistatud mittemuudetavad süsteemi seosed, mis tekivad ise, ning kohandatud seosed.</span><span class="sxs-lookup"><span data-stu-id="1c082-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="1c082-108">Süsteemi seosed luuakse vastendamise ja liitmise ajal taustal vastavalt intelligentsele vastendamisele.</span><span class="sxs-lookup"><span data-stu-id="1c082-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="1c082-109">Need seosed aitavad seostada kliendiprofiili kirjeid teiste vastavate olemite kirjetega.</span><span class="sxs-lookup"><span data-stu-id="1c082-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="1c082-110">Järgmisel diagrammil kirjeldatakse kolme süsteemi seose loomist, kui kliendiolemit vastendatakse täiendavate olemitega, et luua lõplik kliendiprofiili olem.</span><span class="sxs-lookup"><span data-stu-id="1c082-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1c082-111">![Seose loomine](media/relationships-entities-merge.png "Seose loomine")</span><span class="sxs-lookup"><span data-stu-id="1c082-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="1c082-112">***CustomerToContact* seos** loodi kliendi olemi ja kontakti olemi vahel.</span><span class="sxs-lookup"><span data-stu-id="1c082-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="1c082-113">Kliendi olem saab võtme välja **Contact_contactId**, et olla seotud kontakti olemi võtme väljaga **contactId**.</span><span class="sxs-lookup"><span data-stu-id="1c082-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="1c082-114">***CustomerToAccount* seos** loodi kliendi olemi ja konto olemi vahel.</span><span class="sxs-lookup"><span data-stu-id="1c082-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="1c082-115">Kliendi olem saab võtme välja **Account_accountId**, et olla seotud konto olemi võtme väljaga **accountId**.</span><span class="sxs-lookup"><span data-stu-id="1c082-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="1c082-116">***CustomerToWebAccount* seos** loodi kliendi olemi ja veebikonto olemi vahel.</span><span class="sxs-lookup"><span data-stu-id="1c082-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="1c082-117">Kliendi olem saab võtme välja **WebAccount_webaccountId**, et olla seotud veebikonto olemi võtme väljaga **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="1c082-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="1c082-118">Seose loomine</span><span class="sxs-lookup"><span data-stu-id="1c082-118">Create a relationship</span></span>

<span data-ttu-id="1c082-119">Määratlege kohandatud seoseid lehel **Seosed**.</span><span class="sxs-lookup"><span data-stu-id="1c082-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="1c082-120">Iga seos koosneb lähteolemist (võõrvõtit sisaldav olem) ja sihtolemist (olem, millele suunab lähteolemi võõrvõti).</span><span class="sxs-lookup"><span data-stu-id="1c082-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="1c082-121">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Seosed**.</span><span class="sxs-lookup"><span data-stu-id="1c082-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="1c082-122">Valige **Uus seos**.</span><span class="sxs-lookup"><span data-stu-id="1c082-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="1c082-123">Sisestage paanil **Lisa seos** järgmised andmed.</span><span class="sxs-lookup"><span data-stu-id="1c082-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1c082-124">![Sisestage seose üksikasjad](media/relationships-add.png "Sisestage seose üksikasjad")</span><span class="sxs-lookup"><span data-stu-id="1c082-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="1c082-125">**Seose nimi**: seose eesmärki kirjeldav nimi (näiteks **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="1c082-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="1c082-126">**Kirjeldus**: seose kirjeldus.</span><span class="sxs-lookup"><span data-stu-id="1c082-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="1c082-127">**Lähteolem**: valige olem, mida kasutatakse seose allikana (näiteks WebLog).</span><span class="sxs-lookup"><span data-stu-id="1c082-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="1c082-128">**Kardinaalsus**: valige lähteolemi kirjete kardinaalsus.</span><span class="sxs-lookup"><span data-stu-id="1c082-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="1c082-129">Näiteks „mitu“ tähendab, et mitu Weblogi kirjet on seotud ühe WebAccountiga.</span><span class="sxs-lookup"><span data-stu-id="1c082-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="1c082-130">**Lähtevõtme väli**: see tähistab lähteolemi võõrvõtme välja.</span><span class="sxs-lookup"><span data-stu-id="1c082-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="1c082-131">Näiteks WebLogi võõrvõtme väljaks on **accountId**.</span><span class="sxs-lookup"><span data-stu-id="1c082-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="1c082-132">**Sihtolem**: valige olem, mida kasutatakse seose sihtkohana (näiteks WebAccount).</span><span class="sxs-lookup"><span data-stu-id="1c082-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="1c082-133">**Sihtkardinaalsus**: valige sihtolemi kirjete kardinaalsus.</span><span class="sxs-lookup"><span data-stu-id="1c082-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="1c082-134">Näiteks „üks“ tähendab, et mitu Weblogi kirjet on seotud ühe WebAccountiga.</span><span class="sxs-lookup"><span data-stu-id="1c082-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="1c082-135">**Sihtvõtme väli**: see väli tähistab sihtolemi võtme välja.</span><span class="sxs-lookup"><span data-stu-id="1c082-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="1c082-136">Näiteks WebAccounti võtme väljaks on **accountId**.</span><span class="sxs-lookup"><span data-stu-id="1c082-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="1c082-137">Toetatakse vaid mitu-ühele ja üks-ühele seoseid.</span><span class="sxs-lookup"><span data-stu-id="1c082-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="1c082-138">Mitu-mitmele seoseid saab luua kahe mitu-ühele seosega ja lingi olemiga (tegemist on olemiga, millega ühendatakse omavahel lähteolem ja sihtolem).</span><span class="sxs-lookup"><span data-stu-id="1c082-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="1c082-139">Kustutage seos</span><span class="sxs-lookup"><span data-stu-id="1c082-139">Delete a relationship</span></span>

1. <span data-ttu-id="1c082-140">Avage sihtrühmaülevaadetes jaotis **Andmed** > **Seosed**.</span><span class="sxs-lookup"><span data-stu-id="1c082-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="1c082-141">Valige märkeruutude abil seosed, mille soovite kustutada.</span><span class="sxs-lookup"><span data-stu-id="1c082-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="1c082-142">Valige tabeli **Seosed** algusest **Kustuta**.</span><span class="sxs-lookup"><span data-stu-id="1c082-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="1c082-143">Kinnitage, et soovite kustutada.</span><span class="sxs-lookup"><span data-stu-id="1c082-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="1c082-144">Järgmine etapp</span><span class="sxs-lookup"><span data-stu-id="1c082-144">Next step</span></span>

<span data-ttu-id="1c082-145">Süsteemi ja kohandatud seoseid kasutatakse segmentide loomiseks vastavalt mitte enam eraldatud mitmele andmeallikale.</span><span class="sxs-lookup"><span data-stu-id="1c082-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="1c082-146">Lisateavet vt [Segmendid](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1c082-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]