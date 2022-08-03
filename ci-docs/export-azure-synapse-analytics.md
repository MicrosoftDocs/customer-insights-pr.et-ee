---
title: Andmete eksportimine Azure Synapse Analytics (eelvaade)
description: Vaadake, kuidas konfigureerida ühendust Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196389"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Andmete eksportimine Azure Synapse Analytics (eelvaade)

Azure Synapse on analüüsiteenus, mis kiirendab andmeladude ja suurandmesüsteemide läbivaatava ülevaatamise aega. Customer Insights -i andmeid saate sisse tuua ja kasutada jaotises [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>eeltingimused

> [!NOTE]
> Seadke kindlasti kõik **rollimäärangud** vastavalt kirjeldatusele.

- Customer Insightsis peab teie Azure Active Directory (AD) kasutajakontol olema administraatori [roll](permissions.md#assign-roles-and-permissions).

Azure -is:

- Töötav Azure -i tellimus.

- Kui kasutate uut Azure Data Lake Storage Gen2 kontot, [on](connect-service-principal.md) Customer Insightsi **teenindusjuhil salvestusruumi bloobi andmete esitaja** õigused. Data Lake Storage Gen2 **peab olema** [hierarhiline nimeruum](/azure/storage/blobs/data-lake-storage-namespace) lubatud.

- Ressursigrupis, kus Azure Synapse tööruum asub, peavad teenuse printsipaalile *ja* kasutajale, kellel on Customer Insightsis *Azure AD administraatoriõigused,* olema määratud vähemalt **rakenduse Reader**[õigused](/azure/role-based-access-control/role-assignments-portal).

- Kasutajal *Azure AD, kellel on Customer Insightsi* administraatoriõigused, on **salvestusruumi bloobi andmete esitaja** õigused Gen2 kontol, kus andmed asuvad Azure Data Lake Storage ja tööruumiga lingitud Azure Synapse. Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Tööruumi *[Azure Synapse hallataval identiteedil](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* **on** salvestusruumi bloobi andmete esitaja Azure Data Lake Storage õigused Gen2 kontol, kus andmed asuvad ja tööruumiga lingitud Azure Synapse. Lugege lisateavet [Azure'i portaali kasutamise kohta Azure'i rolli määramiseks juurdepääsuks bloobi- ja järjekorraandmetele](/azure/storage/common/storage-auth-aad-rbac-portal) ning [Salvestusruumi Bloobiandmete Kaasautori õigustele](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- Tööruumis Azure Synapse on *Customer Insightsi* **hooldusjuhile määratud** synapse-administraatori [roll](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Ühenduse häälestamine Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Minge **Administraator** > **Ühendused**.

1. Valige **Lisa ühendus** ja valige **Azure Synapse Analytics**.

1. Andke oma ühendusele äratuntav nimi väljal **Kuvatav nimi**. Ühenduse nimi ja tüüp kirjeldavad ühendust. Soovitame valida nime, mis selgitab ühenduse eesmärki ja sihti.

1. Valige, kes saavad seda ühendust kasutada. Vaikimisi on see ainult Administraatorid. Lisateavet leiate teemast [Luba kaastöötajatel kasutada ühendust ekspordi jaoks](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Valige või otsige tellimust, milles soovite Customer Insights -i andmeid kasutada. Kohe, kui tellimus on valitud, saate valida ka **Tööruumi**, **Salvestusruumikonto** ja **Konteineri**.

1. [Vaadake üle andmete privaatsus ja vastavus](connections.md#data-privacy-and-compliance) ning valige **Nõustun**.

1. Ühenduse loomiseks valige **Salvesta**.

## <a name="configure-an-export"></a>Ekspordi konfigureerimine

[!INCLUDE [export-permission-include](includes/export-permission.md)] Jagatud ühendusega ekspordi konfigureerimiseks vajate Customer Insightsis vähemalt **kaasautori** õigusi.

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Lisa eksport**.

1. Valige väljal **Ekspordiühendus** jaotisest Azure Synapse Analytics ühendus. Kui ühendusi pole saadaval, pöörduge administraatori poole.

1. Sisestage ekspordile äratuntav **Kuvatav nimi** ja **Andmebaasi nimi**. Eksport loob ühenduses määratletud tööruumis uue [Azure Synapse järveandmebaasi](/azure/synapse-analytics/database-designer/concepts-lake-database).

1. Valige olemid, kuhu soovite eksportida Azure Synapse Analytics.
   > [!NOTE]
   > Andmeallikad, mis põhinevad [kaustal Common Data Model](connect-common-data-model.md) ei toetata.

1. Valige **Salvesta**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Synapse Analyticsisse eksporditud andmete päringu tegemiseks on teil vaja **salvestusruumi bloobi andmelugejat** juurdepääsu ekspordi tööruumis olevale sihtmälule.

## <a name="update-an-export"></a>Ekspordi värskendamine

1. Minge **Andmed** > **Ekspordid**.

1. Valige **Redigeeri** ekspordil, mida soovite värskendada.

   - **Lisa** või **Eemalda** valikust olemeid. Kui olemid on valikust eemaldatud, ei kustutata neid Synapse Analyticsi andmebaasist. Kuid tulevased andmete värskendamised ei värskenda selles andmebaasis eemaldatud olemeid.

   - **Andmebaasi Nime Muutmine** loob uue Synapse Analytics -ii andmebaasi. Varem konfigureeritud nimega andmebaas ei saa tulevaste värskenduste ajal värskendusi.

[!INCLUDE [footer-include](includes/footer-banner.md)]
