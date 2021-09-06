---
title: Tabelitega ühenduse loomine Microsoft Dataverse -is
description: Andmete importimine Microsoft Dataverse'i hallatavast andmejärvest.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033075"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Andmetega ühendamine Microsoft Dataverse’i hallatavas andmejärves

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Selles artiklis antakse teavet selle kohta kuidas Dataverse -i kasutajad saavad Dataverse hallatavas järves kiiresti analüüsiüksustega ühendust luua. Peate olema Dataverse'i organisatsiooni administraator, et jätkata ja näha hallatavas järves saadaolevate olemite loendit.

## <a name="important-considerations"></a>Olulised kaalutlused

Võrguteenustes nagu Azure Data Lake Storage talletatavaid andmeid saab talletada muus asukohas kui see, kus andmeid rakenduses Dynamics 365 Customer Insights töödeldakse või talletatakse. Kui impordite võrguteenustes talletatavaid andmeid või ühendate konto teenusega, siis nõustute, et andmeid võidakse transportida ja salvestada rakenduses Dynamics 365 Customer Insights. [Lisateavet leiate Microsofti usalduskeskusest.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Teenuse Dataverse hallatava järvega ühenduse loomine

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2. Valige **Lisa andmeallikas**.

3. Valige **Connect Microsoft Dataverse -i hallatavate järvedega** ja seejärel **Edasi**.

4. Sisestage andmeallika **Nimi** ja valige **Järgmine**. Nime juhised: 
   - peab algama tähega;
   - kasutage ainult tähti ja numbreid; erimärkide ja tühikute sisestamine pole lubatud;
   - kasutage 3–64 tähemärki.

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