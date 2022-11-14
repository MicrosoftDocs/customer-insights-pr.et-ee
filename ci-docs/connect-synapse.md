---
title: Andmeallikas ühendamine Azure Synapse (eelvaade)
description: Andmebaasi Azure Synapse kasutamine andmeallikas in Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738151"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Andmeallikas ühendamine Azure Synapse Analytics (eelvaade)

Azure Synapse Analytics on ettevõtte analüütikateenus, mis kiirendab andmeladude ja suurandmesüsteemide ülevaadete tegemise aega. Azure Synapse Analytics koondab parimad SQL-tehnoloogiad, mida kasutatakse ettevõtte andmete ladustamisel, suurandmete jaoks kasutatavaid Sparki tehnoloogiaid, logi- ja aegridade analüüsiks mõeldud Data Explorerit, andmete integreerimiseks mõeldud torujuhtmeid ja ETL/ELT-d ning sügavat integratsiooni teiste Azure’i teenustega, näiteks Power BI, Cosmos DB ja AzureML.

Lisateavet leiate teemast [Azure Synapse Ülevaade](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>eeltingimused

> [!NOTE]
> Synapse tööruume, mille tulemüür on [lubatud](/azure/synapse-analytics/security/synapse-workspace-ip-firewall), praegu ei toetata.
> [!IMPORTANT]
> Seadke kindlasti kõik **rollimäärangud** vastavalt kirjeldatusele.  

**Jaotises Customer Insights** tehke järgmist.

* Teil on **Customer Insightsis administraatori** roll. Lisateavet kasutajaõiguste kohta [leiate jaotisest Customer Insights](permissions.md#add-users).

**Azure’is**:

- Töötav Azure -i tellimus.

- Kui kasutate uut Azure Data Lake Storage Gen2 kontot, vajab *Customer Insightsi* teenusejuht, **milleks on "Dynamics 365 AI for Customer Insights", salvestusruumi bloobiandmete kaasautori** õigusi. Lugege lisateavet Customer Insightsi [teenusedirektoriga Azure Data Lake Storage ühenduse loomise kohta](connect-service-principal.md). Data Lake Storage Gen2 **peab olema** [hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace) lubatud.

- Ressursigrupis asub tööruum, Azure Synapse teenusejuhile *·*(Dynamics 365 AI for Customer Insights) ja *Customer Insightsi* kasutajale tuleb määrata vähemalt **Readeri** õigused. Lisateavet leiate teemast [Azure'i rollide määramine Azure'i portaali abil](/azure/role-based-access-control/role-assignments-portal).

- *Kasutaja* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol, kus andmed asuvad ja on lingitud tööruumiga Azure Synapse . Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse identiteeti haldav tööruum](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol kus asuvad andmed, mis on lingitud Azure Synapse tööruumiga. Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Tööruumis Azure Synapse *vajab* Customer Insightsi **teenindusdirektor, milleks on "Dynamics 365 AI for Customer Insights", Synapse’i administraatori** rolli määramist. **Kasutajal** on vaja vähemalt **tööruumile määratud Synapse’i kaasautori** rolli. Lisateavet leiate teemast [Sünapsi tööruumi juurdepääsujuhtelemendiüles seadmine](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Kui teie Customer Insightsi keskkond salvestab andmed teie [enda sisse Azure Data Lake Storage](own-data-lake-storage.md), vajab kasutaja, kes loob ühenduse vastavalt vajadusele Azure Synapse Analytics, vähemalt sisseehitatud **lugejarolli** Data Lake Storage’i kontol. Lisateavet leiate teemast [Azure'i rollide määramine Azure'i portaali abil](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Ühenduse loomine andmejärvede andmebaasiga Azure Synapse Analytics

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige **Azure Synapse Analytics (Eelvaade)** meetod.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialoogiboks Synapse Analyticsi andmetega ühenduse loomiseks":::
  
1. Sisestage **andmeallikas nimi** ja valikuline **kirjeldus**.

1. Valige [saadaolev](connections.md) ühendus Azure Synapse Analytics või [looge uus](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. Valige valitud ühenduses ühendatud tööruumist andmebaas **ja** valige Azure Synapse Analytics Edasi **.** Praegu toetame ainult andmebaasi tüüpi *Lake’i andmebaasi*.

1. Valige ühendatud andmebaasist allaneelatavad olemid ja valige **Edasi**.

1. Soovi korral valige andmeüksused, milles andmete profileerimine lubatakse.

1. Valige **Salvesta**, et rakendada oma valik ja alustada andmete allaneelamist vastloodud andmeallikas, mis on lingitud Lake’i andmebaasi tabelitega jaotises Azure Synapse Analytics. Avaneb **leht Andmeallikad**, kus kuvatakse uus andmeallikas olekus **Värskendamine**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Andmete laadimine võib võtta aega. Pärast edukat värskendamist saab allaneelatud andmed lehel Olemid [**üle vaadata**](entities.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
