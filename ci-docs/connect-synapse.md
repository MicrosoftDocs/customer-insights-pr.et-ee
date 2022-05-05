---
title: Neelavad andmed alates Azure Synapse Analytics
description: Azure Synapse Andmebaasi kasutamine rakenduses andmeallikas rakenduses andmeallikas Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642654"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse andmeallikas ühendamine (eelvaade)

Azure Synapse Analytics on ettevõtte analüüsiteenus, mis kiirendab aega andmeladude ja suurandmete süsteemide ülevaateks. Azure Synapse Analytics koondab parimad SQL-tehnoloogiad, mida kasutatakse ettevõtte andmete ladustamisel, suurandmete jaoks kasutatavatest Spark-tehnoloogiatest, Logi- ja aegridade analüüsi andmeuurijatest, andmete integreerimise torujuhtmetest ja ETL/ELT-st ning sügavast integratsioonist teiste Azure'i teenustega, nagu Power BI, Cosmos DB ja AzureML.

Lisateavet leiate teemast [Azure Synapse Ülevaade](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>eeltingimused

Ühenduse konfigureerimiseks rakendusest Dynamics 365 Customer Insights rakendusse Azure Synapse peab olema täidetud järgmised eeltingimused.

> [!IMPORTANT]
> Seadke kindlasti kõik **rollimäärangud** vastavalt kirjeldatusele.  

## <a name="prerequisites-in-customer-insights"></a>Eeltingimused Customer Insights -is

* Teil on **Customer Insightsis administraatori** roll. Lisateavet kasutajaõiguste kohta [leiate teemast Customer Insights](permissions.md#assign-roles-and-permissions).

Azure -is: 

- Töötav Azure -i tellimus.

- Kui kasutate uut Azure Data Lake Storage Gen2 kontot, *vajab* Customer Insightsi **teenusedirektor storage blob data contributori** õigusi. Lugege lisateavet Customer Insightsi [teenindusdirektoriga ühenduse loomise Azure Data Lake Storage kohta](connect-service-principal.md). Data Lake Storage Gen2 **peab olema** [hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace) lubatud.

- Ressursirühmas, kus Azure Synapse tööruum asub, *tuleb Customer Insightsi* hooldusdirektorile *ja* kasutajale määrata vähemalt **Readeri** õigused. Lisateavet leiate teemast [Azure'i rollide määramine Azure'i portaali abil](/azure/role-based-access-control/role-assignments-portal).

- *Kasutaja* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol, kus andmed asuvad ja on lingitud tööruumiga Azure Synapse . Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse identiteeti haldav tööruum](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol kus asuvad andmed, mis on lingitud Azure Synapse tööruumiga. Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Tööruumis Azure Synapse vajab *Customer Insightsi* teenusedirektor Määratud Synapse'i administraatori **rolli.** Lisateavet leiate teemast [Sünapsi tööruumi juurdepääsujuhtelemendiüles seadmine](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Andmejärve andmebaasidega ühenduse loomine rakenduses Azure Synapse Analytics

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. **Azure Synapse Analytics Valige meetod (Eelvaade).**

1. Sisestage andmeallikale **Nimi** ja valige andmeallika loomiseks nupp **Edasi**. 

1. Valige saadavalolev [ühendus](connections.md)Azure Synapse Analytics või looge uus ühendus.

1. **Valige valitud** ühendusega ühendatud tööruumist järveandmebaas Azure Synapse Analytics ja valige **Edasi**.

1. Valige ühendatud andmebaasist allaneelatavad olemid. 

1. Soovi korral valige andmeolemid, et lubada andmete profileerimist. 

1. Valige **Salvesta**, et rakendada oma valik ja alustada äsja loodud andmeallikas andmete allaneelamist rakenduses Lake andmebaasi tabelitega Azure Synapse Analytics lingitud andmeallikas lingitud.
