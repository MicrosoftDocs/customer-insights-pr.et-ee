---
title: Azure Synapse andmeallikas ühendamine (eelvaade)
description: Azure Synapse Andmebaasi kasutamine rakenduses andmeallikas rakenduses andmeallikas Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c4ae65613a02df38a30f907dae72d413bf1a702f
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052694"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Azure Synapse Analytics andmeallikas ühendamine (eelvaade)

Azure Synapse Analytics on ettevõtte analüüsiteenus, mis kiirendab aega andmeladude ja suurandmete süsteemide ülevaateks. Azure Synapse Analytics koondab parimad SQL-tehnoloogiad, mida kasutatakse ettevõtte andmete ladustamisel, suurandmete jaoks kasutatavatest Spark-tehnoloogiatest, Logi- ja aegridade analüüsi andmeuurijatest, andmete integreerimise torujuhtmetest ja ETL/ELT-st ning sügavast integratsioonist teiste Azure'i teenustega, nagu Power BI, Cosmos DB ja AzureML.

Lisateavet leiate teemast [Azure Synapse Ülevaade](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>eeltingimused

> [!IMPORTANT]
> Seadke kindlasti kõik **rollimäärangud** vastavalt kirjeldatusele.  

**Customer Insightsis** tehke järgmist.

* Teil on **Customer Insightsis administraatori** roll. Lisateavet kasutajaõiguste kohta [leiate teemast Customer Insights](permissions.md#assign-roles-and-permissions).

**In Azure**:

- Töötav Azure -i tellimus.

- Kui kasutate uut Azure Data Lake Storage Gen2 kontot, *vajab* Customer Insightsi **teenusedirektor storage blob data contributori** õigusi. Lugege lisateavet Customer Insightsi [teenindusdirektoriga ühenduse loomise Azure Data Lake Storage kohta](connect-service-principal.md). Data Lake Storage Gen2 **peab olema** [hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace) lubatud.

- Ressursirühmas, kus Azure Synapse tööruum asub, *tuleb Customer Insightsi* hooldusdirektorile *ja* kasutajale määrata vähemalt **Readeri** õigused. Lisateavet leiate teemast [Azure'i rollide määramine Azure'i portaali abil](/azure/role-based-access-control/role-assignments-portal).

- *Kasutaja* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol, kus andmed asuvad ja on lingitud tööruumiga Azure Synapse . Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse identiteeti haldav tööruum](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol kus asuvad andmed, mis on lingitud Azure Synapse tööruumiga. Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Tööruumis Azure Synapse vajab *Customer Insightsi* teenusedirektor Määratud Synapse'i administraatori **rolli.** Lisateavet leiate teemast [Sünapsi tööruumi juurdepääsujuhtelemendiüles seadmine](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Andmejärve andmebaasiga ühenduse loomine rakenduses Azure Synapse Analytics

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. **Azure Synapse Analytics Valige meetod (Eelvaade).**

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Dialoogiboks Synapse Analyticsi andmetega ühenduse loomiseks":::
  
1. **Sisestage andmeallikas nimi** ja valikuline **kirjeldus**.

1. Valige saadavalolev [ühendus](connections.md)Azure Synapse Analytics või looge uus ühendus.

1. **Valige valitud** ühenduses ühendatud tööruumist andmebaas Azure Synapse Analytics ja valige **Edasi**. Praegu toetame ainult andmebaasi tüüpi *Lake andmebaasi*.

1. Valige ühendatud andmebaasist allaneelatavad olemid ja valige **Edasi**.

1. Soovi korral valige andmeolemid, et lubada andmete profileerimist.

1. Valige **Salvesta**, et rakendada oma valik ja alustada äsja loodud andmeallikas andmete allaneelamist rakenduses Lake andmebaasi tabelitega Azure Synapse Analytics lingitud andmeallikas lingitud. Avaneb **andmeallikate** leht, kus kuvatakse uus andmeallikas olekus **Värskendamine**.
