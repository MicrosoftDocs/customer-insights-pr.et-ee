---
title: Andmetega ühendamine Microsoft Dataverse’i hallatavas andmejärves
description: Andmete importimine Microsoft Dataverse'i hallatavast andmejärvest.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: MT
ms.contentlocale: et-EE
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206948"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Andmetega ühendamine Microsoft Dataverse’i hallatavas andmejärves

Microsoft Dataverse kasutajad saavad hallatavas järves kiiresti luua ühenduse analüütiliste Microsoft Dataverse olemitega. Sama Dataverse'i hallatavat andmejärve saab ühel ajal kasutada ainult üks keskkonna andmeallikas.

> [!NOTE]
> Peate olema organisatsiooni administraator, Dataverse et jätkata ja vaadata hallatavas järves saadaolevate olemite loendit.

## <a name="prerequisites"></a>eeltingimused

- Võrguteenustes nagu Azure Data Lake Storage talletatavaid andmeid saab talletada muus asukohas kui see, kus andmeid rakenduses Dynamics 365 Customer Insights töödeldakse või talletatakse.Võrguteenustes salvestatud andmete importimisel või nendega ühenduse loomisel nõustute, et andmeid saab edastada ja salvestada.Dynamics 365 Customer Insights  [Lisateavet leiate Microsofti usalduskeskusest](https://www.microsoft.com/trust-center).

- Nähtavad on ainult Dataverse olemid, mille [muudatuste jälgimine](/power-platform/admin/enable-change-tracking-control-data-synchronization) on lubatud. Neid olemeid saab eksportida hallatavasse Dataverse andmejärve ja kasutada Customer Insightsis. Valmis Dataverse tabelites on muudatuste jälitus vaikimisi lubatud. Muudatuste jälitus peate kohandatud tabelite jaoks sisse lülitama. Kontrollimaks, Dataverse kas tabelis on muudatuste jälitus lubatud, avage [Power Apps](https://make.powerapps.com) > **Andmetabelid** > **·**. Leidke teile huvipakkuv tabel ja valige see. Avage **Jaotis Sätted** > **Täpsemad suvandid** ja vaadake üle **säte Jälita muudatusi**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Teenuse Dataverse hallatava järvega ühenduse loomine

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige **Lisa andmeallikas**.

1. Valige **Microsoft Dataverse**.

1. **Sisestage andmeallikas nimi** ja valikuline **kirjeldus**.

1. Sisestage **Serveri aadress** Dataverse organisatsiooni jaoks ja seejärel valige **Sisselogimine**.

1. Valige saadaolevast loendist tabelid, mille soovite Customer Insightsi olemitena alla neelata.

   > [!NOTE]
   > Kui mõni tabel on juba valitud, võivad neid kasutada ka teised Dynamics 365 rakendused (nt Dynamics 365 sales Insights või Customer Service Insights). Valikut ei saa muuta. Need tabelid on olemina saadaval pärast andmeallika loomist.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Dialoogiboks, kus kuvatakse keskkonna Dataverse olemite loend.":::

1. Salvestage oma valik, et alustada valitud tabelite sünkroonimist Dataverse rakendusest. Äsja lisatud ühenduse leiate lehelt **Andmeallikad**. See lisatakse järjekorda olemite arvu värskendamiseks ja 0-na kuvamiseks, kuni kõik valitud tabelid on sünkroonitud.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

Andmete laadimine võib võtta aega. Pärast edukat värskendamist saab allaneelatud andmeid vaadata lehelt [**Olemid**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Dataverse’i hallatava järve andmeallika muutmine

Olemi valikut redigeerite alles pärast andmeallika loomist. Näiteks, kui Dataverse'ile lisati täiendavaid olemeid ja soovite ka need importida.
Erinevate Dataverse -i data lake -idega ühendamiseks [looge uus andmeallikas](#connect-to-a-dataverse-managed-lake).

1. Avage suvandid **Andmed** > **Andmeallikad**.

1. Valige värskendatava andmeallikas kõrval käsk **Redigeeri**.

1. Valige saadaolevast olemite loendist täiendavad olemid.

1. Muudatuste rakendamiseks ja lehele Andmeallikad **naasmiseks** klõpsake nuppu **Salvesta**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
