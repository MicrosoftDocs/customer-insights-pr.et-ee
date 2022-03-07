---
title: Customer Insights andmete eksportimine rakendusse Azure Synapse Analytics
description: Vaadake, kuidas konfigureerida ühendus rakendusega Azure Synapse Analytics.
ms.date: 01/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 289c8d545f057b3f70679b485cf4350545c0587b
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231307"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Andmete eksportimine Azure Synapse Analytics (eelvaade)

Azure Synapse on analüüsiteenus, mis kiirendab andmeladude ja suurandmesüsteemide läbivaatava ülevaatamise aega. Customer Insights -i andmeid saate sisse tuua ja kasutada jaotises [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Eeltingimused

Ühenduse konfigureerimiseks Customer Insights rakendusest Azure Synapse -i peavad olema täidetud järgmised eeltingimused.

> [!NOTE]
> Seadke kindlasti kõik **rollimäärangud** vastavalt kirjeldatusele.  

## <a name="prerequisites-in-customer-insights"></a>Eeltingimused Customer Insights -is

* Teil on **Administraatori** roll publiku ülevaadetes. Lisateave [kasutajaõiguste seadmise kohta vaatajaskonna ülevaates](permissions.md#assign-roles-and-permissions)

Azure -is: 

- Töötav Azure -i tellimus.

- Kui kasutate uut Azure Data Lake Storage Gen2 kontot, *vajab publiku ülevaadete teenusejuht* **salvestusruumi bloobiandmete kaasautori** õigusi. Lisateavet vaata [Azure Data Lake Storage -i Gen2 konto ühendamine Azure service -i esindatavaga publiku ülevaadetes](connect-service-principal.md). Data Lake Storage Gen2 **peab olema** [hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace) lubatud.

- Ressursirühmas, Azure Synapse kus tööruum asub, *teenise esindatavas* ja *publiku ülevaate kasutaja* peab olema määratud vähemalt **Lugeja** õigused. Lisateavet leiate teemast [Azure'i rollide määramine Azure'i portaali abil](/azure/role-based-access-control/role-assignments-portal).

- *Kasutaja* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol, kus andmed asuvad ja on lingitud tööruumiga Azure Synapse . Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse identiteeti haldav tööruum](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol kus asuvad andmed, mis on lingitud Azure Synapse tööruumiga. Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Azure Synapse tööruumis *vaatajaskonna ülevaate teenusejuht* vajab **sünapsiadministraatori** rolli määramist. Lisateavet leiate teemast [Sünapsi tööruumi juurdepääsujuhtelemendiüles seadmine](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Loo ühendusja eksport Azure Synapse -ile

### <a name="configure-a-connection"></a>Ühenduse konfigureerimine

Ühenduse loomiseks vajavad **teenuse põhi- ja kasutajakonto Customer Insightsis selle ressursirühma** readeri *õigusi*, kus asub Sünapsi analüüsi tööruum. Lisaks vajavad **Synapse Analyticsi tööruumi teenuse juht ja kasutaja Synapse'i administraatori** õigusi. 

1. Minge **Administraator** > **Ühendused**.

1. Ühenduse konfigureerimiseks valige **Lisa ühendus** ja valige **Azure Synapse Analytics** või valige **paanil** häälestamine **Azure Synapse Analytics**.

1. Andke oma ühendusele äratuntav nimi väljal Kuvatav nimi. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valige või otsige tellimust, milles soovite Customer Insights -i andmeid kasutada. Kohe, kui tellimus on valitud, saate valida ka **Tööruumi**, **Salvestusruumikonto** ja **Konteineri**.

1. Uue ühenduse salvestamiseks valige **Salvesta**.

### <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Ekspordi konfigureerimiseks ühisühendusega on vaja customer Insightsis vähemalt **kaasautori** õigusi. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa eksport**.

1. Valige väljal **Ekspordiühendus** jaotisest **Azure Synapse Analytics** ühendus. Kui te seda jaotisenime ei näe, pole seda tüüpi [ühendusi](connections.md) teie jaoks saadaval.

1. Sisestage ekspordile äratuntav **Kuvatav nimi** ja **Andmebaasi nimi**.

1. Valige, millisesse olemisse soovite eksportida Azure Synapse Analytics.
   > [!NOTE]
   > Andmeallikad, mis põhinevad [kaustal Common Data Model](connect-common-data-model.md) ei toetata.

2. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).

Synapse Analyticsisse eksporditud andmete päringute tegemiseks on vaja **salvestusruumi blob data reader** juurdepääsu ekspordi tööruumi sihtkoha salvestusruumile. 

### <a name="update-an-export"></a>Ekspordi värskendamine

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Redigeeri** ekspordil, mida soovite värskendada.

   - **Lisa** või **Eemalda** valikust olemeid. Kui olemid on valikust eemaldatud, ei kustutata neid Synapse Analyticsi andmebaasist. Kuid tulevased andmete värskendamised ei värskenda selles andmebaasis eemaldatud olemeid.

   - **Andmebaasi Nime Muutmine** loob uue Synapse Analytics -ii andmebaasi. Varem konfigureeritud nimega andmebaas ei saa tulevaste värskenduste ajal värskendusi.
