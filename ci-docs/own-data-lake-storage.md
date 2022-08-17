---
title: Kasutage oma Azure Data Lake Storage Gen2 kontot
author: mukeshpo
description: Siit leiate teavet nõuete kohta, mille kohaselt tuleb Customer Insightsi andmete salvestamiseks kasutada oma Azure Data Lake Storage kontot.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: d2ff49c324c5c5c28213f362ff330d441fcb6052
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246196"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Kasutage oma Azure Data Lake Storage Gen2 kontot

Dynamics 365 Customer Insights annab teile võimaluse salvestada kõik oma andmed Gen2-sse [Azure Data Lake Storage](/azure/storage/blobs/data-lake-storage-introduction).

Andmete salvestamisega Data Lake’i salvestusruumi nõustute, et andmed edastatakse selle Azure’i salvestuskonto jaoks sobivasse geograafilisse asukohta ja salvestatakse seal. Lisateavet leiate teemast [Microsofti usalduskeskus](https://www.microsoft.com/trust-center).

Customer Insightsi administraatorid saavad [luua keskkondi](create-environment.md) ja [määrata protsessis andmesalvestussuvandi](create-environment.md#step-2-configure-data-storage).

## <a name="prerequisites-to-use-your-storage-account"></a>Salvestusruumikonto kasutamise eeltingimused

- Azure Data Lake Storage kontod peavad asuma samas Azure’i piirkonnas, mille valisite Customer Insightsi keskkonna loomisel. Saate vaadata Customer Insightsi keskkonna piirkonda jaotises **Haldussüsteemi** > **teave** > **·**.
- Data Lake’i salvestusruum peab olema Gen2 ja lubatud [peab](/azure/storage/blobs/create-data-lake-storage-account) olema hierarhiline nimeruum. Gen1 salvestusruumi kontosid ei toetata.
- Hoiukontol peab olema konteiner nimega`customerinsights`. Peate selle looma enne, kui kasutate Customer Insightsis oma Data Lake’i salvestusruumi. Customer Insightsi keskkonda häälestav administraator vajab salvestusruumikontol või konteineris rolli Salvestusruumi bloobiandmete esitaja või `customerinsights` salvestusruumi bloobi andmete omanik. Lisateavet salvestusruumikontole õiguse määramise kohta leiate teemast [Salvestusruumikonto](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) loomine.

## <a name="connect-customer-insights-with-your-storage-account"></a>Customer Insightsi ühendamine salvestusruumikontoga

Uue keskkonna loomisel veenduge, et Data Lake’i salvestusruumi konto on olemas ja kõik eeltingimused on täidetud.

1. **Seadke keskkonna loomise** ajal andmete salvestamise **etapis suvandi Salvesta väljundandmed** väärtuseks **Azure Data Lake Storage Gen2**.
1. Valige, **kuidas salvestusruumi** ühendada. Autentimiseks saate valida ressursipõhise ja tellimuspõhise valiku vahel. Lisateavet vaadake jaotisest [Kontoga ühenduse Azure Data Lake Storage loomine Azure’i hooldusjuhi](connect-service-principal.md) kaudu.
   - Azure’i tellimuse puhul **valige ümbrist** sisaldav **tellimus** **, ressursirühm** ja **salvestusruumikonto.**`customerinsights`
   - Kontovõtme jaoks **sisestage** Data Lake’i salvestusruumi konto nimi **ja** kontovõti **.** Selle autentimismeetodi kasutamine tähendab, et teid teavitatakse, kui teie organisatsioon võtmeid pöörab. Peate keskkonna konfiguratsiooni [värskendama](manage-environments.md#edit-an-existing-environment) uue võtmega, kui seda pööratakse.
1. Valige, kas soovite kasutada Azure Private Linki, et luua ühendus salvestusruumikontoga ja [luua ühendus Private Linkiga](security-overview.md#set-up-an-azure-private-link) kaheastmelise protsessi abil.

Kui süsteemi protsessid, nagu andmete allaneelamine, on lõpule viidud, loob süsteem salvestuskontole vastavad kaustad. Andmefailid ja *model.json* failid luuakse ning lisatakse kaustadesse protsessi nime põhjal.

Kui loote Customer Insights'i mitu keskkonda ja salvestate nendest keskkondadest väljundolemid oma salvestuskontole, loob Customer Insights iga keskkonna jaoks eraldi kaustad, mille konteineris on `ci_environmentID`.
