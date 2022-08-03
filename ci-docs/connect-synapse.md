---
title: Azure Synapse andmeallikas ühendamine (eelvaade)
description: Andmebaasi Azure Synapse kasutamine andmeallikas rakenduses Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 54247fbcdc27f6ed8314e0755164083eb461aa64
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206902"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Azure Synapse Analytics andmeallikas ühendamine (eelvaade)

Azure Synapse Analytics on ettevõtte analüüsiteenus, mis kiirendab andmeladude ja suurandmete süsteemide ülevaadete tegemist. Azure Synapse Analytics ühendab parimad SQL-tehnoloogiad, mida kasutatakse ettevõtte andmelaos, Sparki tehnoloogiad, mida kasutatakse suurandmete jaoks, Data Explorer logi- ja aegridade analüüsiks, torujuhtmed andmete integreerimiseks ja ETL/ELT ning sügav integratsioon teiste Azure'i teenustega, näiteks Power BI, Cosmos DB ja AzureML.

Lisateavet leiate ülevaatest [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>eeltingimused

> [!IMPORTANT]
> Seadke kindlasti kõik **rollimäärangud** vastavalt kirjeldatusele.  

**Customer Insightsis tehke järgmist**.

* Teil on Customer Insightsis administraatori **roll**. Lisateavet kasutajaõiguste kohta [leiate Customer Insightsist](permissions.md#assign-roles-and-permissions).

**Azure'is**:

- Töötav Azure -i tellimus.

- Kui kasutate uut Azure Data Lake Storage Gen2 kontot, *vajab* Customer Insightsi **teenusejuht salvestusruumi bloobi andmete esitaja** õigusi. Lugege lisateavet teenusejuhiga ühenduse loomise [kohta Azure Data Lake Storage Customer Insightsi](connect-service-principal.md) jaoks. Data Lake Storage Gen2 **peab olema** [hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace) lubatud.

- Ressursigrupis, kus Azure Synapse asub tööruum, *tuleb teenusejuhile* ja Customer Insightsi *kasutajale* määrata vähemalt **rakenduse Reader** õigused. Lisateavet leiate teemast [Azure'i rollide määramine Azure'i portaali abil](/azure/role-based-access-control/role-assignments-portal).

- *Kasutaja* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol, kus andmed asuvad ja on lingitud tööruumiga Azure Synapse . Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse identiteeti haldav tööruum](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol kus asuvad andmed, mis on lingitud Azure Synapse tööruumiga. Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Tööruumis Azure Synapse vajab *Customer Insightsi* **teeninduse printsipaal Synapse'i administraatori** rolli määramist. Lisateavet leiate teemast [Sünapsi tööruumi juurdepääsujuhtelemendiüles seadmine](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Andmejärve andmebaasiga ühenduse loomine Azure Synapse Analytics

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige **Azure Synapse Analytics (eelvaade)** meetod.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialoogiboks Synapse Analyticsi andmetega ühenduse loomiseks":::
  
1. **Sisestage andmeallikas nimi** ja valikuline **kirjeldus**.

1. Valige saadaolev [ühendus](connections.md)Azure Synapse Analytics või looge uus.

1. **Valige valitud** ühendusega ühendatud tööruumist andmebaas Azure Synapse Analytics ja valige **Edasi**. Praegu toetame ainult andmebaasi tüüpi *järveandmebaasi*.

1. Valige ühendatud andmebaasist allaneelatavad olemid ja valige **Edasi**.

1. Soovi korral valige andmeüksused, milles andmete profileerimist lubada.

1. Valige **Salvesta**, et rakendada oma valik ja alustada andmete allaneelamist vastloodud andmeallikas lingitud järveandmebaasi tabelitega.Azure Synapse Analytics Avaneb **leht Andmeallikad**, kus kuvatakse uus andmeallikas olekus **Värskendamine**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Andmete laadimine võib võtta aega. Pärast edukat värskendamist saab allaneelatud andmeid vaadata lehelt [**Olemid**](entities.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
