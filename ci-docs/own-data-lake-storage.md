---
title: Kasutage oma Azure Data Lake Storage Gen2 kontot
author: mukeshpo
description: Siit leiate teavet nõuete kohta, mille kohaselt tuleb Customer Insightsi andmete salvestamiseks kasutada oma Azure Data Lake Storage kontot.
ms.author: mukeshpo
ms.date: 08/15/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5e4b9348f06d4e5e10b4499ad86b38c9d52da1f5
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304376"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Kasutage oma Azure Data Lake Storage Gen2 kontot

Dynamics 365 Customer Insights annab teile võimaluse salvestada kõik oma andmed Gen2-sse [Azure Data Lake Storage](/azure/storage/blobs/data-lake-storage-introduction). Andmete salvestamisega Data Lake’i salvestusruumi nõustute, et andmed edastatakse selle Azure’i salvestuskonto jaoks sobivasse geograafilisse asukohta ja salvestatakse seal. Lisateavet leiate teemast [Microsofti usalduskeskus](https://www.microsoft.com/trust-center).

Customer Insightsi administraatorid saavad [luua keskkondi](create-environment.md) ja [määrata protsessis andmesalvestussuvandi](create-environment.md#step-2-configure-data-storage).

## <a name="prerequisites"></a>eeltingimused

- Azure Data Lake Storage kontod peavad asuma samas Azure’i piirkonnas, mille valisite Customer Insightsi keskkonna loomisel. Keskkonna piirkonna tundmaõppimiseks **avage Customer Insightsis jaotis Haldussüsteemi** > **·** > **teave**.
- Data Lake’i salvestusruumi konto peab olema Gen2. Azure Data Lake Gen1 salvestusruumi kontosid ei toetata.
- Data Lake’i salvestusruumi kontol peab [olema lubatud](/azure/storage/blobs/data-lake-storage-namespace) hierarhiline nimeruum.
- Hoiukontol peab olema konteiner nimega`customerinsights`. Looge see enne, kui kasutate Customer Insightsis oma Data Lake’i salvestusruumi.
- Customer Insightsi keskkonda häälestav administraator vajab salvestusruumikontol või konteineris rolli Salvestusruumi bloobiandmete esitaja või `customerinsights` salvestusruumi bloobi andmete omanik. Lisateavet salvestusruumikontole õiguse määramise kohta leiate teemast [Salvestusruumikonto](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal) loomine.

## <a name="connect-customer-insights-with-your-storage-account"></a>Customer Insightsi ühendamine salvestusruumikontoga

Uue keskkonna loomisel veenduge, et Data Lake’i salvestusruumi konto on olemas ja kõik eeltingimused on täidetud.

1. **Seadke keskkonna loomise** ajal andmete salvestamise **etapis suvandi Salvesta väljundandmed** väärtuseks **Azure Data Lake Storage Gen2**.
1. Valige, **kuidas salvestusruumi** ühendada. Autentimiseks saate valida ressursipõhise ja tellimuspõhise valiku vahel. Lisateavet vaadake jaotisest [Kontoga ühenduse Azure Data Lake Storage loomine Azure’i hooldusjuhi](connect-service-principal.md) kaudu.
   - Azure’i tellimuse puhul **valige ümbrist** sisaldav **tellimus** **, ressursirühm** ja **salvestusruumikonto.**`customerinsights`
   - Kontovõtme jaoks **sisestage** Data Lake’i salvestusruumi konto nimi **ja** kontovõti **.** Selle autentimismeetodi kasutamine tähendab, et teid teavitatakse, kui teie organisatsioon võtmeid pöörab. Peate keskkonna konfiguratsiooni [värskendama](manage-environments.md#edit-an-existing-environment) uue võtmega, kui seda pööratakse.
1. Valige, kas soovite kasutada Azure Private Linki, et luua ühendus salvestusruumikontoga ja [luua ühendus private linkiga](security-overview.md#set-up-an-azure-private-link).

Kui süsteemi protsessid, nagu andmete allaneelamine, on lõpule viidud, loob süsteem salvestuskontole vastavad kaustad. Andmefailid ja model.json-failid luuakse ning lisatakse kaustadesse protsessi nime põhjal.

Kui loote Customer Insights'i mitu keskkonda ja salvestate nendest keskkondadest väljundolemid oma salvestuskontole, loob Customer Insights iga keskkonna jaoks eraldi kaustad, mille konteineris on `ci_environmentID`.
