---
title: Tabelitega ühenduse loomine Microsoft Dataverse -is
description: Andmete importimine Microsoft Dataverse'i hallatavast andmejärvest.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: 436345d8932820eb4c517a9e9164b1377c1f62d3
ms.sourcegitcommit: 3807202283dd116a30f900a163d8141db621e5a8
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 01/28/2022
ms.locfileid: "8046420"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Andmetega ühendamine Microsoft Dataverse’i hallatavas andmejärves



See artikkel annab teavet selle kohta, kuidas Dataverse kasutajad saavad hallatava järve analüütiliste üksustega Microsoft Dataverse kiiresti ühendust võtta. 

> [!NOTE]
> Hallatavas järves Dataverse saadaolevate olemite loendi vaatamiseks peate olema organisatsiooni administraator.

## <a name="important-considerations"></a>Olulised kaalutlused

Võrguteenustes nagu Azure Data Lake Storage talletatavaid andmeid saab talletada muus asukohas kui see, kus andmeid rakenduses Dynamics 365 Customer Insights töödeldakse või talletatakse.Veebiteenustes talletatud andmete importimisel või nendega ühenduse loomisel nõustute, et andmeid saab edastada ja talletada.Dynamics 365 Customer Insights  [Lisateavet leiate Microsofti usalduskeskusest](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-dataverse-managed-lake"></a>Teenuse Dataverse hallatava järvega ühenduse loomine

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2. Valige **Lisa andmeallikas**.

3. Valige **Microsoft Dataverse** ja valige **Edasi**.

4. Sisestage andmeallika **Nimi** ja valige **Järgmine**. 

5. Sisestage **Serveri aadress** Dataverse organisatsiooni jaoks ja seejärel valige **Sisselogimine**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Kuva andmeafikstsiooni etapp, kus kasutaja saab sisestada Dataverse keskkonna URL-i.":::

6. Valige tabelid, mida soovite kasutada olemitena sihtrühma ülevaadetes saadaolevast loendist.    

   > [!NOTE]
   > Kui mõni tabel on juba valitud, võivad neid kasutada ka teised Dynamics 365 rakendused (nt Dynamics 365 sales Insights või Customer Service Insights). Valikut ei saa muuta. Need tabelid on olemina saadaval pärast andmeallika loomist.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialoogiboks, kus kuvatakse keskkonna Dataverse olemite loend.":::

7. Salvestage oma valik, et alustada valitud tabelite sünkroonimist Dataverse rakendusest. Äsja lisatud ühenduse leiate lehelt **Andmeallikad**. See lisatakse järjekorda olemite arvu värskendamiseks ja 0-na kuvamiseks, kuni kõik valitud tabelid on sünkroonitud.

Sama Dataverse'i hallatavat andmejärve saab ühel ajal kasutada ainult üks keskkonna andmeallikas.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse’i hallatava järve andmeallika muutmine

Olemi valikut redigeerite alles pärast andmeallika loomist. Näiteks, kui Dataverse'ile lisati täiendavaid olemeid ja soovite ka need importida.    
Erinevate Dataverse -i data lake -idega ühendamiseks [looge uus andmeallikas](#connect-to-a-dataverse-managed-lake).

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2. Valige uuendatava andmeallika kõrval suvand kolm punkti.

3. Valige loetelust valik **Redigeeri**.

4. Valige saadaolevate olemite loendist täiendavad olemid ja valige suvand **Salvesta**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
