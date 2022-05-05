---
title: Tabelitega ühenduse loomine Microsoft Dataverse -is
description: Andmete importimine Microsoft Dataverse'i hallatavast andmejärvest.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: e8a294a4bad1581539b5905160cddcd625699d90
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 04/27/2022
ms.locfileid: "8642524"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Andmetega ühendamine Microsoft Dataverse’i hallatavas andmejärves

Selles artiklis antakse teavet selle kohta, kuidas Dataverse kasutajad saavad hallatava järve analüütiliste üksustega Microsoft Dataverse kiiresti ühenduse luua. 

> [!NOTE]
> Hallatavas järves saadaolevate olemite loendi jätkamiseks ja vaatamiseks peate olema organisatsiooni administraator Dataverse.

## <a name="important-considerations"></a>Olulised kaalutlused

1. Võrguteenustes nagu Azure Data Lake Storage talletatavaid andmeid saab talletada muus asukohas kui see, kus andmeid rakenduses Dynamics 365 Customer Insights töödeldakse või talletatakse.Veebiteenustes talletatavate andmete importimisel või nendega ühenduse loomisel nõustute, et andmeid saab edastada ja salvestada rakendusega Dynamics 365 Customer Insights. [Lisateavet leiate Microsofti usalduskeskusest](https://www.microsoft.com/trust-center).
2. Nähtavad on ainult Dataverse olemid, mille [muudatuste jälgimine](/power-platform/admin/enable-change-tracking-control-data-synchronization) on lubatud. Neid olemeid saab eksportida hallatavasse Dataverse andmejärve ja kasutada Customer Insightsis. Kastivälistel Dataverse tabelitel on vaikimisi lubatud muudatuste jälgimine. Kohandatud tabelite muudatuste jälgimine peate sisse lülitama. Kui soovite kontrollida, kas tabel on Dataverse muudatuste jälgimiseks lubatud, avage [Power Apps](https://make.powerapps.com) > **andmetabelid** > **·**. Leidke oma huvipakkuv tabel ja valige see. **Avage sättedLisatavad** > **suvandid** ja vaadake üle **säte Muudatuste** jälitamine.

## <a name="connect-to-a-dataverse-managed-lake"></a>Teenuse Dataverse hallatava järvega ühenduse loomine

1. Avage teenuses Customer Insights **Andmed** > **Andmeallikad**.

2. Valige **Lisa andmeallikas**.

3. Valige **Microsoft Dataverse** ja valige **Edasi**.

4. Sisestage andmeallika **Nimi** ja valige **Järgmine**. 

5. Sisestage **Serveri aadress** Dataverse organisatsiooni jaoks ja seejärel valige **Sisselogimine**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Kuva andmeafikstsiooni etapp, kus kasutaja saab sisestada Dataverse keskkonna URL-i.":::

6. Valige saadaolevast loendist tabelid, mida soovite olemitena Customer Insightsi alla neelata.    

   > [!NOTE]
   > Kui mõni tabel on juba valitud, võivad neid kasutada ka teised Dynamics 365 rakendused (nt Dynamics 365 sales Insights või Customer Service Insights). Valikut ei saa muuta. Need tabelid on olemina saadaval pärast andmeallika loomist.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialoogiboks, kus kuvatakse keskkonna Dataverse olemite loend.":::

7. Salvestage oma valik, et alustada valitud tabelite sünkroonimist Dataverse rakendusest. Äsja lisatud ühenduse leiate lehelt **Andmeallikad**. See lisatakse järjekorda olemite arvu värskendamiseks ja 0-na kuvamiseks, kuni kõik valitud tabelid on sünkroonitud.

Sama Dataverse'i hallatavat andmejärve saab ühel ajal kasutada ainult üks keskkonna andmeallikas.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse’i hallatava järve andmeallika muutmine

Olemi valikut redigeerite alles pärast andmeallika loomist. Näiteks, kui Dataverse'ile lisati täiendavaid olemeid ja soovite ka need importida.    
Erinevate Dataverse -i data lake -idega ühendamiseks [looge uus andmeallikas](#connect-to-a-dataverse-managed-lake).

1. Avage suvandid **Andmed** > **Andmeallikad**.

2. Valige uuendatava andmeallika kõrval suvand kolm punkti.

3. Valige loetelust valik **Redigeeri**.

4. Valige saadaolevate olemite loendist täiendavad olemid ja valige suvand **Salvesta**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
