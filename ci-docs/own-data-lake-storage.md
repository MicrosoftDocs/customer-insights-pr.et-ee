---
title: Kasuta oma Azure Data Lake Storage Gen2 kontot
author: mukeshpo
description: Siit leiate teavet nõuete kohta, mida peate kasutama oma Azure Data Lake Storage kontot Customer Insightsi andmete talletamiseks.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5acb58906c1a9db54337f3b4dc2ab7891db7954e
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011928"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Kasuta oma Azure Data Lake Storage Gen2 kontot

Dynamics 365 Customer Insights annab teile võimaluse salvestada kõik oma andmed Gen2-s [Azure Data Lake Storage](/azure/storage/blobs/data-lake-storage-introduction).

Andmete salvestamisega Data Lake Storage'i nõustute, et andmed edastatakse ja salvestatakse selle Azure'i salvestusruumikonto jaoks sobivasse geograafilisse asukohta. Lisateavet leiate teemast [Microsofti usalduskeskus](https://www.microsoft.com/trust-center).

Customer Insightsi administraatorid saavad [luua keskkondi](create-environment.md) ja [määrata protsessi andmesalvestussuvandi](create-environment.md#step-2-configure-data-storage).

## <a name="prerequisites-to-use-your-storage-account"></a>Salvestuskonto kasutamise eeltingimused

- Azure Data Lake Storage kontod peavad asuma samas Azure'i piirkonnas, mille valisite Customer Insightsi keskkonna loomisel. Customer Insightsi keskkonna piirkonda saate kontrollida jaotises **Administraatori teave** > **·** > **·**.
- Data Lake Storage peab olema Gen2 ja lubatud [on](/azure/storage/blobs/create-data-lake-storage-account) hierarhiline nimeruum. Gen1 salvestuskontosid ei toetata.
- Nimega konteiner `customerinsights` peab olema salvestuskontol. Enne oma Data Lake Storage'i kasutamist Customer Insightsis peate selle looma. Customer Insightsi keskkonda häälestav administraator vajab salvestusruumikontol või `customerinsights` konteineris rolli Salvestusruumi bloobiandmete kaasautor või salvestusruumi bloobiandmete omanik. Salvestusruumikontole õiguse määramise kohta leiate lisateavet teemast [Salvestusruumikonto](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) loomine.

## <a name="connect-customer-insights-with-your-storage-account"></a>Customer Insightsi ühendamine oma salvestuskontoga

Uue keskkonna loomisel veenduge, et Data Lake Storage'i konto oleks olemas ja kõik eeltingimused oleksid täidetud.

1. Seadke keskkonna loomise ajal olevas **andmesalvestusetapis** väärtusele **Salvesta väljundandmed** väärtusele **Azure Data Lake Storage Gen2**.
1. Valige, kuidas **salvestusruumi** ühendada. Autentimiseks saate valida ressursipõhise suvandi ja tellimusel põhineva suvandi vahel. Lisateavet leiate teemast [Kontoga Azure Data Lake Storage ühenduse loomine Azure'i teenusedirektori](connect-service-principal.md) abil.
   - Azure'i tellimuse puhul **valige konteinerit** **sisaldav tellimus**, **ressursirühm** ja **salvestusruumikonto.**`customerinsights`
   - Kontovõtme puhul **esitage** Data Lake Storage'i konto nimi **ja** kontovõti **·**. Selle autentimismeetodi kasutamine tähendab, et teid teavitatakse sellest, kas teie organisatsioon klahvide pöörleb. Pööramisel peate keskkonnakonfiguratsiooni [värskendama](manage-environments.md#edit-an-existing-environment) uue võtmega.
1. Valige, kas soovite salvestusruumikontoga [ühenduse loomiseks ja kaheastmelise protsessiga eralingiga ühenduse loomiseks kasutada Azure Private Linki](security-overview.md#private-links-tab).

Kui süsteemiprotsessid, nagu andmete allaneelamine, on lõpule viidud, loob süsteem salvestuskontole vastavad kaustad. Andmefailid ja *model.json* failid luuakse ning lisatakse kaustadesse protsessi nime põhjal.

Kui loote Customer Insights'i mitu keskkonda ja salvestate nendest keskkondadest väljundolemid oma salvestuskontole, loob Customer Insights iga keskkonna jaoks eraldi kaustad, mille konteineris on `ci_environmentID`.
