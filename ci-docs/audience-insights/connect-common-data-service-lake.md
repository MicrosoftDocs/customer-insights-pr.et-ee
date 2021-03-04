---
title: Ühenduse loomine Common Data Service'i hallatava andmejärve olemitega
description: Andmete importimine Common Data Service'i hallatavast andmejärvest.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: et-EE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267808"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Andmetega ühendamine Common Data Service’i hallatavas andmejärves

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

See artikkel annab teavet selle kohta, kuidas olemasolevad Dynamics 365 kliendid saavad kiiresti ühendada oma analüütiliste üksustega Common Data Service'i hallatavas järves. Peate olema Common Data Service'i organisatsiooni administraator, et jätkata ja näha hallatavas järves saadaolevate olemite loendit.

## <a name="important-considerations"></a>Olulised kaalutlused

Võrguteenustes nagu Azure Data Lake Storage talletatavaid andmeid saab talletada muus asukohas kui see, kus andmeid rakenduses Dynamics 365 Customer Insights töödeldakse või talletatakse. Kui impordite võrguteenustes talletatavaid andmeid või ühendate konto teenusega, siis nõustute, et andmeid võidakse transportida ja salvestada rakenduses Dynamics 365 Customer Insights. [Lisateavet leiate Microsofti usalduskeskusest.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Teenuse Common Data Service hallatava järvega ühenduse loomine

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2. Valige **Lisa andmeallikas**.

3. Valige **Teenusega Common Data Service ühenduse loomine** ja valige suvand **Edasi**.

4. Sisestage andmeallika **Nimi** ja valige **Järgmine**. Nime juhised: 
   - peab algama tähega;
   - kasutage ainult tähti ja numbreid; erimärkide ja tühikute sisestamine pole lubatud;
   - kasutage 3–64 tähemärki.

5. Sisestage oma Common Data Service’i organisatsiooni **serveri aadress** ja valige suvand **Logi sisse**.

   > [!div class="mx-imgBorder"]
   > ![Dialoogiaken Common Data Service’i serveri aadressi sisestamiseks](media/enter-CDS-org-details.png)

6. Valige saadaolevate olemite loendist need olemid, mida soovite valmendada.    

   > [!NOTE]
   > Kui mõni olem on juba valitud, võidakse neid kasutada teistes Dynamics 365 rakendustes (nt Dynamics 365 Sales Insights või Customer Service Insights). Valikut ei saa muuta. Need olemid on saadaval pärast andmeallikas loomist.

   > [!div class="mx-imgBorder"]
   > ![Common Data Service’i organisatsiooni olemite loendit näitav dialoogiaken](media/select-analytical-entities.png)

7. Salvestage oma valik, et alustada valitud olemite sünkroonimist Common Data Service’i hallatava järvega. Äsja lisatud ühenduse leiate lehelt **Andmeallikad**. See pannakse värskendamiseks järjekorda ja kuvab olemite arvuna 0, kuni kõik olemid on sünkroonitud.

Sama Common Data Service'i hallatavat andmejärve saab ühel ajal kasutada ainult üks keskkonna andmeallikas.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Common Data Service’i hallatava järve andmeallika muutmine

Olemi valikut redigeerite alles pärast andmeallika loomist. Näiteks, kui Common Data Service'ile lisati täiendavaid olemeid ja soovite ka need importida.    
Muu Common Data Service’iga ühenduse loomiseks [looge uus andmeallikas](#connect-to-a-common-data-service-managed-lake).

1. Avage sihtrühmaülevaadetes jaotis **Andmed** > **Andmeallikad**.

2. Valige uuendatava andmeallika kõrval suvand kolm punkti.

3. Valige loetelust valik **Redigeeri**.

4. Valige saadaolevate olemite loendist täiendavad olemid ja valige suvand **Salvesta**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]