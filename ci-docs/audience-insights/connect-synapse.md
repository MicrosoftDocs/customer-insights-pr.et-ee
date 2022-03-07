---
title: Andmete nesting alates Azure Synapse Analytics
description: Andmebaasi Azure Synapse kasutamine andmeallikas Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356043"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Azure Synapse andmeallikas ühendamine (eelvaade)

Azure Synapse Analytics on ettevõtte analüüsiteenus, mis kiirendab aega andmeladude ja suurandmete süsteemide ülevaate saamiseks. Azure Synapse Analytics koondab parimad SQL-tehnoloogiad, mida kasutatakse ettevõtte andmehoidlates, Suurandmete jaoks kasutatavad Spark-tehnoloogiad, logi- ja ajasarjade analüüsi data explorer, andmete integreerimise torujuhtmed ja ETL/ELT ning sügav integratsioon teiste Azure'i teenustega, nagu Power BI, Cosmos DB ja AzureML.

Lisateavet leiate teemast [Azure Synapse Ülevaade](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>eeltingimused

Ühenduse konfigureerimiseks Customer Insights rakendusest Azure Synapse -i peavad olema täidetud järgmised eeltingimused.

> [!IMPORTANT]
> Seadke kindlasti kõik **rollimäärangud** vastavalt kirjeldatusele.  

## <a name="prerequisites-in-customer-insights"></a>Eeltingimused Customer Insights -is

* Teil on **customer Insightsis administraatori** roll. Lisateave [kasutajaõiguste kohta sihtrühma ülevaadetes](permissions.md#assign-roles-and-permissions).

Azure -is: 

- Töötav Azure -i tellimus.

- Kui kasutate uut Azure Data Lake Storage Gen2 kontot, *vajab publiku ülevaadete teenusejuht* **salvestusruumi bloobiandmete kaasautori** õigusi. Lugege vaatajaskonna ülevaate [saamiseks lisateavet teenusedirektoriga ühenduse loomise Azure Data Lake Storage kohta](connect-service-principal.md). Data Lake Storage Gen2 **peab olema** [hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace) lubatud.

- Ressursirühmas, Azure Synapse kus tööruum asub, *teenise esindatavas* ja *publiku ülevaate kasutaja* peab olema määratud vähemalt **Lugeja** õigused. Lisateavet leiate teemast [Azure'i rollide määramine Azure'i portaali abil](/azure/role-based-access-control/role-assignments-portal).

- *Kasutaja* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol, kus andmed asuvad ja on lingitud tööruumiga Azure Synapse . Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse identiteeti haldav tööruum](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol kus asuvad andmed, mis on lingitud Azure Synapse tööruumiga. Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse tööruumis *vaatajaskonna ülevaate teenusejuht* vajab **sünapsiadministraatori** rolli määramist. Lisateavet leiate teemast [Sünapsi tööruumi juurdepääsujuhtelemendiüles seadmine](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Ühendus andmejärve andmebaasidega Azure Synapse Analytics

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige **Azure Synapse Analytics (eelvaade)** meetod.

1. Sisestage andmeallikale **Nimi** ja valige andmeallika loomiseks nupp **Edasi**. 

1. [Valige saadaoleva ühenduse](connections.md)Azure Synapse Analytics või looge uus ühendus.

1. **Valige valitud** ühendusega ühendatud tööruumist järveandmebaas Azure Synapse Analytics ja valige **Edasi**.

1. Valige olemid, mida ühendatud andmebaasist neelata. 

1. Soovi korral valige andmeolemid, mis lubavad andmete profileerimist. 

1. Valiku **rakendamiseks ja vastloodud andmeallikas andmete allaneelamise alustamiseks valige Salvesta**, mis on lingitud tabelitega Lake andmebaasi Azure Synapse Analytics tabelitega.
