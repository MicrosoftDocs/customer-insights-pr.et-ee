---
title: Andmetega ühendamine Microsoft Dataverse’i hallatavas andmejärves
description: Andmete importimine Microsoft Dataverse'i hallatavast andmejärvest.
ms.date: 05/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 9ae0b964d8d39835715b7ddadc712e2338b855af
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9082152"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Andmetega ühendamine Microsoft Dataverse’i hallatavas andmejärves

Microsoft Dataverse kasutajad saavad hallatava järve analüütiliste üksustega Microsoft Dataverse kiiresti ühenduse luua.

> [!NOTE]
> Hallatavas järves saadaolevate olemite loendi jätkamiseks ja vaatamiseks peate olema organisatsiooni administraator Dataverse.

## <a name="important-considerations"></a>Olulised kaalutlused

1. Võrguteenustes nagu Azure Data Lake Storage talletatavaid andmeid saab talletada muus asukohas kui see, kus andmeid rakenduses Dynamics 365 Customer Insights töödeldakse või talletatakse.Veebiteenustes talletatavate andmete importimisel või nendega ühenduse loomisel nõustute, et andmeid saab edastada ja salvestada rakendusega Dynamics 365 Customer Insights. [Lisateavet leiate Microsofti usalduskeskusest](https://www.microsoft.com/trust-center).
2. Nähtavad on ainult Dataverse olemid, mille [muudatuste jälgimine](/power-platform/admin/enable-change-tracking-control-data-synchronization) on lubatud. Neid olemeid saab eksportida hallatavasse Dataverse andmejärve ja kasutada Customer Insightsis. Kastivälistel Dataverse tabelitel on vaikimisi lubatud muudatuste jälgimine. Kohandatud tabelite muudatuste jälgimine peate sisse lülitama. Kui soovite kontrollida, kas tabel on Dataverse muudatuste jälgimiseks lubatud, avage [Power Apps](https://make.powerapps.com) > **andmetabelid** > **·**. Leidke oma huvipakkuv tabel ja valige see. **Avage suvandId** > **Sätted** Täpsemad ja vaadake üle **säte Muudatuste jälgimine**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Teenuse Dataverse hallatava järvega ühenduse loomine

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige **Microsoft Dataverse**.

1. **Sisestage andmeallikas nimi** ja valikuline **kirjeldus**.

1. Sisestage **Serveri aadress** Dataverse organisatsiooni jaoks ja seejärel valige **Sisselogimine**.

1. Valige saadaolevast loendist tabelid, mida soovite Customer Insightsi olemitena alla neelata.

   > [!NOTE]
   > Kui mõni tabel on juba valitud, võivad neid kasutada ka teised Dynamics 365 rakendused (nt Dynamics 365 sales Insights või Customer Service Insights). Valikut ei saa muuta. Need tabelid on olemina saadaval pärast andmeallika loomist.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialoogiboks, kus kuvatakse keskkonna Dataverse olemite loend.":::

1. Salvestage oma valik, et alustada valitud tabelite sünkroonimist Dataverse rakendusest. Äsja lisatud ühenduse leiate lehelt **Andmeallikad**. See lisatakse järjekorda olemite arvu värskendamiseks ja 0-na kuvamiseks, kuni kõik valitud tabelid on sünkroonitud.

Sama Dataverse'i hallatavat andmejärve saab ühel ajal kasutada ainult üks keskkonna andmeallikas.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse’i hallatava järve andmeallika muutmine

Olemi valikut redigeerite alles pärast andmeallika loomist. Näiteks, kui Dataverse'ile lisati täiendavaid olemeid ja soovite ka need importida.
Erinevate Dataverse -i data lake -idega ühendamiseks [looge uus andmeallikas](#connect-to-a-dataverse-managed-lake).

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige värskendatava andmeallikas kõrval Käsk **Redigeeri**.

1. Valige saadaolevate olemite loendist täiendavad olemid ja valige suvand **Salvesta**.
