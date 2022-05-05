---
title: Customer Insights andmete eksportimine rakendusse Azure Synapse Analytics
description: Siit saate teada, kuidas konfigureerida ühendus rakendusega Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e77227e1e353c02cfb13e26a8ecbe0768ba6c0fa
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642554"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Andmete eksportimine rakendusse Azure Synapse Analytics (Eelvaade)

Azure Synapse on analüüsiteenus, mis kiirendab andmeladude ja suurandmesüsteemide läbivaatava ülevaatamise aega. Customer Insights -i andmeid saate sisse tuua ja kasutada jaotises [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Eeltingimused

Ühenduse konfigureerimiseks Customer Insights rakendusest Azure Synapse -i peavad olema täidetud järgmised eeltingimused.

> [!NOTE]
> Seadke kindlasti kõik **rollimäärangud** vastavalt kirjeldatusele.  

## <a name="prerequisites-in-customer-insights"></a>Eeltingimused Customer Insights -is

* Teie Azure Active Directory (AD) kasutajakontol **on Customer Insightsis administraatori** roll. Lugege lisateavet kasutajaõiguste seadmise [kohta](permissions.md#assign-roles-and-permissions).

Azure -is: 

- Töötav Azure -i tellimus.

- Kui kasutate uut Azure Data Lake Storage Gen2 kontot, *vajab* Customer Insightsi **teenusedirektor storage blob data contributori** õigusi. Lisateavet vaata [Azure Data Lake Storage -i Gen2 konto ühendamine Azure service -i esindatavaga publiku ülevaadetes](connect-service-principal.md). Data Lake Storage Gen2 **peab olema** [hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace) lubatud.

- Ressursirühmas, kus Azure Synapse tööruum asub, *tuleb hooldusdirektorile* *Azure AD ja customer Insightsi* administraatoriõigustega kasutajale määrata vähemalt **Readeri** õigused. Lisateavet leiate teemast [Azure'i rollide määramine Azure'i portaali abil](/azure/role-based-access-control/role-assignments-portal).

- Customer *Azure AD Insightsi* administraatoriõigustega kasutaja vajab **salvestusruumi bloobi andmete kaasautori** õigusi Gen2 kontol Azure Data Lake Storage, kus andmed asuvad ja on tööruumiga lingitud Azure Synapse. Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- *[Azure Synapse identiteeti haldav tööruum](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* vajab **Mälubloobiandmete Kaasautori** õigusi Azure Data Lake Storage Gen2 kontol kus asuvad andmed, mis on lingitud Azure Synapse tööruumiga. Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Tööruumis Azure Synapse vajab *Customer Insightsi* teenusedirektor Määratud Synapse'i administraatori **rolli.** Lisateavet leiate teemast [Sünapsi tööruumi juurdepääsujuhtelemendiüles seadmine](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Loo ühendusja eksport Azure Synapse -ile

### <a name="configure-a-connection"></a>Ühenduse konfigureerimine

Ühenduse loomiseks vajavad **customer Insightsi teenusedirektor ja kasutajakonto Readeri** õigusi *ressursirühmas*, kus asub Synapse Analyticsi tööruum. Lisaks vajavad **Synapse Analyticsi tööruumi teenusehaldur ja kasutaja Synapse'i administraatori** õigusi. 

1. Minge **Administraator** > **Ühendused**.

1. Ühenduse konfigureerimiseks valige **Lisa ühendus** ja valige **Azure Synapse Analytics** või valige **paanil** häälestamine **Azure Synapse Analytics**.

1. Andke oma ühendusele äratuntav nimi väljal Kuvatav nimi. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Kui te midagi ei tee, on vaikeväärtuseks Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valige või otsige tellimust, milles soovite Customer Insights -i andmeid kasutada. Kohe, kui tellimus on valitud, saate valida ka **Tööruumi**, **Salvestusruumikonto** ja **Konteineri**.

1. Uue ühenduse salvestamiseks valige **Salvesta**.

### <a name="configure-an-export"></a>Ekspordi konfigureerimine

Kui teil on juurdepääs sellist tüüpi ühendusele, saate selle ekspordi konfigureerida. Ühisühendusega eksportimise konfigureerimiseks on customer Insightsis vaja vähemalt **kaasautoriõigusi**. Lisateavet leiate teemast [Eksportimise konfigureerimiseks vajalikud õigused](export-destinations.md#set-up-a-new-export).

1. Minge **Andmed** > **Ekspordid**.

1. Valige uue ekspordi loomiseks **Lisa eksport**.

1. Valige väljal **Ekspordiühendus** jaotisest ühendus **Azure Synapse Analytics**. Kui te seda jaotisenime ei näe, pole seda tüüpi [ühendusi](connections.md) teie jaoks saadaval.

1. Sisestage ekspordile äratuntav **Kuvatav nimi** ja **Andmebaasi nimi**.

1. Valige, millistesse olemitesse soovite eksportida Azure Synapse Analytics.
   > [!NOTE]
   > Andmeallikad, mis põhinevad [kaustal Common Data Model](connect-common-data-model.md) ei toetata.

2. Valige **Salvesta**.

Ekspordi salvestamine ei käivita eksporti kohe.

Eksportimine käitatakse iga [kavandatud värskendusega](system.md#schedule-tab). Samuti saate [eksportida andmeid nõudmisel](export-destinations.md#run-exports-on-demand).

Synapse Analyticsisse eksporditud andmete päringute tegemiseks on vaja **salvestusruumi bloobi andmelugeja** juurdepääsu ekspordi tööruumi sihtkoha salvestusruumile. 

### <a name="update-an-export"></a>Ekspordi värskendamine

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Redigeeri** ekspordil, mida soovite värskendada.

   - **Lisa** või **Eemalda** valikust olemeid. Kui olemid on valikust eemaldatud, ei kustutata neid Synapse Analyticsi andmebaasist. Kuid tulevased andmete värskendamised ei värskenda selles andmebaasis eemaldatud olemeid.

   - **Andmebaasi Nime Muutmine** loob uue Synapse Analytics -ii andmebaasi. Varem konfigureeritud nimega andmebaas ei saa tulevaste värskenduste ajal värskendusi.
